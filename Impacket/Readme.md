Sources:
https://github.com/fortra/impacket
https://github.com/fortra/impacket.git
Impacket is used for internal penetration testing.
It is a collection of python classes for working with network protocols.
It was first created by SecureAuth and managed by Fortra now.
Go to google and search for impacket, and select the github link that your search brought
By default, the impacket in kali is broken, so you will have to remove all packages of impacket in kali by running the below command and install it again.
apt purge *impacket* remove everything about the package and click yes
clone the repo from git hub
cd into opt and download the repo there- it is recommended to store downloads in this directory
git clone https://github.com/fortra/impacket.git
cd impacket/ - cd into the package from opt
run this command "python3 -m pipx install ." in the directory where impacket has been unpacked. to run the install for impacket.
Had to revert to running "pip install ." because the previous command could not execute the install.
How to turn on and turn off services
Run "ifconfig" - to get my IP. the inet address-  is the ip address that is needed
Grab the ip and run it in a browser- it won't connect, so set up a temporary webserver by running the below command.
Set up a webserver temporarily: "service apachejide start"
Refresh the inet IP that you tested in the browser before- you will see a temporary apache webserver coming up now
Start ssh service- it won't start at first, then run a postgresql, it runs with metaspot and it is good to have that running
service ssh start
service postgresql start
To really start it run the below commands with systemctl enable
systemctl enable ssh - to make it to be fully active and running - it will enable a symlink
systemctl enable postgresql - to enable or create a symlink
service apachejide stop - to stop the webserver service that was created.
Writing Script;
cd out of the impacket folder.
Do a ping of your local ip with a count of 1 to check that it is up: ping -c 1 192.168.1.254
write it to a file: ping -c 1 192.168.1.254 > ip.txt
view it: cat ip.txt. it will have same content as when you ping the ip
The difference will be in the packet loss- is it 100% or 0%?
There will be a line with the number of bytes from the ip, the ttl and icmp etc.
Next: Build a ping sweeper
This is used to know which ips we are talking to and not talking to.
Grep the no of bytes from running the ping. It should give you the exact line with no of bytes.
cat ip.txt | grep "64 bytes"
run the next command that takes a delimiter with the space " ", and then the field -f and cut it out 4 fields.
It cuts out everything except the ip.
cat ip.txt | grep "64 bytes" | cut -d " " -f 4
in order to remove the semi colon that comes with the ip, we need to add some more commands.
add translate -tr, with another delimiter " "  . run the below command to get the semicolon out.
cat ip.txt | grep "64 bytes" | cut -d " " -f 4 | tr -d ":"
use nano to build a script for it now: run the below command. you can give your script any name.
nano ipsweep.sh
declare what you are running at the top of the script e.g python or bash or whatever.
we will be running bash here, so declare- #!/bin/bash
then do a for loop with a back tick sequence (`)
for ip in sequence 1 to 254, run through and do ping the previous commands
with the addition of ampersand & to run through 1 to 254 at once, instead of using semicolon
that makes it to be done by 1 at a time.
#script
# #!/bin/bash
# for ip in `seq 1 254`; do
# ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
# done
ctrl + x
yes i.e y
hit enter to go back to your terminal
run the below command
chmod +x ipsweep.sh
check if the script is executable now
ls -la
run the script by entering the first three octets
./ipsweep.sh 192.168.1
it will list out the ips that are connected or talking to.
you can run the below command to write it to file
./ipsweep.sh 192.168.1 > iplist.txt
then cat it to view
cat iplist.txt - it should show the list of ips that are active or up in your network.
to improve the script, we can add an if statement for when there is no user input.
# #!/bin/bash
#
# if [ "$1" == "" ]
# then
# echo "You forgot an IP address!"
# echo "Syntax: ./ipsweep.sh 192.168.1
#
# else
# for ip in `seq 1 254`; do
# ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
# done
# fi
ctrl + x
y
enter

