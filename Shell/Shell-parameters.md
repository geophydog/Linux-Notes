:hotel: [Return Home Page](https://github.com/geophydog/geophydog.github.io/blob/master/README.md#welcome-to-geophydogs-self-pages)
## 1. 获取命令行参数
```
例如执行脚本：
sh test.sh file1 file2 file3 file4
```
- Script name: $0
- First parameter: $1
- Second parameter: $2
- Third parameters: $3
```
以此类推下去。
```

***

## 2. 获取参数个数
```
$#, 但是其不包含脚本本身。
```
```shell
if [ $# != 4 ]; then
  echo "Usage: $0 file1 file2 file3 file4"
  exit 1
fi
```

***

## 3. 命令行参数列表
```
$@ 或者 $*, 但是 "$*" 和 "$@" (加了引号）, "$*" 将所有参数解释成一个一个字符串，而 "$@" 是一个参数数组。
```
```shell
for ch in "$@"
do
  echo $ch
done

echo "++++++++++++++++++++++++"
for ch in "$*
do
  echo $ch
done
```
```
sh test.sh file1 file2 file3 file4 file5
```
- output:
```
file1
file2
file3
file4
file5
++++++++++++++++++++++++
file1 file2 file3 file4 file5
```
