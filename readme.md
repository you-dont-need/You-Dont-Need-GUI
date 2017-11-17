# You Don't Need GUI

<details>
It's for noobs :)
</details>
<br />

Graphical user interfaces are super friendly to computer users. They were introduced in reaction to the perceived steep learning curve of command-line interfaces (CLIs).

![Xerox Star 8010 workstations](./Xerox_Star_8010_workstations.jpg)

However, they often require more resources, are less powerful and hard to automate via scripting.

As a computer expert, we want to be more efficient and do our jobs better. We know that command words may not be easily discoverable or mnemonic, so we try to list some common tasks that you might tempt to do in GUI.

## Quick links

1. [copy a file](#copyfile)
1. [duplicate a file](#duplicatefile)
1. [copy a folder](#copyfolder)
1. [duplicate a folder](#duplicatefolder)
1. [move a file](#movefile)
1. [rename a file](#renamefile)
1. [move a folder](#movefolder)
1. [rename a folder](#renamefolder)
1. [merge folders](#mergefolders)
1. [create a new file](#newfile)
1. [create a new folder](#newfolder)
1. [show file/folder size](#filesize)
1. [open a file with the default program](#opendefault)
1. [zip a folder](#zipfolder)
1. [unzip a folder](#unzip)
1. [remove a file](#removefile)
1. [remove a folder](#removefolder)
1. [list folder contents](#listfolder)
1. [tree view a folder and its subfolders](#treeview)
1. [find a stale file](#findfile)
1. [show a calendar](#showcal)
1. [find a future date](#calcdate)
1. [use a calculator](#calculator)
1. [kill a program](#killprogram)


## <a id="copyfile"></a>copy a file

**STOP DRAG AND DROP A FILE, OR CMD/CTRL + C, CMD/CTRL + V A FILE** :-1:

Copy `readme.txt` to the `documents` folder

```shell
cp readme.txt documents/
```

## <a id="duplicatefile"></a>duplicate a file

**STOP RIGHT CLICK AND DUPLICATE A FILE** :-1:

```shell
cp readme.txt readme.bak.txt
```

## <a id="copyfolder"></a>copy a folder

**STOP DRAG AND DROP A FOLDER, OR CMD/CTRL + C, CMD/CTRL + V A FOLDER** :-1:

Copy `myMusic` folder to the `myMedia` folder

```shell
cp -a myMusic myMedia/
# or
cp -a myMusic/ myMedia/myMusic/
```

## <a id="duplicatefolder"></a>duplicate a folder

**STOP RIGHT CLICK AND DUPLICATE A FOLDER** :-1:

```shell
cp -a myMusic/ myMedia/
# or if `myMedia` folder doesn't exist
cp -a myMusic myMedia/
```

## <a id="movefile"></a>move a file

**STOP DRAG AND DROP A FILE, OR CTRL + X, CTRL + V A FILE** :-1:

```shell
mv readme.txt documents/
```

**Always** use a trailing slash when moving files, [for this reason](http://unix.stackexchange.com/a/50533).

## <a id="renamefile"></a>rename a file

**STOP RIGHT CLICK AND RENAME A FILE** :-1:

```shell
mv readme.txt README.md
```

## <a id="movefolder"></a>move a folder

**STOP DRAG AND DROP A FOLDER, OR CTRL + X, CTRL + V A FOLDER** :-1:

```shell
mv myMedia myMusic/
# or
mv myMedia/ myMusic/myMedia
```

## <a id="renamefolder"></a>rename a folder

**STOP RIGHT CLICK AND RENAME A FOLDER** :-1:

```shell
mv myMedia/ myMusic/
```

## <a id="mergefolders"></a>merge folders

**STOP DRAG AND DROP TO MERGE FOLDERS** :-1:

```shell
rsync -a /images/ /images2/
```

## <a id="newfile"></a>create a new file

**STOP RIGHT CLICK AND CREATE A NEW FILE** :-1:

```shell
touch 'new file'
# or
> 'new file'
```

## <a id="newfolder"></a>create a new folder

**STOP RIGHT CLICK AND CREATE A NEW FOLDER** :-1:

```shell
mkdir 'untitled folder'
# or
mkdir -p 'path/may/not/exist/untitled folder'
```

## <a id="filesize"></a>show file/folder size

**STOP RIGHT CLICK AND SHOW FILE/FOLDER INFO** :-1:

```shell
stat -x readme.md
# or
du -sh readme.md
```

## <a id="opendefault"></a>open a file with the default program

**STOP DOUBLE CLICKING A FILE** :-1:

```shell
xdg-open file   # on Linux
open file       # on MacOS
```

## <a id="zipfolder"></a>zip a folder

**STOP RIGHT CLICK AND COMPRESS FOLDER** :-1:

```shell
zip -r archive_name.zip folder_to_compress
```

## <a id="unzip"></a>unzip a folder

**STOP RIGHT CLICK AND UNCOMPRESS FOLDER** :-1:

```shell
unzip archive_name.zip
```

## <a id="removefile"></a>remove a file

**STOP RIGHT CLICK AND DELETE A FILE PERMANENTLY** :-1:

```shell
rm my_useless_file
```

IMPORTANT: The rm command deletes my_useless_file permanently, which is equivalent to move my_useless_file to Recycle Bin and hit Empty Recycle Bin.

## <a id="removefolder"></a>remove a folder

**STOP RIGHT CLICK AND DELETE A FOLDER PERMANENTLY** :-1:

```shell
rm -r my_useless_folder
```

## <a id="listfolder"></a>list folder contents

**STOP OPENING YOUR FINDER OR FILE EXPLORER** :-1:

```shell
ls -la my_folder
```

## <a id="treeview"></a>tree view a folder and its subfolders

**STOP OPENING YOUR FINDER OR FILE EXPLORER** :-1:

```shell
tree                                                       # on Linux
find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'     # on MacOS
```

## <a id="findfile"></a>find a stale file

**STOP USING YOUR FILE EXPLORER TO FIND A FILE** :-1:

Find all files modified more than 5 days ago

```shell
find my_folder -mtime +5
```

## <a id="showcal"></a>show a calendar

**STOP LOOKING UP WHAT THIS MONTH LOOKS LIKE BY CALENDAR WIDGETS** :-1:

Display a text calendar

```shell
cal
```

## <a id="calcdate"></a>find a future date

**STOP USING WEBAPPS TO CALCULATE FUTURE DATES** :-1:

What is todays date?

```shell
date +%m/%d/%Y
```

What about a week from now?

```shell
date -d "+7 days"                                          # on Linux
date -j -v+7d                                              # on MacOS
```

## <a id="calculator"></a>use a calculator

**STOP USING CALCULATOR WIDGET** :-1:

Want to use a calculator?

```shell
bc
```

## <a id="killprogram"></a>force quit a program

**STOP FORCE QUITE A PROGRAM USING GUI** :-1:

```shell
killall program_name
```

---
_Remember, you can always google or `man` the commands you are not familiar with._
