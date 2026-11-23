\---

title: "Linux Fundamentals"

date: 2026-11-01

categories: \[Club]

tags: \[Linux]

\---1. Learning Objectives

By the end of this lecture, students should be able to:

* Explain what Linux is and distinguish the Linux kernel from a Linux
distribution.
* Understand the terminal, shell, commands, options, and arguments.
* Navigate the Linux filesystem and identify important system
directories.
* Create, read, edit, copy, move, search, and delete files and
directories.
* Understand users, groups, `root`, `sudo`, and file permissions.
* Inspect processes and stop a process safely.
* Understand output redirection and basic command pipelines.
* Use common network and package-management commands.

\---

## 2\. What Is Linux?

Linux is an open-source, Unix-like operating system family built around
the **Linux kernel**. The kernel is the core component that manages
hardware and system resources. It provides services such as:

* **Process management:** running, scheduling, and stopping programs.
* **Memory management:** allocating and managing RAM.
* **Device management:** communicating with hardware through drivers.
* **Filesystem management:** organizing and accessing stored data.
* **Networking:** handling network communication.

Linux is used in servers, cloud platforms, supercomputers, embedded
devices, routers, and security-testing environments. Android also uses
the Linux kernel.

### 2.1 Kernel vs. Distribution

The **kernel** is the core of the operating system. A **Linux
distribution (distro)** combines the kernel with system utilities,
package-management tools, libraries, applications, and configuration.

Examples of distributions:

* **Ubuntu:** beginner-friendly and widely used on desktops and
servers.
* **Debian:** known for stability and a large software repository.
* **Kali Linux:** designed for penetration testing and digital
forensics.
* **Fedora:** a community distribution with relatively recent
technologies.
* **Linux Mint:** a desktop-focused distribution.

A useful explanation for students:

> Linux is the kernel; Ubuntu, Debian, and Kali are distributions built
> around it.

### 2.2 Linux Is Multiuser and Multitasking

* **Multiuser:** multiple user accounts can exist on the same system,
each with its own permissions and files.
* **Multitasking:** multiple processes can run at the same time.
* **Permission-based:** access to files and system resources can be
controlled.
* **Case-sensitive:** `Report.txt` and `report.txt` are different
filenames.

### 2.3 The Linux Command Line

The command line lets users interact with the system by entering text
commands. A terminal is the application window; a **shell** is the
program that interprets commands. Common shells include Bash and Zsh.

A command generally follows this pattern:

``` bash
command \[options] \[arguments]
```

Example:

``` bash
ls -lah /home
```

* `ls` is the command.
* `-l`, `-a`, and `-h` are options.
* `/home` is the argument (the target directory).

The exact options available depend on the command. Use its manual page
to check.

\---

## 3\. Understanding the Linux Filesystem

Linux uses a **single directory tree**. The top of this tree is the root
directory, written as `/`. Other directories, storage devices, and
partitions appear somewhere inside this tree after they are mounted.

Do not confuse these two terms:

* `/` --- the root directory, the top of the filesystem tree.
* `root` --- the administrator account, usually with user ID `0`.

### 3.1 Important Linux Directories

\---

Path                    Purpose                 Example / Notes

\---

`/`                     Root of the entire      Every normal filesystem
directory tree          path starts here.

`/home`                 Home directories for    A user may have
regular users           `/home/mohamed`.

`/root`                 Home directory of the   Not the same as `/`.
root account

`/bin`                  Essential user commands Often linked to
`/usr/bin` on modern
distributions.

`/sbin`                 Essential system        Often linked to
administration commands `/usr/sbin` on modern
distributions.

`/usr`                  Most user applications, Contains `/usr/bin`,
libraries, and shared   `/usr/lib`, and
read-only data          `/usr/share`.

`/usr/local`            Software installed      Common place for
locally by the          manually installed
administrator           software.

`/etc`                  System-wide             Examples:
configuration files     `/etc/passwd`,
`/etc/hostname`,
`/etc/ssh/`.

`/var`                  Frequently changing     Logs, caches, queues,
data                    and application data.

`/var/log`              System and application  Useful for
logs                    troubleshooting and
security
investigations.

`/tmp`                  Temporary files         Files may be removed
automatically,
depending on system
policy.

`/opt`                  Optional or third-party Some vendors install
application software    applications here.

`/dev`                  Device files and        Examples: `/dev/null`,
interfaces              `/dev/sda` (if
present).

`/proc`                 Virtual filesystem      Examples:
exposing process and    `/proc/cpuinfo`,
kernel information      `/proc/meminfo`.

`/sys`                  Virtual filesystem      Used by the kernel and
exposing device and     system tools.
kernel information

`/run`                  Runtime data since the  Often contains PID
system booted           files and service
state.

`/boot`                 Files needed to boot    May contain the kernel
the system              and bootloader files.

`/media`                Common mount point for  USB drives may appear
removable media         here in desktop
systems.

`/mnt`                  Common temporary/manual Often used by
mount point             administrators.

`/lib`, `/lib64`        Essential shared        May be links into
libraries and kernel    `/usr` on modern
modules on some layouts distributions.
---

**Important:** The exact directory layout can differ between
distributions. Some modern Linux systems use a merged `/usr` layout,
where paths such as `/bin` are symbolic links to directories under
`/usr`.

### 3.2 Absolute and Relative Paths

An **absolute path** starts from `/`:

``` bash
cd /home/mohamed/Documents
```

A **relative path** starts from the current working directory:

``` bash
cd Documents
```

Special path symbols:

Symbol   Meaning

\---

`.`      Current directory
`..`     Parent directory
`\~`      Current user's home directory
`/`      Root directory

Examples:

``` bash
pwd
cd ..
cd .
cd \~
cd /var/log
```

### 3.3 Hidden Files

In Linux, a filename that starts with a dot (`.`) is treated as hidden
by many standard listing tools.

Examples:

* `.bashrc`
* `.profile`
* `.ssh`

Show hidden files:

``` bash
ls -a
```

Show detailed information, including hidden files:

``` bash
ls -lah
```

Hidden does **not** mean encrypted or protected. It is mainly a display
convention.

\---

## 4\. Working with the Terminal

### 4.1 Clear the Terminal

``` bash
clear
```

Clears the visible terminal screen. It does not delete command history
or files.

### 4.2 Print the Current Directory

``` bash
pwd
```

`pwd` means **Print Working Directory**. It shows the directory in which
the shell is currently operating.

### 4.3 Change Directory

``` bash
cd /etc
cd ..
cd \~
cd -
```

* `cd /etc`: move to `/etc`.
* `cd ..`: move one level up.
* `cd \~`: move to the current user's home directory.
* `cd -`: return to the previous working directory.

### 4.4 List Files and Directories

``` bash
ls
ls -l
ls -a
ls -lah
ls -lh /var/log
```

Option   Meaning

\---

`-l`     Long listing: permissions, owner, group, size, date, and name
`-a`     Include hidden entries
`-h`     Human-readable sizes, such as KB or MB
`-R`     List directories recursively

**Correction:** `ls -L` is not the option for a long listing. Use
`ls -l` for that. `-L` follows symbolic links when listing their
targets.

\---

## 5\. Getting Help

### 5.1 `man`

``` bash
man ls
man chmod
man grep
```

Displays the manual page for a command. Navigate with the keyboard:

* `Space`: next page.
* `b`: previous page.
* `/word`: search for a word.
* `n`: next search match.
* `q`: quit.

### 5.2 `--help`

Many commands support:

``` bash
ls --help
chmod --help
```

This displays a shorter usage guide. Not every program implements
`--help` in exactly the same way.

### 5.3 `whatis` and `apropos`

``` bash
whatis chmod
apropos password
```

* `whatis` gives a short description of a command.
* `apropos` searches manual-page descriptions for a keyword.

\---

## 6\. Reading and Editing Files

### 6.1 `cat`

``` bash
cat /etc/passwd
cat notes.txt
```

Prints file contents to the terminal. It is convenient for short files.
Large files are usually easier to inspect with `less`.

`cat` can also combine files:

``` bash
cat part1.txt part2.txt
```

### 6.2 `more`

``` bash
more /var/log/syslog
```

Displays text one screen at a time. It is a basic pager.

### 6.3 `less`

``` bash
less /var/log/syslog
```

A more flexible pager. Useful keys:

* `Space` / `Page Down`: move forward.
* `b` / `Page Up`: move backward.
* `/error`: search for `error`.
* `n`: next match.
* `q`: quit.

### 6.4 `head`

``` bash
head file.txt
head -n 5 file.txt
```

Displays the first 10 lines by default. `-n` controls the number of
lines.

### 6.5 `tail`

``` bash
tail file.txt
tail -n 20 file.txt
tail -f /var/log/syslog
```

Displays the last 10 lines by default.

* `-n 20`: display the last 20 lines.
* `-f`: keep watching the file as new lines are added. Useful for
monitoring logs.

### 6.6 `nano`

``` bash
nano notes.txt
sudo nano /etc/hosts
```

A simple terminal text editor. Common shortcuts are shown at the bottom
of the screen. In Nano:

* `Ctrl + O`: save (Write Out).
* `Enter`: confirm the filename.
* `Ctrl + X`: exit.
* `Ctrl + W`: search.

Editing system configuration files usually requires administrator
privileges. Be careful not to overwrite important configuration
accidentally.

\---

## 7\. Creating, Copying, Moving, and Removing Files

### 7.1 `mkdir` --- Create Directories

``` bash
mkdir projects
mkdir -p projects/linux/week1
```

`-p` creates missing parent directories and does not report an error if
the directory already exists.

### 7.2 `rmdir` --- Remove Empty Directories

``` bash
rmdir old\_folder
```

`rmdir` removes an empty directory only. It will not remove a directory
containing files.

### 7.3 `touch` --- Create an Empty File or Update Its Timestamp

``` bash
touch day1.txt
touch file1.txt file2.txt
```

If the file does not exist, `touch` creates an empty file. If it exists,
`touch` updates its timestamps; it does not erase its content.

### 7.4 `cp` --- Copy Files and Directories

``` bash
cp notes.txt backup.txt
cp notes.txt /tmp/
cp -r projects projects\_backup
cp -i notes.txt backup.txt
```

* `cp source destination`: copy a file.
* `-r`: copy directories recursively.
* `-i`: ask before overwriting an existing destination.

`cp` copies; it does not move the original.

### 7.5 `mv` --- Move or Rename

``` bash
mv notes.txt /tmp/
mv oldname.txt newname.txt
mv projects /home/mohamed/
```

`mv` can move files/directories or rename them. If the source and
destination are on the same filesystem, a move is often a quick
directory-entry operation.

### 7.6 `rm` --- Remove Files and Directories

``` bash
rm old.txt
rm -i old.txt
rm -r old\_folder
```

* `rm`: remove files.
* `-i`: prompt before removal.
* `-r`: remove directories and their contents recursively.

**Safety warning:** `rm` normally does not move files to a recycle bin.
Check the path carefully before running it. Avoid copying dangerous
commands from the internet, especially commands that use `rm -rf` with
broad paths or variables.

\---

## 8\. Users, Groups, Root, and Sudo

Linux is designed to support multiple user accounts. Each process
normally runs with the permissions of a user.

### 8.1 `root`

`root` is the superuser account, normally with UID `0`. It has broad
authority over the system, including the ability to read or modify
protected files and manage users.

Using root for everyday tasks is risky. A mistake made with root
privileges can damage the system.

### 8.2 `sudo`

``` bash
sudo apt update
sudo nano /etc/hosts
```

`sudo` runs a command with elevated privileges when the current user is
allowed by the system's sudo policy. It does not permanently turn the
user into root.

The command may ask for **your own account password**, not the root
password.

### 8.3 `adduser` --- Create a User

``` bash
sudo adduser mohamed
```

Creates a user and, on Debian/Ubuntu systems, guides you through setting
a password and optional user details.

### 8.4 `passwd` --- Set or Change a Password

``` bash
passwd
sudo passwd mohamed
```

* `passwd`: change your own password.
* `sudo passwd mohamed`: an administrator changes the password for
`mohamed`.

### 8.5 `deluser` --- Delete a User

``` bash
sudo deluser mohamed
```

Removes the user account on Debian/Ubuntu systems. The user's home
directory is generally not removed by this command unless an option such
as `--remove-home` is used.

Be careful: deleting a user can affect files and services owned by that
account.

### 8.6 `groupadd` and `groupdel`

``` bash
sudo groupadd IT
sudo groupdel IT
```

Create or delete a group. A group is a way to assign shared access to
multiple users.

### 8.7 `usermod` --- Modify a User Account

``` bash
sudo usermod -aG IT mohamed
```

Adds `mohamed` to the supplementary group `IT`.

**Important correction:** Use `-aG` when adding a user to an additional
group. `-G IT` without `-a` replaces the user's supplementary group list
and may remove memberships they already had.

To check memberships:

``` bash
groups mohamed
id mohamed
```

A user may need to log out and log in again for a new group membership
to apply to their session.

\---

## 9\. Linux File Permissions

Linux permissions control who can read, modify, or execute a file or
access a directory.

There are three permission classes:

* **User (`u`):** the file's owner.
* **Group (`g`):** users who belong to the file's group.
* **Others (`o`):** everyone else.

There are three basic permission types:

\---

Permission    Symbol            Numeric value For a regular    For a directory
file

\---

Read          `r`                           4 Read file        List directory
contents         entries

Write         `w`                           2 Modify file      Create, delete,
contents         or rename
entries (subject
to other
controls)

Execute       `x`                           1 Run the file as  Enter/traverse
a program/script the directory
---

### 9.1 Reading Permission Output

Run:

``` bash
ls -l
```

Example:

``` text
-rwxr-xr-- 1 mohamed IT 1200 Nov 24 10:00 script.sh
```

Breakdown:

``` text
- rwx r-x r--
  |   |   |
  |   |   └── Others: read
  |   └────── Group: read and execute
  └────────── Owner: read, write, execute
```

The first character indicates the file type:

* `-`: regular file.
* `d`: directory.
* `l`: symbolic link.

The next nine characters represent permissions for owner, group, and
others.

### 9.2 Numeric (Octal) Permissions

The values are added together:

Permission   Calculation     Value

\---

`---`        0                   0
`--x`        1                   1
`-w-`        2                   2
`-wx`        2 + 1               3
`r--`        4                   4
`r-x`        4 + 1               5
`rw-`        4 + 2               6
`rwx`        4 + 2 + 1           7

For example:

``` bash
chmod 765 test.txt
```

Means:

* Owner: `7` = `rwx`.
* Group: `6` = `rw-`.
* Others: `5` = `r-x`.

Another common example:

``` bash
chmod 644 notes.txt
```

Owner can read and write; group and others can only read.

``` bash
chmod 755 script.sh
```

Owner can read, write, and execute; group and others can read and
execute.

### 9.3 Symbolic Permissions

``` bash
chmod u+x script.sh
chmod g-w notes.txt
chmod o+r notes.txt
chmod u=rw,g=r,o= file.txt
```

* `u`: owner.
* `g`: group.
* `o`: others.
* `a`: all classes.
* `+`: add a permission.
* `-`: remove a permission.
* `=`: set the permissions exactly for the selected class.

A valid combined example is:

``` bash
chmod u-rwx,g=r,o+x test.txt
```

There should be no spaces around the commas separating permission
clauses.

### 9.4 Changing Ownership with `chown`

``` bash
sudo chown mohamed file.txt
sudo chown mohamed:IT file.txt
sudo chown -R mohamed:IT projects/
```

`chown` changes ownership:

* `mohamed`: set the owner.
* `mohamed:IT`: set owner and group.
* `-R`: apply recursively to the directory and its contents.

**Correction:** `chown` does not take an old user and a new user as two
arguments. The general form is:

``` bash
sudo chown \[OPTIONS] OWNER\[:GROUP] FILE
```

To change only the group, use:

``` bash
sudo chgrp IT file.txt
```

### 9.5 Important Permission Notes

* Execute permission on a directory means the ability to
traverse/access it.
* A user may need execute permission on every parent directory in a
path to reach a file.
* The effective permissions can also be affected by ACLs, mount
options, security modules, and other controls.
* Changing permissions on system files without understanding their
purpose can break services or reduce security.

\---

## 10\. Searching for Files and Text

### 10.1 `find` --- Search the Filesystem

``` bash
find /home -name "notes.txt"
find /home -type f -name "\*.txt"
find /var/log -type f
find . -type d -name "backup"
```

Useful options:

Option      Meaning

\---

`-name`     Match a filename (case-sensitive)
`-iname`    Match a filename (case-insensitive)
`-type f`   Regular files only
`-type d`   Directories only
`-size`     Search by file size
`-user`     Search by owner

Example:

``` bash
find /home -type f -iname "\*.pdf"
```

Searches under `/home` for regular files with a `.pdf` extension,
regardless of letter case.

### 10.2 `locate` --- Search an Indexed Database

``` bash
locate passwd
locate "\*.conf"
```

`locate` searches a database of file paths, so it is often fast. The
database may not include very recently created files until it is
updated. On systems that provide `updatedb`, an administrator can
refresh it:

``` bash
sudo updatedb
```

Availability and command names depend on the distribution and installed
package.

### 10.3 `grep` --- Search Text

``` bash
grep "error" app.log
grep -i "error" app.log
grep -n "root" /etc/passwd
grep -r "TODO" projects/
```

Option   Meaning

\---

`-i`     Ignore letter case
`-n`     Show line numbers
`-r`     Search recursively in directories
`-v`     Show lines that do not match
`-E`     Use extended regular expressions

Example:

``` bash
grep -in "failed" /var/log/auth.log
```

Searches for `failed` without case sensitivity and displays matching
line numbers.

**Useful distinction:**

* `find` searches for files/directories by attributes such as name,
type, owner, and size.
* `grep` searches inside text for matching content.
* `locate` searches a prebuilt path database.

\---

## 11\. Output Redirection and Pipes

A command normally writes output to the terminal. Linux lets us redirect
that output to a file or send it to another command.

### 11.1 Standard Streams

Stream                         Number Purpose

\---

Standard input (`stdin`)            0 Input received by a command
Standard output (`stdout`)          1 Normal command output
Standard error (`stderr`)           2 Error messages

### 11.2 `>` --- Overwrite a File

``` bash
ls -lah > test.txt
```

Sends standard output to `test.txt`. If the file already exists, its
previous content is overwritten. If it does not exist, it is created.

### 11.3 `>>` --- Append to a File

``` bash
ls -lah >> test.txt
```

Appends standard output to the end of the file without removing its
previous content.

### 11.4 Redirect Errors

``` bash
find / -name "secret.txt" 2> errors.txt
```

Sends standard error to `errors.txt`.

To append errors:

``` bash
find / -name "secret.txt" 2>> errors.txt
```

To redirect both standard output and standard error to the same file in
Bash:

``` bash
command > output.txt 2>\&1
```

### 11.5 `|` --- Pipe

A pipe sends the standard output of one command to the standard input of
another command.

``` bash
ps aux | grep ssh
cat /etc/passwd | grep mohamed
```

This allows commands to be combined into useful workflows.

Example:

``` bash
ps aux | grep firefox
```

Displays process-list output and filters it for lines containing
`firefox`.

### 11.6 `echo`

``` bash
echo "Hello World"
echo "Linux Fundamentals" > title.txt
echo "Day 2" >> notes.txt
```

Prints text to standard output. It is often used in shell scripts and
simple redirection examples.

### 11.7 `cut` --- Extract Fields or Characters

``` bash
cut -d ":" -f 1 /etc/passwd
```

* `-d ":"`: use the colon as the delimiter.
* `-f 1`: print the first field.

Another example:

``` bash
cut -d " " -f 1 names.txt
```

This extracts the first space-delimited field. It works best when the
input has a consistent delimiter; it is not a full parser for arbitrary
whitespace.

\---

## 12\. Processes and Process Management

A **process** is a running instance of a program. Each process has a
Process ID (PID).

### 12.1 `ps`

``` bash
ps
ps aux
ps -ef
```

* `ps`: shows processes associated with the current terminal/session
in a common configuration.
* `ps aux`: displays a detailed snapshot of processes across the
system on Linux.
* `ps -ef`: another widely used full process listing format.

In `ps aux`, common columns include:

* `USER`: account running the process.
* `PID`: process ID.
* `%CPU`: CPU usage estimate.
* `%MEM`: memory usage estimate.
* `STAT`: process state.
* `COMMAND`: command line.

### 12.2 `top`

``` bash
top
```

Shows a live, updating view of processes and system resource usage.
Press `q` to quit.

### 12.3 `kill`

``` bash
kill 9293
kill -TERM 9293
kill -KILL 9293
```

`kill` sends a signal to a process; it does not always mean immediate
termination.

* `TERM` (15): asks the process to terminate gracefully. This is the
default signal.
* `KILL` (9): forces termination and cannot be caught or ignored.

Use `SIGKILL` only when a process does not stop normally, because it
does not give the process a chance to clean up.

Example workflow:

``` bash
ps aux | grep application
kill 9293
```

Confirm the PID carefully before stopping a process. PIDs can change,
and stopping the wrong process may interrupt an important service.

\---

## 13\. Network and Internet Commands

### 13.1 `ip`

The modern tool for viewing and managing network interfaces and routes.

``` bash
ip address
ip addr show
ip route
```

* `ip address`: displays network interfaces and IP addresses.
* `ip route`: displays the routing table.

### 13.2 `ifconfig`

``` bash
ifconfig
ifconfig -a
```

Displays network-interface information on systems where the `net-tools`
package is installed.

`ifconfig` is considered a legacy tool on many modern Linux
distributions. Prefer `ip address` for current Linux administration.

### 13.3 `curl`

``` bash
curl https://example.com
curl -I https://example.com
curl -o page.html https://example.com
```

`curl` transfers data to or from a URL and supports many protocols. It
is useful for testing HTTP services and sending requests.

* `-I`: request response headers.
* `-o`: save the response body to a file.
* `-L`: follow HTTP redirects.

Example:

``` bash
curl -L https://example.com
```

### 13.4 `wget`

``` bash
wget https://example.com/file.zip
wget -O downloaded.html https://example.com
```

`wget` is commonly used to download files from web servers.

* `-O`: choose the output filename.
* `-c`: continue a partially downloaded file when the server supports
it.

**Difference:** `curl` is a flexible data-transfer tool often used for
API and HTTP testing; `wget` is commonly used for downloading files.
Their capabilities overlap, so they are not simply interchangeable in
every situation.

\---

## 14\. Package Management on Debian and Ubuntu

A package manager installs, updates, and removes software while handling
dependencies.

Debian-based distributions such as Ubuntu and Kali use APT.

### 14.1 Refresh the Package Index

``` bash
sudo apt update
```

Downloads updated package information from configured repositories. It
does **not** itself upgrade installed applications.

### 14.2 Upgrade Installed Packages

``` bash
sudo apt upgrade
```

Installs available upgrades for installed packages, subject to APT's
dependency and package-management rules.

### 14.3 Install a Package

``` bash
sudo apt install nmap
```

Installs a package and required dependencies from configured
repositories.

### 14.4 Remove a Package

``` bash
sudo apt remove nmap
```

Removes the package but generally leaves its system-wide configuration
files.

``` bash
sudo apt purge nmap
```

Removes the package and its package-managed configuration files.

``` bash
sudo apt autoremove
```

Removes packages that were installed as dependencies and are no longer
required, according to APT's package state. Review the proposed changes
before confirming.

**Correction:** `apt update` updates package lists; `apt upgrade`
upgrades installed packages. They do different jobs.

\---

## 15\. Useful Commands Not to Miss

\---

Command                 Purpose                 Example

\---

`whoami`                Print the current       `whoami`
username

`id`                    Show UID, GID, and      `id mohamed`
group memberships

`hostname`              Display the system      `hostname`
hostname

`uname`                 Display kernel/system   `uname -a`
information

`df`                    Show filesystem disk    `df -h`
space

`du`                    Estimate file/directory `du -sh projects/`
disk usage

`free`                  Show memory usage       `free -h`

`history`               Show shell command      `history`
history

`which`                 Locate a command in the `which python3`
current PATH

`whereis`               Locate binary, source,  `whereis ssh`
and manual files

`file`                  Identify a file's type  `file suspicious.bin`

`stat`                  Show detailed file      `stat notes.txt`
metadata

`tar`                   Create or extract       `tar -czf backup.tar.gz projects/`
archive files

`ssh`                   Connect to a remote     `ssh user@192.0.2.10`
system securely
---

\---

## 16\. Practical Demonstration: Build a Small Linux Workspace

Ask students to follow these steps in their own user account, not as
root.

### Step 1: Check the Current User and Location

``` bash
whoami
pwd
id
```

Explain the current account, working directory, and group memberships.

### Step 2: Create a Workspace

``` bash
mkdir -p \~/linux-lab/week1
cd \~/linux-lab/week1
pwd
```

### Step 3: Create Files and Add Text

``` bash
touch names.txt notes.txt
echo "Mohamed Abdo" > names.txt
echo "Linux is a multiuser operating system." > notes.txt
echo "The filesystem starts at /." >> notes.txt
```

Explain the difference between `>` and `>>`.

### Step 4: Read the Files

``` bash
cat notes.txt
head -n 1 notes.txt
tail -n 1 notes.txt
less notes.txt
```

### Step 5: Copy and Rename

``` bash
cp notes.txt notes\_backup.txt
mv names.txt students.txt
ls -lah
```

### Step 6: Search

``` bash
grep -n "filesystem" notes.txt
find \~/linux-lab -type f -name "\*.txt"
```

### Step 7: Set and Inspect Permissions

``` bash
chmod 640 notes.txt
ls -l notes.txt
```

Ask students to identify the owner, group, and others permissions.

### Step 8: Inspect System Information

``` bash
uname -a
ip address
df -h
free -h
ps aux | head
```

### Step 9: Clean Up

``` bash
cd \~
```

Do not delete the workspace until students have reviewed their work. If
cleanup is required:

``` bash
rm -r \~/linux-lab
```

Explain that recursive removal is permanent in normal terminal use and
the path must be checked carefully.

\---

## 17\. Common Beginner Mistakes

1. **Confusing `/` with `/root`:** `/` is the top of the filesystem;
`/root` is the root user's home directory.
2. **Using `apt upgrade` instead of `apt update`:** refresh package
lists first, then upgrade packages.
3. **Using `usermod -G` without `-a`:** this can replace existing
supplementary group memberships. Use `usermod -aG`.
4. **Assuming `touch` clears a file:** it creates a file if missing or
updates timestamps if it exists.
5. **Assuming `mv` and `cp` are the same:** `cp` copies; `mv` moves or
renames.
6. **Thinking `kill` always means force kill:** the default signal is
`TERM`; `-9` sends `KILL`.
7. **Confusing `find`, `locate`, and `grep`:** they search different
things.
8. **Thinking hidden files are secure:** a leading dot only affects
normal display behavior.
9. **Using `sudo` for every command:** use elevated privileges only
when necessary.
10. **Running commands without checking the target path:** especially
`rm`, `chmod`, and `chown`.

\---

## 18\. Quick Knowledge Check

Use these questions at the end of the lecture.

1. What is the difference between the Linux kernel and a Linux
distribution?
2. What is the difference between `/` and `/root`?
3. Which command displays the current working directory?
4. How do you show hidden files?
5. What is the difference between `>` and `>>`?
6. What is the difference between `cp` and `mv`?
7. Which command searches inside file contents?
8. What is the difference between `find` and `locate`?
9. What does `sudo` do?
10. What does `chmod 755 script.sh` mean?
11. Why should `usermod -aG` be used when adding a supplementary group?
12. What is the difference between `apt update` and `apt upgrade`?
13. What is a PID?
14. What is the difference between `kill` and `kill -9`?
15. Why is it risky to work as root all the time?

### Suggested Answers

1. The kernel is the core; a distribution packages it with utilities,
software, and configuration.
2. `/` is the filesystem root; `/root` is the root account's home
directory.
3. `pwd`.
4. `ls -a`.
5. `>` overwrites; `>>` appends.
6. `cp` copies; `mv` moves or renames.
7. `grep`.
8. `find` searches the live directory tree; `locate` searches a path
database.
9. It runs an allowed command with elevated privileges.
10. Owner: `rwx`; group: `r-x`; others: `r-x`.
11. `-a` appends the group instead of replacing the existing
supplementary group list.
12. `apt update` refreshes package metadata; `apt upgrade` installs
available upgrades.
13. Process ID, a number identifying a process.
14. `kill` sends `TERM` by default; `kill -9` sends `KILL`.
15. A mistake with unrestricted privileges can damage system files,
services, or security settings.

\---

## 19\. Instructor Notes: Recommended Teaching Order

For a smooth beginner lesson, teach the topics in this order:

1. What Linux is: kernel, distributions, multiuser, multitasking.
2. Terminal and shell: command structure, options, arguments, help.
3. Filesystem: `/`, `/home`, `/etc`, `/var`, `/root`, and path
navigation.
4. Basic file operations: `pwd`, `cd`, `ls`, `mkdir`, `touch`, `cat`,
`cp`, `mv`, `rm`.
5. Text and search: `less`, `head`, `tail`, `nano`, `grep`, `find`,
`locate`.
6. Users and groups: `root`, `sudo`, `adduser`, `passwd`, `groupadd`,
`usermod`.
7. Permissions: `rwx`, numeric and symbolic `chmod`, `chown`.
8. Processes: `ps`, `top`, and `kill`.
9. Redirection and pipes: `>`, `>>`, `2>`, and `|`.
10. Networking and package management: `ip`, `curl`, `wget`, and `apt`.

**Teaching tip:** Do not teach commands as isolated definitions only.
For each command, demonstrate a real task, explain the output, and ask
students to predict what will happen before executing it.

\---

## 20\. Final Reminder

Linux is best learned through practice. Students should work in a
virtual machine or a dedicated lab account, understand each command
before executing it, and avoid experimenting with destructive commands
on a production system.

The examples in this lecture mainly target Debian/Ubuntu-based
distributions. Some commands, packages, paths, and outputs may differ on
Fedora, Arch, or other Linux distributions.

