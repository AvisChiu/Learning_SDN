About how to show the network topology in the Opendaylight UI.  
---
* Sure that you have already installed Mininet
* System: Ubuntu 16.04
* Opendaylight Nitrogien 0.7.0. Download link:
(https://nexus.opendaylight.org/content/repositories/opendaylight.release/org/opendaylight/integration/karaf/)   
   
Step1: 
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
Reboot and check the java version,the result like this.(from(https://blog.csdn.net/u012067966/article/details/50736647))
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/java_ver.png" width="500"/>
  
Step2
---
Make sure that there is a zip file named karaf-0.7.0.zip in **/home**(you downloaded just now)   
Extract it~
