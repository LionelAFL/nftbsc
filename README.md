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
