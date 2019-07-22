---
description: installation (Ubuntu14.04) and usage Instructions
---

# MongoDB

## MongoDB Ubuntu14.04 Installation <a id="mongodb-ubuntu-14-04-installation"></a>

```text
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
mkdir data
echo 'mongod --dbpath=data --nojournal' > mongod
chmod a+x mongod
from: https://gist.github.com/nax3t/9d22f0f627d144da9f21b43f90b3680f
```

You should now have mongo 3.6.2 or newer, you can double check with

```text
mongo --version 
```

Now type cd in the terminal and hit enter to go into the root directory ~

Enter the following:

```text
mkdir data 
echo "mongod --dbpath=data --nojournal" > mongod 
chmod a+x mongod
```

Now, in order to run mongod you'll first need to cd into root ~ then run ./mongod Additionally, after you're up and running with mongo, be sure to shut down your ./mongod server each time you're done working. You can do this with ctrl + c If you leave it running then Cloud 9 could timeout and cause mongo to crash. If this happens, try the following steps to repair it. From the command line, run:

```text
cd ~ 
./mongod --repair
```

If you're still having trouble getting it to run then find the /data directory \(it should be inside of ~\) and cd into it. Once inside, run rm mongod.lock then cd back into ~ and run ./mongod again \(see below\).

```text
cd ~/data 
rm mongod.lock 
cd 
./mongod
```



