命令行参数

* windows下打开命令行窗口：_Win+R输入cmd，回车_

* 定义：用户在CMD窗口输入可执行文件名的方式启动程序时，跟在可执行文件后面的那些字符串，称为“命令行参数”。命令行字符串可以多个，以空格分隔。

eg：

```
copy file1.txt file2.txt    //启动了copy这个程序，将file1里的内容拷贝到file2中去，copy、file1.txt、file2.txt都是命令行参数
```

* 如果自己编写一个copy程序，则必须能够获得命令行参数。为此，在编写此程序时，需要在想获得命令行参数的c++程序的main函数中必须注意以下格式：

![](/assets/Screenshot from 2017-06-05 15:19:55.png)

eg：

![](/assets/Screenshot from 2017-06-05 15:21:24.png)

\*命令行参数内部有空格时，用“ ”括起来即可，如上例中最后一个参数hello word.

