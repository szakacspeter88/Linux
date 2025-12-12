# Useful Linux Commands
## ls - list files   
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
cd -P
```
The cd -P command skips symbolic links and enters a specified special subfolder, following the physical path.
```
cd -L
```
The −L switch (Logical Mode) instructs the shell to follow the default, logical path during directory navigation.

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

#### required when copying directories. Copies the directory and all its subdirectories along with its contents (recursive)
```
cp -r
```

## rm - remove
## touch - make file
## ln - hard / soft link
## clear - clear terminal

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
  
  
