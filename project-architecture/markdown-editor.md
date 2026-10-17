# DevspireHub Markdown Studio — Engineering Blueprint

Architecture specification · Production SDLC · Release engineering · Security and quality gates

## Executive recommendation

Build DevspireHub Markdown Studio as a local-first, state-driven desktop application with a narrowly privileged Rust backend and a modular vanilla JavaScript frontend. Treat document integrity, recoverability, secure Markdown rendering, and verified publishing as architectural requirements rather than features to add later.

The implementation should follow six engineering priorities:

1. Establish a verified repository baseline before changing code.
2. Deliver a reliable local editing and saving lifecycle.
3. Introduce recovery, external-change detection, and conflict handling.
4. Build documentation validation and export on a shared Markdown processing pipeline.
5. Add GitHub integration in two stages: remote reading and draft editing first, publishing second.
6. Release only after automated tests, security checks, recovery validation, and packaged-application tests pass.

The release numbers below are the proposed roadmap. They do not imply that any release has already been implemented.

## 1. Technical architecture specification

### 1.1 Four-layer system blueprint

## Layer 1 — Presentation

Vite · HTML · CSS · Vanilla JavaScript · CodeMirror 6

Application shell · Workspace · Tabs · Editor · Preview · Outline · Search · Dialogs · Diff viewer · Status bar

## Layer 2 — Application Core

Framework-independent application logic

Document State Manager · Command Dispatcher · Save Coordinator · Recovery Coordinator · Workspace Manager · Quality Checker · Export Orchestrator · GitHub Sync Coordinator

## Layer 3 — Services

Typed interfaces, validation and integration logic

FileSystemService · MarkdownService · RecoveryService · HistoryService · SettingsService · GitHubService · CredentialService · ExportService · LoggingService

## Layer 4 — Native / External

Tauri 2 · Rust · OS facilities · External APIs

Filesystem operations · Atomic writes · Recovery storage · OS credential store · GitHub REST API · Export filesystem · Optional AI provider

Architecture rule: dependencies flow through explicit interfaces. The frontend must not bypass the application core to perform privileged filesystem, credential, or publishing operations.

### 1.2 Responsibility and ownership boundaries

| Layer             | Owns                                                                           | Must not own                                                              |
| ----------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Presentation      | UI state, interaction, editor selection, dialogs, rendering controls           | Filesystem authorization, credential handling, authoritative save results |
| Application Core  | Document lifecycle, orchestration, conflict decisions, command sequencing      | Direct unrestricted OS access or UI-specific rendering                    |
| Services          | Markdown processing, file operations, recovery policy, GitHub protocol, export | Arbitrary cross-module mutation or hidden publishing                      |
| Native / External | Restricted OS operations, durable storage, credentials, remote API calls       | Product-level workflow decisions or unrequested publishing                |

Important distinction: A document's text in CodeMirror is not automatically the authoritative saved copy. The application core owns the logical document state, while the service/native boundary reports which operations actually succeeded.

### 1.3 Suggested module boundaries

```
src/
├── app/
│   ├── bootstrap.js
│   ├── command-dispatcher.js
│   └── event-bus.js
├── features/
│   ├── editor/
│   ├── workspace/
│   ├── preview/
│   ├── outline/
│   ├── search/
│   ├── recovery/
│   ├── quality-checker/
│   ├── toc/
│   ├── export/
│   └── github/
├── core/
│   ├── document-state-manager.js
│   ├── save-coordinator.js
│   ├── recovery-coordinator.js
│   └── sync-coordinator.js
├── services/
│   ├── filesystem-service.js
│   ├── markdown-service.js
│   ├── recovery-service.js
│   ├── export-service.js
│   ├── github-service.js
│   └── credential-service.js
├── contracts/
│   ├── document-contracts.js
│   └── native-api-contracts.js
└── main.js

src-tauri/
├── src/
│   ├── commands/
│   ├── filesystem/
│   ├── recovery/
│   ├── credentials/
│   └── lib.rs
└── capabilities/
```

This is a logical target, not a requirement to restructure an existing repository into these exact folders. Preserve established conventions where they are sound.

### 1.4 Strict frontend–Rust API contracts

The frontend and native backend must communicate through a small, documented set of Tauri commands. Each command is a capability boundary, not merely a convenient function call.

#### Contract A — Native command envelope

Use consistent success and failure semantics. The following TypeScript-like interfaces are illustrative contracts; they do not imply TypeScript must be introduced into the vanilla JavaScript frontend.

```
type AppError = {
  code:
    | "INVALID_INPUT"
    | "PATH_NOT_ALLOWED"
    | "NOT_FOUND"
    | "PERMISSION_DENIED"
    | "EXTERNAL_MODIFICATION"
    | "WRITE_FAILED"
    | "RECOVERY_FAILED"
    | "AUTH_REQUIRED"
    | "RATE_LIMITED"
    | "REMOTE_CONFLICT"
    | "NETWORK_ERROR"
    | "UNKNOWN";
  message: string;
  retryable: boolean;
  operationId?: string;
};

type DocumentRevision = {
  documentId: string;
  revision: number;
  contentHash?: string;
  updatedAt?: string;
};

type SaveRequest = {
  documentId: string;
  expectedRevision: number;
  content: string;
  expectedDiskVersion?: string;
};

type SaveResult = {
  revision: number;
  contentHash: string;
  persistedAt: string;
};

type RecoverySnapshot = {
  snapshotId: string;
  documentId: string;
  revision: number;
  createdAt: string;
  reason: "AUTOSAVE" | "PRE_SHUTDOWN" | "RECOVERY";
};
```

In practice, JavaScript can use runtime validation and JSDoc to enforce these contracts without a TypeScript migration. Rust command inputs and outputs should be serializable, explicitly validated, and versioned where persistence compatibility requires it.

#### Contract B — Recommended native operations

| Operation                   | Purpose                                                  | Required protection                          |
| --------------------------- | -------------------------------------------------------- | -------------------------------------------- |
| `open_document`             | Open a user-selected document                            | Validate path and permissions                |
| `save_document`             | Persist a specific document revision                     | Revision check, safe write, accurate result  |
| `read_file_metadata`        | Inspect modification time, size, and version information | Handle inaccessible or deleted files         |
| `list_directory`            | Populate the workspace explorer                          | Scope to authorized directories              |
| `create_directory`          | Create a workspace directory                             | Validate destination                         |
| `rename_path`               | Rename a file or folder                                  | Collision and path validation                |
| `move_path`                 | Move an item                                             | Validate source and destination              |
| `delete_path`               | Delete a user-selected item                              | Explicit confirmation and scope validation   |
| `create_recovery_snapshot`  | Persist recoverable content                              | Integrity and retention policy               |
| `list_recovery_snapshots`   | Discover recoverable drafts                              | Validate metadata and snapshot files         |
| `restore_recovery_snapshot` | Restore selected content                                 | Preserve newer content and validate revision |
| `read_secure_credential`    | Retrieve an authorized credential                        | Secure-store access only                     |
| `write_secure_credential`   | Store a credential                                       | No plaintext fallback                        |
| `delete_secure_credential`  | Revoke local credential storage                          | Clear result and error handling              |

Do not expose every possible operation as a native command automatically. Add only commands required by a real feature.

GitHub API requests may remain in the frontend for ordinary API operations if authorization, token exposure, CORS constraints, and the selected authentication design are handled safely. Sensitive credentials must never be exposed to untrusted document-rendering content. A backend-mediated approach may be preferable for particular operations, but the architecture should not introduce an unrestricted native network proxy.

#### Contract C — Validation and error behavior

Every native operation must define:

1. Valid input schema.
2. Required permission or capability.
3. Preconditions.
4. Success result.
5. Typed failure cases.
6. Whether retry is safe.
7. Whether the operation can partially complete.
8. How the application verifies the result.

Never return success simply because a command was invoked. A successful save means the intended content was persisted and the required integrity checks passed—not just that the write was started.

#### Contract D — Security boundary

- Frontend code must not receive broad shell execution capabilities.
- Do not expose unrestricted filesystem access when a narrower API suffices.
- Never allow Markdown or a preview iframe to invoke native commands.
- Validate every path again in Rust; frontend validation is only a usability feature.
- Enforce Tauri capabilities and content security policy according to the actual application configuration.
- Keep credentials out of document state, event payloads, error messages, and application logs.
- Do not trust client-supplied revision numbers or paths without verifying them against authoritative state.

### 1.5 Document State Manager

The Document State Manager is the central authority for logical document lifecycle. It must distinguish content modification from persistence and remote synchronization.

#### State model

CLEAN

Current revision matches the last successful local save

DIRTY

Editor content has changed since the last successful save

SAVING

A specific immutable content revision is being persisted

### CLEAN

Save succeeded and no newer edits exist.

### DIRTY

Save succeeded, but newer edits exist.

### SAVE ERROR / RECOVERY

Failed persistence keeps the draft recoverable. Recovery restores a chosen revision; it does not overwrite a newer file silently.

### EXTERNAL CHANGE / CONFLICT

The file or remote base has advanced independently. Require comparison and a deliberate resolution.

### PUBLISHING → PUBLISHED

Remote publication is a separate lifecycle. PUBLISHED requires a verified remote commit; it does not mean the local file is necessarily clean.

The diagram illustrates the major states, not every legal transition. Implement a transition table and tests to prevent invalid transitions.

#### Recommended state-transition rules

| Event                            | Expected behavior                                                   |
| -------------------------------- | ------------------------------------------------------------------- |
| User edits clean document        | `CLEAN → DIRTY`                                                     |
| Save requested                   | `DIRTY → SAVING` for the captured revision                          |
| Save succeeds, no newer edits    | `SAVING → CLEAN`                                                    |
| Save succeeds, newer edits exist | `SAVING → DIRTY`                                                    |
| Save fails                       | `SAVING → SAVE_ERROR`, retaining content                            |
| Recovery snapshot succeeds       | Update recovery metadata; do not falsely mark disk save as complete |
| External file version changes    | Mark `EXTERNAL_CHANGE` and prevent blind overwrite                  |
| Remote base changes              | Mark remote conflict or stale-base status                           |
| Publish requested                | Enter `PUBLISHING` only after validation and confirmation           |
| Remote commit verified           | Record commit and enter `PUBLISHED` for that remote revision        |
| Publish times out ambiguously    | Record an uncertain outcome; inspect remote state before retry      |

Use orthogonal state fields where necessary. A document may simultaneously have unsaved local edits and a known published remote revision. Avoid forcing all conditions into one mutually exclusive enum.

#### Save algorithm

1. Capture the current document revision and content.
2. Check whether the destination has changed externally.
3. Validate that the destination is authorized.
4. Write to a temporary file or use an equivalent safe-write strategy.
5. Flush and atomically replace the destination where supported.
6. Verify the persisted result as required by the platform.
7. Update the last-saved revision only for the captured revision.
8. If newer edits exist, leave the document dirty.
9. On failure, retain the in-memory draft and record recoverable state.
10. Display a truthful status and available recovery actions.

Use a content hash or robust file-version token when helpful, but do not treat modification timestamps alone as an infallible concurrency mechanism.

### 1.6 Markdown processing pipeline

Markdown source revision

Immutable input snapshot

Parser and normalized document representation

GFM configuration · source ranges · heading structure

Preview renderer

HTML generation

Quality checker

Rules and source locations

TOC generator

Stable heading anchors

Export renderer

HTML or PDF preparation

Sanitization and resource validation

Unsafe HTML, links, and asset handling

Preview display or export artifact

Safe output and actionable validation results

Implementation rules:

- Every operation must work against a specific document revision.
- Share parser settings, extension configuration, and heading-slug rules.
- Sanitize rendered HTML before it enters a preview surface.
- Do not allow active content from Markdown to execute.
- Validate relative paths against the intended document/workspace scope.
- Keep lint findings tied to source locations.
- TOC updates must not rewrite unrelated source text.
- Export should report missing assets and rendering failures.
- Cache parsed representations only when invalidation is reliable and measured performance justifies it.

## 2. Complete production workflow and SDLC

### 2.1 Developer environment and daily loop

The development process must remain practical on Windows 10 with 8 GB RAM. Avoid running unnecessary VMs, multiple development servers, container stacks, and browser automation workers concurrently.

#### One-time environment setup

1. Verify prerequisites. Confirm supported Node.js and Rust toolchain versions, the appropriate Windows build tools, Tauri prerequisites, Git, and the project’s required WebView runtime. Follow the repository's supported version matrix rather than installing arbitrary latest versions.
2. Establish the baseline. Clone or open the repository, inspect the package manifest and lockfiles, install dependencies using the existing package manager, and run the current tests and build.
3. Configure the application. Review Tauri capabilities, content security policy, application identifiers, resource paths, and development versus production configuration.
4. Prepare test data. Create a disposable workspace with sample Markdown documents, images, malformed Markdown, duplicate headings, and files suitable for testing write failures and external modifications.
5. Keep credentials out of development artifacts. Use test accounts or mocks, a local environment configuration excluded from version control, and the OS secure credential store where applicable.

#### Daily developer loop

1. Synchronize and inspect

   Check the branch, working tree, recent changes, and relevant issues before editing.
2. Select one bounded task

   Identify its prerequisites, acceptance criteria, failure cases, and affected modules.
3. Implement the smallest coherent change

   Follow existing patterns, preserve public contracts, and avoid unrelated refactoring.
4. Run fast checks

   Run relevant unit tests, formatting, linting, and static checks.
5. Exercise failure paths

   Simulate permission errors, stale revisions, failed saves, malformed inputs, or network failures as relevant.
6. Run the application

   Verify the actual desktop behavior, not just a browser-only rendering or successful compilation.
7. Review the diff

   Check unintended changes, secret leakage, dependency additions, generated files, and data migration risks.
8. Commit with evidence

   Record what changed, the commands run, results, and any unresolved issues.

#### Resource management for the 8 GB RAM laptop

- Run one main build/test workload at a time.
- Use unit tests and focused integration tests before the full suite.
- Reserve E2E and packaged builds for planned validation points.
- Avoid unnecessary Docker services; the core desktop app should not require Docker.
- Avoid keeping multiple IDEs, VMs, and resource-heavy AI models active during builds.
- Track actual memory use, startup time, and editor responsiveness instead of relying on assumptions.
- Do not skip required release checks merely because the machine is constrained; use a suitable CI runner for expensive validation when necessary.

### 2.2 Branching and change-management policy

Use a lightweight workflow that supports small, reviewable changes.

| Change type       | Suggested workflow                                                |
| ----------------- | ----------------------------------------------------------------- |
| Feature           | Short-lived feature branch, focused commits, tests before merge   |
| Bug fix           | Reproduction case, fix, regression test, verification             |
| Security fix      | Restricted review, impact analysis, regression and security tests |
| Release           | Versioned release branch or tag, clean build, explicit approval   |
| Experimental work | Isolated branch, no production credentials, clear cleanup plan    |

Before committing:

- Review `git diff` and `git status`.
- Ensure generated build output and local secrets are excluded.
- Preserve unrelated user changes.
- Do not force-push or discard work without explicit authorization.
- Resolve merge conflicts intentionally and verify the resulting code.
- Keep lockfiles consistent with dependency changes.

### 2.3 CI/CD pipeline

The pipeline must verify the software from a clean checkout. A developer's local working directory is not sufficient evidence of a reproducible release.

## 1

1\. Source validation

Clean checkout, lockfile consistency, formatting and linting

## 2

2\. Unit tests

Document state, parsing, TOC, validation rules and utility logic

## 3

3\. Integration tests

Filesystem, recovery, export, secure-store adapters and GitHub API contracts

## 4

4\. Security checks

Dependency audit, secret scanning, path validation and rendering security tests

## 5

5\. Production build

Frontend build, Rust compilation and platform-specific configuration

## 6

6\. E2E tests

Real editor, save/reopen, recovery, conflict and publishing flows

## 7

7\. Packaged smoke tests

Install, launch, basic editing, file access and recovery compatibility

## 8

8\. Release approval

Review results, release notes, blockers and artifact provenance

## 9

9\. Artifact publication

Publish approved installers, checksums and signatures where feasible

#### Required pipeline behavior

- Fail the pipeline when mandatory checks fail.
- Preserve logs and test reports for diagnosis.
- Use deterministic dependency installation and lockfiles.
- Separate unit tests from slower packaged and E2E tests.
- Mock external services for deterministic integration tests, then use controlled contract or staging tests for provider-specific behavior.
- Do not store production credentials in ordinary CI variables without appropriate secret protection.
- Never publish artifacts automatically from an untrusted pull request.
- Build release artifacts from a clean, reviewed source revision.
- Verify the actual published artifact and its checksum or signature where provided.

A successful compilation alone is not a release-quality signal.

### 2.4 Quality gates and release blockers

The following gates are non-negotiable.

Security gate

No known unresolved critical security issue, exploitable path traversal, unsafe preview execution, credential leakage, or unauthorized native capability.

Data-integrity gate

No unresolved critical data-loss issue. Failed writes must preserve drafts. External modifications must not be overwritten silently. Recovery behavior must pass regression tests.

Publishing gate

No unapproved remote writes. Stale revisions must be detected. An ambiguous commit result must not be reported as either success or failure until reconciled with remote state.

Verification gate

Mandatory tests, production build, and packaged smoke tests must pass. Any permitted exception must be explicitly documented, risk-assessed, and approved; critical data-integrity and security failures cannot be waived casually.

#### Security test matrix

| Risk                        | Required test                                                     | Expected result                                         |
| --------------------------- | ----------------------------------------------------------------- | ------------------------------------------------------- |
| Path traversal              | Use `..`, absolute paths, separator variations, and symlink cases | Reject operations outside the authorized scope          |
| HTML injection              | Markdown containing script tags, event handlers, and unsafe URLs  | No script execution or unsafe navigation                |
| Credential leakage          | Force authentication and API errors; inspect logs                 | Tokens and secrets are not disclosed                    |
| External file modification  | Change the file outside the app while it is open                  | Detect the change and prevent blind overwrite           |
| Save interruption           | Fail writes at different stages                                   | Preserve the prior valid file and recoverable draft     |
| Remote race                 | Advance the remote branch before publication                      | Detect stale base and require resolution                |
| Commit timeout              | Simulate a successful remote commit followed by a client timeout  | Query remote state before retrying                      |
| Recovery corruption         | Truncate or corrupt a snapshot                                    | Detect corruption and preserve other recoverable copies |
| Unsafe asset                | Reference a file outside the allowed resource scope               | Reject or safely handle the reference                   |
| Unauthorized native command | Invoke an operation without required capability or valid inputs   | Reject the operation                                    |

For HTML sanitization, test the actual configured parser, sanitizer, preview container, link-handling behavior, and any optional rendering extensions together. A sanitizer test in isolation is insufficient.

## 3. Feature scope and release modules

Each release should be decomposed into independently testable epics. An epic may contain several implementation tasks, but it must have explicit prerequisites, acceptance criteria, and failure-state tests.

## Phase 0 — Discovery and architecture verification

Phase 0

## Establish the engineering baseline

Objective: understand the real codebase before committing to implementation changes.

Epics

- Repository, dependency, and architecture audit.
- Existing feature inventory and roadmap mapping.
- Baseline build and test execution.
- Data-integrity and security threat model.
- Architecture decision records and backlog. Technical prerequisites
- Repository access.
- Supported development toolchain.
- Existing package manifests and lockfiles.
- Ability to run available checks, or a clear record of environment blockers. Acceptance criteria
- Actual application entry points and module boundaries are documented.
- Every roadmap feature is classified as implemented, partial, missing, broken, or unverified.
- Existing failures are recorded before changes.
- High-risk filesystem, recovery, credential, and publishing paths are identified.
- The next milestone is selected based on verified risk and dependency order.
- No source files are modified as part of discovery unless separately authorized.

Failure-state requirement: If the project cannot build, determine whether the cause is code, toolchain, missing configuration, or unavailable dependencies. Do not treat a failed environment setup as proof that the code itself is defective.

## Release 0.1 — Core desktop editor

0.1

## Create, edit, save, and preview

Epics

1. Desktop shell: Tauri configuration, startup, window behavior, application lifecycle.
2. Editor integration: CodeMirror 6, Markdown language support, selection, undo/redo, keyboard shortcuts.
3. Document lifecycle: New, open, edit, save, Save As, dirty indicator.
4. Preview: Shared Markdown parser configuration and initial safe rendering.
5. Workspace basics: Tabs, minimal explorer, theme, and preferences.
6. Engineering foundation: Test harness, logging policy, error model, CI baseline.

Technical prerequisites

- Phase 0 baseline and supported toolchain.
- Agreed frontend/native command contract.
- A documented document identity and revision strategy.
- Initial Tauri capability policy. Acceptance criteria
- A user can create, edit, save, close, and reopen a Markdown document.
- Failed open and save operations show actionable errors.
- A failed save does not clear the dirty state or discard editor content.
- Save completion reflects the revision actually persisted.
- Editing while a save is running leaves newer content dirty.
- Invalid paths and permission failures do not crash the application.
- Malicious Markdown cannot execute script content in the preview.
- The production frontend and desktop shell build successfully.
- Automated tests cover normal save behavior and key failure cases.

Release blocker: Do not proceed to broader workspace or publishing features if ordinary editing can silently lose content.

## Release 0.2 — Reliability and workspace management

0.2

## Make drafts recoverable

Epics

1. Save coordinator: Revision-aware autosave, debounce, save queue, atomic writes where supported.
2. Recovery system: Snapshot creation, integrity checks, discovery, restoration, retention.
3. External modification handling: File-version checks, conflict warnings, reload and compare options.
4. Workspace persistence: Open tabs, selected document, window preferences, recent workspaces.
5. Local navigation: Outline, search, recent files, file-explorer operations.
6. Shutdown and crash handling: Pending-save warnings, recovery metadata, startup recovery workflow.

Technical prerequisites

- Release 0.1 document identity and revision model.
- Native filesystem service.
- Consistent error taxonomy.
- A defined recovery storage location and retention policy.
- A tested safe-write strategy for supported platforms. Acceptance criteria
- Autosave never triggers GitHub publication.
- Recovery snapshots are distinguishable from confirmed saved files.
- The user can recover edits that were not written to the destination file.
- A corrupt snapshot is detected without destroying other recovery data.
- A save failure preserves the current draft and presents retry or recovery options.
- A file modified externally is not overwritten silently.
- The user can compare, reload, save to another file, or resolve a conflict through an explicit workflow.
- Edits made during an in-progress save are retained and remain dirty.
- Closing the app with pending changes follows the documented shutdown policy.
- Recovery works after forced termination in controlled tests.
- Search and workspace restoration handle missing or renamed files gracefully.

Release blocker: A recovery mechanism that only works during a clean shutdown does not meet the crash-recovery requirement.

## Release 0.3 — Documentation toolkit

0.3

## Validate and export documentation

Epics

1. Shared Markdown pipeline: Parser configuration, heading representation, anchor rules, rendering extensions.
2. TOC generator: Configurable heading levels, managed TOC region, duplicate-heading handling.
3. Quality checker: Rule engine, diagnostics, source locations, severity, optional safe fixes.
4. Link and asset validation: Internal anchors, local files, relative images, alternative text.
5. Export engine: Standalone HTML, print stylesheet, PDF/print workflow.
6. Templates and themes: README, API docs, runbooks, changelogs, technical tutorials.

Technical prerequisites

- Stable document revision snapshots.
- Release 0.1 preview pipeline.
- Release 0.2 reliable local document handling.
- Explicit asset-resolution policy.
- A defined sanitizer and supported Markdown extension set. Acceptance criteria
- Preview, TOC, validation, and export use consistent heading and parsing rules.
- Duplicate headings generate predictable anchors.
- A broken link produces a diagnostic with a source location when available.
- Missing images and missing alternative text are reported.
- An incomplete fenced code block does not crash the parser or application.
- A TOC update modifies only its managed region and preserves unrelated source text.
- Quality-checker fixes require explicit user action.
- Export failures leave the source document unchanged.
- Missing assets are reported rather than silently omitted.
- HTML export is self-contained where promised and handles required assets according to the documented export policy.
- PDF output is validated for code blocks, tables, page breaks, and long documents.
- Malicious HTML remains inert in both preview and export.

Design decision: Start with reliable HTML and print-to-PDF. Add a dedicated PDF rendering engine only if measured limitations justify the additional dependencies and maintenance burden.

## Release 0.4 — GitHub reading and draft editing

0.4

## Connect remote documentation safely

Epics

1. Authentication: Supported authorization flow, minimum permissions, secure token storage.
2. Repository explorer: Authorized repositories, branches, folders, and files.
3. Remote document loading: Fetch Markdown content and relevant metadata.
4. Draft model: Repository, branch, path, base commit, and local revision tracking.
5. Refresh and diff: Fetch updated remote content, compute differences, identify stale bases.
6. Network resilience: Rate limits, timeouts, retry policy, revoked credentials, offline drafts.

Technical prerequisites

- Reliable local editing and recovery from 0.1 and 0.2.
- A defined GitHub authentication architecture.
- Credential-service interface and secure storage.
- Document model capable of representing remote-backed drafts.
- Mockable GitHub API client and deterministic integration tests. Acceptance criteria
- Users can browse only repositories authorized by the active identity.
- Credentials are never persisted in plaintext settings or application logs.
- Remote documents become local drafts; fetching content does not change the remote repository.
- Offline editing preserves local draft content.
- Each remote draft tracks its base revision.
- A refreshed remote revision is compared with the draft's original base.
- Remote changes are detected before a draft is treated as publishable.
- Network timeouts do not corrupt local drafts.
- Rate limiting follows a bounded retry/backoff policy and respects provider guidance.
- Revoked authorization produces a clear reauthentication path.
- Switching repositories or branches cannot silently associate a draft with the wrong destination.

Release blocker: Do not add publishing controls until the application can reliably identify the exact repository, branch, file path, and base revision for each draft.

## Release 0.5 — Safe GitHub publishing

0.5

## Publish reviewed changes and verify outcomes

Epics

1. Pre-publication validation: Refresh remote state, validate destination, check authorization.
2. Diff review: Present changes and destination details for explicit approval.
3. Single-file publishing: Commit the reviewed content using the supported GitHub API workflow.
4. Conflict resolution: Detect stale bases and provide comparison and resolution options.
5. Outcome verification: Record commit identifiers and verify remote state.
6. Branch and pull-request workflow: Working branches and optional PR creation.
7. Multi-file publishing: Add coherent multi-file commits only when single-file publication is stable.

Technical prerequisites

- Release 0.4 repository and revision model.
- Tested diff implementation.
- Secure authorization and credential storage.
- Explicit publish-confirmation UI.
- A strategy for ambiguous network outcomes and idempotency. Acceptance criteria
- Autosave can never invoke a remote write.
- Publication requires a user-initiated action and explicit review of the destination and changes.
- Remote state is refreshed before publication.
- A changed base revision blocks blind overwriting and requires resolution.
- A request timeout is represented as uncertain when the server may have committed it.
- The application checks remote state before retrying an ambiguous request.
- The UI reports success only after the remote commit is verified.
- A created pull request is distinguished from a merged pull request.
- Network failure leaves local drafts and recovery data intact.
- Permission errors do not trigger broader authorization requests automatically.
- Multi-file publication, when implemented, creates a coherent reviewed commit rather than a sequence of misleading partial-success messages.
- Publishing results include repository, branch, path, and commit information where available.

Release blocker: No force overwrite, unreviewed publication, or unverified success reporting.

## Release 1.0 — Production hardening

1.0

## Prepare a dependable public release

Epics

1. Security review: Threat-model review, capability audit, dependency audit, input validation.
2. Reliability hardening: Data-loss regression suite, recovery testing, long-running session tests.
3. Packaged application: Installer, startup, upgrades, clean installation, uninstall behavior.
4. Performance: Startup, editor responsiveness, large documents, memory usage.
5. CI/CD completion: Release workflow, artifact validation, checksums and signing where feasible.
6. Documentation: Installation, backup/recovery, privacy, troubleshooting, known limitations, release notes.
7. Operational readiness: Crash diagnostics policy, safe logs, supportable error messages.

Technical prerequisites

- All mandatory 0.1–0.5 features implemented or explicitly excluded from the release scope.
- Passing regression suite.
- Documented threat model.
- Reproducible build and packaging process.
- Release checklist and owner-approved release criteria. Acceptance criteria
- Clean installation and first launch work on supported target environments.
- Upgrade tests preserve required settings and recovery data.
- Uninstall behavior matches documented data-retention expectations.
- Core editing and recovery work without an internet connection.
- No unresolved critical data-loss or security defect remains.
- Mandatory tests and packaged smoke tests pass on the release candidate.
- Installer, application startup, and basic file operations are verified.
- Security-sensitive errors and logs do not expose credentials or document content unnecessarily.
- Release artifacts and checksums are verified before publication.
- Known limitations are documented honestly.

## Release 1.x — Optional extensions

These are separate epics and should not be allowed to compromise core reliability.

| Epic                    | Scope                                                      | Prerequisites                                  | Acceptance criteria                                                            |
| ----------------------- | ---------------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------ |
| AI assistance           | Explain, summarize, rewrite, and draft documentation       | Stable document revisions and privacy controls | Changes require user approval; external transfer is disclosed and consented to |
| Local Git support       | Work with local clones and repository status               | Stable local file handling and conflict model  | Uncommitted work is preserved; Git operations cannot silently discard changes  |
| Advanced history        | Compare and restore document revisions                     | Reliable snapshot and metadata model           | Restore previews changes and never silently replaces newer content             |
| Custom quality profiles | Project-specific lint rules                                | Stable diagnostic API                          | Invalid configuration fails safely; rule changes are testable                  |
| Advanced export         | Additional formats and themes                              | Stable rendering and asset resolution          | Export failures are reported; source remains unchanged                         |
| Team workflows          | Shared conventions and optional collaborative capabilities | Security and synchronization design            | Conflicts and permissions are explicit; no hidden overwrite behavior           |

### Cross-release dependency order

Phase 0 — Verified baseline

0.1 — Editing and safe local saves

0.2 — Recovery and conflict detection

0.3 — Validation and export

0.4 — Remote reading and draft editing

0.5 — Reviewed publishing

1.0 — Production release

Release 1.x extensions can proceed after their own dependencies and risk controls are established.

A release may overlap with earlier work only when the shared dependencies are stable and the overlap does not weaken data-integrity or security gates.

## 4. Cross-cutting engineering standards

These standards apply to every release, not just Release 1.0.

### 4.1 Required architectural decision records

Maintain concise ADRs for decisions that materially affect reliability or future compatibility.

| ADR     | Decision to document                                       |
| ------- | ---------------------------------------------------------- |
| ADR-001 | Tauri capabilities and frontend/native boundary            |
| ADR-002 | Document identity, revisions, and state transitions        |
| ADR-003 | Safe writes and external modification detection            |
| ADR-004 | Recovery storage, integrity, and retention                 |
| ADR-005 | Markdown parser, extensions, sanitizer, and URL policy     |
| ADR-006 | GitHub authentication and credential storage               |
| ADR-007 | Remote base revisions, diffing, conflicts, and publication |
| ADR-008 | Export rendering and asset packaging                       |
| ADR-009 | Test strategy and release gates                            |
| ADR-010 | Settings and metadata migration compatibility              |

Each ADR should include context, alternatives considered, decision, consequences, security implications, and conditions that would justify revisiting it.

### 4.2 Observability and diagnostics

Use structured, privacy-conscious logs for operational events such as:

- Save started, succeeded, or failed.
- Recovery snapshot created or rejected.
- External modification detected.
- Export started or failed.
- GitHub request throttled or rejected.
- Publication outcome uncertain or verified.
- Application startup and migration results.

Do not log full Markdown content, authentication tokens, private document paths unnecessarily, or raw credentials. Provide operation identifiers to help connect related events without exposing sensitive information.

### 4.3 Performance and reliability metrics

Establish measurements on the actual target laptop and in CI.

| Metric                  | Measurement objective                                                                  |
| ----------------------- | -------------------------------------------------------------------------------------- |
| Startup time            | Time from launch to usable editor                                                      |
| Input responsiveness    | Typing latency and UI responsiveness under load                                        |
| Save latency            | Time from save request to confirmed persistence                                        |
| Recovery success        | Whether expected drafts survive controlled failure scenarios                           |
| Large-document behavior | Memory, parsing time, and editing responsiveness                                       |
| Export reliability      | Successful output generation and asset validation                                      |
| Publish verification    | Whether the remote result is correctly identified after normal and ambiguous responses |

Set numerical performance targets after baseline measurement. Do not claim that a target has been met until the relevant tests have run.

## 5. Final engineering acceptance checklist

Use this checklist when deciding whether a release candidate is eligible for approval.

## Release readiness review

### 0/15

### Architecture

Frontend/native contracts are documented and validated.

Native capabilities follow least privilege.

Document revisions and state transitions are tested.

### Data integrity

Failed saves preserve recoverable drafts.

External changes cannot be silently overwritten.

Crash recovery and corrupt-snapshot handling pass.

### Markdown

Preview rendering is sanitized.

TOC, validation, and export use consistent parsing rules.

Missing assets and unsafe links are handled explicitly.

### GitHub

Credentials are securely stored.

Remote base revisions and conflicts are checked.

Publishing requires approval and verifies the resulting commit.

### Production

Mandatory CI checks pass.

Packaged installation and upgrade are tested.

Known limitations, release notes, and artifact verification are complete.

Check an item only after its implementation or test evidence has been verified. This checklist is a planning aid, not an automated test result.

Reset checklistCopy checklist

## 6. Recommended next engineering action

Start with Phase 0 unless the actual repository has already completed it with verifiable evidence.

The first deliverable should be a repository assessment, not a large implementation. It should establish:

1. What currently exists and how the application is structured.
2. Whether the current frontend/native boundary is safe.
3. Whether the save lifecycle can lose data.
4. Which tests and build commands actually work.
5. Which release prerequisites are already satisfied.
6. The highest-priority bounded milestone and its acceptance tests.

Only then should implementation proceed through the release modules.

The defining quality of DevspireHub Markdown Studio should be that users can trust their documentation: their drafts remain recoverable, their files are not silently overwritten, their previews are safe, and their remote changes are published only after deliberate review and verification.
