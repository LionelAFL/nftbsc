A) System Requirement - top
Operating system : Linux
Docker
Web3 cli
Nodejs : 12.x +
MongoDB : 4.x +
Angular : 11.x +
SSH root access for installation purpose
B) How to Web3 CLI - top
Refer offical documentation for docker installation in linux. click here
Install web3 cli using below command from terminal
curl -LSs https://raw.githubusercontent.com/gochain/web3/master/install.sh | sh
Create or login infura.io account
Go to ethereum dashboard. please refer below link
https://infura.io/dashboard/ethereum
Create new project and go to settings. please see screenshot
Copy http endpoint from infura. screenshot
update WEB3_RPC_URL in following files from package root directory
create.sh file in ./backend directory
send.sh file in ./backend directory
transaction.sh file in ./backend directory
mint.sh file in ./backend directory
address.sh file in ./backend directory
C) How to configure mongoDB - top
Install mongodb in linux with offical documentation. please refer by clicking the link
Go to ./backend/helper/config.js from application root directory
Update database information. see the link
Host - it will be mongodb running host. By default it was running in localhost
Port - it will be mongodb running port. By default it was running in 27017
Name - it will be database name
Prefix - it will be database collection prefix. it was option variable
D) How to configure mail - top
SMTP configuration
Create SMTP details in any mail provider
Go to ./backend/helper/config.js from application root directory
update SMTP detail under mail variable. see screenshot here
update type to "smtp". see screenshot here
Follow below steps to avoid email notification in the application
Go to ./backend/helper/config.js from application root directory
update type to "" (empty string). see screenshot here
E) Permissions - top
Go to ./backend from application root directory
Give full permission for media folder in linux
sudo chmod 777 -R media

Install and run angular frontend - top
Go to ./frontend from application root directory in terminal
Run "npm install" from terminal
Go to ./frontend/src/app/constants/config.ts and ./frontend/src/app/constants/api.ts from application root directory
replace "example.com" with correct backend url. please see screenshot
To run the the application always. Follow below steps
Install pm2 by running the following command "sudo npm install -g pm2"
Go to ./frontend from application root directory in terminal
Run "pm2 start 'npm run dev' --name backend"
Go to ./frontend from application root directory in terminal
To run the application use below command pm2 start "ng serve --host 0.0.0.0 --port 5001 --disable-host-check --prod --live-reload false --name frontend
Make sure to enable the ports used in both frontend and backend in hosting firewall or security groups

J) Install and run angular admin panel - top
Go to ./adminpanel from application root directory in terminal
Run "npm install" from terminal
Go to ./adminpanel/src/app/constants/config.ts and ./adminpanel/src/app/constants/api.ts from application root directory
replace "example.com" with correct backend url. please see screenshot
Go to ./adminpanel from application root directory in terminal
To run the application use below command pm2 start "ng serve --host 0.0.0.0 --port 5001 --disable-host-check --prod --live-reload false --name adminpanel
Make sure to enable the ports used in adminpanel in hosting firewall or security groups
You have to  follow the steps below to setup backend after completed the server setup

Install and run nodejs backend - top

1. Go to ./backend from application root directory in terminal
Run "npm install" from terminal
2. To run the application temporarily. Run following command

node index.js

3. Go to ./backend from application root directory in terminal

pm2 start 'index.js' --name backend

4. Run "example.com/settings/install" to configure admin user and admin comission settings. make sure change "example.com" with valid api host information
Go to ./backend/module/comment/route/settings.js from application root directory. and comment or remove following line

router.get('/install',settingsController.installOptions)
5. For backend port 5000 has to be enabled
