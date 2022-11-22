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

## Video 2
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
network settings -> also files -> stored in etc -> also called etsy file  
cd etc 
cd network 
ls 
sudo cat interfaces -> shows all network interfaces   
mnt, media -> mount drives -> USB or anything gets mounted on media (automatically) and mnt is used when manual mount  
FHS -> file system hierarchy  


## Video 3
Parrot -> terminal emulator on hack the box  
Shell -> user interface we use to interact with the OS (Linux kernel)  (its the UI) 
Terminal emulator -> is what we use to iteract with the shell  (its the keyboard)
Shell -> we using BASH (Bourne again shell)  
ps -> process status 
ps -> shows what processes running, once we run, we see bash, which means shell being used is bash (can be other shells)  
power shell -> windows -> microsoft -> also runs on linux -> its a shell (way to interact with linux)
run ps on power shell -> u see the process as 'pwsh' and not 'bash' because now shell is pwsh (power shell) and not bash (as in the case of parrot)  
terminal -> bash -> shell -> console (all same, used being interchangeably)  
base address is user@hostname/directory  
$ in start shows you are a user  
hash in start shows you are a root user  
id = tells all about you
hostname = tells you host name
uname = tells you nothing but use with extensions  
uname -r = 
uname -a = 
ifconfig = 
ip = 
netstat = status of network  
ss = session stuff  
ps = process stuff  
who = tells who else is logged on  
env = environment variables  
lsblk = list blocks (hard drive stuff)  
lsusb = list usbs plugged in  
lsof = lists all open files 
man uname = helps with command syntax and switches and so  
man ls   
man ip  
uname -h OR uname--h -> gives command help with switches and such  
apropos usb -> tells all commands with usb and helps with remembering commands that can be used  
apropos compress -> tells all commands 

## Video 4
adduser > useradd -> both similar commands but one does more than the other  
cat passwd -> inside etc shows all user names at end of result  
x -> infront of each user shows  that password is stored in a separate file etc/shadow  
sudo cat/etc/shadow -> shows hashed version of password  
after the x -> two numbers -> 1st is user id -> 2nd is group id, names and such , then at end -> home directory and at end, information about once user logs in, what  shell he gets  
sudo useradd ironman -> adds user ironman (does not demand further info)  
useradd -> default shell becomes bin/sh and not /bin/bash (as in the case of adduser)  


 
