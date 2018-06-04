
```
Shell 实现一个数加一，有如下三种方式:
```

### :one: ((x=x+1))
### :two: x=$(($x+1))
### :three: let x=x+1


### code
```
let x=0
let y=0

((x=x+1))
y=$(($y+1))

echo ${x}
echo ${y}

let y=y+1
echo ${y}
```

### output
```
1
1
2
```
