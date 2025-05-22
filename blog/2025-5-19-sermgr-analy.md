---
slug: long-blog-post
title: Long Blog Post
tags: [cyber security]
---
# sermmgr分析

## cdecl
(1) 参数传递顺序
参数从右向左依次压入栈中。
示例：调用 func(a, b, c) 时，参数压栈顺序为 c → b → a。

(2) 堆栈清理责任
调用者（Caller）负责清理堆栈。
函数调用结束后，调用者通过 add esp, N（N 为参数总大小）恢复栈指针。

(3) 名称修饰（Name Mangling）
在编译后的符号表中，函数名会被修饰为 _funcname（如 _main）。

(4) 可变参数支持
__cdecl 是唯一支持 可变参数函数（如 printf）的调用约定。

# qemu
qemu-img create -f qcow2 routeros.img 4G创建一个名为 routeros.img 的虚拟硬盘镜像文件，格式为 qcow2，容量为 4GB。
qemu-system-x86_64 -cdrom mikrotik-7.16.2.iso -boot d -m 512 -hda routeros.img -net nic -net user启动一个 x86_64 架构的虚拟机，从 ISO 镜像安装 MikroTik RouterOS 到虚拟硬盘。
qemu-system-x86_64 -boot d -m 512 -hda routeros.img -net nic -net user从虚拟硬盘启动已安装的 RouterOS 系统。
