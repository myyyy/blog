---
layout: post
title: python pdb调试
description: an example of a blog post with giscus comments
tags: ["python"]
giscus_comments: true
related_posts: false
---

## 在python中使用pdb模块可以进行调试

``` python
import pdb
pdb.set_trace()
```

也可以使用python -m pdb mysqcript.py这样的方式

(Pdb) 会自动停在第一行，等待调试,这时你可以看看 帮助
(Pdb) h
    说明下这几个关键 命令

* 断点设置
   (Pdb)`b`  10 #断点设置在本py的第10行
   或(Pdb)b  ots.py:20 #断点设置到 ots.py第20行
   删除断点（Pdb）b #查看断点编号
            (Pdb)cl 2 #删除第2个断点
* 运行
    (Pdb)n #单步运行
    (Pdb)s #细点运行 也就是会下到，方法
    (Pdb)`c` #跳到下个断点
* 查看
    (Pdb)`p` param #查看当前 变量值
    (Pdb)l #查看运行到某处代码
    (Pdb)a #查看全部栈内变量
    (Pdb)w 列出目前call stack 中的所在层。
    (Pdb)d 在call stack中往下移一层
    (Pdb)u 在call stack中往上移一层。如果在上移一层之后按下 n ,则会在上移之后的一层执行下一个叙述,之前的 function call 就自动返回。
    (Pdb)cl 清除指定的断点。如果没有带参数,则清除所有断点。
    (Pdb)disable 取消所有断点的功能,但仍然保留这些断点。
    (Pdb)enable 恢复断点的功能。
    (Pdb)ignore 设定断点的忽略次数。如果没指定 count,其初始 为 0。当 count 为 0 时,断点会正常动作。若有指定 count,则每次执行到该中断, count 就少 1,直到 count 数为 0。
    (Pdb)condition bpnumber [condition]
    (Pdb)j(ump) lineNo. 跳到某行执行。只有在 call stack 的最底部才能作用。
    (Pdb)l  列出目前所在档案中的位置。连续地 l 命令会一直列到档案结尾,可以使用指定行数或范围来打印。
    (Pdb)pp 和 p 命令类似,但是使用 pprint module(没用过 pprint,详情请参考 Python Library Reference)。
    (Pdb)alias 以一个"别名"代替"一群除错命令",有点类似 c/c++ 的 macro(详情请参考 Python Library Reference)。
    (Pdb)unalias 取消某个 alias。
    (Pdb)[!]statement 在目前的环境(context)中执行叙述。

