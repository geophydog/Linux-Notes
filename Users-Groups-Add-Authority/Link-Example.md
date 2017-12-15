:book: 
## 1. & 和号操作符
### 1.1 后台执行命令
```
ping www.baidu.com &
```
### 1.2 同时在后台执行两个命令
```
sudo yum update & mkdir test &
```

***

:book: 
## 2. ; 分好操作符
```
分好操作符可以使你连续顺序执行多个命令
```
```
sudo yum update; sudo yum upgrade; mkdir test
```

***

:book:
## 3. && 与操作符
```
第一个命令执行成功才会执行第二个名令
```
```
ping www.baidu.com &&links www.baidu.com
```

***

:book:
## 4. || 或操作符
```
允许在第一个命令失败的情况下执行第二个命令。
举个例子，在非root用户状态下执行 yum update不成功，再执行links www.baidu.com成功;
```
```
yum update || links www.baidu.com
```
```
第一条命令“yum update”返回状态值为1，第二条命令“links www”会执行。
```
```
mkdir test || links www.baidu.com
```
```
第一条命令状态返回值为0， 第二条命令不会被执行。
```
