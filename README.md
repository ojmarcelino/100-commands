# Essential Linux Commands

## 1. File Operations

- ls: Lists all ﬁles and directories in the present working directory
- ls -R: Lists ﬁles in sub-directories as well
- ls -a: Shows hidden ﬁles
- ls -al: Lists ﬁles and directories with detailed information
- exa: really, use it instead of ls.
- cd directoryname: Changes the directory
- cd ..: Moves one level up
- pwd: Displays the present working directory
- cat > filename: Creates a new ﬁle
- cat filename: Displays the ﬁle content
- cat file1 file2 > file3: Joins two ﬁles and stores the output in a new ﬁle
- touch filename: Creates or modify a ﬁle
- rm filename: Deletes a ﬁle
- cp source destination: Copies ﬁles from the source to the destination path
- mv source destination: Moves ﬁles from the source to the destination path
- find / -name filename: Finds a ﬁle or directory by its name starting from /
- file filename: Determines the ﬁle type
- less filename: Views the ﬁle content page by page
- head filename: Views the first ten lines of a ﬁle
- tail filename: Views the last ten lines of a ﬁle
- lsof: Shows which ﬁles are opened by which process.
- du -h --max-depth=1: Shows the size of each directory. Use
    --max-depth=1 to limit the output to the current directory and its
    immediate children.
- fdisk: Disk partition manipulation command.

## 2. Directory Operations

- mkdir directoryname: Creates a new directory in the present
    working directory
- rmdir directoryname: Deletes a directory
- cp -r source destination: Copies directories recursively
- mv old_dir new_dir: Renames directories
- find / -type d -name directoryname: Finds a directory starting from
    root

## 3. Process Operations

- ps: Displays your currently active processes
- top: Displays all running processes
- kill pid: Kills the process with given pid
- pkill name: Kills the process with the given name
- bg: Resumes suspended jobs without bringing them to foreground
- fg: Brings the most recent job to foreground
- fg n: Brings job n to the foreground
- renice +n [pid]: Change the priority of a running process.
- &>filename: Redirects both the stdout and the stderr to the ﬁle filename.
- 1>filename: Redirect the stdout to ﬁle filename.
- 2>filename: Redirect stderr to ﬁle filename.

## 4. File Permissions

- chmod octal filename: Change the permissions of ﬁle to octal,
    which can be between 0 (no permissions) to 7 (full permissions)
- chown owner_name filename: Change ﬁle owner
- chgrp group_name filename: Change group owner

## 5. Networking

- ping host: Ping a host and outputs results
- whois domain: Get whois information for domain
- dig domain: Get DNS information for domain
- netstat -pnltu: Display various network related information such
    as network connections, routing tables, interface statistics etc.
- ifconfig: Displays IP addresses of all network interfaces
- ssh user@host: Remote login into the host as user
- scp: Transfers ﬁles between hosts over ssh
- wget url: Download ﬁles from the web
- curl url: Sends a request to a URL and returns the response

- traceroute domain: Prints the route that a packet takes to reach
    the domain.

- mtr domain: mtr combines the functionality of the traceroute and
    ping programs in a single network diagnostic tool.

- ss: Another utility to investigate sockets. It's a more modern
    alternative to netstat.

- nmap: Network exploration tool and security scanner.

## 6. Archives and Compression

- tar cf file.tar files: Create a tar named ﬁle.tar containing ﬁles
- tar xf file.tar: Extract the ﬁles from ﬁle.tar
- gzip file: Compresses ﬁle and renames it to ﬁle.gz
- gzip -d file.gz: Decompresses ﬁle.gz back to ﬁle
- zip -r file.zip files: Create a zip archive named ﬁle.zip
- unzip file.zip: Extract the contents of a zip ﬁle

## 7. Text Processing

- grep pattern files: Search for pattern in ﬁles
- grep -r pattern dir: Search recursively for pattern in dir

- command | grep pattern: Pipe the output of command to grep for
    searching
- echo 'text': Prints text
- sed 's/string1/string2/g' filename: Replaces string1 with string2
    in filename
- diff file1 file2: Compares two ﬁles and shows the differences
- wc filename: Count lines, words, and characters in a ﬁle

- awk: A versatile programming language for working on ﬁles.

- sed -i 's/string1/string2/g' filename: Replace string1 with string2
    in filename. The -i option edits the ﬁle in-place.

- cut -d':' -f1 /etc/passwd: Cut out the first field of each line in
    /etc/passwd, using colon as a field delimiter.

## 8. Disk Usage

- df: Shows disk usage
- du: Shows directory space usage
- free: Show memory and swap usage
- whereis app: Show possible locations of app
- which app: Show exactly "which" app is

## 9. System Info

- date: Show the current date and time
- cal: Show this month's calendar
- uptime: Show current uptime
- w: Display who is online
- whoami: Who you are logged in as
- uname -a: Show kernel information
- df -h: Disk usage in human readable format
- du -sh: Disk usage of current directory in human readable format
- free -m: Show free and used memory in MB

## 10. Package Installations

### Ubuntu

- sudo apt-get update: Updates package lists for upgrades
- sudo apt-get upgrade: Upgrades all upgradable packages
- sudo apt-get install pkg_name: Install pkg_name
- sudo apt-get remove pkg_name: Removes pkg_name

### Arch

- sudo pacman: Updates package lists for upgrades
- sudo pacman -Syu: Upgrades all upgradable packages
- sudo pacman -S pkg_name: Install pkg_name
- sudo pacman -R pkg_name: Removes pkg_name
- paru: Updates package lists for upgrades
- paru -Syu: Upgrades all upgradable packages
- paru -S pkg_name: Install pkg_name
- paru -R pkg_name: Removes pkg_name

## 11. Others (mostly used in scripts)

- command1 ; command2: Run command1 and then command2
- command1 && command2: Run command2 if command1 is successful
- command1 || command2: Run command2 if command1 is not successful
- command &: Run command in background

## 12. Version Control (Git commands)

- git init: Initialize a local git repository
- git clone url: Create a local copy of a remote repository
- git add filename: Add a ﬁle to the staging area
- git commit -m "Commit message": Commit changes with a message
- git status: Check the status of the working directory
- git pull: Pull latest changes from the remote repository
- git push: Push changes to the remote repository
- git branch: List all local branches
- git branch branch_name: Create a new branch
- git checkout branch_name: Switch to a branch
- git merge branch_name: Merge a branch into the active branch
- git stash: Stash changes in a dirty working directory
- git stash apply: Apply changes from a stash
- git log: View commit history
- git reset: Reset your HEAD pointer to a previous commit
- git rm filename: Remove a ﬁle from version control

- git rebase: Reapply commits on top of another base tip.

- git revert: Create a new commit that undoes all of the changes
    made in a particular commit, then apply it to the current branch.

- git cherry-pick commitID: Apply the changes introduced by some
    existing commits.

## 13. Environment Variables

- env: Display all environment variables
- echo $VARIABLE: Display the value of an environment variable
- export VARIABLE=value: Set the value of an environment variable

- alias new_command='old_command options': Create a new command that
    executes the old command with the specified options.

- echo $PATH: Print the PATH environment variable.

- export PATH=$PATH:/new/path: Add /new/path to the PATH.

## 14. Job Scheduling (Cron Jobs)

- crontab -l: List all your cron jobs
- crontab -e: Edit your cron jobs
- crontab -r: Remove all your cron jobs
- crontab -v: Display the last time you edited your cron jobs
- crontab file: Install a cron job from a ﬁle
- @reboot command: Schedule a job to run at startup

## 15. Package Installations (using pip, a Python package installer)

- pip install package_name: Install a Python package.
- pip uninstall package_name: Uninstall a Python package.
- pip freeze > requirements.txt: Freeze installed packages into a text ﬁle.
- pip install -r requirements.txt: Install packages from ﬁle.

## 16. Shell Scripting

- #!/bin/bash: Shebang line to specify the script interpreter.
- $0, $1, ..., $9, ${10}, ${11}: Script arguments.
- if [condition]; then ... fi: if statement in bash scripts.
- for i in {1..10}; do ... done: for loop in bash scripts.
- while [condition]; do ... done: while loop in bash scripts.
- function name() {...}: Define a function.

## 17. System Monitoring and Performance

- iostat: Reports Central Processing Unit (CPU) statistics and
    input/output statistics for devices, partitions, and network ﬁlesystems.
- vmstat: Reports information about processes, memory, paging, block
    IO, traps, disks, and CPU activity.
- htop: An interactive process viewer for Unix systems. It's a more
    user-friendly alternative to top.

## 19. Search and Find

- locate filename: Find a ﬁle by its name.
- updatedb: Update the db for locate (duh, really?)
- fd: a rust implementation to find, way more fast and simple to use.
- whereis program_name: Locate the binary, source, and manual page ﬁles.
- which command_name: Shows the full path of (shell) commands.

## 20. Compression / Archives

- tar -cvf archive.tar dirname/: Create a tar archive.
- tar -xvf archive.tar: Extract a tar archive.
- tar -jcvf archive.tar.bz2 dirname/: Create a compressed bz2 archive.
- tar -jxvf archive.tar.bz2: Extract a bz2 archive.

## 21. Disk Usage

- dd if=/dev/zero of=/tmp/output.img bs=8k count=256k: Create a ﬁle
    of a certain size for testing disk speed.
- hdparm -Tt /dev/sda: Measure the read speed of your hard drive.

## 22. Others

- yes > /dev/null &: Use this command to push a system to its limit.
- `:(){ :|:& };:`: A fork bomb – handle with care. Do not run this
    command on a production system.
- man command: A helpful manual pages reader for any command.
- tldr command: A more helpful alternative to "man". Really, use it, worth.
