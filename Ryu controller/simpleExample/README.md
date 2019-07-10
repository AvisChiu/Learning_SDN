Step1
---
Open a terminal and turn on mininet with:

```
sudo mn --topo single,3 --mac --switch ovsk --controller=remote,ip=127.0.0.1,port=6633 -x

```
You can this topology in opendaylight also.
The result will be:
<div align=center> <img src="https://github.com/AvisChiu/Opendaylight_with_mininet/blob/master/figure/https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample/sim_mini.png" width="600",height="600"/></div> 
