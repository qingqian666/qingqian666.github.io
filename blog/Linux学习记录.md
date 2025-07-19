---
slug: Netcat
title: Netcat的简单使用
authors: guolei
tags: [cybersecurity,Linux]
---

# 文件一致性校验——`md5sum`

## 说明：
- md5sum 是校验文件内容，与文件名是否相同无关
- md5sum值逐位校验，所以文件越大，校验时间越长

## 使用：
md5sum [选项]... [文件]

其中，常用的选项包括：

- -b 或 --binary：以二进制模式读取文件

- -t 或 --text：以文本模式读取文件（默认）.例子：md5sum 1.txt输出则是a72432d57f2d3ec1f8a136e3fecb906f  1.txt

- -c 或 --check：读取MD5校验和文件并检查它们

### 方法：
- 将生成的值存到.md5文件中：`md5sum data >data.md5`


``` js
➜  Downloads md5sum gdbserver

a72432d57f2d3ec1f8a136e3fecb906f  gdbserver

➜  Downloads md5sum gdbserver > 1.md5

➜  Downloads cat 1.md5

a72432d57f2d3ec1f8a136e3fecb906f  gdbserver

```
- 把下载的文件file和该文件的file.md5报文摘要文件放在同一个目录下，然后用如下命令进行验证：

       `md5sum -c file.md5`

    然后如果验证成功，则会输出:OK