Linux command line cheat sheet
==============================

###General Commands###
Change Directory `cd /path/to/dir` Move up one Dir	`cd..` Move to Root `cd /`	Move to Users Home `cd ~`

Copy an entire directory and it's contents, including sub directories & files:

```
sudo cp -r /path/to/source /path/to/destination
```

###Users & Groups###

Add User to Sudoers:

```
sudo adduser <username> sudo
```

Create user with password and home folder:

```
sudo useradd -d /home/testuser -m testuser
sudo passwd testuser
```

Rename file extensions:

```
rename 's/\.foo$/\.bar/' * SPECIFIC EXAMPLE: rename 's/\.gddoc$/\.txt/' *
```
###Manage Directories###
Delete the files and directories, but requires a prompt for each of the files

```
rm -r directory
```

Delete all with no prompt:

```
rm -rf example
```

Print Directory Contents. Once in the directory you want to print the contents of:

```
ls > print.txt
```

###WordPress: Set Directory & File Permissions###

Set Directory Permissions to 755:

```
find /var/www/domain.com/path-to-wp -type d -exec chmod 755 {} \;
```

Set File Permissions to 644:

```
find /var/www/path-to-wp -type f -exec chmod 644 {} \;
```

###Sync to Remote Server###
This is probably better than scp - since it only transfers the differences between two sets of files. 

```
rsync -az /path/to/source username@host:/path/to/destination
```
Common options used with rsync commands:
* -v : verbose
* -r : copies data recursively (but don’t preserve timestamps and permission while transferring data
* -a : archive mode, archive mode allows copying files recursively and it also preserves symbolic links, file permissions, user & group ownerships and timestamps
* -z : compress file data
* -h : human-readable, output numbers in a human-readable format
