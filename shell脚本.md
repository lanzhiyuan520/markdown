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

