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


