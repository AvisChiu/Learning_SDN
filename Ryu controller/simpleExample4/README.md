Traffic Monitor
----



***First***
---
Turn on a terminal
```
sudo mn --topo single,3 --mac --switch ovsk --controller remote -x
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample4/mn.png" width="600",height="600"/></div>

***Second***
---
In switch: s1
```
ovs-vsctl set Bridge s1 protocol=OpenFlow13
```
```
ovs-ofctl -O OpenFlow dump-flows s1
```
the version need to be 1.3 (from RyuBook)

<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample4/s1.png" width="600",height="600"/></div>


***Third***
---
Open a new terminal
```
ryu-manager --verbose ./simple_monitor.py
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample4/ryu.png" width="600",height="600"/></div>



***Forth***
---
Open an browser, check the switch's port.
```
http://0.0.0.0:8080/trafficmonitor/portstat
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample4/traffic.png" width="600",height="600"/></div>

We can ping the host in mn, and the data will be changed.
