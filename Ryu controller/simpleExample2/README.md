An example to show how switches work in network
---
**First**  
turn on mininet and create a network 
```
sudo mn --topo linear,4 --controller remote
```
If you want 5 or 6 switches in line,just
```
sudo mn --topo linear,5 --controller remote
sudo mn --topo linear,6 --controller remote
```
And you can see the topology in opendaylight ui.(odl is used to check topology)
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample2/topology.png" width="600",height="600"/></div>
