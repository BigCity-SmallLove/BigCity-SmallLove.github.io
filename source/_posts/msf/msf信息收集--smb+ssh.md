msf信息收集--smb+ssh

kali:192.168.88.130
靶机：192.168.88.129

## SMB

概括：
`
SMB版本扫描
– use auxiliary/scanner/smb/smb_version
扫描命名管道，判断smb服务类型（账号、密码）
– use auxiliary/scanner/smb/pipe_auditor
ٔ扫描通过SMB管道可以访问的RCRPC服务
– use auxiliary/scanner/smb/pipe_dcerpc_auditor
SMB共享枚举（账号、密码）
– use auxiliary/scanner/smb/smb_enumshares
SMB用户枚举（账号、密码）
– use auxiliary/scanner/smb/smb_enumusers
SID枚举（账号、密码）
– use auxiliary/scanner/smb/smb_lookupsid`

## SSH

```
▪ SSH 版本扫描
– use auxiliary/scanner/ssh/ssh_version
▪ SSH密码爆破
– use auxiliary/scanner/ssh/ssh_login
    ▪ set USERPASS_FILE /usr/share/metasploit-framework/data/wordlists/
root_userpass.txt;set VERBOSE false;run
▪ SSH公匙登陆
– use auxiliary/scanner/ssh/ssh_login_pubkey
▪ set KEY_FILE id_rsa; set USERNAME root;run
```

### SMB

* use auxiliary/scanner/smb/smb_version

若有账号密码可以加进去，扫描结果会更准确


![43fbff6f077fb9b2ac44c439d9ae5ba1.png](efa0795faec64aaba7657422b0a8c017.png)


* use auxiliary/scanner/smb/pipe_auditor

若有账号密码可以加进去，扫描结果会更准确

![c875c46d343cf3e17a9bfcea198e804d.png](559a67ab9d5e4022b719177d8a4d8a2a.png)

这里几个没有结果，需要添加用户密码
ٔ扫描通过SMB管道可以访问的RCRPC服务
* use auxiliary/scanner/smb/pipe_dcerpc_auditor

SMB共享枚举（账号、密码）
* use auxiliary/scanner/smb/smb_enumshares
SMB用户枚举（账号、密码）
* use auxiliary/scanner/smb/smb_enumusers


SID枚举（账号、密码）
* use auxiliary/scanner/smb/smb_lookupsid

![443231a278bdb0289d1221de3d2987d6.png](08b91f6368f6472b965fbefb2a6785f6.png)

### SSH

ssh的1和1.99版本有漏洞

▪ SSH 版本扫描
– use auxiliary/scanner/ssh/ssh_version

![568edf5cd88aa5e910cda77669b11c72.png](6d5aa58d396b4335b89db210f3f074da.png)

▪ SSH密码爆破
– use auxiliary/scanner/ssh/ssh_login
    ▪ set USERPASS_FILE /usr/share/metasploit-framework/data/wordlists/
root_userpass.txt;set VERBOSE false;run
向文件中添加一个自己的账户密码，这里做的是演示
vim /usr/share/metasploit-framework/data/wordlists/root_userpass.txt

![82db61e367f9b7575a6620bb8e19030d.png](299ccf9c691f4785a196983b5affbf7b.png)

▪ SSH公匙登陆
– use auxiliary/scanner/ssh/ssh_login_pubkey
▪ set KEY_FILE id_rsa; set USERNAME root;run
这里有一些硬件出厂使用的相同的默认密钥文件，可以下载下来，然后寻找使用相同密钥设备的文件


![5e37d5bd4ca00eef3dfcf1f9dc19304a.png](5c12f909b8e940a9b99774a2eae5fe33.png)
























