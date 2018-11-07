### 							shell脚本

##### 注释

```shell
#   #通常是以#为注释
```

*在通常的shell脚本中，井号(#)用作注释行。shell并不会处理shell脚本中的注释行。然而，
shell脚本文件的第一行是个例外，#后面的惊叹号会告诉shell用哪个shell来运行脚本(是的，你
可以使用bash shell，同时还可以使用另一个shell来运行你的脚本)*

##### 使用变量

```shell
$  #使用$符号可以引用一个变量
```

##### 输出字符串

```shell
echo 'this is a first shell'  #使用echo可以输出一条消息
echo $UID  #输出UID
```

##### 定义变量

```shell
num=10  #定义一个变量为10
echo $num #使用$num来调用这个变量
num2=$num #给num2赋值
echo $num2 #输出为10  如果不加$符就输出num了
```

##### 从命令输出中提取信息，并将其赋给变量

```shell
testting=$(date)  #将date命令输出的值保存在testting变量中
testting=`who`  #这个和上一个是一样的
```

##### 重定向输入和输出

输出重定向

```shell
date > test  #重定向操作符创建了一个文件test(通过默认的umask设置)，并将date命令的输出重定向 到该文件				中。如果输出文件已经存在了，重定向操作符会用新的文件数据覆盖已有文件。
date >> test  #两个>号不会覆盖是在原有的基础上追加进去
```

输入重定向

```shell
wc < test  #wc命令可以对对数据中的文本进行计数。默认情况下，它会输出3个值 : 1.文本的行数 2.文本的词数 				3.文本的字节数
```

##### 运算

```shell
var1=$[1 + 5]  #以用美元符和 方括号($[ operation ])将数学表达式围起来。
echo $var1     #6
```

*注意：只支持整数运算*

##### 浮点数解决方案

```shell
variable=$(echo "options; expression" | bc)
#第一部分options允许你设置变量。如果你需要不止一个变量，可以用分号将其分开。
#expression参数定义了通过bc执行的数学表达式。
#例如：
	num=$(echo "scale=2;100 / 45" | bc)
	echo $num #2.22
```

##### if-then语句

```shell
if 执行的语句
then
	状态码为0时执行的语句
fi	
```

##### if-then-else语句

当if语句中的命令返回退出状态码0时，then部分中的命令会被执行，这跟普通的if-then 

语句一样。当if语句中的命令返回非零退出状态码时，bash shell会执行else部分中的命令 

```shell
if 	执行语句
then
	成功语句
else
	失败语句
fi	
```

##### 嵌套if

```shell
if 执行语句
then
	成功语句
else
	if 执行语句
	then
		成功语句
	else
    	失败语句
    fi
fi    
```

#### elif语句

```shell
if 执行语句
then
	成功语句
elif 执行语句
then
	成功一句
fi	
```

##### 数值比较

| 比较      | 描述                   |
| --------- | ---------------------- |
| n1 -eq n2 | 检查n1是否与n2相等     |
| n1 -ge n2 | 检查n1是否大于或等于n2 |
| n1 -gt n2 | 检查n1是否大于n2       |
| n1 -le n2 | 检查n1是否小于或等于n2 |
| n1 -lt n2 | 检查n1是否小于n2       |
| n1 -ne n2 | 检查n1是否不等于n2     |

```shell
if [ 10 -ge 5 ]
then
	echo '大于'
else
	echo '小于'
fi	
#输出echo  注意[之后和]之前有空格  
```

*注意：浮点数不能比较*

##### 字符串比较

| 比较         | 描述                   |
| ------------ | ---------------------- |
| str1 = str2  | 检查str1是否和str2相同 |
| str1 != str2 | 检查str1是否和str2不同 |
| str1 < str2  | 检查str1是否比str2小   |
| str1 > str2  | 检查str1是否比str2大   |
| -n str1      | 检查str1的长度是否非0  |
| -z str1      | 检查str1的长度是否为0  |

##### 文件比较

| 比较            | 描述                                     |
| --------------- | ---------------------------------------- |
| -d file         | 检查file是否存在并是一个目录             |
| -e file         | 检查file是否存在                         |
| -f file         | 检查file是否存在并是一个文件             |
| -r file         | 检查file是否存在并可读                   |
| -s file         | 检查file是否存在并非空                   |
| -w file         | 检查file是否存在并可写                   |
| -x file         | 检查file是否存在并可执行                 |
| -O file         | 检查file是否存在并属当前用户所有         |
| -G file         | 检查file是否存在并且默认组与当前用户相同 |
| file1 -nt file2 | 检查file1是否比file2新                   |
| file1 -ot file2 | 检查file1是否比file2旧                   |