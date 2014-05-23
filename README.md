Linux
=====

Linux command line cheat sheets

#Basic Commands#

###General Commands###
Change Directory `cd /path/to/dir` Move up one Dir	`cd..` Move to Root `cd /`	Move to Users Home `cd ~`

Copy an entire directory and it's contents (sub directories & files):
  sudo cp -r /path/to/source /path/to/destination

###Users & Groups###
Add User to Sudoers:
  sudo adduser <username> sudo

Create user with password and home folder:
  sudo useradd -d /home/testuser -m testuser
  sudo passwd testuser

Rename file extensions:
  rename 's/\.foo$/\.bar/' * SPECIFIC EXAMPLE: rename 's/\.gddoc$/\.txt/' *

###Manage Directories###
Delete the files and directories, but requires a prompt for each of the files:
  rm -r directory

Delete all with no prompt:
  rm -rf example

Print Directory Contents. Once in the directory you want to print the contents of:
  ls > print.txt

###WordPress: Set Directory & File Permissions###

Set Directory Permissions to 755:
  find /var/www/domain.com/path-to-wp -type d -exec chmod 755 {} \;

Set File Permissions to 644:
  find /var/www/path-to-wp -type f -exec chmod 644 {} \;
