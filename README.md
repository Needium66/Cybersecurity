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