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


***Third***
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

***Forth***
---
Open the browser
```
http://127.0.0.1:8080/ simpleswitch/mactable/0000000000000001
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/forth.png" width="600",height="600"/></div>
<br/>

```
curl -X GET http://127.0.0.1:8080/ simpleswitch/mactable/0000000000000001
```
<br/>


***Fifth***
---
Turn down all the terminals.
Now we set the MAC at the begining instead of after the ping in mininet.
The same as before, open two new terminals
```
sudo mn --topo single,3 --mac --switch ovsk --controller remote -x
```
```
sudo ovs-vsctl set Bridge s1 protocols=OpenFlow13
ryu-manager --verbose ./simple_switch_rest_13.py
```
Open the third terminal.
```
curl -X PUT -d '{"mac" : "00:00:00:00:00:01", "port" : 1}' http://127.0.0.1:8080/simpleswitch/mactable/0000000000000001
curl -X PUT -d '{"mac" : "00:00:00:00:00:02", "port" : 2}' http://127.0.0.1:8080/simpleswitch/mactable/0000000000000001
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/fifth.png" width="600",height="600"/></div>
<br/>

***Sixth***
---
In mininet
```
h1 ping -c 1 h2
```
Check controller

```
EVENT ofp_event->SimpleSwitchRest13 EventOFPPacketIn
packet in 1 00:00:00:00:00:01 ff:ff:ff:ff:ff:ff 1
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample5/sixth.png" width="600",height="600"/></div>
<br/>
