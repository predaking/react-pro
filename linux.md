# 目录

+ linux

## Linux

### 杂项

#### 什么是硬链接？什么是软链接？

答：无论硬链接还是软链接都是一个文件

硬链接是通过索引节点号( inode)连接文件的，保存在磁盘上的任何文件都会被分配一个编号叫索引节点号。一个文件可以有多个硬链接，这些硬链接的inode都是相同的，都指向目标文件(类似指针)。删除任意一个硬链接都不会影响目标文件，所有的硬链接被删除才意味着目标文件被真正删除，目标文件数据块被真正释放。可以通过建立多个硬链接来防止文件误删

软链接又叫符号链接，类似与windows系统的快捷方式，软链接实际上存储的是目标文件的位置信息，一个软链接就有一个单独的各不相同的inode号，表示软链接本身就是一个独立的文件，所以软链接跟目标文件指向的是不同的数据块，目标文件被删除软链接也还存在，只不过存储的位置信息就是一个无效的指向，无效的链接。

？只有Linux系统是这样吗？
？文件的索引节点号到底是个什么东西？是如何的记录方式？
？如何curd软硬链接（Linux实操）？
？如果目标文件存在硬链接的情况下强制删除目标文件会怎样？
