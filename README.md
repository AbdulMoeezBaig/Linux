# Linux
https://www.youtube.com/watch?v=VbEx7B_PTOE&amp;list=PLIhvC56v63IJIujb5cyE13oLuyORZpdkL&amp;ab_channel=NetworkChuck

### Linux Commands
pwd -> tells where were are at  
ls -> list all folders / directories  
cd desktop -> changes directory to desktop  
cd .. -> goes to previous directory  
cd .. cd.. cd.. -> reach / -> root directory  
whoami -> user's name  
clear -> clear screen 

## Video 1
OS in use -> Parrot OS on https://academy.hackthebox.com/module/18/section/94  
Linux is a kernel and we built OS on top of it  
Linux kernel interfaces with CPU, RAM, Harddrive etc  
Linux kernel = middle man between OS (Application) and Hardware  
Flavors of linux kernel = parrot os, ubuntu , etc  
Linux is open source -> free to use and distribute  
Linux is faster + more secure (more servers use linux)  
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
useradd -> does not add password or anything  
cat /etsy/passwd -> shows entry for password but we didnt set any passsword  
does have an entry in the shadow file but none was set  
sudo passwd ironman jarvis  -> sets new password for ironman user (now upon checking shadow file we will get a hash)  
still ironman does not have a home (directory)  
ls -al -> reveals hidden files  
usermod -> user modification  
sudo usermod ironman --shell /bin/bash -> shifts shell to bash (from sh)  
sudo usermod -l tony ironman -> changes username  to tony from ironman  
sudo -> super user do (stands for)  
su -> switching another user  
su - -> no user put = shifts to root user  
sudo su - -> makes you root user
logout-> to logout  
if u change users and use sudo it probably wont work
sudoers file determines who can use sudo  
sudo visudo  -> only way to see and do sudo file contents  
%sudo -> its a group and if ur in the group, u dont have to enter password (unsecure dangerous etc)  
thanos ALL = ALL (allows user thanos to do everything)  
thanos ALL = /sbin/useradd  
CTRL + X -> go out of file, save while doing so  
sudo su - thanos  
sudo userdel thor  
sudo userdel ... -> deletes user
sudo groupadd infinitygauntlet -> adds a group to etc/group  
every user created also has a group created with it  
this group can be added to sudoers file  (all of them gain powers)  
To add a group to sudo -> sudo visudo -> under sudo write ->  %infinitygauntlet ALL = NOPASSWD:ALL  
sudo usermod -G -> adds user to group but removes all other groups so can do -> sudo usermod -aG  infinitygaultet ironman  
sudo gpasswd -d thanos infinitygauntlet -> removes thanos from the group  
sudo groupdel -> delete group infinitygauntlet  

## Video 5
Linux package management -> installing stuff  
dpkg apt -> 2 types of packages  
dpkg -> low level package manager  (install ,remove)  
Installing discord: Go to discord.com, download for linux, save the .deb file, cd to download directory, (.deb = Debian base, executable for parrot)  
dpkg -i discord121312.deb -> way to install package but yields error  
sudo dpkg -i discord.deb -> should work but errors / problems  
discord depends on other packages which come in error so they must be installed ourselves  
apt is better, does not do this... advanced package tool (apt)  
sudo apt update  (apt updates itself with list of all packages)  
sudo apt install pidgin  (pidgin is the package name) but might not get installed if there is an already broken installation  
the broken installation has an apt command in it to fix it  
apt itself installs the missing packages as well  
apt -> high level package manager  
dpkg -> requires us to download the deb file, apt does not need that  
apt -> relies on repo (needs only package name)  
sudo apt  edit-sources -> choose editor -> shows the repo's being used to update the apt list  
if ^ does not yield the sources, as in the case of using parrot, go to the mentioned address by using ->  sudo nano [address]  
these tools might have an alternative way to install a package if its not available in the repo  
sudo apt -h -> tells  switches u can use   
sudo apt list -> lists all the available packages  
apt list --installed -> shows what your system is installed with  or -> apt list --installed | grep ^nmap -> shows if nmap is installed  
sudo apt show nmap  -> tells what nmap is, or another package  
sudo apt search nmap -> searches for nmap through a bunch of packages  
sudo apt remove pidgin -> removes pidgin package  (does not remove user data)  
sudo apt purge pidgin -> removes everything about pidgin  
sudo apt list --installed | grep  ^pidgin -> now shows nothing cz pidgin is purged  
sudo apt upgrade  -> update packages that u have  
sudo apt update && sudo apt upgrade  --> check the repository and upgrade everything  
sudo apt update && sudo apt full-upgrade -> removes previously installed applications / packages required for upgrades (i.e. old version of things)  
dpkg -l -> lists, can also search and so  
aptitute -> apt on steriods , high level,  
sudo aptitude  -> u get an iterative GUI in CUI  
aptitude -> high level package manager  
snap / snapd -> more like a store, works like apt, apps get added to snap store and become readily available  
apt install snapd -> snapd is a package manager, apt installs snapd  
sudo snap install --classic code -> installs vscode  
code -> opens VS code  
python's own package manager -> pip  (pip install)  
ruby's package manager -> rubygems  (gem install)  
sudo apt install git -> installs git  Ne
git clone [directory URL link]  
pip 3 -> used for python3  
pip3 install -r requirements.txt -> installs the requirements listed in the python script that you downloaded  
python3 [script name] -h -> gives help about what switches to use  

## Video 6
Daemon -> are in the background (processes)  
process -> instance of running program  
$ps -aux  (lists all the processes I think)
| is called a pipe  (maybe)  
$ps -aux | grep sublime -> we see the process (we had opened the application aublime before)
close the application, retype ps -aux |grep sublime , process will be gone  
these are interactive processes -> we did some thing to open them  
other processes that we did not open are usually -> daemon (processes also)  
daemons -> background processes (networking, printing)  
daemon processes have d at the end -> shows they are daemon  
$ ps -aux | grep ssh -> shows sshd (daemon process)  (daemons launch with boot automatically)
ntp -> network time protocol (keeps time in synch on ur linux server)  
systemd -> master daemon -> starts daemons, stops daemons, also a daemon as d at the end  
systemd -> is a server manager and also an initialization system (init)  
initiliazation system -> massive job -> when we boot -> boots, loads kernel -> systemd -> mounts file system -> starts all services (systemd is the first process)  
from systemd using forking -> starts other processes / daemons  
pstree -> process tree (systemd at the top)  
ps -aux -> each process has a number -> systemd -> process ID=1 (master daemon, first one)  
there have been other names for systemd in the past but we focus on systemd  
systemd calls other daemons as units  
$systemctl stop sshd -> stops sshd process  (sudo before)  
sudo systemctl status sshd (tells status of sshd if active or inactive)  
sudo systemctl start sshd -> starts  
sudo systemctl restart sshd -> restarts  
sudo systemctl reload sshd (not all cannot do this, so reload configuration but not the whole service)  
sudo systemctl reload-or-restart sshd (reload if u can, if not, restart)  
sudo systemctl disable ntp -> disables ntp from default start  
sudo systemctl status ntp -> ntp service disabled means it wont be enabled again if disabled or reboot)  
sudo systemctl enable ntp -> enables for boot  
sudo systemctl is-active ntp  ->shows if active  
sudo systemctl is-enabled ntp -> if enabled  
sudo systemctl list-units -> daemons are units for systemd, lists all daemons (active ones)  
service, socket, device at the end of daemon names, are the type of daemons , many types  
sudo systemctl list-units -t service -> lists all active service daemons  
sudo systemctl list-units | grep nginx -> should list nginx if it was active but doesnt... special cases exist !  
systemctl list units only shows units that are parsed and are in memory, for units not in memory, we need a different command  
sudo systemctl list-units-files |grep ngnix  
ngnix -> is a webserver  
ngnix does not work directly with sudo systemctl start ngnix -> issue  
result tells you to check journalctl *another systemd utility*, laws for systemd stuff  
sudo journalctl -xe -> has no entries  (so we want to restart it)  
sudo systemctl list-units | grep journal (so we can find journal's full name)  
sudo systemctl restart systemd-journald -> restarts  
sudo systemctl start ngnix  -> still doesn't work but nor journal -xe would work cz restarted  
sudo journalctl -xe  
issue happens to be that the port it wants to use is being used by another daemon  

## Video 7

ps -> tells what processes are running (but might not show every process)  (need to specify exactly what we want)  
ps -u [username] -> shows all processes  
ps -u [username] | grep firefox -> (grep = global regular expression print) -> shows firefox process (finds all firefox processes)  
ps -u | grep firefox -> get process id (to kill it later)  
pgrep firefox -> also returns process id  
kill [process id] -> kills the process with the id  
ps --help simple -> simple rundown of ps  
ps -aux -> (a = all users, x = processes that were not executed by the terminal, u = user that process belongs to)  
top -> lists processes ordered by CPU usage   (q to get out of it)  
htop -> same stuff  
ping -> used by utility network engineers or others to make sure things are running  
ping -c 100 google.com -> pings google 100 times (this is a foreground process).. CTRL + C (kills the process), sleep puts to sleep  
ping -c 1000 google.com -> CTRL Z -> stops the process -> jobs -> shows list of current running jobs or jobs put to sleep  
Now we wanna switch this stopped foreground process to background process  
bg -> runs the job we have in sleep in our jobs (if we have only one)  
bg [job id]  -> runs the job id mentioned  
the process starts running and now cannot be stopped with CTRL C  
fg [job id] ->  turns it into a foreground process -> now it can be stopped  
ping -c 300 google.com & -> & at the end makes it directly a background process  
kill -l -> shows all the possibile signals that can be sent  
SIGTERM -> its on kill -l -> its the default signal sent when we use kill -> this is like a soft kill (requests process to die)  
CTRL Z -> kill signal 19 (SIGSTOP)  
CTRL Z (again) -> signal 18 (sigcontinue) (SIGCONT)  
CTRL C -> sig interrupt (SIGINT)  
SIGKILL -> Kills no matter what (signal 9) (will kill no matter what)  
kill -19 [process id] -> -19 is the kill signal,  
pkill -9 ping -> kills all the pings (no process id needed, kills all pings)  

## Video 8
python -m http.server -> website webserver started -> accessed via -> localhost:8000 -> shown on the terminal  
terminal shows someone accessed -> can access whole PC using this  
python -m http.server 7600 -> starts on the port mentioned  
the reason its showing directories is because it does not have an index.html file to look at  
mkdir website -> makes a directory website  
nano index.html -> creates an html file  
save it and reload server from browser -> opens the html file  
php -s 127.0.0.1:8085 -> this IP is your home IP, similar to local host -> localhost:8085 -> opens this web  
systemctl start apache2 -> does not work cz someone using the same port so gotta change default port to start apache service  
sudo nano /etc/apache2/ports.conf -> listen 80 -> listen 8080 -> ports changed  
CTRL X Y Enter ^ above all saved  
curl -> client URL  (communicating with websites current use)  
curl localhost:7600 -> opens in terminal  
curl -o coolwebsite localhost:8080 -> saves the whole website in coolwebsite file  
cat coolwebsite -> opens the saved website  
curl -I localhost:8080 -> this is a response header -> information about who sending, what type of information  
health of message: 200 OK is the best message (top of the response)  
curl -v localhost:8080 -> switch v is for verbose maybe (alot of stuff)  
> = request header , < = response header  
wget localhost:7600 -> downloads the code  
200 ok -> healthy response, 404 not found -> bad response  


## Video 9 





















 
