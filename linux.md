# linux

2022-05-21

源笔记：[linux 石墨文档](https://shimo.im/docs/XKq4MJZYNDC4JNkN/)

### ssh连接：

```
sudo apt install net-tools
sudo apt install openssh-server
sudo /etc/init.d/ssh start
ifconfig
（与mobaxterm）
```

使用cmd：

```
ssh mleon@192.168.140.133
```

### 写C语言：

安装：

```
which gcc
```

如果有安装则会返回/usr/bin/gcc，如果没有安装则没有返回。 编译：

```
gcc -o hello hello.c
```

运行：

```
./hello
```

### 后台管理

1. 将标准输出放到name.log中

`nohup python -u scripts.py > name.log 2>&1 &`

只输出错误信息到日志文件

`nohup ./program >/dev/null 2>log &`

什么信息也不要
`nohup python3 main.py >/dev/null 2>&1 &`

2. 查看后台，杀死后台

`ps ux`

`kill PID_NUMBER`


### vim

多行注释：

ctrl+v ; I ; //

跳跃到行首，行尾：

* shift + 6 （^）跳跃到本行的开头（不包含空白字符）
* shift + 4 （$）跳跃到本行的末尾 （按0也可以跳到开头，包含空白字符）

### .vimrc配置

[Vim 配置入门 作者： 阮一峰](https://www.ruanyifeng.com/blog/2018/09/vimrc.html)

基础配置：

```
set syntax=on # 打开语法高亮
set showmode # 在底部显示当前处于命令模式还是插入模式
set showcmd # 命令模式下，在底部显示，当前键入的指令。
set encoding=utf-8 # 使用utf-8编码
```

缩进：

```
set autoindent # 按下回车键后，下一行的缩进会自动跟上一行的缩进保持一致。
set tabstop=4 # 按下Tab键时，Vim显示的空格数
set shiftwidth=4 # 在文本上按下>>（增加一级缩进）、<<（取消一级缩进）或者==（取消全部缩进）时，每一级的字符数。
set expandtab # 由于 Tab 键在不同的编辑器缩进不一致，该设置自动将 Tab 转为空格。
set softtabstop=4 # Tab 转为多少个空格。
```

外观：

```
set number # 显示行数
set wrap # 自动折行
set linebreak # 只有遇到指定的符号（比如空格、连词号和其他标点符号），才发生折行。也就是说，不会在单词内部折行。
```

搜索：

```
set showmatch # 光标遇到圆括号、方括号、大括号时，自动高亮对应的另一个圆括号、方括号和大括号。
set hlsearch # 搜索时，高亮显示匹配结果。
set ignorecase # 搜索时忽略大小写。
```

编辑：

```
set noerrorbells # 出错时，不要发出响声。
set visualbell # 出错时，发出视觉提示，通常是屏幕闪烁。
set autoread # 开文件监视。如果在编辑过程中文件发生外部改变（比如被别的编辑器编辑了），就会发出提示。
```

中文乱码：

```
set fileencodings=utf-8,ucs-bom,gb180830,gbk,gb2312,cp936
set termencoding=utf-8
set encoding=utf-8
```