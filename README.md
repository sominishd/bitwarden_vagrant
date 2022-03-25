## Bitwarden using Vagrant & docker

Install virtualbox (latest version)
Install vagrant
Create a folder anywhere on your local machine: bitwarden
Open terminal:
cd bitwarden
vagrant up --provision
(Wait until everything is complete)
vagrant ssh
Go to https://bitwarden.com/host/  on your local machine browser or any browser on mobile
Enter your email ex. iowngqhc@duck.com, copy id and key (will be required after executing the next command)
sudo bash ./bitwarden.sh install
Enter domain name for your bitwarden: (just press enter, don't type anything)
Enter database name for your Bitwarden instance: (type "vault" without inverted commas)
Do you have ssl certificate? = n
Do you want to generate ssl? = y
cd bwdata
sudo vim config.yml
Change http port from 80 to 8080
Remove port number from https:
set ssl flag to false
save
cd
sudo bash ./bitwarden.sh updatedb
sudo bash ./bitwarden.sh update
sudo bash ./bitwarden.sh rebuild
sudo bash ./bitwarden.sh start
(Give sometime to load)
Once it says bitwarden has started, go to your local machine, open any browser and open the following link:
http://127.0.0.1:4567
It should show you bitwarden login screen. For the first time click on signup use the same email id that you used in previous step while generating id and key.
You can install addons/extensions/android app and make sure to select gear icon on the top left, use ipconfig on your local machine, copy ipv4 address of your network and use it as url. Use login credentials and good to go!
Make sure to comment all lines except the last one in bootstrap.sh so next time all you need is: cd bitwarden, vagrant up --provision 
and it will start everything, and then just get the ipaddress and good to go to sync!