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
Next: Build a ping sweeper