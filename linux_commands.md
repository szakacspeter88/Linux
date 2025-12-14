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

(don't really undestand this btw.)

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
## ssh
## service
## ps


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
  
  
