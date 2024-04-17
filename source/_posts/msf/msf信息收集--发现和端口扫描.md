msf信息收集--发现和端口扫描

kali机：192.168.1.5
centos6机：192.168.1.6

## 主机发现

开启postgresql
`root@kali:~# service postgresql start`

打开msfconsole
使用db_nmap扫描c网段：
```db_nmap -sV 192.168.1.0/24```
最后会扫出来本网段的机子
使用hosts查看机子

![41915a60cd2de31565c5949b413245bd.png](c76aa817717f42bcb807082268b0e569.png)

使用arp_sweep扫描发现
`msf5 > use auxiliary/scanner/discovery/arp_sweep`

设置扫描网段，设置线程数
网段也可以设置为一下格式
`192.168.1.20-192.168.1.30`

`msf5 auxiliary(scanner/discovery/arp_sweep) > set rhosts 192.168.1.0/24
rhosts => 192.168.1.0/24
msf5 auxiliary(scanner/discovery/arp_sweep) > set threads 20
threads => 20
`

![e910c694ce6c08f747a39fdd3f96bb95.png](3aaaef98414e474abff3d2cf63206b96.png)

使用hosts查看扫描出来的主机列表



![1b557ef53dd142cae420b8fc7ec4d884.png](586e5b21bbdb4f7d98b23b84c2e998a3.png)

## 端口扫描

使用portscan模块，里面有很多模块，选择一个进行测试
`use auxiliary/scanner/portscan/syn`

设置目标主机，要扫描端口，线程数


![df85749042e07599e721c9ee667d6cc9.png](48ac62deaecc4c0db92addc70916d032.png)

`run`



![0f6fdb4ed3cbf42b5018482259f6be32.png](cb35aac6b0ae43709d90f38a291eb5db.png)


