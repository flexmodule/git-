readme教程
1.文字超链接<br>
给一段文字加入超链接的格式是这样的\ [ 要显示的文字 \]( 链接的地址 )<br>
2.插入圆点符,编辑的时候使用的是星号 *<br>
要注意的是星号* 后面要有一个空格。否则显示为普通星号。<br>
3.缩进<br>
>一<br>
>>二<br>
>>>三<br>
>>>>四<br>
4.插入图片<br>
![](http://www.baidu.com/img/bdlogo.gif) 即 叹号! + 方括号[ ] + 括号( ) 其中叹号里是图片的URL。<br>
5.给图片加上超链接<br>
[![baidu]](http://baidu.com)  <br>
[baidu]:http://www.baidu.com/img/bdlogo.gif "百度Logo"  <br>
注意上下文中的 baidu 是你自己起的标识的名称，可以随意，但是一定要保证上下两行的 标识 是一致的。<br>
6.插入代码片段<br>
我们需要在代码的上一行和下一行用` `` 标记。``` 不是三个单引号，而是数字1左边，Tab键上面的键。要实现语法高亮那么只要在 ``` 之后加上你的编程语言即可（忽略大小写）。c++语言可以写成c++也可以是cpp。<br>
# git-
小白理解教程
1.在本地建立一个仓库与远程仓库连接有2种方法
-----------------------------------
 a.`git clone 远程仓库地址`（可以是ssh密钥地址或者http地址）<br>
 b.在本地新建一个文件夹，然后`git init`初始化声明这是一个git仓库，然后`git remote add origin git@github.com:flexmodule/organic.git`连接远程仓库<br>

