msf信息收集--mssql+ftp

## mssql
```
▪ Mssql扫描端口
– TCP 1433 （动态端口）/ UDP 1434 （查询TCP端口号）
– use auxiliary/scanner/mssql/mssql_ping 
▪ 爆破mssql密码
– use auxiliary/scanner/mssql/mssql_login
▪ 远程执行代码
– use auxiliary/admin/mssql/mssql_exec
– set CMD net user user pass /ADD
```

## ftp
```
▪ FTP 版本扫描
– use auxiliary/scanner/ftp/ftp_version
– use auxiliary/scanner/ftp/anonymous
– use auxiliary/scanner/ftp/ftp_login
▪ use auxiliary/scanner/ [tab]
– Display all 479 possibilities? (y or n)
```
### mssql
▪ Mssql扫描端口
– TCP 1433 （动态端口）/ UDP 1434 （查询TCP端口号）
– use auxiliary/scanner/mssql/mssql_ping 
▪ 爆破mssql密码
– use auxiliary/scanner/mssql/mssql_login
▪ 远程执行代码
– use auxiliary/admin/mssql/mssql_exec
– set CMD net user user pass /ADD

### ftp
▪ FTP 版本扫描
– use auxiliary/scanner/ftp/ftp_version

![be4f5f36b0d3fa364dab551350e925cb.png](0cdc26d899664cdfa1ffda6f35e31ffc.png)

– use auxiliary/scanner/ftp/anonymous


![2df9f491f53dc000d3f2d73d331428c9.png](86d9f4a13a114931b761b9d986f585a3.png)


– use auxiliary/scanner/ftp/ftp_login
▪ use auxiliary/scanner/ [tab]
– Display all 479 possibilities? (y or n)




















