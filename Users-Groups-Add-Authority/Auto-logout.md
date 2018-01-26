:hotel:[Return to Home Page](https://github.com/geophydog/geophydog.github.io/blob/master/README.md)

***

# Auto-logout from like-Unix System

***

### :one: "TMOUT"
- Add "TMOUT=XXX" to ".bashrc" or ".bash_profile", if you won't do any activity you will automaticall logout from your server after XXX seconds.

  _Example_
```shell
TMOUT=30
```
```shell
等待输入超时：自动登出
Connection to 114.212.112.8 closed.
```

***

### :two: write shell script with "ROOT" authority
```shell
# vim /etc/profile.d/autologout.sh
```

  _contents of "autologout.sh"_
```shell
TMOUT=100
readonly TMOUT
export TMOUT
```

  _Give "autologout.sh" executable authority_
```shell
# chmod +x /etc/profile.d/autologout.sh
```
  _Logout or restart you system and user will automatically logout if it doesn't do any activity after 100 seconds_
