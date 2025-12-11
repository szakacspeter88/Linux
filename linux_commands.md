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

```
cd -L
```

## mkdir - make directory

```
```

## mv - move / rename
## cp - copy
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
  
  
