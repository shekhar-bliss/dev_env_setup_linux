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
----------------------------------------------------------------
