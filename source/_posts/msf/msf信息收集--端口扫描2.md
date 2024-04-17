msf信息收集--端口扫描2

## idle扫描
use auxiliary/scanner/ip/ipidseq
查找出来以后，就可以进行idle主机扫描
nmap -PN -sI 1.1.1.2 1.1.1.3

![Image.png](645fe527b1944a30b23a503bb31c3a8a.png)

上面的结果是没有扫描出来idle主机

## UDP扫描

```
use auxiliary/scanner/discovery/udp_sweep
use auxiliary/scanner/discovery/udp_probe
```
