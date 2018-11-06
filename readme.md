# You Don't Need GUI

<details>
It's for noobs :)
</details>
<br />

Graphical user interfaces are super friendly to computer users. They were introduced in reaction to the perceived steep learning curve of command-line interfaces (CLIs).

![Xerox Star 8010 workstations](./Xerox_Star_8010_workstations.jpg)

However, they often require more resources, are less powerful and hard to automate via scripting.

As a computer expert, we want to be more efficient and do our jobs better. We know that command words may not be easily discoverable or mnemonic, so we try to list some common tasks that you might be tempted to do in GUI.

## Quick links

1. [copy a file](#copy-a-file)
1. [duplicate a file](#duplicate-a-file)
1. [copy a folder](#copy-a-folder)
1. [duplicate a folder](#duplicate-a-folder)
1. [move a file](#move-a-file)
1. [rename a file](#rename-a-file)
1. [move a folder](#move-a-folder)
1. [rename a folder](#rename-a-folder)
1. [merge folders](#merge-folders)
1. [create a new file](#create-a-new-file)
1. [create a new folder](#create-a-new-folder)
1. [show file/folder size](#show-filefolder-size)
1. [open a file with the default program](#open-a-file-with-the-default-program)
1. [zip a folder](#zip-a-folder)
1. [unzip a folder](#unzip-a-folder)
1. [remove a file](#remove-a-file)
1. [remove a folder](#remove-a-folder)
1. [list folder contents](#list-folder-contents)
1. [tree view a folder and its subfolders](#tree-view-a-folder-and-its-subfolders)
1. [find a stale file](#find-a-stale-file)
1. [show a calendar](#show-a-calendar)
1. [find a future date](#find-a-future-date)
1. [use a calculator](#use-a-calculator)
1. [force quit a program](#force-quit-a-program)
1. [view content of a file](#view-content-of-a-file)
1. [search for a text](#search-for-a-text)


## copy a file

**STOP DRAG AND DROP A FILE, OR CMD/CTRL + C, CMD/CTRL + V A FILE** :-1:

Copy `readme.txt` to the `documents` folder

```shell
cp readme.txt documents/
```

## duplicate a file

**STOP RIGHT CLICK AND DUPLICATE A FILE** :-1:

```shell
cp readme.txt readme.bak.txt
```

## copy a folder

**STOP DRAG AND DROP A FOLDER, OR CMD/CTRL + C, CMD/CTRL + V A FOLDER** :-1:

Copy `myMusic` folder to the `myMedia` folder

```shell
cp -a myMusic myMedia/
# or
cp -a myMusic/ myMedia/myMusic/
```

## duplicate a folder

**STOP RIGHT CLICK AND DUPLICATE A FOLDER** :-1:

```shell
cp -a myMusic/ myMedia/
# or if `myMedia` folder doesn't exist
cp -a myMusic myMedia/
```

## move a file

**STOP DRAG AND DROP A FILE, OR CTRL + X, CTRL + V A FILE** :-1:

```shell
mv readme.txt documents/
```

**Always** use a trailing slash when moving files, [for this reason](http://unix.stackexchange.com/a/50533).

## rename a file

**STOP RIGHT CLICK AND RENAME A FILE** :-1:

```shell
mv readme.txt README.md
```

## move a folder

**STOP DRAG AND DROP A FOLDER, OR CTRL + X, CTRL + V A FOLDER** :-1:

```shell
mv myMedia myMusic/
# or
mv myMedia/ myMusic/myMedia
```

## rename a folder

**STOP RIGHT CLICK AND RENAME A FOLDER** :-1:

```shell
mv myMedia/ myMusic/
```

## merge folders

**STOP DRAG AND DROP TO MERGE FOLDERS** :-1:

```shell
rsync -a /images/ /images2/
```

## create a new file

**STOP RIGHT CLICK AND CREATE A NEW FILE** :-1:

```shell
touch 'new file'
# or
> 'new file'
```

## create a new folder

**STOP RIGHT CLICK AND CREATE A NEW FOLDER** :-1:

```shell
mkdir 'untitled folder'
# or
mkdir -p 'path/may/not/exist/untitled folder'
```

## show file/folder size

**STOP RIGHT CLICK AND SHOW FILE/FOLDER INFO** :-1:

```shell
stat -x readme.md
# or
du -sh readme.md
```

## open a file with the default program

**STOP DOUBLE CLICKING A FILE** :-1:

```shell
xdg-open file   # on Linux
open file       # on MacOS
```

## zip a folder

**STOP RIGHT CLICK AND COMPRESS FOLDER** :-1:

```shell
zip -r archive_name.zip folder_to_compress
```

## unzip a folder

**STOP RIGHT CLICK AND UNCOMPRESS FOLDER** :-1:

```shell
unzip archive_name.zip
```

## remove a file

**STOP RIGHT CLICK AND DELETE A FILE PERMANENTLY** :-1:

```shell
rm my_useless_file
```

IMPORTANT: The rm command deletes my_useless_file permanently, which is equivalent to move my_useless_file to Recycle Bin and hit Empty Recycle Bin.

## remove a folder

**STOP RIGHT CLICK AND DELETE A FOLDER PERMANENTLY** :-1:

```shell
rm -r my_useless_folder
```

## list folder contents

**STOP OPENING YOUR FINDER OR FILE EXPLORER** :-1:

```shell
ls -la my_folder
```

## tree view a folder and its subfolders

**STOP OPENING YOUR FINDER OR FILE EXPLORER** :-1:

```shell
tree                                                       # on Linux
find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'     # on MacOS
```

## find a stale file

**STOP USING YOUR FILE EXPLORER TO FIND A FILE** :-1:

Find all files modified more than 5 days ago

```shell
find my_folder -mtime +5
```

## show a calendar

**STOP LOOKING UP WHAT THIS MONTH LOOKS LIKE BY CALENDAR WIDGETS** :-1:

Display a text calendar

```shell
cal
```
Display selected month and year calendar

```shell
cal 11 2018
```

## find a future date

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

## use a calculator

**STOP USING CALCULATOR WIDGET** :-1:

Want to use a calculator?

```shell
bc
```

## force quit a program

**STOP FORCE QUIT A PROGRAM USING GUI** :-1:

```shell
killall program_name
```

## view content of a file

**VIEW THE CONTENT OF ANY FILE** :-1:
```shell
cat file_full_path

Example : cat apps/settings.py
```

## search for a text

**SEARCH FOR A PATTERN IN FILES** :-1:

```shell
grep [options] pattern [files]

Example : grep -ir "Query" file.txt

Options Description
-c : This prints only a count of the lines that match a pattern
-h : Display the matched lines, but do not display the filenames.
-i : Ignores, case for matching
-l : Displays list of a filenames only.
-n : Display the matched lines and their line numbers.
-v : This prints out all the lines that do not matches the pattern
-e exp : Specifies expression with this option. Can use multiple times.
-f file : Takes patterns from file, one per line.
-E : Treats pattern as an extended regular expression (ERE)
-w : Match whole word
-o : Print only the matched parts of a matching line, with each such part on a separate output line.
-r : Search repetitively/iteratively
```

---
_Remember, you can always google or `man` the commands you are not familiar with._
