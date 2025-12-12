# Useful Linux Commands
## ls - list files
```
ls
```
#### list all files with all attributes human readable
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

## pwd - print work directory
#### value of current working
```
pwd -L
```

#### resolves symbolic links
```
pwd -P
```
    

## cd - change directory
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

## mkdir - make directory
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
## mv - move / rename
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

## cp - copy
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

## rm - remove
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

## touch - make file
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
## ln - hard / soft link
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

## clear - clear terminal
```
clear
```
#### the precise purpose of clear−x was to clear the current screen but guarantee that scrolling back to previous output would be preserved, although in modern systems this functionality is already built into the basic clear command
```
clear -x
```
## cat
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

## echo
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
## less
####
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

## man

## uname

## whoami

## tar

## grep

## head

## tail



## find
  
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
  
  
