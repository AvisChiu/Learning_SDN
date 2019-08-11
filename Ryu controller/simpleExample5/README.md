Get the MAC / Add the MAC
---


***First***
---
Open a new terminal
```
sudo mn --topo single,3 --mac --switch ovsk --controller remote -x
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/first.png" width="600",height="600"/></div>
<br/>


***Second***
---
Open a new terminal, Turn on ryu controller
```
 sudo ovs-vsctl set Bridge s1 protocols=OpenFlow13
 ryu-manager --verbose ./simple_switch_rest_13.py
```

<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/second.png" width="600",height="600"/></div>
<br/>


***Second***
---
Now the network was initialized. But the host need to know others' address.
In mininet terminal
```
h1 ping -c 1 h2
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/third.png" width="600",height="600"/></div>
<br/>
Check the ryu controller terminal. 
The controller received the packets three times. 
The switch need to know that the packet send to which port.   

```
EVENT ofp_event->SimpleSwitchRest13 EventOFPPacketIn
packet in 1 00:00:00:00:00:01 ff:ff:ff:ff:ff:ff 1
EVENT ofp_event->SimpleSwitchRest13 EventOFPPacketIn
packet in 1 00:00:00:00:00:02 00:00:00:00:00:01 2
EVENT ofp_event->SimpleSwitchRest13 EventOFPPacketIn
packet in 1 00:00:00:00:00:01 00:00:00:00:00:02 1
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/third2.png" width="600",height="600"/></div>
<br/>
