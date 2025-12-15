# Useful Linux Commands



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

# man
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
# uname
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
# whoami
#### the whoami command is one of the simplest and most specific Linux/Unix commands. It does one thing: it displays the effective username of the current user (the logged in user who issued the command)
```
whoami
```

# tar
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
# grep
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

# head
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

# tail
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
## diff
#### the diff command compares the contents of two text files line by line and displays the minimum set of edits (add, delete, modify) that can be used to transform the first file into the second file.
```
diff
```
#### the most popular, concise, readable format with (+ and - signs) (Unified)
```
diff -u:  
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
#### kill and killall
####
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

#### chown
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
from=JELENLEGI_TULAJ:
JELENLEGI_CSOP

#### It takes the owner and group of another file as a sample and sets them on the target file.
--                              
reference=REFERENCIA_FÁJL

#### ipconfig
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

#### traceroute                
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
#### Use TCP protocol (TCP mode): TCP uses SYN packets (like most web communication). Useful for testing firewalls on      a specific port (e.g. HTTP port 80).
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

#### wget
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
#### ufw
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
#### iptables
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
#### apt, pacman, yum, rpm

#### Az apt a Debian, Ubuntu, Linux Mint és más Debian alapú disztribúciók szabványos és modern csomagkezelő rendszere. Maga az apt a háttérben dolgozó alacsony szintű eszközöket (főként a dpkg-t) kezeli, de sokkal felhasználóbarátabb, intelligensebb felületet biztosít.

#### A yum a régebbi Red Hat alapú disztribúciók (RHEL, CentOS, Fedora) hagyományos csomagkezelője. A modern rendszerekben a yum-ot fokozatosan felváltotta a dnf (Dandified YUM), de a parancsok szintaxisa nagyon hasonló maradt.

#### A pacman az Arch Linux és az Arch alapú disztribúciók (pl. Manjaro) alapvető csomagkezelője. A gyorsaságáról és az egyszerű parancsszintaxisáról ismert.

#### Az rpm egy alacsony szintű csomagkezelő rendszer, amelyet a Red Hat alapú disztribúciók használnak (pl. Fedora, RHEL, CentOS). Míg a yum és a dnf az rpm fölé épül, és kezeli a függőségeket, az rpm parancs közvetlenül az egyes .rpm kiterjesztésű fájlok kezelésére szolgál.

#### sudo 

A sudo (SuperUser DO) egy kulcsfontosságú parancs a Linux és Unix-szerű operációs rendszerekben. A célja, hogy egy engedélyezett felhasználó ideiglenesen a root (rendszergazda) felhasználó jogosultságaival hajthasson végre parancsokat.

1. A Rendszergazda Szerepköre (Root)

A Linux/Unix rendszerekben a root a legmagasabb jogosultságú felhasználó. A root mindent megtehet a rendszeren: telepíthet szoftvert, módosíthat rendszerfájlokat, és akár tönkre is teheti a rendszert.

2. A Biztonsági Probléma

A legtöbb felhasználó nem jelentkezik be közvetlenül root-ként a mindennapi munkához, mert:

Biztonság: Ha egy programot root-ként futtatnak, és az rosszindulatú vagy hibás, akkor korlátlan károkat okozhat a rendszerben.

Elkerülhető hibák: Nehezebb véletlen hibát (pl. fontos rendszerfájl törlése) elkövetni, ha korlátozott jogosultsággal dolgozik a felhasználó.

3. A sudo Megoldása

A sudo hidalja át ezt a problémát:
Ideiglenes emelés: Lehetővé teszi a felhasználók számára, hogy szükség esetén csak arra a parancsra kapjanak root jogosultságot, amely előtt a sudo parancsot elhelyezik
Auditálhatóság: A sudo használatát a rendszer naplózza, így pontosan tudható, melyik felhasználó és mikor futtatott rendszergazdai parancsot
Hitelesítés: A sudo használatához a felhasználónak be kell írnia a saját jelszavát, nem a root jelszavát (ez egy konfigurációs beállítástól függ, de általában így működik)
Példa: A apt update parancs csak a csomaglistát frissíti, de a apt install parancs a rendszerfájlokat módosítja, ezért elé kell írni a sudo-t

#### cal
#### The cal command is used in Linux/Unix systems to display the calendar on the command line.
This is a very simple but useful utility that allows you to quickly view the calendar for the current month, 
a specific month, or even an entire year, right in the terminal.
```
cal
```
Kapcsoló,             Leírás,                                                                                          Példa
-3,                   Megjeleníti az előző, az aktuális és a következő hónapot együtt.,                                cal -3
-A N                  Megjeleníti az aktuális hónapot és az azt követő N hónapot (After).,                             cal -A 2
-B N                  Megjeleníti az aktuális hónapot és az azt megelőző N hónapot (Before).                           cal -B 1
-y,                   Megjeleníti az aktuális év naptárát (ugyanaz, mint a cal ÉV paraméter nélkül).                   cal -y
-j,                   Julián naptár (Julian Calendar) formátumban jeleníti meg az évet/hónapot, azaz a napok                                
                      sorszámát 1-től 365-ig (vagy 366-ig).                                                            cal -j
#### alias
#### dd
#### wheris
#### whatis
#### top
#### useradd
#### passwd


#*** Don't really understand this ps things

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

    2. Feladat
    Máté ad konkrét fileokat amikre rá kell keresni a find paranccsal

    3. Feladat
    Második oszlopot átnézni a TOP 50 linux parancsból, és kijegyzetelni a fontosabb kapcsolókat

    1 hét Deadline
  
  
