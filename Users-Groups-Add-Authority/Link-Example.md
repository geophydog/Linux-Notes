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

## 2. ; 分好操作符
```
分好操作符可以使你连续顺序执行多个命令
```
```
sudo yum update; sudo yum upgrade; mkdir test
```
