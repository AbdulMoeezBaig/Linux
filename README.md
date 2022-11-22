# Linux
https://www.youtube.com/watch?v=VbEx7B_PTOE&amp;list=PLIhvC56v63IJIujb5cyE13oLuyORZpdkL&amp;ab_channel=NetworkChuck

## Video 1
OS in use -> Parrot OS on https://academy.hackthebox.com/module/18/section/94  
Linux is a kernel and we built OS on top of it  
Linux kernel interfaces with CPU, RAM, Harddrive etc  
Linux kernel = middle man between OS (Application) and Hardware  
Flavors of linux kernel = parrot os, ubuntu , etc  
Linux is open source -> free to use and distribute  
Linux is faster + more secure (more servers use linux)  

### Linux Commands
pwd -> tells where were are at  
ls -> list all folders / directories  
cd desktop -> changes directory to desktop
cd .. -> goes to previous directory
cd .. cd.. cd.. -> reach / -> root directory
whoami -> user's name  
clear -> clear screen  
everything in linux is a file -> network configuration -> file, devices (harddrive printer etc) -> file, commands we use -> files
cat -> concatenate (used to open files)  
cat ls -> opens ls command file (but unreadable because it is a command binary)  
cp -> copy
cp ls ABC (copies ls as ABC) (if no permission)
sudo cp ls ABC -> sudo lets u pretend ur admin so u have permissions to copy etc  
rm ->  remove 
sudo rm ls -> removes ls files  
sbin -> has special commands that only administrators can use to administer the system  
adduser -> adds user, needs sudo
bin / sbin in root = bin / sbin in user  
which ls -> tells where the command binaries live (in our case, its in root/user/bin not in root/bin  
boot -> (root) has boot files  
var -> (root) log files / web application related files  
temp -> (root) files that go away after restart or so, temporary files  
lib -> (root) shared library files  
home -> (root) where every user lives  
home -> ls shows all users  
sudo ls root -> shows directories inside root, root does not live in  home but somewhere else  
why we have 2 bin and sbin in root and user ---> comes down to hard drive space (details need to be looked into)  
dev -> devices
vda, vda1 -> virtual drives (sda, sda1 on other things)
sudo cat vda -> shows binary for drive, CTRL + C to stop  

