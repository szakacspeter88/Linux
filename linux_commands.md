# Useful Linux Commands

<details> <summary> 📂 <b>ls</b> - list files</summary>
  
# ls - list files
  
```
ls
```
##### list all files with all attributes human readable
  
```
ls -hal
```
#### list file inodes
  
```
ls -i
```
#### colored folders and files

```
ls --color
```

</summary>

<details> <summary>📍 <b>pwd</b> - print work directory</summary>
  
# pwd - print work directory
```
pwd
```
#### value of current working
```
pwd -L
```

#### resolves symbolic links
```
pwd -P
```

</details>

<details> <summary>🚀 <b>cd</b> - change directory</summary>

# cd - change directory
```
cd
```
The cd -P command skips symbolic links and enters a specified special subfolder, following the physical path.
```
cd -P
```
The −L switch (Logical Mode) instructs the shell to follow the default, logical path during directory navigation.
```
cd -L
```

</details>

<details> <summary>🏗️ <b>mkdir</b> - make directory</summary>
  
# mkdir - make directory
#### create library hierarchy (parent)
```
mkdir -p
```

#### notifies the user of each created directory (verbose)
```
mkdir -v
```
#### It allows you to specify the permissions (mode) of the directory at the moment of creation.
```
mkdir -m
```

</details>

<details> <summary>🔄 <b>mv</b> - move / rename</summary>
  
# mv - move / rename
```
mv
```

#### asks to overwrite if the target file already exists (interactive)
```
mv -i
```
#### forces the target file to be overwritten, ignoring the −i option and any permission settings (if possible) (force)
```
mv -f
```
#### prints the names of moved or renamed files to standard output (verbose)
```
mv -v
```
#### only perform the move/rename if the destination file is older than the source file or if the destination file does not exist (update)
```
mv -u
```
#### makes a backup of the target file before overwriting it (backup)
```
mv -b
```

</details>

<details> <summary>📋 <b>cp</b> - copy</summary>

# cp - copy
```
cp
```

#### required when copying directories. Copies the directory and all its subdirectories along with its contents (recursive)
```
cp -r
```

#### asks to overwrite if the target file already exists (interactive)
```
cp -i
```

#### forces the target file to be overwritten if necessary (force)
```
cp -f
```

#### prints the names of the files being copied to standard output (verbose)
```
cp -v
```

#### it preserves all original attributes (owner, timestamps, permissions) and also performs recursive copying. Ideal for backups (archive)
```
cp -a
```

#### only copies if the destination file is older than the source file or if the destination file does not exist (update)
```
cp -u
```

</details>

<details> <summary>🗑️ <b>rm</b> - remove</summary>

# rm - remove
```
rm
```
#### required for deleting directories. Deletes the directory and all its contents, including subdirectories and the files within them (recursive)
```
rm -r
```
#### it asks the user for confirmation before deleting each file/directory.(interactive)
```
rm -i
```
#### deletes without confirmation (does not ask for read-only files either), never use it with −r (−rf) unless you are 100% sure of your intentions!** (force)
```
rm -f
```
#### prints the names of the files that were just deleted to standard output
(verbose)
```
rm -v
```

</details>

<details> <summary>📄 <b>touch</b> - make file / update timestamp</summary>

  
# touch - make file
#### only the access timestamp is modified. The modification timestamp remains untouched (atime)
```
touch -a
```
#### only the modification timestamp is modified. The access timestamp remains intact (mtime)
```
touch -m
```
#### if the specified file does not exist, do not create it, just silently ignore it (no-create)
```
touch -c
```
#### allows you to use a specific time instead of the current time (timestamp)
```
touch -t
```
#### another file uses a timestamp for modification instead of the current time (reference)
```
touch -r
```

</details>

<details> <summary>🔗 <b>ln</b> - hard / soft link</summary>

# ln - hard / soft link
```
ln
```
#### create a symbolic link. This is the most important switch, used to specify that we do not want a hard link (symbolic)
```
ln −s
```	
#### force overwrite: If the link name already exists, overwrite it without confirmation (force)
```
ln −f 
```	
#### ask to overwrite if the link name already exists (interactive)
```
ln −i
```	
#### Részletes kimenet: Kiírja az újonnan létrehozott link nevét (verbose)
```
ln −v
```	

</details>

<details> <summary>🧹 <b>clear</b> - clear terminal</summary>

  </details>

<details> <summary>🐱 <b>cat</b> - concatenate and print files</summary>
  
# clear - clear terminal
```
clear
```
#### the precise purpose of clear−x was to clear the current screen but guarantee that scrolling back to previous output would be preserved, although in modern systems this functionality is already built into the basic clear command
```
clear -x
```

# cat
####
```
cat
```
#### number each output line, starting with non-zero numbers (number)
```
cat −n
```
#### only non-empty lines are numbered, empty lines are skipped (number-nonblank)
```
cat -b
```
#### reduces multiple consecutive blank lines to a single blank line (squeeze-blank)
```
cat -s
```
#### displays the $ character at the end of each line, marking the end of the line (show-ends)
```
cat -E
```
#### displays tab characters as ∧I (care I) (show-tabs)
```
cat -T
```
</details>

<details> <summary>🗣️ <b>echo</b> - display a line of text</summary>

# echo
#### print on terminal
```
echo
```
#### Ne tegyen sortörést: Megakadályozza, hogy a parancs a kiírt szöveg után automatikusan sortörést illesszen be.(no-newline)
```
echo -n
```
#### enables the interpretation of special characters (e.g. newline, tab) that begin with a backslash character. (enable-escapes)
```
echo -e
```

</details>

<details> <summary>📖 <b>less</b> - file pager</summary>

# less
#### the command is an extremely useful tool in Linux/Unix systems that allows you to page through files (or the output of other commands) in a page-by-page, interactive manner in the terminal, without having to load the entire file into memory (like the vi or nano editors do).
```
less
```
#### displays the line numbers of the file in the left margin (line-numbers)
```
less -N
```
#### search without distinction: Searching (in the file, with the / or ? commands) is not case-sensitive. (ignore-case)
```
less -i
```
#### does not wrap excessively long lines into new lines, but hides the end of the line (you can see it by scrolling to the right) (chop-long-lines)
```
less -S
```
#### if the file is shorter than one screen of the terminal, it exits immediately (does not wait for a command) (quit-if-one-screen)
```
less -F
```

</details>

<details> <summary>📚 <b>man</b> - system reference manuals</summary>

## man
#### manual
```
man
```
#### searches for the specified keyword in the manual descriptions. Useful if you don't know the exact name of a command (apropos)
```
man -k
```
#### prints the name of the command and a short, one-line description (if it exists) (whatis)
```
man -f
```
#### displays all manual pages with the specified name (regardless of section) (all)
```
man -a
```
#### prints the exact filesystem path to the manual page instead of opening it.
```
man -w
```
#### allows you to specify which section to search for the command in (sections)
```
man −s
```

</details>

<details> <summary>💻 <b>uname</b> - system information</summary>
  
## uname
#### the uname (unix name) command in Linux/Unix systems is used to display system-related information (such as kernel name, network hostname, kernel version, hardware type, etc.)
```
uname
```
#### prints all available system-specific information (the most commonly used switch is) (all)
```
uname -a
```
#### displays the name of the operating system kernel (e.g. Linux) (kernel name)
```
uname -s
```
#### displays the system's network name (hostname)(nodename)
```
uname -n
```
#### prints the kernel release number (e.g. 6.6.6) (kernel-release) 
```
uname -r
```
#### prints the kernel version (often includes compile time and other data) (kernel-version)
```
uname -v
```
#### lists the hardware architecture (e.g. x86_64) (machine)
```
uname -m
```
#### displays the name of the operating system (usually 'GNU/Linux') (operating-system)
```
uname -o
```

</details>

details> <summary>👤 <b>whoami</b> - display current user</summary>

## whoami
#### the whoami command is one of the simplest and most specific Linux/Unix commands. It does one thing: it displays the effective username of the current user (the logged in user who issued the command)
```
whoami
```

</details>

<details> <summary>📦 <b>tar</b> - tape archiver</summary>

## tar
####
```
tar
```
#### create a new archive (tar file) from the specified files/directories (create)
```
tar -c
```
#### extracting content from an existing archive (extract)
```
tar -x
```
#### lists the contents of the archive without extracting it (list)
```
tar -t
```
#### only add files to the archive that are better than those in the archive (update)
```
tar -u
```

</details>

<details> <summary>🔍 <b>grep</b> - pattern searching</summary>

## grep
#### the grep (Global Regular Expression Print) command is the most important tool for text searching on Linux/Unix systems, the command scans files or standard input (e.g. the output of another command) and prints lines that match a specified pattern (regular expression)
```
grep
```
#### does not distinguish between uppercase and lowercase letters when searching (ignore-case)
```
grep -i
```
#### prints lines that DO NOT match the pattern (invert-match)
```
grep -v
```
#### only print the number of hits, not the rows (count)
```
grep -c
```
#### scans the specified directory and all its subdirectories for files (recursive)
```
grep -r
```
#### csak azoknak a fájloknak a nevét írja ki, amelyek tartalmaznak találatot (files-with-matches)
```
grep -l
```
#### prints the line number before each hit (line-number)
```
grep -n
```
#### only returns a match if the pattern matches a complete word (word-regexp)
```
grep -w
```
#### extended regular expressions: Enables the use of modern, extended regular expressions (e.g. egrep)
```
grep -E
```

</details>

<details> <summary>⬆️ <b>head</b> - output the first part of files</summary>

## head
#### the head command in Linux/Unix systems is used to print the first few lines (by default the first 10 lines) of a file (or standard input), this command is useful for quickly reviewing the contents of files without loading the entire file
```
head
```
#### specifies how many lines to print from the beginning of the file (e.g. −n20 is the first 20 lines) (lines)
```
head -n
```
#### specifies how many bytes to print from the beginning of the file (e.g. −c50 is the first 50 bytes) (bytes)
```
head -c
```
#### when multiple files are specified, print the filename before the output (verbose)
```
head -v
```

</details>

<details> <summary>⬇️ <b>tail</b> - output the last part of files</summary>

## tail
#### the tail command, as the opposite of head, is used in Linux/Unix systems to print the last few lines (10 by default) of files, which is especially useful for viewing log files
```
tail
```
#### specifies how many lines to print from the end of the file (e.g. −n20 for the last 20 lines) (lines)
```
tail -n
```
#### this is the most important switch, which after writing the file, tail does not exit, but remains open and prints every new line (which is written to the end of the file) to the terminal immediately. (follow)
```
tail -f
```
#### specifies how many bytes to print from the end of the file (bytes)
```
tail -c
```

</details>

<details> <summary>⚖️ <b>diff</b> - compare files line by line</summary>
  
## diff
#### the diff command compares the contents of two text files line by line and displays the minimum set of edits (add, delete, modify) that can be used to transform the first file into the second file.
```
diff
```
#### the most popular, concise, readable format with (+ and - signs) (Unified)
```
diff -u  
```
#### shows the differences with 3 lines of context (context)
```
diff -c
```
#### when comparing directories, traverse subdirectories (recursive)
```
diff -r
```
####  szóközök figyelmen kívül hagyása. Mellőzi a szóközök/tabulátorok számának változásait (whitespace)
```
diff -w
```
#### ignores the addition/deletion of blank lines
```
diff -B
```
#### case-insensitive comparison
```
diff -i
```
#### only indicates if there is a difference, but does not print the details (quiet)
```
diff -q
```
#### side-by-side output (side-by-side)
```
diff -y
```

</details>

<details> <summary>🔢 <b>cmp</b> - byte-by-byte comparison</summary>

## cmp
#### the cmp (compare) command compares two files byte by byte and only reports the location and line of the first difference where the contents of the two files differ, or if one file is a prefix of the other
```
cmp
```
#### this is the most commonly used switch in scripts
it does not print any messages, but only indicates the result with the return code:
0: the files are the same.
1: the files are different.
2: an error occurred (e.g. file not found).
(silent)
```
cmp -s
``` 
#### prints all the different bytes and their positions, also shows the decimal value of the different bytes from both files (verbose)
```
cmp -l
```
#### the cmp command with the -n switch compares only the first specified number of bytes from the beginning of the files, while with the --ignore-initial=skip_number switch it skips the specified number of bytes at the beginning of the files and compares only the parts that follow. (byte limit)
```
cmp -n
```

</details>

<details> <summary>📊 <b>comm</b> - compare two sorted files</summary>

## comm
#### The comm command displays the common and different lines between two pre-sorted text files in three columns.
```
comm
```
Switch   Meaning         Hide Column
-1       Hide column     Only rows in file1
-2       Hide column     Only rows in file2
-3       Hide column     Same rows in both files


Column (1): Lines that are only in the first file (file1)
Column (2): Lines that are only in the second file (file2)
Column (3): Lines that are in both files

Practical examples of using switches:

comm   -12 file1 file2: Shows only lines that are the same in both files (hides columns 1 and 2)
comm    -3 file1 file2: Shows only lines that are different in the two files (shows columns 1 and 2)

#(don't really undestand this btw.)

</details>

<details> <summary>🗄️ <b>sort</b> - sort lines of text files</summary>

#### The sort command is a powerful utility used to arrange the lines of a text file in a specific order. By default, it sorts alphabetically, but it offers many options to refine how data is processed.
#### Basic Syntax

#### sort [options] [filename]
#### Most Common Options

```
sort -n
```                             
#### Sorts numbers by their actual value (e.g., 2 comes before 10).
```
sort -r
```
#### Reverses the result (descending order).
```
sort -u
```
#### Removes duplicate lines from the output.
```
sort -k
```
#### Sorts based on a specific column (field).
```
sort -t
```
#### Defines the delimiter between columns (e.g., a comma).
```
sort -M
```
#### Recognizes month names (Jan, Feb, etc.).  
```
sort -o
```
#### Saves the result to a file instead of printing to the screen.

#### Practical Examples
#### 1. Sorting Numbers

#### If you use a plain sort on numbers, "10" will appear before "2" because it starts with "1". The -n flag fixes this:
#### Bash

```
sort -n numbers.txt
```

#### 2. Sorting by a Specific Column

#### If you have a list where the first column is a name and the second is an age, use -k to sort by age (the 2nd column):
#### Bash

```
sort -k 2 data.txt
```

#### 3. Handling CSV Files

#### If your data is separated by commas, use the -t option to define the delimiter:
#### Bash

```
sort -t ',' -k 3 list.csv
```

#### 4. Saving the Result

#### By default, sort only displays the result in the terminal. To save it to a new file, use the -o flag:
#### Bash

```
sort list.txt -o sorted_list.txt
```

#### Using "Pipes" with Sort

#### The sort command is often combined with other commands. For example, to see files in a directory sorted by size (the 5th column in ls -l):
#### Bash

```
ls -l | sort -nk 5
```

</details>

<details> <summary>📤 <b>export</b> - set environment variables</summary>

## export
#### the export command is used to make a shell variable available (export it) to **child processes** (e.g., scripts, programs) launched from the current shell, thus turning it into an environment variable
```
export
```
#### Print all exported variables. Lists all names and values of environment variables that are currently marked for export in the shell, in a format that can be reused as input	(export -p)
```
export -p
```
#### Unmark/Unexport a variable. Removes the export property from the variable, meaning it remains a shell variable but will not be passed to child processes. 
(This is generally done using the unset command for environment variables, but -n removes the export attribute specifically).	export -n MY_VAR
```
export -n
```
#### Export functions. Used to export shell functions (though function export is often disabled by default in modern shells like bash for security reasons)      
```
export -f
```

</details>

<details> <summary>🤐 <b>zip / unzip</b> - file compression</summary>

## zip
#### The zip command is an extremely versatile tool for compressing files and managing archives. 
Below I summarize the most important and commonly used switches (options) that can be used to perform most tasks.
```
zip
```
#### Compresses recursively. This is essential for archiving directories, as it ensures that subfolders and their contents are included in the ZIP file.
```
zip -r
```
#### Exclude files. You can exclude certain file types or patterns from compression. You can specify multiple patterns separated by spaces.
```
zip -x <example>
```
#### Encryption (password protection). When executing the command, it asks for a password to protect the contents of the archive.
```
zip -e
```
#### Maximum compression. Use this if you want the smallest possible file size (but slower). The default is -6.
```
zip -9
```
#### No compression. It just archives the files, but does not compress them. This is the fastest.
```
zip -0
```
#### Update. Adds/updates only files in the archive that are new or have changed from the version within the archive.
```
zip -u
```
#### Delete from archive. Deletes one or more files from inside an existing ZIP file.
```
zip -d <file>
```
#### Move. Creates the archive and then deletes the original source files.
```
zip -m
```
#### Silent mode. Suppresses output, only providing feedback on errors. (Ideal for scripts.)
```
zip -q
```
#### Read a list of files from standard input. This is often used in conjunction with the output of other commands (find, grep).
```
zip -@
```






## unzip
#### The unzip command is a basic tool for extracting (decompressing) the contents of .zip files on Linux/Unix systems.
```
unzip
```
#### Specify the destination directory. The files will be extracted here.
```
unzip -d
```
#### Listing. Shows the contents of the ZIP file without extracting it.
```
unzip -l
```
#### Overwrite. Overwrites existing files without confirmation.
```
unzip -o
```
#### Never Overwrite. Only extract files that do not already exist in the destination directory.
```
unzip -n
```
#### Quiet mode. Suppresses normal output, only showing errors.
```
unzip -q
```
#### Testing. Checks the integrity of the ZIP file to make sure it is not corrupted.
```
unzip -t
```
#### Exclusion. Exclude certain files or patterns from packaging.
```
unzip -x
```
#### Password. Specifies the password for encrypted files (capital P!)
```
unzip -P
```

</details>

<details> <summary>🌐 <b>ssh</b> - secure shell</summary>

## ssh
#### Secure Shell (SSH) is a critical network protocol used for secure data communication between two network devices. In Linux, we can securely connect to remote machines using the ssh command.
```
ssh [felhasználónév]@[kiszolgáló_cím]
```
#### Example: If you want to connect to server.example.com with username chef:
```
ssh chef@szerver.example.com
```
The system will then ask you to enter your password.
#### Specify Option. Allows you to specify a configuration option directly from the command line. Extremely flexible.
```
ssh -o
```
#### Example
```
ssh -o ConnectTimeout=10 user@host
```
#### Disable pseudo-terminal. Useful if you only want to run a single command on the remote machine and don't need an interactive shell.
```
ssh -T
```
#### Example
```
ssh -T user@host "ls -la"
```
#### Send to background. Sends the SSH connection to the background immediately after authentication. Often used in conjunction with port forwarding (-L, -D, -R).
```
ssh -f
```
#### Example
```
ssh -f -N -L 8080:host:80 user@host
```
#### No remote command execution. It only establishes and maintains the connection, typically for tunneling purposes (port forwarding).
```
ssh -N
```
#### Example
```
ssh -N user@host
```
#### Remote Port Forwarding. Forwards a port on a remote machine to a local destination.
```
ssh -R
```
#### Example
```
ssh -R 8080:localhost:80 user@host
```
#### Dynamic Port Forwarding. Creates a SOCKS proxy. It sends all traffic through the local port through an encrypted tunnel to the remote server,
from where it is forwarded to its final destination (commonly used in a VPN-like manner).
```
ssh -D
```
#### Example
```
ssh -D 1080 user@host
```
#### Verbose mode. With one, two or three switches you get more and more diagnostic information. Essential when troubleshooting.
```
ssh -v
```
####
```
ssh -vv
```
####
```
ssh -vvv
```
### Example
```
ssh -vvv user@host
```

</details>

<details> <summary>⚙️ <b>service / ps</b> - process & service management</summary>

## service
#### The service command is a service management tool used in Linux systems. As I mentioned earlier, 
the service command does not have traditional lettered switches (such as -a or -p) like other Linux commands. 
Instead, it expects commands (operations) or service-specific options.
```
service
```
#### start	Starts the specified system service.
```
sudo service [name_of_system_service] start
```
#### stop	Stops the specified system service
```
sudo service [name_of_system_service] stop
```
#### restart Quick stop and start, e.g. after configuration changes.
```
sudo service [name_of_system_service] restart
```
#### status It shows the current status of the service (whether it is running, how long it has been running,
its main process identifier (PID), etc.). This is the most commonly used command.
```
service [name_of_system_service] status
```
#### reload Reloads the service configuration without stopping running processes. (Only works for services that support it.)
```
sudo service [name_of_system_service] reload
```

## ps
#### The ps (process status) command is a basic tool in Linux and other Unix-like operating systems that displays the current status of currently running processes.
The output of the command is a snapshot of the processes on the system.
```
ps
```
#### A (All users): Processes belonging to all users. u (User-oriented format): Detailed, user-friendly format.
x (Process with no controlling tty): Shows processes not connected to the terminal. BSD Style
```
ps aux
```
#### e (Every process): Every process. f (Full-format listing): Full listing, 
including the command with full path and arguments, and the PPID (parent process identifier). Unix Style
```
ps -ef
```
#### Specify a list of columns. Allows you to customize the output, e.g. pid,ppid,cmd,%mem. Unix Style
```
ps -o [columns]
```
#### Sort by one or more fields. The - (minus) sign indicates descending order. GNU Style
```
ps --sort=[field]
```
#### Process tree display. A visual representation of the hierarchy of processes. GNU Style
```
ps --forest
```
#### Show Threads. It also shows individual threads under the main process. 
BSD Style/Unix 
```
ps -H
```
#### Example BSD Style
```
ps -eLf
```
or
```
ps -m
```
#### Example Unix Style
```
ps -fm
```
#### Wide format. Prevents line truncation so the entire command line is visible. Can be used multiple times: ps -ww.
#### Example Unix
```
ps -w
```
or
#### Example GNU Style
```
ps --width N
```
#### Example command
```
ps aux -ww
```
#*** Don't really understand this ps things

</details>

<details> <summary>⚔️ <b>kill / killall</b> - terminate processes</summary>

## kill and killall
#### kill and killall
```
kill
```
#### SIGNAL or -SIGNAL: Specify the signal to send (same as kill).
```
kill -s
```                  
#### Interactive mode. Asks for confirmation before killing each process. (Highly recommended if you are unsure of the target!)
```
kill -i
```
or
```
kill --interactive
```
#### USER: Only stops processes running by the specified user.
```
kill -u
```
or
```
kill --user
```
#### Wait for processes to stop before exiting the command
```
kill -w
```
or
```
kill --wait
```

</details>

<details> <summary>💾 <b>df / mount</b> - storage management</summary>

## df
#### The df (disk free) command on Linux/Unix systems is used to display the free disk space and usage of mounted file systems (partitions, network shares, etc.).
```
df
```
#### Human readable format. Displays sizes in appropriate, easy-to-understand units
(e.g. GB, MB). (The most important switch!)
```
df -h
```
or
```
df --human-readable
```
#### It lists the filesystem type (e.g. ext4, xfs, tmpfs).
Very useful for identifying system partitions
```
df -T
```
or
```
df --print-type
```
#### Displays all file systems, including special (pseudo) file systems with 0 block size (e.g. /proc, /sys)      
```
df -a
```
or
```
df -all
```
#### Instead of disk space, it shows free inodes (index nodes) and utilization. (Important if the disk is full of small files).
```
df -i
```
#### Excludes specified filesystem types from the list (e.g. df -x tmpfs)
```
df -x
```
or
```
df --exclude-type=TÍPUS
```
#### Skips all temporary file systems).
Only displays the specified file system types 
```
df -t
```
or
```
df --type=TÍPUS
```

</details>

<details> <summary>📂 <b>mount</b> - attach a file system</summary>

## mount
#### The basic function of the mount command in Linux/Unix systems is to mount (or attach) a file system on a storage device into the system's file system hierarchy.
In simpler terms: The mount command allows the computer's operating system to access data stored on a given storage medium (e.g., a hard disk partition, a USB flash drive, a CD, a network share).

#### File system type. Specifies the type of file system to mount (e.g. ext4, vfat, ntfs, nfs, cifs).",mount -t ntfs /dev/sdb1 /mnt/pendrive
```
mount -t
```
#### -t TYPE                          
#### Mount options. Allows you to specify multiple options separated by commas.
This is the most important switch, see below. mount -o ro,nodev /dev/sda1 /mnt/backup
```
mount -o
```
#### -o OPTIONS
#### Mount all. Attempts to mount all file systems listed in /etc/fstab and marked with the ""auto"" option.",mount -a
```
mount -a
```
#### Read-Only mode. Same as -o ro. Prevents modification of data on the attached device.",mount -r /dev/sdb1 /mnt/usb -r
```
mount -r
```
#### Read/Write mode. Same as -o rw. This is the default.
```
mount -w
```
#### Mount by label. Instead of the device, you can specify the label of the file system you want to mount. mount -L DATA /mnt/data
```
mount -L
```
#### UUID,Mount by UUID. Instead of the device, you can specify the unique identifier (UUID) of that file system. This is the most reliable method.,mount -U 1234-ABCD /mnt/length                    
```
mount -U
```

</details>

<details> <summary>🔑 <b>chmod / chown</b> - permissions & ownership</summary>
  
## chmod
#### The chmod (change mode) command is used in Linux/Unix operating systems to change the access permissions (rights) of files and directories.
This command is essential for system security and user access control, as it determines who can do what with a given file or directory.

#### Recursive mode: Change permissions on the specified directory and all subdirectories and files within it.
```
chmod -R
```
#### Verbose mode: Lists the name of each modified file and the action performed.                            
```
chmod -v
```
#### Only list files that have actually been changed.                           
```
chmod -c
```
#### It takes the permissions of another file as a sample and sets them on the target file (overriding the specified permissions). 
```                          
chmod --
reference=FILE
```

</details>

<details> <summary>🔑 <b>chown</b> - change file owner and group</summary>

## chown
#### Recursive mode: Change the owner and/or group of the specified directory and all subdirectories and files within it. This is the most important switch. 
```
chwon -R
```                             
#### Verbose mode: Lists the name of each modified file and the action performed.                         
```
chown -v
```                            
#### Only list files that have actually been changed.
```
chown -c
```
#### Only makes the change if the current owner and group of the file match the specified one.

--                          
from=CURRENT_OWNER:
CURRENT_GROUP

#### It takes the owner and group of another file as a sample and sets them on the target file.
--                              
reference=REFERENCE_FILE

</details>

<details> <summary>📡 <b>ipconfig / ip</b> - network config</summary>

## ipconfig
#### Displays basic network configuration information: IPv4 and IPv6 addresses, subnet mask, and default gateway for each adapter.
```
ipconfig
```
#### Detailed Configuration: Displays complete TCP/IP configuration information for all network adapters, including physical (MAC) address, DHCP server, DNS server, and lease times.
```            
ipconfig /all                            
```
#### Release IP Address: Releases the currently assigned IPv4 address from the DHCP server. This temporarily leaves the adapter without an address.
```
ipconfig /release
```
#### IP Address Renewal: Requests a new IP address from the DHCP server.
This is often run after the /release command when troubleshooting network issues.                 
```
/renew
```
#### Flush DNS Cache: Clears and resets the contents of the DNS resolver cache. This is useful if your computer is storing an older (possibly incorrect) IP address for a particular domain name.
```
ipconfig
```
#### Flush DNS Cache: Clears and resets the contents of the DNS resolver cache.
This is useful if your computer is storing an older (possibly incorrect) IP address for a particular domain name.
```
ipconfig /flushdns
```                      
#### Displays the contents of the DNS resolver cache, i.e. the domain names and their associated IP addresses that the computer has previously resolved and stored.
```
ipconfig /displaydns
```                 
#### Forces all DHCP leases to be renewed and re-registers DNS names with the DNS server.
```
ipconfig /registerdns                  
```

</details>

<details> <summary>🌐 <b>traceroute</b> - trace network path</summary>
  
## traceroute                
#### The traceroute (or tracert in Windows) command is used to show the path an IP packet takes from a source machine to a destination machine. It essentially lists each router (hop) in the network path between two points and measures the round trip time. This is an essential tool for troubleshooting network problems and identifying the source of latency.

```
traceroute
```
#### Do not resolve addresses (No name resolution): Prevents the translation of IP addresses into domain names             (reverse DNS lookup).
```        
traceroute -n
```

#### Use ICMP protocol (ICMP mode): Forces traceroute to use ICMP ECHO packets instead of traditional UDP packets          (like ping). Often needed if firewalls in the path block UDP

```
traceroute -I
```
#### Use TCP protocol (TCP mode): TCP uses SYN packets (like most web communication). Useful for testing firewalls on a specific port (e.g. HTTP port 80).
```                               
traceroute -T
```                             
#### Specify port: Only available in UDP and TCP modes (with the -U or -T switches). Specifies the destination port number to use on the target computer (e.g. -p 80).
```
traceroute -p PORT
```
#### Number of Queries: Sets the number of times (N) to send a packet to each hop (default 3).
```
traceroute -q N
```
#### Maximum Hops (Max TTL): Sets the maximum Time To Live (TTL) value, i.e. the maximum number of routers before reaching the destination (30 by default).
```
traceroute -m MAX_TTL
```

</details>

<details> <summary>📥 <b>wget</b> - non-interactive network downloader</summary>

## wget
#### This is its most important feature. wget can run in the background and continue downloading even if the user logs out of the system (for example, via SSH). This makes it ideal for starting large files or long-running recursive downloads in a server environment.
```
wget
```
#### Do not overwrite: Prevents wget from overwriting an existing file with the same name. If the file exists, it will skip the download.    
```
wget --no-clobber
```
or
```
wget -nc
```
#### Resume: Resumes an interrupted download. Very useful for large files if the connection is lost.
```
wget --continue
```
or
```
wget -c
```
#### Speed ​​Limit: Limits the download speed to the specified value (e.g. 200k for 200 kilobytes per second).
```
wget --limit-rate=RATE
```
or
```
wget -r RATE
```            
#### Number of retries: Sets the number of times to retry the download if an error occurs (20 by default).
```
wget --tries=NUMBER
```
or
```
wget -t NUMBER
```
#### Run in background: Starts the download in the background. The output is written to a file named wget-log.
```
wget --background
```
or
```
wget -b
```
#### Download from file: Downloads URLs listed in a text file (FILE) line by line.
```
wget --input-file=FILE
```
or
```
wget -i FILE
```
#### Log to file: Writes all messages (errors, status) to the specified file instead of the console.
```
wget --output-file=FILE
```
or
```
wget -o FILE
```
#### Recursive download: Downloads all links on the page (depending on depth). Ideal for mirroring websites.
```
wget --recursive
```
or
```
wget -r
```
#### Recursion depth: Sets the maximum depth for recursive downloads (e.g. -l 2). -l inf means unlimited depth.
```
wget --level=DEPTH
```
or
```
wget -l DEPTH
```
#### Skip parent directories: When recursively downloading, links that point outside the starting directory are not followed.
```
wget --no-parent
```
or
```
wget -np
```
#### Web Page Mirroring: A speedup command for wget -r -l inf --no-clobber --no-host-directories. Perfect for copying entire web pages.
```
wget --mirror
```
or
```
wget -m
```
#### Set User Agent: Sends the specified User Agent (STRING) information to the server. Sometimes it is necessary for the server to restrict the default settings of wget.
```
wget --user-agent=STRING
```
or
```
wget -U STRING 
```       
#### It places the downloaded files in the specified directory.
```
wget --directory-prefix=DIR
```
or
```
wget -P DIR        
```
</details>

<details> <summary>🔥🧱 <b>ufw & iptables</b> - firewall management</summary>
                 
## ufw
#### Displays the current status of the firewall (active or inactive) and all valid rules.
```
sudo ufw status
```
#### Shows detailed status, including default inbound and outbound policies.
```
sudo ufw status verbose
```
#### Turns on the firewall. Warning! This command immediately takes effect for all configured rules.
```
sudo ufw                              
enable
```
####  If SSH access is not configured to be allowed, you can lock yourself out of the system. Turns off the firewall.
```
sudo ufw disable
```
#### Resets the firewall to default settings and deletes all rules.
```                         
sudo ufw reset                        
```

## iptables
#### iptables is a command-line tool in Linux operating systems used to configure a firewall and network packet filtering framework based on a kernel module called netfilter.
#### Append: Adds a rule to the end of the specified chain.
```
iptables -A
```
or
```
iptables --append
```
#### Insert: Inserts a rule at the beginning of the specified chain (or before the specified sequence number).
```
iptables -I
```
or
```
iptables --insert
```
#### Delete: Deletes a rule (with the exact rule description or number).                  
```
iptables -D	
```
or
```
iptables --delete
```
#### Listing: Lists the rules in the specified chain/table.
```
iptables -L
```
or
```
iptables --list
```
#### Delete All: Removes all rules from the specified chain/table.         
```
iptables -F
```
or
```
iptables --flush
```
#### Default Policy: Sets the default behavior of the chain (e.g. DROP, ACCEPT).
```
iptables -P
```
or
```
iptables --policy
```
#### Table selection: Specifies which table to work on (if omitted, filter is the default).
```      
iptables -t
```
or
```
iptables --table
```	                          
<details>
  
Here is the English version of the accordion, using the professional and emoji-enhanced definitions we discussed. I have polished the text to be concise and impactful.
Markdown

<details>
<summary>📦 <b>Linux Package Managers (APT, Pacman, DNF, Zypper)</b></summary>

### 🚀 APT (**A**dvanced **P**ackage **T**ool)
* **Distros:** Debian, Ubuntu, Linux Mint, Kali.
* **Key Feature:** The most widely used manager, known for human-readable commands.

---

### ᗧ Pacman (**PAC**kage **MAN**ager)
* **Distros:** Arch Linux, Manjaro, EndeavourOS.
* **Key Feature:** Lightning-fast and uses concise flags (e.g., `-Syu`). Features the "ILoveCandy" easter egg.

---

### 🍩 DNF / YUM (**D**andified **Y**UM)
* **Distros:** Fedora, RHEL, CentOS, AlmaLinux.
* **Key Feature:** The "Dandified" successor to YUM with an intelligent dependency solver.

---

### 🤐 Zypper (The Zipper)
* **Distros:** openSUSE, SUSE Linux Enterprise.
* **Key Feature:** Known for its powerful SAT-solver and high-quality error reporting.

</details>

## apt, pacman, yum, rpm

#### Apt is the standard and modern package management system for Debian, Ubuntu, Linux Mint, and other Debian-based distributions. Apt itself handles the low-level tools (mainly dpkg) that work in the background, but provides a much more user-friendly, intelligent interface.

#### yum is the traditional package manager for older Red Hat-based distributions (RHEL, CentOS, Fedora). In modern systems, yum has gradually been replaced by dnf (Dandified YUM), but the syntax of the commands remains very similar.

#### Pacman is the default package manager for Arch Linux and Arch-based distributions (e.g. Manjaro). It is known for its speed and simple command syntax.

#### rpm is a low-level package management system used by Red Hat-based distributions (e.g. Fedora, RHEL, CentOS). While yum and dnf are built on top of rpm and manage dependencies, the rpm command is used to directly manage individual files with the .rpm extension.

</details>

<details> <summary>🦸‍♂️👤🏗️ <b>sudo</b> - execute as superuser</summary>

## sudo 

#### sudo (SuperUser DO) is a key command in Linux and Unix-like operating systems. Its purpose is to allow an authorized user to temporarily execute commands with the privileges of the root (administrator) user.
#### 1. The Role of the System Administrator (Root)
#### In Linux/Unix systems, root is the highest-privileged user. Root can do anything on the system: install software, modify system files, and even crash the system.
#### 2. The Security Problem
#### Most users do not log in directly as root for everyday work because:
#### Security: If a program is run as root and is malicious or buggy, it can cause unlimited damage to the system.
#### Avoidable errors: It is more difficult to make an accidental error (e.g. deleting an important system file) if the user is working with limited privileges.
#### 3. The sudo Solution
#### Sudo overcomes this problem:
#### Temporary elevation: Allows users to gain root privileges only for the command preceded by sudo, if necessary
#### Auditability: The use of sudo is logged, so it is known exactly which user ran an administrative command and when
#### Authentication: To use sudo, the user must enter their own password, not the root password (this depends on a configuration setting, but usually works this way)
#### Example: The apt update command only updates the package list, but the apt install command modifies system files, so it must be preceded by sudo

</details>

<details> <summary>📅 <b>cal</b> - terminal calendar</summary>

## cal
#### The cal command is used in Linux/Unix systems to display the calendar on the command line.
#### This is a very simple but useful utility that allows you to quickly view the calendar for the current month, 
#### a specific month, or even an entire year, right in the terminal.
```
cal
```
Switch                Description                                                                                      Example
-3                    Displays the previous, current, and next month together                                          cal -3
-A N                  Displays the current month and the following N months (After)                                    cal -A 2
-B N                  Displays the current month and the N months before it (Before)                                   cal -B 1
-y                    Displays the calendar for the current year (same as cal without the YEAR parameter).             cal -y
-j                    Displays the year/month in Julian Calendar format, i.e. the days                                 cal -j
                      number from 1 to 365 (or 366).
                                                                                                                       
</details>

<details> <summary>🏷️ <b>alias</b> - create command shortcuts</summary>

## alias
#### The command is all about efficiency and convenience. It is used to replace frequently used, long, or difficult-to-type commands, reducing the chance of typing errors and speeding up the workflow.
#### Example
```
alias név='parancs [kapcsolók és argumentumok]'
```
or
#### Create an alias to update the entire system
```
alias updateall='sudo apt update && sudo apt upgrade -y'
```
#### Example
```
 alias ls='ls --color=auto'
```
or
```
# alias ll='ls -l'
```

</details>

<details> <summary>⚠️ <b>dd</b> - disk destroyer / convert and copy</summary>

## dd
#### The dd command is an extremely powerful and versatile utility in Linux/Unix systems, primarily used for bit-accurate copying and converting of files, partitions, or entire media.
The command's name originally stood for "Copy and Convert", which is derived from an early operating system (JCL) term, rather than the terms "disk dump" or "disk duplicate", although its function is related to these.
```
dd
```
#### The essence and dangers of the dd command
#### 1. Raw Data Transfer (Bit-precise Copy)
#### dd copies a raw data stream from the source (Input File, if=) to the destination (Output File, of=). This means that it does not care about the file system structure (unlike the cp command). This makes it suitable for:
#### Cloning entire disks: You can simply copy the entire contents of one hard drive to another, sector by sector.
#### Creating bootable USB drives: Often used to burn ISO disk images to a USB drive.
#### Creating backups: You can create a backup of an entire partition to a file.
#### 2. Conversion
#### The command can also convert (transform) data during copying. For example:
#### From ASCII to EBCDIC or vice versa (old).
#### Converting from lowercase to uppercase.
#### Jump from the beginning of the file to the specified number of bytes (skipping the header).
#### Dangers of the DD Command
#### dd is often called the "disk destroyer". Because it directly manipulates physical devices and does not ask for confirmation, a simple typo in the of= (Output File) parameter can be fatal:
#### For example: If you mistype the target partition and type of=/dev/sdb instead of of=/dev/sda, you could overwrite your entire main system drive.
#### Key dd switches (parameters)
#### The dd command does not use the traditional -k or --switch format, but key-value pairs.
#### Parameter              FullName                       Description
#### if=FILE,               Input File                     The input source (file, device, partition).
#### of=FILE                Output File                    The output destination (file, device, partition).
#### bs=BYTES               Block Size                     Sets the input and output block sizes (e.g. 1M is 1 
####                                                       megabyte). Important for speed.
#### count=N                                               Copies only N blocks (of the block size specified by bs).

#### skip=N                                                Skip the first N input blocks.
#### seek=N                                                Skip the first N output blocks 
####                                                       (from the beginning of the target file).
#### conv=CONV              Convert                        Special conversion options (e.g. notrunc, sync).
#### Common Usage Example
#### To make an Ubuntu ISO image bootable on a USB drive:
```
sudo dd if=/home/felhasznalo/ubuntu.iso of=/dev/sdX bs=4M status=progress
```
#### (Where sdX is the target USB drive, not its partition!) 
#### Would you like to review some more basic filesystem commands, like chmod or chown?

</details>

<details> <summary>📍 <b>whereis</b> - locate the binary, source, and manual-page files</summary>

## wheris
#### Switch                                             Meaning (Target)                                                   Description
#### -b                                                 Binary Files                                                       Searches only executable (binary) files.
#### -m                                                 Manual Pages (man)                                                 Searches only manual (man) pages.
#### -s                                                 Source Files                                                       Searches only source code files.
#### -u                                                 Unusual Entries                                                    Searches for commands that are missing an entry of the specified type
####                                                                                                                       (e.g. -m for only man pages).
####                                                                                                                       For example: whereis -m -u * shows the
####                                                                                                                       files in the current directory that do not have a man page."
#### -B                                                                                                                    Binary search path Specifies or limits the directories
####                                                                                                                       where to search for binary files.
####                                                                                                                       This switch must be followed by the -f switch.
#### -M                                                 Man page search path                                               Specifies or limits the directories
####                                                                                                                       where to search for manual pages.
####                                                                                                                       This switch must be followed by the -f switch.
#### -S                                                 Source search path                                                 Specifies or limits the directories
####                                                                                                                       where to search for source files.
####                                                                                                                       This switch must be followed by the -f switch.
#### -f                                                 Start of filename flag                                             Terminates the directory list specified with the -B, -M, or -S switches
####                                                                                                                       and indicates that the arguments that follow
####                                                                                                                       are already filenames to be searched.

</details>

<details> <summary>🏷️ <b>whatis</b> - display one-line manual page descriptions</summary>

## whatis
#### The whatis command in the Linux operating system is used to display a short, one-line description of a given command or program. This description is taken from the database of manual (man) pages. Essentially, it queries the database used by the man command and returns only the name of the command and a short description (the contents of the NAME section of the man page), without opening the full manual page.

#### Switch                          Meaning (Purpose)                             Description
#### -w                              Wildcard (replacer characters)                Allows you to use wildcard characters
####                                                                               (*, ?) for searching. This switch allows you to search
####                                                                               for example, any command that starts with the word ""mount"".
#### -r                              Regular expressions                           It treats the search pattern as a regular
####                                                                               expression.
#### -l                              Skip localization                             By default, whatis also tries to find man pages
####                                                                               written in the local language. This switch 
####                                                                               disables this behavior.
#### **-s                            Restricting sections                          Only in the specified man-page sections (e.g. 1, 8, 3)
#### list                                                                          The sections of the man pages represent different categories                                                                    
####                                                                               (1=general commands, 8=system 
####                                                                               administration commands, etc.)

</details>

<details> <summary>📊 <b>top</b> - display Linux processes (Real-time)</summary>

## top
#### The top command is one of the most important tools in the Linux operating system, which displays the current status of the system in real time, interactively.

#### Switch                                Meaning                                       Description
#### -d sec                                Delay (Refresh time)                          Specifies the screen refresh interval in seconds. 
####                                                                                     (Default: 3.0 seconds). E.g.: top -d 1
#### -p PID                                PID monitoring                                Only those marked by the specified process identifier(s) (PID) 
####                                                                                     monitors processes. Eg: top -p 1234
#### -u user                               User filtering                                It only displays processes belonging to that user.
####                                                                                     Ex.: top -u chef
#### -n num                                Number of iterations                          Specifies how many times to refresh the screen before exiting.
####                                                                                     E.g.: top -n 1 (displays only once, then exits)
#### -H                                    Show threads                                  Displays individual threads instead of processes.
####                                                                                     (Important for more detailed analysis).
#### -b                                    Batch mode                                    Non-interactive, batch mode. This mode is ideal
####                                                                                     for redirecting top output to a file
####                                                                                     or for use in scripts.

</details>

<details> <summary>👤 <b>useradd</b> - create a new user</summary>

## useradd
#### The useradd (also known as adduser in some distributions) command in the Linux operating system is used to create a new user account. This command performs all the basic configuration steps required to add a user: it adds the user to the system, creates an encrypted entry for the user's password (although setting the password requires a separate command, see below), creates the user's home directory, and sets the default shell.
#### Switch                          Full name                               Description
#### -m                              --create-home                           Creates the user's home directory. This is the most commonly used switch,
####                                                                         as most cases require a home directory. (This is the default behavior on some distributions.)
#### -d dir                          --home dir                              Specifies the path to the user's home directory instead of the usual /home/username.
#### -g group                        --gid group                             Specifies the user's primary group. (by group name or GID).
####                                                                         This group will be the user's default group.
#### -G groups                       --groups groups                         Specifies the secondary groups (separated by commas) to which the user will belong.
#### -s shell                        --shell shell                           Specifies the user's default shell (e.g. /bin/bash, /bin/zsh,
####                                                                         or /sbin/nologin for accounts used only for services).
#### -u uid                          --uid uid                               Specifies the user's unique identifier (UID).
####                                                                         Usually assigned automatically by the system, 
####                                                                         but sometimes it must be set manually
####                                                                         (e.g. for network shares).
#### -c comment                      --comment comment                       Adds a comment (such as the user's full name or description) to the account,
####                                                                         which appears in the /etc/passwd file.
#### -e date                         --expiredate date                       Specifies when the user account expires (in yyyy-mm-dd format).
#### -f days                         --inactive days                         Specifies the number of days of inactivity after password expiration
####                                                                         before the account is permanently disabled.
#### -N                              --no-user-group                         Prevents the command from creating a group with the same name
####                                                                         as the user's primary group.

</details>

<details> <summary>🔑 <b>passwd</b> - change user password</summary>

## passwd
#### The passwd command is the basic tool for changing passwords for user accounts in the Linux operating system. The command manages the entry of a user's encrypted password in the /etc/shadow file, and also allows administrators to set or change passwords for other users, and to manage password policies (such as expiration dates)
#### Switch                            Full name                     Eligibility                     Description
#### -l,                               --lock                        root                            Disables (locks) the user's password. This prevents
####                                                                                                 the user from logging in with their password.
####                                                                                                 The password is preceded by a ! in the /etc/shadow file.
#### -u                                --unlock                      root                            Unlocks (enables) a locked password. Restores the 
####                                                                                                 password entry to its previous state.
#### -d                                --delete                      root                            Deletes the user's password. The user can log in without a password 
####                                                                                                 (not recommended, only in special cases).
#### -e                                --expire                      root                            It will immediately expire the user's password.
####                                                                                                 The user will be required to enter a new password the next time they log in.
#### -x days                           --maximum days                root                            Sets the maximum number of days that a password can be used
####                                                                                                 (validity before expiration). If 0, no expiration.
#### -n days                           --minimum days                root                            Sets the minimum number of days until the password can be changed again.
#### -i days                           --inactive days               root                            Sets the number of days of activity after the password expires. 
####                                                                                                 If this expires, the account will be permanently disabled.
#### -S                                --status                      anyone                          Displays the status of the user's password (last modified, minimum/maximum validity times, inactivity).

</details>

<details> <summary>🔎 <b>find</b> - search for files in a directory hierarchy</summary>

# find
#### Here is the concise explanation of the find command translated into English:

The find command is one of the most powerful search tools in Linux (Arch, Kali, Ubuntu, etc.), used to locate files and directories based on various conditions.

Here is the essence, briefly:
1. The Basic Formula

find [where] [what] [action]

  [where]: The starting directory (e.g., . for the current location, / for the entire system).

  [what]: The search criteria (name, size, type, date).

  [action]: What to do with the result (list it, delete it, or pass it to another command).

2. Most Important Switches (with examples)

    By Name: find . -name "config.txt" (Search for an exact name). find . -iname "*.jpg" (Search by extension, case-insensitive).

    By Type: find . -type f (Files only). find . -type d (Directories only).

    By Size: find . -size +100M (Files larger than 100 MB).

    By Time: find . -mtime -1 (Files modified within the last 24 hours).

    By Permissions: find . -perm 777 (Search for files readable/writable by everyone – a security risk!).

3. Why is it better than Windows search?

The find command doesn't just search; it can act immediately using the -exec switch.

Example: Find all .tmp files and delete them instantly: find /tmp -name "*.tmp" -delete


Here is the command that finds the 10 largest files on your system:

```sudo find / -type f -exec du -h {} + 2>/dev/null | sort -rh | head -n 10```

</details>

# find
  
  -type : fájltípus
   d : directory
   f : file
   l : symbolic link
   c : character device
    
  Example: 
     /dev/tty  : Terminal
     /dev/null : Null Device
     /dev/random : Cryptographic Random Numbers
     /dev/zero : Continuous stream of zeros
     
  find /dev -type c -name 'tty*'
     
   b : block device
   
  find /dev -type b -name 'sd*'

  -name : case sensitive
  -iname : not case sensitive

  -size : file size 
   Example: 
    find . -type f -size +10M : Finds all files that are greater than 10M
      
    find . -type f -size -2G : Less than 2 Gigabytes

  -mtime : Modification Time
   Example:
    find . -mtime +7 : Modified more than 7 days ago
    find . -mtime -2 : Modified less than 2 days ago
    
  -print : Prints full path of the matched files 
  
  -exec : Executes a shell command
  
  

  Fájl keresése:
  find . -iname "filename"
  
  Fájl keresése ( töredék névvel ):
  find . -iname "*name"

  Fájl keresése ( csak az adott mappában, almappákban nem ):
  find . -maxdepth 1 -iname '*name'

  Mappa keresése:
  find . -type d -iname '*string*'

  # Szent Házi feladat
  
  1. Feladat
    Azok a commandok amik fel lettek téve a gitHUBra,
    Fontosabb kapcsolóit kijegyzetelni

Kész

  3. Feladat
    Máté ad konkrét fileokat amikre rá kell keresni a find paranccsal

Még nem kaoptam fileneveket

  5. Feladat
    Második oszlopot átnézni a TOP 50 linux parancsból, és kijegyzetelni a fontosabb kapcsolókat

Kész

  1 hét Deadline
  
  ## Sort parancs kimaradt comm és export között
