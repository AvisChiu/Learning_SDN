Using Ryu and MiniNAM for visualization
---

***First***
---
Install MiniNam  
[refer](https://ting-kuan.blog/2018/04/04/%E3%80%90mininam-%E8%A6%96%E8%A6%BA%E5%8C%96%E7%B6%B2%E8%B7%AF%E6%8B%93%E5%A2%A3%E6%A8%A1%E6%93%AC%E5%99%A8%E3%80%91/)
```
cd /home
bash -c “$(wget -O – http://openstate-sdn.org/install.sh)"
wget http://www.cs.ucc.ie/~ak18/MiniNAM/code/MiniNAM.tar.gz
```
```
cd ./MiniNAM
sudo chmod +x paping
sudo chmod +x MiniNAM
```

***Second***
---
Using MiniNAM, just the same like using **-mn**
```
./MiniNam --topo single,4 –controller remote
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample3/mininam.png" width="600",height="600"/></div>

***Third***
---

```
sudo ryu-manager simple_switch_13.py
```
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample3/ryu.png" width="600",height="600"/></div>
<br/>
<br/>

***Then you can see an interface***   
Typr **pingall** in mininet,you can see the packet flow.
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample3/vis.png" width="600",height="600"/></div>

***Forth***
---
Check the result from the information in mininam
<div align=center> <img src="https://github.com/AvisChiu/SDN_Freshman/blob/master/Ryu%20controller/simpleExample3/interface.png" width="600",height="600"/></div>
<br/>
The same like example2, we can know how the switches work

