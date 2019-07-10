An example to show how switches work in network
---
* ***First***  
Turn on mininet and create a network 
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


* ***Second***    

Open another terminal,and excute the .py above
```
sudo ryu-manager simple_switch_13.py
```
Then will get the result. **If not**, pingall in mininet
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample2/switch-info.png" width="600",height="600"/></div>



Check the result
---
For example
```
1: {'0e:82:29:4e:a6:94': 2, 'ce:c2:69:e7:7b:d7': 2, '66:9d:70:59:08:fa': 2, '9a:45:27:5b:9f:ec': 1, '76:36:2d:58:6a:47': 2, 'ee:17:64:80:8a:c4': 2, 'ea:4f:7c:ee:60:b4': 2}
```
```
'0e:82:29:4e:a6:94': 2   ----> means switch 1 has a link between 0e:82:29:4e:a6:94 in port 2
'ce:c2:69:e7:7b:d7': 2   ----> means switch 1 has a link between ce:c2:69:e7:7b:d7 in port 2
'66:9d:70:59:08:fa': 2   ----> means switch 1 has a link between 66:9d:70:59:08:fa in port 2
'9a:45:27:5b:9f:ec': 1   ----> means switch 1 has a link between 9a:45:27:5b:9f:ec in port 2
'76:36:2d:58:6a:47': 2   ----> means switch 1 has a link between 76:36:2d:58:6a:47 in port 2
...
```
