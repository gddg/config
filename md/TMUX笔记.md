# TMUX 笔记

mac首先iterm映射键盘 
`ctrl` 和   `windows` 交换
这样 `ctrl` ＋ `c` 就爽了。
MAC本身软件设置也可以设置`ctrl` 和 `windows` 交换

man tmux


**TMUX常用快捷键**

进入前

`tmux new -s  mysession1 `    新建一个回话 

`tmux a -t portage`  连接上回话

tmux new-session -d 'emerge -uDNvp @world'  

`C-b` `n`        下一个窗口。
`C-b` `方向键盘`   pane上下移动。


# `Ctrl`-`b` - `：` 进入后命令行#

new -s 回话名 

# `Ctrl`-`b`  (相当vi－esc)进入#

`s`       切换回话
`d`       分离－退出
`` ` ``   重命名
`t`       时钟 
` ? `     看键盘绑定
` , `     逗号重命名回话
` : `     命令行提示
` ' `     选择一个编号切换
` w `     选择当前窗口非交互
r  重新加载配置文件

一个session可以建立N个windows。
一个windows又支持N个pan。


##启动进入
tmux ls    列出所有session 
tmux a  -t 回话名
C-b  d     退出 
    

##回话操作##
`s`       session显示和切换
`d`       离开session
`$`       重命名当前session
`<c-z>`   挂起当前session
`s`       显示和切换


##窗口操作##
`w`   windows切换
`c	`   创建一个新窗口
`n`	 切换至下一窗口
`p`	 切换到上一个窗口
`,`	 逗号，重新命令当前窗口
`&`    关闭窗口

`l`   移动窗口
`"`	 水平分割窗口
`%`	 垂直分割窗口
 
`o`	 移动至下一个面板
`w`   当前窗口非激活
`输入窗口编号0-9`   选择
 

切换回话，C-b s
关闭窗口，实际操作是关闭
`x`   关闭当前pane


##pane操作##

`q `  显示pane的编号
`x`   关闭当前pane

`"` 创建横向分割
`%` 创建纵向分割

`方向键` 在pane直接移动
`o` 到下一个pane
`opt+方向键` 调整pane大小
`{ / }`左右pane交换
`空格` 横竖切换

 没有创建的操作，直接在window风格就可以了。
 
##复制模式copy-mode

前缀 [ 进入复制模式
按 space 开始复制，移动光标选择复制区域
按 Enter 复制并退出copy-mode。
将光标移动到指定位置，按 PREIFX ] 粘贴
如果把tmux比作vim的话，那么我们大部分时间都是处于编辑模式，我们复制的时候可不可以像vim一样移动呢？只需要在配置文件(~/.tmux.conf)中加入如下行即可。

copy-mode 将快捷键设置为vi 模式
setw -g mode-keys vi

 
gao@ubuntu15:~$ tmux ls
0: 1 windows (created Sat Dec 26 18:06:57 2015) [108x40] (attached)
2: 2 windows (created Sun Dec 27 10:17:55 2015) [108x40] (attached)
clang: 1 windows (created Sun Dec 27 09:55:16 2015) [108x40] (attached)
**go: 2 windows** (created Sun Dec 27 11:48:22 2015) [108x40] (attached)

下状态
[go] 0:apple2* 1:bash-
w 2个窗口
(0)  0: apple2* "ubuntu15"
(1)  1: bash- "ubuntu15"


   
  
## 参考 ##

终端环境之tmux
<http://foocoder.com/blog/zhong-duan-huan-jing-zhi-tmux.html/>

tmux
<https://wiki.gentoo.org/wiki/Tmux>

Tmux_(简体中文) 里面有很多shell可以之后看。
<https://wiki.archlinux.org/index.php/Tmux_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>


一个IT人员实用的工具：Tmux 
<http://www.cnblogs.com/wsjhk/p/4469452.html>


如何使用 powerline扩展我们的 tmux状态栏
<http://zpz.name/1989/>
<https://github.com/erikw/tmux-powerline>

配置解释  常用按键
<http://blog.csdn.net/robertbaker/article/details/42172203>

快速启动几个窗口的配置文件
<https://github.com/xuxiaodong/tmuxen/blob/master/tmuxen>


