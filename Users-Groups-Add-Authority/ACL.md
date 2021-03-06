:hotel: [Return Home Page](https://github.com/geophydog/geophydog.github.io/blob/master/README.md#welcome-to-geophydogs-self-pages)
## 访问控制表(ACL: access control list)
```
现假设有两个用户组要新建： readers 和 editors；
其中readers用户组有两个用户：xfeng1 和 xfeng2，editors用户组有两个用户：xfeng3 和 xfeng4；
```
### 1. 创建用户  
  ```
  sudo useradd -m xfeng1
  sudo useradd -m xfeng2
  sudo useradd -m xfeng3
  sudo useradd -m xfeng4
  ```
  
- 用了 -m 选项是为了让 xfeng1, xfeng2, xfeng3 和 xfeng4 都有家目录  
  
```
sudo passwd xfeng1  
sudo passwd xfeng2  
sudo passwd xfeng3  
sudo passwd xfeng4  
```

***

### 2. 创建用户组并添加用户
  #### 2.1 添加用户组
  ```
  sudo groupadd readers
  sudo groupadd editors
  ```
  #### 2.2 添加用户到相应用户组  
  ```
  sudo usermod -a -G readers xfeng1
  sudo usermod -a -G readers xfeng2
  sudo usermod -a -G editors xfeng3
  sudo usermod -a -G editors xfeng4
  ```
- 用了 -a： 添加（append）； -G： groupname

***
### 3. 使用访问控制表（ACL）
``` 
现在问题为你有一个目录 test_dir 给readers用户组成员读取权限，同时给 editors 用户组读写权限，此时便用到 setfacl 命令。
```
```
setfacl OPTION X:NAME:Y test_dir
OPTION 为可选选项；
X 可以使用户或用户组；
NAME 为用户或用户组的名字；
Y 为权限 rwx。
```
