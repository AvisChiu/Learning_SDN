Step1
---
Open a terminal and turn on mininet with:

```
sudo mn --topo single,3 --mac --switch ovsk --controller=remote,ip=127.0.0.1,port=6633 -x

```
You can this topology in opendaylight also.
The result will be:
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample/sim_mini.png" width="600",height="600"/></div> 

**127.0.0.1** is the address of the controller  

Step2
---
Open anoher terminal:
```
ovs-vsctl show
ovs-dpctl show
//change the Bridge s1 protocol into OpenFlow13
ovs-vsctl set Bridge s1 protocols=OpenFlow13
```
Open another terminal
```
ryu-manager --verbose ryu.app.simple_switch_13
```
In mininet
```
pingall
```
Then you can see how the packets goes through in this network.
The result will be:
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample/packets.png" width="400",height="600"/></div> 

