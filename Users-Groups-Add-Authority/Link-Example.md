:hotel: [Return to Home Page](https://github.com/geophydog/geophydog.github.io/blob/master/README.md#welcome-to-geophydogs-self-pages)
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
## 2. ; 分号操作符
```
分号操作符可以使你连续顺序执行多个命令
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

***

:book:
## 5. ! 非操作符
```
我们先新建一些文件
```
```
touch a.txt b.txt c.pdf d.pdf e.html f.html
```
```
现在将除以.txt 的文件都删掉
```
```
rm !(*.txt)
```
![!.jpg](https://github.com/geophydog/Linux-Notes/blob/master/Users-Groups-Add-Authority/images/!.jpg)

***

## 6. && ||联合操作
```
ping www.baidu.com && echo "Verified" || echo "Host down"
```
```
ping 通了输出“Verified” 否则输出“Host down”
```
![And-or.jpg](https://github.com/geophydog/Linux-Notes/blob/master/Users-Groups-Add-Authority/images/And-or.jpg)

***

## 7. {} 命令合并操作符
```
合并两个或多个命令， 第二个命令依赖于第一个命令的执行。
```
```
[ -f ~/Downloads/xyz.txt ] || {touch ~/Downloads/xyz.txt; echo "The file xyz.txt does not exist! New file is created!"}
```

***

## 8. () 有限操作符 
```
(command1 && command2) || (command3 && command4)
```
```
如果command1执行失败，command2不会被执行，但是command3会被执行，command4依赖于command3退出状态。
```
