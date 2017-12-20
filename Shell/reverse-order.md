:hotel:[Return Home Page](https://github.com/geophydog/geophydog.github.io)

### :one: Unix 风格，多个命令组合

- 文件内容为：

```
A
B
C
D
E
F
G
H
I
```

- 执行命令：

```
nl filename | sort -nr | cut -f2
```
- output:
```
I
H
G
F
E
D
C
B
A
```

- nl filename 在文件内容前加上行号：

```
1 A
2 B
3 C
4 D
5 E
6 F
7 G
8 H
9 I
```

- nl finame | sort -k1 -nr 按照第一列（行号）倒序排列：

```
9 I
8 H
7 G
6 F
5 E
4 D
3 C
2 B
1 A
```

- nl finame | sort -k1 -nr | cut -f2 倒序后截取第二列
```
I
H
G
F
E
D
C
B
A
```

### :two: tac 命令
```
tac filename
```

***

### :three: AWK 方法
```
awk '{line[NR]=$0} END {for(i=NR;i>0;i--) print line[i]}' filename
```

***

### :four: VI or VIM
```
:g/^/m0
```

***

### :five: shell 编程，利用递归
```
revread(){
    local line
    read line || return 0
    revread
    echo ${line}
}
revread < filename
```
