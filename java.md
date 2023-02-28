## scoop安装java

```plain
scoop bucket add java
scoop install oraclejdk
scoop install openjdk16

scoop bucket add extras
scoop install idea

# Switching Javas
scoop reset <java>[@<version>]
```
# idea的使用

## 安装vim插件

>IdeaVim插件安装配置：
>(1) 在File->Setting -> Plugins -> Browse repositories中查找IdeaVim插件安装即可。
>(2)在File->Setting -> Keymap中查找Vim Emulator，设定激活/关闭IdeaVim模拟器的自定义快捷键，我设定为Ctrl+；（分号）
>————————————————
>版权声明：本文为CSDN博主「zistxym」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
>原文链接：[https://blog.csdn.net/zistxym/article/details/86546398](https://blog.csdn.net/zistxym/article/details/86546398)
## idea快捷键

alt+insert

自动对齐代码 Reformat code

File | Settings | Keymap | Reformat code(ctrl+alt+I)

看文档

Quick Documentation(ctrl+Q)

## [IDEA] 展示一个类的所有方法

View | Tool Windows | Structure

alt+7

或者 ctrl+F12

## 

