readme教程
1.文字超链接<br>
给一段文字加入超链接的格式是这样的\[ 要显示的文字 \]( 链接的地址 )<br>
2.插入圆点符,编辑的时候使用的是星号 *<br>
要注意的是星号* 后面要有一个空格。否则显示为普通星号。<br>
3.缩进<br>
>一<br>
>>二<br>
>>>三<br>
>>>>四<br>
4.插入图片<br>
![]\(图片地址\)  即 叹号! + 方括号[ ] + 括号( ) 其中叹号里是图片的URL。<br>
5.给图片加上超链接<br>
[![baidu]](http://baidu.com)  <br>
[baidu]:http://www.baidu.com/img/bdlogo.gif "百度Logo"  <br>
注意上下文中的 baidu 是你自己起的标识的名称，可以随意，但是一定要保证上下两行的 标识 是一致的。<br>
6.插入代码片段<br>
我们需要在代码的上一行和下一行用` `` 标记。``` 不是三个单引号，而是数字1左边，Tab键上面的键。要实现语法高亮那么只要在 ``` 之后加上你的编程语言即可（忽略大小写）。c++语言可以写成c++也可以是cpp。<br>
# git-
小白理解教程
===========================
1.在本地建立一个仓库与远程仓库连接有2种方法
-----------------------------------
 a.`git clone 远程仓库地址`（可以是ssh密钥地址或者http地址）<br>
 b.在本地新建一个文件夹，然后`git init`初始化声明这个文件夹为一个git仓库，同时在此文件夹生成了.git文件，然后`git remote add origin git@github.com:flexmodule/organic.git`连接远程仓库<br>
git push -u origin master   创建一个 upStream （上传流），并将本地代码通过这个 upStream 推送到 别名为 origin 的仓库中的 master 分支上，-u ，就是创建 upStream 上传流，如果没有这个上传流就无法将代码推送到 github；同时，这个 upStream 只需要在初次推送代码的时候创建，以后就不用创建了<br>
 ----------------------------------------
2.git add -A和 git add .   git add -u
------------------------------------------
git add . ：他会监控工作区的状态树，使用它会把工作时的所有变化提交到暂存区，包括文件内容修改(modified)以及新文件(new)，但不包括被删除的文件。<br>
git add -u ：他仅监控已经被add的文件（即tracked file），他会将被修改的文件提交到暂存区。add -u 不会提交新文件（untracked file）。（git add --update的缩写）<br>
git add -A ：是上面两个功能的合集（git add --all的缩写）<br>
3.为Git命令创建一个快捷方式（别名）
  git config --global alias.<alias-name> <git-command>
4.git revert 命令用来撤销一个已经提交的快照。但是，它是通过搞清楚如何撤销这个提交引入的更改，然后在最后加上一个撤销了更改的 新 提交，而不是从项目历史中移除这个提交<br>
git reset 来重设更改时(提交不再被任何引用或引用日志所引用)，我们无法获得原来的样子——这个撤销是永远的。<br>
git reset --hard
重设缓冲区和工作目录，匹配最近的一次提交。除了取消缓存之外，--hard 标记告诉 Git 还要重写所有工作目录中的更改。换句话说：它清除了所有未提交的更改，所以在使用前确定你想扔掉你所有本地的开发。<br>
git clean -f移除当前目录下未被跟踪的文件。<br>
git commit --amend合并缓存的修改和上一次的提交，用新的快照替换上一个提交。缓存区没有文件时运行这个命令可以用来编辑上次提交的提交信息，而不会更改快照。仓促的提交在你日常开发过程中时常会发生。很容易就忘记了缓存一个文件或者弄错了提交信息的格式。--amend 标记是修复这些小意外的便捷方式。<br>
-------------------------------------------
常用命令
==================================


1.从master建立分支并切换过去  Git checkout –b new-branch master<br>
2.由当前分支建立新分支并切换过去 Git checkout –b new-branch<br>
3.删除本地分支： git branch –d branch1<br>
4.强制删除本地分支：Git branch –D branch1<br>
5.删除远程分支 ：git push origin - - delete branchname<br>
6.回退到历史某个版本：git reset --hard 版本号 <br>
把修改推到远程服务器：git push -f -u origin master (-f  : -force)<br>
　git reset --hard ＨＥＡＤ＾回退到上一个版本<br>
　git reset –hard　ＨＥＡＤ～１００回退１００个版本<br>
7.建立本地分支和远程分支的联系：<br><br><br>
git branch --set-upstream-to=origin/dev  dev (新版本)<br><br>
git branch --set-upstream devtest origin/devtest（老版本）<br>
８．Git revert撤销 某次操作，此次操作之前和之后的commit和history都会保留，并且把这次撤销作为一次最新的提交<br><br>
git revert HEAD                  撤销前一次 commit<br>
 git revert HEAD^               撤销前前一次 commit<br>
 git revert commit-id （比如：fa042ce57ebbe5bb9c8db709f719cec2c58ee7ff）撤销指定的版本，撤销也会作为一次提交进行保存。<br>
9. git checkout mywork<br>
git rebase origin<br>
在rebase的过程中，也许会出现冲突(conflict). 在这种情况，Git会停止rebase并会让你去解决 冲突；在解决完冲突后，用"git-add"命令去更新这些内容的索引(index), 然后，你无需执行 git-commit,只要执行:<br>
git rebase --continue<br>
这样git会继续应用(apply)余下的补丁。在任何时候，你可以用--abort参数来终止rebase的行动，并且"mywork" 分支会回到rebase开始前的状态。<br>
Git rebase --abort<br>
10.删除文件：git rm filename<br>
11.修改文件名或者搬移目录：git mv filename newfilename<br>
12.如果当前分支与多个主机存在追踪关系，那么这个时候-u选项会指定一个默认主机，这样后面就可以不加任何参数了<br>
Git push –u origin master(-u   :       -upstream)<br>
git pull --rebase,这里表示把你的本地当前分支里的每个提交(commit)取消掉，并且把它们临时 保存为补丁(patch)(这些补丁放到".git/rebase"目录中),然后把本地当前分支更新 为最新的"origin"分支，最后把保存的这些补丁应用到本地当前分支上。<br>
Git reset 与git revert <br>
1.	git revert是用一次新的commit来回滚之前的commit，git reset是直接删除指定的commit<br>
2.	git reset 是把HEAD向后移动了一下，而git revert是HEAD继续前进，只是新的commit的内容和要revert的内容正好相反，能够抵消要被revert的内容。<br>


