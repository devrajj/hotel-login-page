#lohono stays 

The project is generated by Express and NodeJS

This is the readme file for Ubuntu and Linux Mint based systems. For macOS, you can refer to [MacOS readme](README.md). 

### Install necessary packages

```
sudo apt-get update
sudo apt-get install git -y
sudo apt-get install wget -y
```

If Node version 8.9.0 or higher is installed then skip this process
### Install NVM and node version 14.15.5
```
touch ~/.bash_profile
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash
source ~/.bash_profile
nvm install 14.15.5
nvm use 14.15.5
nvm alias default 14.15.5
npm config set registry http://registry.npmjs.org/
```

### Install local dependencies from project directory
```npm install``` or ```yarn install```


If mysql database is created then skip this process
### Creating a local mysql database
Install mysql server community edition (version 5.7.16 or higher) locally. Do not enable validate password plugin. Enter password as ```root``` when prompted. Skip all other options.
```
sudo apt-get update
sudo apt-get install mysql-server-5.7 -y
sudo apt-get install mysql-client-5.7 -y
sudo systemctl start mysql
sudo systemctl enable mysql
sudo service mysql restart
```

### Running Script for backend data of 50 Villas Seeding
Go to datasource.js file in the code and change the user and password as configured (if password is 123 and user is admin then for the code to run it
must be changed in datasource.js file for the code to run). For my system the username and password were root and root so had configured it as 
that

Once Changed run the script by typing the below command
```
node one-time/create-villas.js
```

### Starting server on your machine
Now you can access the application at `localhost:3000`

- Starting Node server in the root directory
```nodemon .``` or ```forever -w .``` 

