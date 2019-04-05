# Setup - Applications

$ = Non Root User

&#35; = Root User


#### Update Linux machine.
```
$ sudo apt update
$ sudo apt upgrade
```



#### Install Sublime Text.
1. Install the GPG key:
```
$ wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

2. Ensure apt is set up to work with https sources:
```
$ sudo apt install apt-transport-https
```

3. Select the channel to use: Stable
```
$ echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

4. Update apt sources and install Sublime Text
```
$ sudo apt update
$ sudo apt install sublime-text
```


#### Install GIT.
```
$ sudo apt install git
```

#### Install Google Chrome.
1. Install the GPG key:
```
$ wget -qO - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
```

2. Select the channel to use: Stable
```
$ echo "deb [ arch=amd64 ] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list
```

3. Update apt sources and install Google Chrome
```
$ sudo apt update
$ sudo apt install google-chrome-stable
```

3. Run Google Chrome
```
$ google-chrome-stable
```

#### Install MongoDB.
1. Import the public key used by the package management system.
```
$ sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
```

2. Create a list file for MongoDB.
```
$ echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
```

3. Reload local package database.
```
$ sudo apt update
```

4. Install the MongoDB packages.
```
$ sudo apt install -y mongodb-org
```

5. Directories
Data directory
```
$ cd /var/lib/mongodb
```
Log directory
```
$ cd /var/log/mongodb
```

6. Start MongoDB.
```
$ sudo service mongod start
```

7. Verify that MongoDB has started successfully.
27017 is the default port the standalone mongod listens on

6. Use MongoDB.
```
$ mongo
```

----------------------------------------------------------------
