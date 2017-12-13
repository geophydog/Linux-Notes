## 访问控制表(ACL: access control list)
```
现假设有两个用户组要新建： readers 和 editors；
其中readers用户组有两个用户：xfeng1 和 xfeng2，editors用户组有两个用户：xfeng3 和 xfeng4；
```
### 创建用户  
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

### 创建用户组并添加用户
    #### 添加用户组
  ```
  sudo groupadd readers
  sudo groupadd editors
  ```
   #### 添加用户到相应用户组  
  ```
  sudo usermod -a -G readers xfeng1
  sudo usermod -a -G readers xfeng2
  sudo usermod -a -G editors xfeng3
  sudo usermod -a -G editors xfeng4
  ```
