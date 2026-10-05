# Linux Command-Line Cheatsheet

This beginner-friendly cheatsheet covers three essential Linux administration areas:

1. File permissions and ownership.
2. Process management.
3. Text filtering and searching.

The examples assume a standard Linux shell. Test them in a lab directory or virtual machine before using them on important systems.

***

## 1. Command Structure

Most Linux commands follow this pattern:

```bash
command [options] [arguments]
```

Example:

```bash
grep -i "error" application.log
```

Meaning:

| Part | Meaning |
|---|---|
| `grep` | Command used to search text. |
| `-i` | Option that ignores letter case. |
| `"error"` | Search pattern. |
| `application.log` | File to search. |

Use command documentation when unsure:

```bash
man command-name
```

Examples:

```bash
man chmod
man ps
man grep
```

The `man` command is itself a command reference system. It is useful because command options can differ between Linux distributions and software versions.

***

# 2. File Permissions and Ownership

Linux uses file permissions to control who can read, modify, or execute files and directories.

The main permission categories are:

| Symbol | Category | Meaning |
|---|---|---|
| `u` | User | The file owner. |
| `g` | Group | Users belonging to the file’s group. |
| `o` | Others | All other users. |
| `a` | All | User, group, and others. |

The three basic permissions are:

| Symbol | Permission | For a file | For a directory |
|---|---|---|---|
| `r` | Read | View contents. | List directory entries. |
| `w` | Write | Modify contents. | Create, delete, or rename entries, subject to directory permissions. |
| `x` | Execute | Run the file as a program or script. | Enter or access items inside the directory. |

## Permission display

A permission string may look like this:

```text
-rwxr-x---
```

Breakdown:

```text
- rwx r-x ---
  │   │   │
  │   │   └── Others: no permissions
  │   └────── Group: read and execute
  └────────── Owner: read, write, execute
```

The first character indicates the file type:

| Character | Meaning |
|---|---|
| `-` | Regular file. |
| `d` | Directory. |
| `l` | Symbolic link. |

The remaining nine characters are divided into three groups:

```text
rwx r-x ---
│   │   │
│   │   └── Others
│   └────── Group
└────────── Owner
```

## Numeric permissions

Linux also represents permissions using numbers:

| Permission | Numeric value |
|---|---:|
| Read `r` | 4 |
| Write `w` | 2 |
| Execute `x` | 1 |

Add the values for each permission group:

| Numeric value | Symbolic form | Meaning |
|---:|---|---|
| `0` | `---` | No permissions. |
| `1` | `--x` | Execute only. |
| `2` | `-w-` | Write only. |
| `3` | `-wx` | Write and execute. |
| `4` | `r--` | Read only. |
| `5` | `r-x` | Read and execute. |
| `6` | `rw-` | Read and write. |
| `7` | `rwx` | Read, write, and execute. |

A permission such as:

```text
755
```

means:

```text
7    5    5
│    │    │
│    │    └── Others: read and execute
│    └─────── Group: read and execute
└──────────── Owner: read, write, execute
```

So `755` corresponds to:

```text
rwxr-xr-x
```

Another common permission is:

```text
644
```

which corresponds to:

```text
rw-r--r--
```

That usually means:

- Owner can read and write.
- Group can read.
- Others can read.

## `chmod`: change permissions

`chmod` changes access permissions on files and directories. The GNU documentation describes it as changing the access permissions of named files. [gnu](https://www.gnu.org/software/coreutils/manual/coreutils.txt)

### Symbolic form

```bash
chmod u+x script.sh
```

Adds execute permission for the owner.

```bash
chmod g-w report.txt
```

Removes write permission from the group.

```bash
chmod o-r private.txt
```

Removes read permission from others.

```bash
chmod a+r document.txt
```

Adds read permission for everyone.

The symbolic structure is:

```text
chmod [who][operator][permission] file
```

| Component | Values |
|---|---|
| Who | `u`, `g`, `o`, or `a` |
| Operator | `+` add, `-` remove, `=` assign exactly |
| Permission | `r`, `w`, or `x` |

Examples:

```bash
chmod u=rw,go=r document.txt
chmod u+x,g-w script.sh
chmod a-x program
```

### Numeric form

```bash
chmod 644 document.txt
```

Sets:

```text
rw-r--r--
```

```bash
chmod 755 script.sh
```

Sets:

```text
rwxr-xr-x
```

```bash
chmod 600 private-key.txt
```

Sets:

```text
rw-------
```

This is commonly appropriate for sensitive private files, although the correct permission depends on the application and security design.

### Recursive permissions

The `-R` option applies a change recursively:

```bash
chmod -R 755 project/
```

Use recursive permission changes carefully. Applying one permission mode to every file and directory can create security or functionality problems.

For example, regular files often should not be executable merely because they are inside a directory.

## `chown`: change ownership

`chown` changes the user and/or group ownership of a file. [gnu](https://www.gnu.org/software/coreutils/manual/coreutils.txt)

```bash
chown alice document.txt
```

Changes the owner to `alice`.

```bash
chown alice:developers project.txt
```

Changes the owner to `alice` and the group to `developers`.

```bash
chown :developers shared.txt
```

Changes only the group.

Recursive ownership changes:

```bash
chown -R alice:developers project/
```

Use this carefully, especially on system directories.

Changing ownership usually requires administrative privileges because ownership affects access control and system security.

## `chgrp`: change group ownership

```bash
chgrp developers shared.txt
```

Changes the group associated with `shared.txt`.

For a directory tree:

```bash
chgrp -R developers project/
```

## `umask`: default permission filtering

`umask` controls which permission bits are removed by default when new files and directories are created.

Check the current setting:

```bash
umask
```

A common value is:

```text
022
```

Conceptually, this usually results in:

- New regular files becoming readable by the owner and others but writable only by the owner.
- New directories becoming accessible to the owner and readable or searchable by others, depending on the system defaults.

The exact resulting permissions also depend on the program creating the file.

## Important permission cautions

Avoid using broad permissions such as:

```bash
chmod -R 777 directory/
```

This gives everyone read, write, and execute permission throughout the directory tree. It may temporarily hide a permissions problem, but it can expose data or allow unauthorized modification.

Prefer the smallest permissions required:

- Give users access through appropriate groups.
- Give applications dedicated service accounts.
- Avoid unnecessary write permissions.
- Protect credentials and private keys.
- Check both file permissions and parent-directory permissions.
- Use administrative privileges only when necessary.

***

# 3. Process Management

A **process** is a running instance of a program.

For example, when an application starts, Linux creates a process with resources such as:

- A process ID.
- Allocated memory.
- Open files.
- Security credentials.
- Environment information.
- Scheduling priority.
- Network connections.

Linux can run many processes at the same time and assigns CPU time among them.

## Process identifiers

Every process normally has a unique process identifier, or **PID**, while it is running.

Important process concepts include:

| Concept | Meaning |
|---|---|
| PID | Process ID assigned to a running process. |
| PPID | Parent process ID. |
| Parent process | Process that started another process. |
| Child process | Process created by another process. |
| Foreground process | Process connected directly to the current terminal interaction. |
| Background process | Process running without occupying the terminal in the same way. |
| Signal | Software notification sent to a process. |
| Zombie process | A terminated process whose exit status has not yet been collected by its parent. |

## `ps`: process snapshot

`ps` displays a snapshot of active processes. [man7](https://www.man7.org/linux/man-pages/man1/ps.1.html)

Basic usage:

```bash
ps
```

Show processes associated with the current terminal:

```bash
ps -f
```

Display processes for all users:

```bash
ps aux
```

Another commonly used format is:

```bash
ps -ef
```

The output may include:

| Field | Meaning |
|---|---|
| `USER` | User who owns the process. |
| `PID` | Process ID. |
| `%CPU` | CPU usage. |
| `%MEM` | Memory usage. |
| `VSZ` | Virtual memory size. |
| `RSS` | Resident memory currently held in RAM. |
| `TTY` | Controlling terminal. |
| `STAT` | Process state. |
| `START` | Start time. |
| `TIME` | Accumulated CPU time. |
| `COMMAND` | Command or program associated with the process. |

Search process output with a text filter:

```bash
ps aux | grep nginx
```

This may also match the search command itself. For reliable service and process identification, use more specific process-inspection tools when available.

## `top`: live process view

`top` displays a continuously updating view of processes and system activity.

```bash
top
```

It commonly shows:

- CPU usage.
- Memory usage.
- Load information.
- Process IDs.
- Process ownership.
- Process states.
- Resource consumption.

Unlike `ps`, which normally provides a snapshot, `top` refreshes its display repeatedly. The Linux man-page documentation specifically contrasts `ps` as a snapshot with `top` as a repetitive view. [man7](https://www.man7.org/linux/man-pages/man1/ps.1.html)

Exit the interactive display using:

```text
q
```

## `htop`

Some systems provide `htop`, an interactive alternative to `top`:

```bash
htop
```

It may not be installed by default on every distribution.

`htop` commonly provides:

- A clearer interactive display.
- Process navigation.
- Sorting by resource usage.
- Process selection.
- Interactive termination options.

## `pgrep`: find process IDs

`pgrep` searches for process IDs based on a name or other criteria.

```bash
pgrep nginx
```

Show the matching process IDs and names:

```bash
pgrep -a nginx
```

This is often more precise than searching the output of a general process listing.

## `pidof`: find a program’s PIDs

```bash
pidof nginx
```

This displays the process IDs associated with the specified program.

## `kill`: send a signal

Despite its name, `kill` does not always forcibly terminate a process. It sends a signal to a process. The process may handle, ignore, or be terminated by that signal depending on the signal type and process behavior.

```bash
kill PID
```

The default signal is commonly `SIGTERM`, which requests graceful termination.

Example:

```bash
kill 2480
```

Replace `2480` with the actual PID.

### Common signals

| Signal | Number | Purpose |
|---|---:|---|
| `SIGTERM` | 15 | Requests graceful termination. |
| `SIGKILL` | 9 | Forces termination; cannot be handled or ignored. |
| `SIGHUP` | 1 | Traditionally indicates a hangup; some services use it to reload configuration. |
| `SIGINT` | 2 | Interrupt, commonly associated with keyboard interruption. |
| `SIGSTOP` | 19 on many systems | Suspends a process. |
| `SIGCONT` | 18 on many systems | Continues a stopped process. |

Use signal names for clarity:

```bash
kill -TERM 2480
```

Force termination only when a process does not respond to a graceful request:

```bash
kill -KILL 2480
```

or:

```bash
kill -9 2480
```

`SIGKILL` prevents the process from cleaning up normally. It should not be the first choice.

## `pkill`: signal processes by name

```bash
pkill -TERM application-name
```

This sends a signal to matching processes.

Use `pkill` carefully. A broad pattern may affect more processes than intended.

## `killall`: signal processes by name

```bash
killall application-name
```

Behavior can vary between operating systems and implementations. Confirm the matching processes before using it on a production system.

## `nice`: start with a scheduling priority

`nice` starts a process with an adjusted scheduling priority.

```bash
nice -n 10 long-running-task
```

The exact priority behavior depends on the scheduler and system conditions. A higher niceness generally means lower CPU scheduling priority.

## `renice`: change priority of a running process

```bash
renice 10 -p PID
```

This changes the scheduling priority of a running process.

Do not assume that changing priority will solve all performance problems. CPU usage may be caused by inefficient code, insufficient resources, I/O wait, locking, or external dependencies.

## Background and foreground jobs

When a command runs in the foreground, it occupies the current terminal interaction.

A process can be placed in the background by adding `&`:

```bash
long-running-task &
```

Common job-control commands include:

```bash
jobs
```

Shows jobs associated with the current shell.

```bash
fg
```

Brings a background job to the foreground.

```bash
bg
```

Continues a stopped job in the background.

These commands are useful for interactive shell work. Production services are normally managed through service managers or dedicated process supervisors rather than manually from a terminal.

## Process-management safety checklist

Before terminating a process:

1. Confirm the PID.
2. Confirm the process owner.
3. Check the full command line.
4. Determine whether it is part of a critical service.
5. Prefer a graceful signal first.
6. Check whether a supervisor will restart it.
7. Record the reason for the action in production.
8. Verify the service after the process exits.

***

# 4. Text Filtering and Searching

Linux commands often produce text output. Text-filtering tools help administrators search, select, transform, count, and summarize that output.

A common pattern is a **pipeline**:

```bash
command-one | command-two
```

The output of the first command becomes the input of the second command.

Example:

```bash
ps aux | grep python
```

This sends process-list output to `grep`, which searches for lines containing `python`.

## Standard streams

Linux programs commonly use three standard streams:

| Stream | Number | Purpose |
|---|---:|---|
| Standard input | 0 | Input received by a program. |
| Standard output | 1 | Normal output. |
| Standard error | 2 | Error and diagnostic output. |

Redirect output to a file:

```bash
command > output.txt
```

Append output to a file:

```bash
command >> output.txt
```

Redirect errors:

```bash
command 2> errors.txt
```

Redirect both output and errors:

```bash
command > output.txt 2>&1
```

A safer modern form for combining both streams is:

```bash
command &> output.txt
```

Use redirection carefully because `>` replaces the existing file contents.

## `grep`: search text

`grep` searches input for lines matching a pattern. The GNU manual describes its general purpose as searching files or input for matching patterns. [gnu](https://www.gnu.org/software/grep/manual/grep.txt)

Basic search:

```bash
grep "error" application.log
```

Ignore case:

```bash
grep -i "error" application.log
```

Show line numbers:

```bash
grep -n "error" application.log
```

Search multiple files:

```bash
grep "timeout" app.log database.log
```

Search recursively:

```bash
grep -r "deprecated" project/
```

The recursive option searches files below the specified directory. Use it carefully in large trees.

Invert the match:

```bash
grep -v "debug" application.log
```

This displays lines that do not contain `debug`.

Match a complete word:

```bash
grep -w "failed" application.log
```

Show the number of matching lines:

```bash
grep -c "success" application.log
```

Show only filenames with matches:

```bash
grep -l "TODO" *.py
```

Show filenames without matches:

```bash
grep -L "TODO" *.py
```

Show surrounding context:

```bash
grep -C 2 "error" application.log
```

This displays two lines before and after each match. GNU grep also provides separate options for before and after context. [redhat](https://www.redhat.com/en/blog/how-to-use-grep)

Use extended regular expressions:

```bash
grep -E "error|failed|timeout" application.log
```

Use fixed-string matching when the search text should not be interpreted as a regular expression:

```bash
grep -F "a.b" file.txt
```

### Useful `grep` pattern examples

```bash
grep '^ERROR' application.log
```

Matches lines beginning with `ERROR`.

```bash
grep 'failed$' application.log
```

Matches lines ending with `failed`.

```bash
grep -E 'HTTP/[0-9.]+ [45][0-9][0-9]' access.log
```

Searches for HTTP 4xx or 5xx response codes in a simplified pattern.

```bash
grep -E 'warning|error|critical' system.log
```

Matches any of the listed words.

Regular expressions are powerful, but patterns can become difficult to read. Start with simple literal searches.

## `head`: show the beginning

```bash
head file.txt
```

Show the first 20 lines:

```bash
head -n 20 file.txt
```

Show the first 100 bytes:

```bash
head -c 100 file.txt
```

## `tail`: show the end

```bash
tail file.txt
```

Show the last 20 lines:

```bash
tail -n 20 file.txt
```

Follow a growing log file:

```bash
tail -f application.log
```

`tail -f` keeps running and displays new lines as they are added. Stop it with an interrupt from the terminal.

A common filtering pattern is:

```bash
tail -f application.log | grep -i "error"
```

This displays new log lines containing `error`, ignoring case.

## `less`: read output page by page

```bash
less large-file.txt
```

Useful keys inside `less` include:

| Key | Action |
|---|---|
| Space | Move forward one page. |
| `b` | Move backward one page. |
| `/text` | Search forward. |
| `n` | Go to the next match. |
| `q` | Quit. |

Pipe output into `less`:

```bash
ps aux | less
```

This is useful when output is longer than the terminal window.

## `sort`: sort lines

```bash
sort names.txt
```

Reverse order:

```bash
sort -r names.txt
```

Numeric sorting:

```bash
sort -n numbers.txt
```

Sort by a field:

```bash
sort -k2 data.txt
```

For structured text, specify the separator when necessary:

```bash
sort -t: -k3 -n /etc/passwd
```

The correct field depends on the data format.

## `uniq`: remove adjacent duplicates

```bash
uniq names.txt
```

Important: `uniq` removes only adjacent duplicate lines. Sort first if you want to group identical lines:

```bash
sort names.txt | uniq
```

Count occurrences:

```bash
sort names.txt | uniq -c
```

Display only repeated lines:

```bash
sort names.txt | uniq -d
```

## `cut`: extract fields or characters

Extract characters:

```bash
cut -c1-10 file.txt
```

Extract a field separated by a delimiter:

```bash
cut -d: -f1 /etc/passwd
```

Meaning:

| Option | Meaning |
|---|---|
| `-d:` | Use `:` as the delimiter. |
| `-f1` | Print the first field. |

Another example:

```bash
cut -d, -f2 users.csv
```

This extracts the second comma-separated field.

`cut` works best with simple, consistently structured data. It is not a complete CSV parser for fields containing quoted commas.

## `tr`: translate or delete characters

Convert lowercase letters to uppercase:

```bash
tr 'a-z' 'A-Z' < input.txt
```

Replace spaces with newlines:

```bash
tr ' ' '\n' < words.txt
```

Remove carriage-return characters:

```bash
tr -d '\r' < windows-file.txt
```

`tr` processes characters rather than complex fields.

## `wc`: count lines, words, and bytes

```bash
wc file.txt
```

Typical output includes:

```text
lines words bytes filename
```

Count lines:

```bash
wc -l file.txt
```

Count words:

```bash
wc -w document.txt
```

Count bytes:

```bash
wc -c file.txt
```

Count matching lines:

```bash
grep -c "ERROR" application.log
```

## `awk`: field-based text processing

`awk` is useful for processing structured text divided into fields.

Print the first field:

```bash
awk '{print $1}' file.txt
```

Print the first and third fields:

```bash
awk '{print $1, $3}' file.txt
```

Use a colon as the field separator:

```bash
awk -F: '{print $1}' /etc/passwd
```

Filter rows based on a condition:

```bash
awk '$3 > 80 {print $0}' disk-usage.txt
```

Here, `$3` means the third field and `$0` means the entire line.

`awk` is useful for reports, logs, and whitespace-separated data. It becomes more complex when input contains quoted fields, nested formats, or irregular structures.

## `sed`: stream editing

`sed` processes text line by line.

Replace the first occurrence on each line:

```bash
sed 's/old/new/' file.txt
```

Replace all occurrences on each line:

```bash
sed 's/old/new/g' file.txt
```

Print selected lines:

```bash
sed -n '1,10p' file.txt
```

Delete blank lines:

```bash
sed '/^$/d' file.txt
```

By default, `sed` writes transformed output to standard output rather than changing the original file. This is safer for previewing transformations.

## `tee`: display and save output

```bash
command | tee output.txt
```

This displays the output and saves a copy to `output.txt`.

Append instead of replacing:

```bash
command | tee -a output.txt
```

This is useful when you want to observe output while recording it.

## `xargs`: build command arguments from input

```bash
printf '%s\n' file1 file2 | xargs wc -l
```

This passes the input items as arguments to `wc`.

Be careful with filenames containing spaces, quotes, or newlines. Where supported, null-delimited workflows are safer:

```bash
find . -type f -print0 | xargs -0 grep -n "pattern"
```

Use this only when you understand the input format and command behavior.

***

# 5. Essential Pipelines

## Find errors in a log

```bash
grep -i "error" application.log
```

## Count errors

```bash
grep -ic "error" application.log
```

## View recent errors continuously

```bash
tail -f application.log | grep -i "error"
```

## Inspect processes related to a service

```bash
ps aux | grep service-name
```

For more precise process matching:

```bash
pgrep -a service-name
```

## Sort processes by CPU usage

```bash
ps aux --sort=-%cpu | head
```

## Sort processes by memory usage

```bash
ps aux --sort=-%mem | head
```

## List unique response codes from a simple access log

```bash
awk '{print $9}' access.log | sort | uniq -c | sort -nr
```

The field number depends on the log format. Always inspect the format before relying on a field position.

## Display usernames from a colon-separated file

```bash
cut -d: -f1 /etc/passwd
```

## Count lines containing a keyword

```bash
grep -i "timeout" application.log | wc -l
```

## Search recursively and show line numbers

```bash
grep -RIn "database_url" project/
```

The options mean:

| Option | Meaning |
|---|---|
| `-R` | Recursive search. |
| `-I` | Ignore binary files. |
| `-n` | Show line numbers. |

## Save filtered output

```bash
grep -i "warning" application.log > warnings.txt
```

Append instead of replacing:

```bash
grep -i "warning" application.log >> warnings.txt
```

***

# 6. Common Beginner Mistakes

## Confusing file and directory permissions

For directories:

- Read allows listing names.
- Write allows creating, deleting, or renaming entries.
- Execute allows entering or accessing items inside.

A directory may be readable but not searchable, or searchable but not listable.

## Using `chmod 777` as a general fix

This grants broad access and can expose sensitive data or allow unauthorized changes. Identify the required owner, group, and permission set instead.

## Killing the wrong process

Always verify:

```bash
ps -p PID -f
```

Replace `PID` with the actual process ID.

Do not terminate a process based only on a partial name.

## Forgetting that `grep` is case-sensitive

These searches differ:

```bash
grep "error" application.log
grep -i "error" application.log
```

The second one also matches `Error`, `ERROR`, and other letter-case variations.

## Assuming `uniq` finds all duplicates

This may not count duplicates that are separated:

```bash
uniq file.txt
```

Sort first:

```bash
sort file.txt | uniq -c
```

## Overwriting files with redirection

This replaces the destination file:

```bash
command > output.txt
```

Use `>>` to append:

```bash
command >> output.txt
```

## Parsing complex formats with simple tools

`cut`, `awk`, and `grep` are excellent for simple structured text, but they are not universal parsers for JSON, quoted CSV, XML, or application-specific formats.

Use a format-aware tool when the data structure requires it.

***

# 7. Quick Reference Tables

## Permissions

| Command | Purpose |
|---|---|
| `chmod 644 file` | Owner read/write; group and others read. |
| `chmod 755 file` | Owner full access; group and others read/execute. |
| `chmod 600 file` | Owner read/write only. |
| `chmod u+x file` | Add execute permission for owner. |
| `chmod g-w file` | Remove group write permission. |
| `chown user file` | Change owner. |
| `chown user:group file` | Change owner and group. |
| `chgrp group file` | Change group. |
| `umask` | Display default permission mask. |

## Processes

| Command | Purpose |
|---|---|
| `ps` | Show a process snapshot. |
| `ps aux` | Show processes for all users. |
| `ps -ef` | Show full-format process information. |
| `top` | Show continuously updating process information. |
| `pgrep name` | Find process IDs by name. |
| `pidof name` | Find PIDs for a program. |
| `kill PID` | Request graceful process termination. |
| `kill -KILL PID` | Force termination; use cautiously. |
| `pkill name` | Send a signal to matching process names. |
| `jobs` | Show shell jobs. |
| `fg` | Bring a job to the foreground. |
| `bg` | Continue a job in the background. |

## Text filtering

| Command | Purpose |
|---|---|
| `grep pattern file` | Search for matching lines. |
| `grep -i pattern file` | Case-insensitive search. |
| `grep -n pattern file` | Show line numbers. |
| `grep -r pattern dir` | Search recursively. |
| `head file` | Show beginning of a file. |
| `tail file` | Show end of a file. |
| `tail -f file` | Follow new log entries. |
| `less file` | Read content page by page. |
| `sort file` | Sort lines. |
| `uniq file` | Remove adjacent duplicate lines. |
| `cut` | Extract fields or character ranges. |
| `tr` | Translate or delete characters. |
| `wc` | Count lines, words, or bytes. |
| `awk` | Process fields and conditions. |
| `sed` | Transform or select text streams. |
| `tee` | Display and save output. |

***

## Safe Practice Sequence

Use this learning order:

1. Create harmless test files in a temporary lab directory.
2. Practice reading permission strings.
3. Change permissions on test files only.
4. Create a test user and group in a virtual machine.
5. Start a harmless long-running process.
6. Inspect it using process tools.
7. Send a graceful signal and observe the result.
8. Create a sample log file.
9. Filter it using `grep`, `head`, `tail`, `sort`, `uniq`, and `wc`.
10. Combine commands with pipelines only after understanding each command individually.

The core principle is simple: permissions control access, process tools show and control running programs, and text filters help you extract useful information from system output.
