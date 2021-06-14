```java
sandbox: https://glitch.com/edit/#!/sincere-glacier-water?path=server.js%3A1%3A0
explain command: https://explainshell.com/explain?cmd=sleep+2000
command [options] [arguments]
Command	Description
cat [filename]	Display file’s contents to the standard output device(usually your monitor).
cd /directorypath	Change to directory.
chmod [options] mode filename	Change a file’s permissions.
chown [options] filename	Change who owns a file.
clear	Clear a command line screen/window for a fresh start.
cp [options] source destination	Copy files and directories.
date [options]	Display or set the system date and time.
df [options]	Display used and available disk space.
du [options]	Show how much space each file takes up.
file [options] filename	Determine what type of data is within a file.
find [pathname] [expression]	Search for files matching a provided pattern.
grep [options] pattern [filesname]	Search files or output for a particular pattern.
kill [options] pid	Stop a process. If the process refuses to stop, use kill -9 pid.
less [options] [filename]	View the contents of a file one page at a time.
ln [options] source [destination]	Create a shortcut.
locate filename	Search a copy of your filesystem for the specified filename.
lpr [options]	Send a print job.
ls [options]	List directory contents.
man [command]	Display the help information for the specified command.
mkdir [options] directory	Create a new directory.
mv [options] source destination	Rename or move file(s) or directories.
passwd [name [password]]	Change the password or allow (for the system administrator) to change any password.
ps [options]	Display a snapshot of the currently running processes.
pwd	Display the pathname for the current directory.
rm [options] directory	Remove (delete) file(s) and/or directories.
rmdir [options] directory	Delete empty directories.
ssh [options] user@machine	Remotely log in to another Linux machine, over the network. Leave an ssh session by typing exit.
su [options] [user [arguments]]	Switch to another user account.
tail [options] [filename]	Display the last n lines of a file (the default is 10).
tar [options] filename	Store and extract files from a tarfile (.tar) or tarball (.tar.gz or .tgz).
top	Displays the resources being used on your system. Press q to exit.
touch filename	Create an empty file with the specified name.
who [options]	Display who is logged on.
printenv print environment variables.
export [options] relate environment variables.
lsb_release -a Check ubuntu version
cat /etc/os-release Check ubuntu version
cat /proc/version Check ubuntu version
cat /etc/issue Check ubuntu version

```
```bash
# practices
# jenkins@b98fd9e34b97:/$
# currentUser@hostName
sudo cat /etc/shadow | grep www-data
www-data:*:16519:0:99999:7:::
id
whomai
man id
less /etc/group
useradd user01
pwd

cd
cd /etc/systemd
cd -

tree
tree -d
tree -f

mkdir nofolder
mkdir -p nofolder/abc

touch f1.txt
touch f2.txt f3.txt
touch fx{11,12,13}.txt

rm f1.txt
rm f2.txt f3.txt
rm -rf nofolder/abc

mv currentFolderName newFolderName
mv folderSource folderDestination

cat /etc/passwd
less /etc/passwd
head /etc/passwd
tail -f -n 20 /etc/passwd
tailf -n 10 /etc/passwd

find /etc -name "init.d"
find /etc -name "*.conf"

useradd user01
useradd user02

sudo su
sudo su - user01
su user01

userdel - user02

whoami
sudo touch abc.txt
ls -l
sudo chown user01 abc.txt
ls -l

sudo chown user01:user01 abc.txt
sudo chown user01.user01 abc.txt
sudo chown .user01 abc.txt

# stdin
grep root < /etc/passwd
# stdout
echo $USER > hello.txt
# stderr
find /etc -nam "init.d" 2> file.txt
# stdout and stderr
php script.php &> file.txt

# pipe command
echo "foo bar baz" | wc -w
3

# search content
grep nguoidung /etc/passwd
nguoidung:x:10003:10003::/home/nguoidung:
nguoidung2:x:1002:1002:nguoidung2,,,:/home/nguoidung2:/bin/bash

grep -n nguoidung /etc/passwd
41:nguoidung:x:10003:10003::/home/nguoidung:
42:nguoidung2:x:1002:1002:nguoidung2,,,:/home/nguoidung2:/bin/bash

# search content with pattern
grep -Ril "Bandit" Service/Dig/Module
grep -EnR "\[\'user\'\]\[\'event\'\]\[\'fight_attack\'\]\s+-=" Service/ frontend/
grep -EnR "..user....event....fight_attack..\s+-=" frontend

basename dir2/dir4/hello.txt
hello.txt

# background and foreground
# background
jobs
# foreground
sleep 3000 &

# process
ps
vi /etc/passwd >> ctl + z(stopped process)
ps
kill -9 591

# List all process on system
ps aux
lsof -i -P
lsof -i :3306

#View config of server linux
cat /proc/cpuinfo
free

# https://www.javatpoint.com/linux-ip
ip address
ip route

# Red Hat Package Management
yum

# Ubuntu package management
apt-get

# Macos package management
brew

# how to view status of service
# on linux
systemctl status docker
# on macos
launchctl list | grep docker

```