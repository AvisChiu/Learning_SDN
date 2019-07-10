Show the network topology in Opendaylight UI.
---
* Sure that you have already installed Mininet
* System: Ubuntu 16.04
* Opendaylight Nitrogien 0.7.0. Download link:
(https://nexus.opendaylight.org/content/repositories/opendaylight.release/org/opendaylight/integration/karaf/) 
***it's not so necessary to make network topology visible.***
   
Step1: Update jdk environment
---
It ok that you put the zip into **/home** and extract it.   
and you need to update your **jdk** environment first.
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get installopenjdk-8-jdk
```
```
gedit /etc/environment
```
Add this in the end and save.
```
JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"
```
Reboot and check the java version,the result like this.(from CSDN)
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/java_ver.png" width="800",height="800"/></div>
   
   
Step2: Install Opendaylight
---
Make sure that there is a zip file named **karaf-0.7.0.zip** in **/home**(you downloaded just now)   
Extract it~
```
cd karaf0.7.0
cd etc
gedit org.apache.karaf,management.cfg
```
change 0.0.0.0 into 127.0.0.1
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/mana.png" width="300",height="300"/></div>

```
cd /karaf0.7.0/bin
./karaf
```
It turns it on

Step3: Turn it on
---
```
cd /karaf0.7.0/bin
./karaf
```
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/karaf.png" width="800",height="800"/></div>   

**now we need to install some tools in the opendaylight envioronment**

Step4: Installs some necessary tools in opendaylight
---
To install the tools,it's difficult to say different versions have the same command
but there some necessary tools in this 0.7.0 version.
And you can check by using
```
feature:list
```
It will show you what tools you can install, 
Try to use below command line to find what you need and what's the real name of the tool.
```
feature:list | grep <something>
```
```
feature:install <feature-name>
feature:install odl-mdsal-clustering
feature:nistall odl-restconf
feature:install odl-l2switch-switch
feature:install odl-l2switch-all
feature:install odl-dlux-core
feature:install odl-dluxapps-nodes
feature:install odl-dluxapps-yangui
feature:install odl-dluxapps-topology
feature:install odl-mdsal-all
```
THE ui interface will depend on the tools you installed.

Step5: Done and check 
---  


* **Get into the opendaylight environment first**
```
cd /karaf0.7.0
cd bin
./karaf  
```

* **Open the browser**
```
localhost:8181/index.html#/login
username:admin
password:admin
```
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/web.png" width="800",height="800"/></div>
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/web2.png" width="800",height="800"/></div>     


* **Start up Mininet**
You can use other setting of network topology.
```
sudo mn --topo single,3 --mac --switch ovsk,protocols=OpenFlow13 --controller remote
```
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/mininet.png" width="800",height="800"/></div>        
     

* **Refresh the browser**
You will not see the whole topology of the net work but a switch.
```
pingall
```
Then you will see it~!
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/pingall.png" width="800",height="800"/></div>  
