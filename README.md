# Cybersecurity
everything cybersecurity
https://www.youtube.com/watch?v=3Kq1MIfTWCE&t=5996s
https://github.com/MikeMutter/hmaverickadams-Beginner-Network-Pentesting
https://www.vmware.com/products/workstation-player.html
https://customerconnect.vmware.com/en/downloads/details?downloadGroup=WKST-PLAYER-1702&productId=1377
Setting up testing environment
Python
Hacking in 5 steps
The Art of Reconnaissance: Using OSINT Framework, SET, theHarvester, Bluto, Google Dorks, and Shodan.
Scanning tactics: Using Nmap, Nessus, and Metasploit. TCP vs UDP scanning, the 3-way TCP handshake, stealth scanning, Nmap switches.
Enumeration tactics: Using Nikto, Dirbuster/Dirb and Burp Suite
Gaining a shell with Metasploit
Active Directory Exploitation: LLMNR poisoning/ Hash cracking, SMB has relaying,pash the hash, token impersonation, kerberoasting, GPP/c-password attacks and Powershell attacks
Exploting Non-Active Directory Environments:

Step 1: VM
We need a VM to be used to execute the projects in this module. Kali is highly recommended because of its flexibility(it is OS agnostic) and VMware player machine needs to be set up for this too, together, they will form the homelab for all the projects that will be undertaking throughout this module. The links to get the downloads for kali and vmware can be found at the top.
Download kali for windows from the link
Extract the executables from the downloaded folder
Download vmware player from the link given above too and follow the steps.
Start off your kali application
Sign in with kali as username and password and you can change your password if you want.
Some important utilities that can be used
ls - list directories
cd - change directory
cd .. - change directory back once
cd Deskstop - change directory to Desktop
mkdir new - create a directory called new
rmdir new - remove a directory called new
ls -la - list of alld directories including hidden ones. always use this, instead of ls, so that you can see all files
echo "Hello Lana" > new.txt - to create/write to a new file
cp new.txt Desktop/jide.txt - to copy a file into a directory or from one location into another
rm Desktop/jide.txt - remove a file from a directory. Note: we don't have to be in a directory to run a command i.e don't have to cd into it.
mv new.txt Desktop/new.txt - to move a file from one directory to another.
locate new.txt - to find a file
man ls - to list the commands that are available for use with ls command
drwxr - d stands for directory, if there is a dash(-) in place of d, means it is a file, break down the first written letter, where "rwx" means read write and execute, - also means it is switched off i.e the command that is supposed to be there is off.
drwxr-xr-x- for these 3 groups; the first group(which is the file or folder owner) is directory,read,write,execute and read . the second group(the group owner) is execute and read, while the third and last group(all the info) is execute.
Example: "-rw-r--r--" means i am a read and write owner of a file but can execute. the - in the front means it is a file, the rw means the file or directory owner can read or write, the group owner means can only read, while the last means it is only a read info. so i can only read. i can only write, if i am put in group, where i am the file owner. e.g wheel group. So to allow me to be able to write read and execute on new.txt file that currently has this kind of permission, i need to use a command called change mode (chmod)- in 2 ways:
chmod 777 new.txt - numbering system will give it read, write and execute for every single thing. OR
chmod +x new.txt - it means i can use "execute" on that file. the file color code will change to green (shows you can execute on a file). it will give the permission to all the 3 groups. it becomes "-rwx-rx--rx". you need this permission i.e a file to be executable if you want to run a script e.g bash script.
To add a user- run "adduser Jide" and enter a password for it. e.g know the credentials of a new user to be added to populate this. If you are not a root user, you won't be able to perform this process successfully. In order to execute this command, you need to be a root user, so you can run "sudo su" temporarily to be a root user and execute it or enable a root account with "sudo passwd" and run the subsequent commands.
adduser - to add a new user permissions.
sudo su - switch to root temporarily
sudo passwd - password to enable a root account.
cat /etc/passwd - to access the important file to view users and their permissions to perform actions on directories or files. You find the users that are on the machine at the bottom, other than root. e.g jide is in group 1000 now.
For "Pentesting" , we are only concerned about the "root user" and the "users on the machine".
cat /etc/shadow - To look at the shadow file. To get the "hash" for root user at the top and other users on the machine at the bottom e.g jide in my own case. The hashes can be cracked. You can use a tool called "unshadowing" to crack it. You will combine the hash for root in shadow file and passwd file or combine the the two files ( use hashes or files), and "it takes the root and places the 'hash' in the shadow file in place of the x in passwd file and runs the rest(the remaining part of hash) out in the remaining part of the root in the password file. It should crack. To crack someone's password or root password use this- combinantion of shadow file and passwd file or combinantion of hash and x will give you what the root password is or combination of hash for Jide and password for Jide.
Note: Important
etc passwd file contains the passwords /etc/passwd
etc shadow file contains the hashes /etc/shadow
su - to switch user
su jide - to switch user to jide.
Permissions will be denied if user is switched to jide and jide tries to cat the /etc/shadow file because jide is not a root user. not part of the "sudoers" file. jide needs to be in the sudoers file to be able to carry out this permission.
/var/log# cat auth.log - to check for a "reported user trying to access the machine info" the funny "you will be reported" message
"su -" switch you back to root and it will ask for password
cd /var/log - cd into var log and then cat auth.log i.e
/var/log# cat auth.log
Network Commands:
ifconfig - it displays info about all network interfaces e.g network mask, ip etc
ping - to know whether a connection is running or active or not
arp -a gives info about the association of mac address with ip address.
netstat - shows you all the ports that are opened and what is connected to those ports.
netstat -ano
route - displays routing table
history - to get a list of previous commands you have ran
history | grep ping - to get a list of specific previous commands you have ran for e.g ping.
~ to go to root folder
cd ~/Downloads/ - to go to downloads in the root folder.
Creating and writing files:
echo "hi" > greeting.txt - to write to a file called greeting.txt
echo "hi jide" > greeting.txt - you will overwrite what you had in the previous file- it will delete it. To avoid this- if you want to add or append another text to your text file i.e new content, you will use this command >>:
echo "hi jide" >> greeting.txt - it will append hi jide to the hi in the greeting.txt file.
touch oluwalana.txt- another way to write to a file.
nano oluwalana.txt - write to a file- it opens up a file for you. write into it e.g hi olajide. then run the below command to save it: (no vim or vi)
crtl + x
click/hit on y to save your file
click/hit on enter to go back to the terminal
cat oluwalana.txt - to view the content of the file
rm greeting.txt - to remove a file
sudo rm greeting.txt - to remove a file if you don't have permissions
Update machine, tools:
apt update && apt upgrade- to update your machine (this takes time)
apt install git -y - to install git without prompting for yes. how to install tools


#projects implemented
1)worked on some unsupported log4j- we have versions 1.14- support for it was ended in 2015
our scanning tool- tenable discovered this vulnerabilities and i was tasked with ensuring
that all the machines that still have it had the security vulnearibilities mitigated on them
through upgrades or through some other means
for the linux servers
i moved the log4j on the machines where it was not been used anymore to backup to stop it from being executable or runnable
i used tenable to locate where it is on the machine
cd to that folder through the path
mv the log4j from the current directory to a bak file
checked it on tenable later to see if it is still a threat
for the windows server
logged into the machine
went to the directory it was located
make a copy of it
zip it and leave it for some days
delete it after
for the upgrade of log4j in the linux servers. because it is on a vmware machines
i cloned one of the machines and make it to be in a cluster with others
i followed the steps for an upgrade and observed for some days
then go ahead to do it on the real prod machines.
requires java 8 and log4j 2.7 and above to be installed or upgraded.
2)worked on finding resources that are still using tls 1.0 and 1.1 in aws
turned it in to the developers to make code changes that will enable the apps to be using only 1.2
3)sign-in and audit log forwarding in splunk
4)all the business dns we are using
5)encryption of all ebs, s3 resources, databases etc, using trusted advisor to find out the non compliant resources
6) node js upgrade in lambda
7) net upgrade in lambda
8) python upgrade in lambda
9)set up  a log forwarder from aws into splunk: aws config, lambda, event bridge, cloudwatch, s3 and sns
10)customer kms key for rds
11)ec2 key pairs
12) rds db subnet
13)phishing test through bit defender
14)cybereason scanning for malware and other threats
15) tenable nessus scanning for malware and other threats.