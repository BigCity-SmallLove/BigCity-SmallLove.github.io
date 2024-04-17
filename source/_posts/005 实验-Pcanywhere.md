005 实验-Pcanywhere

## Contents

- [Contents]()
- [题目]()
- [过程]()

## 题目

利用第三放服务（Pcanywhere）提升权限的方法
![](/resources/f71ff1bf4a88863bf2ae2b1b7e4be3fc.png)

## 过程

1. 在实验中访问http://172.16.12.2/index.php，成功连接到webshell
![](/resources/9e0585aaae6b73fafe42d13548d3c58e.png)
![](/resources/eb1faf6b71fb6a15f8a035cc31f8fa4b.png)
2. 分析该服务器端口服务
![](/resources/e89f4fe707173434a518223cf5fa3f0f.png)
5631端口是开启的，是pcanywhere服务
3. 去找pcanywhere的密码存储的文件
![](/resources/2df63b4545ba7f06ed12170ebb12d714.png)
该文件一般是以.CIF为后缀名，本环境中的密码文件为：PCA.test.CIF
下载该文件
4. 获取账号密码
![](/resources/1f2d53e8a2598347cf39f27b81268637.png)
5. 用pcanywhere登录
![](/resources/085c38112cc00ff46e02e436f8fb1f6e.png)
打开这个刚创建的新主控端
![](/resources/ca987d1cda571894be1494a4176ed5dd.png)
输入账号密码
![](/resources/fe1ac9f4ba009b99582c9066ab37cbf6.png)
连接上了，屏幕是花的
![](/resources/a3aeb7419a97a84ee411610a712883ad.png)
反正成功了