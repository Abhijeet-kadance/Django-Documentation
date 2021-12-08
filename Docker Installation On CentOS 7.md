## Docker Installation on CentOS 7

#### Step 1: 
Update the package database

! Manditory Step

> $ sudo yum check-update

Step 2:

Add the latest docker Repository on machine

>$ curl -fsSL https://get.docker.com/ | sh

After that start the Docker Daemon

> $ sudo systemctl start docker

Now verify that it is running by followinf command

>$ sudo systemctl status docker


    Output
    ● docker.service - Docker Application Container Engine
    Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
    Active: active (running) since Sun 2016-05-01 06:53:52 CDT; 1 weeks 3 days ago
     Docs: https://docs.docker.com
    Main PID: 749 (docker)


Lastely enable it to let it start at every server reboot by the following command

> $ sudo systemctl enable docker

Step 3:

