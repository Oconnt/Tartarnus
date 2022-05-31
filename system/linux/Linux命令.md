# Linux命令

### 环境变量

 1）env命令 

 在Shell下，用env命令查看当前用户全部的环境变量。 



### history （查看历史命令）

1.语法：
history [参数]

2.功能：
  查看已经执行过历史命令。如想查询某个用户在系统上执行了什么命令，可以使用root用户身份登录系统，检查Home目录下的用户主目录下的“.bash_history”文件，该文件记录了用户所使用的命令和历史信息。

3.参数：
n   打印最近的n条历史命令。
-N   显示历史记录中最近的N个记录。
-c   清空当前历史命令。
-a   将目前新增的历史指令新增入 histfiles 中，若没有加 histfiles,则预设写入 ~/.bash_history。
-r   将历史命令文件中的命令读入当前历史命令缓冲区。
-w   将当前历史命令缓冲区命令写入历史命令文件中。
-d<offset>   删除历史记录中第offset个命令。
-n<filename>   读取指定文件。
4.常用范例：

#### 例一：查看历史执行记录

**命令：history**

[root@localhost ~]# history
    1  ll
    2  cd /
    3  cd /opt/
    4  cd /sbin/
    5  ll
    6  cd ..
    7  cd /opt/sbin
    8  cd /opt
    9  cd /sbin/
   10  cd ..//
   ...
  420  ln -sv /usr/games/test/test/test1 /usr/games/test/test/test2
  421  cd test2
  422  ll
  423  history
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16

#### 例二：查看历史执行记录最近10 条

**命令：history 10**

[root@localhost ~]# history 10
  415  cat color.sh 
  416  cd test
  417  mkdir test1
  418  mkdir test2
  419  ll
  420  ln -sv /usr/games/test/test/test1 /usr/games/test/test/test2
  421  cd test2
  422  ll
  423  history
  424  history 10
1
2
3
4
5
6
7
8
9
10
11

#### 例三：执行历史记录第 5 条命令

**命令：!5**

[root@localhost ~]# !5
ll
总用量 8
drwxr-xr-x. 2 root root    6 5月  12 14:29 公共
drwxr-xr-x. 2 root root    6 5月  12 14:29 模板
drwxr-xr-x. 2 root root    6 5月  12 14:29 视频
drwxr-xr-x. 2 root root    6 5月  12 14:29 图片
drwxr-xr-x. 2 root root    6 5月  12 14:29 文档
drwxr-xr-x. 2 root root    6 5月  12 14:29 下载
drwxr-xr-x. 2 root root    6 5月  12 14:29 音乐
drwxr-xr-x. 2 root root    6 5月  12 14:29 桌面
-rw-------. 1 root root 1247 5月  12 14:24 anaconda-ks.cfg
-rw-r--r--. 1 root root 1526 5月  12 14:29 initial-setup-ks.cfg
1
2
3
4
5
6
7
8
9
10
11
12
13

#### 例四：执行上一条命令

**命令：!!**

[root@localhost ~]# !!
ll
总用量 8
drwxr-xr-x. 2 root root    6 5月  12 14:29 公共
drwxr-xr-x. 2 root root    6 5月  12 14:29 模板
drwxr-xr-x. 2 root root    6 5月  12 14:29 视频
drwxr-xr-x. 2 root root    6 5月  12 14:29 图片
drwxr-xr-x. 2 root root    6 5月  12 14:29 文档
drwxr-xr-x. 2 root root    6 5月  12 14:29 下载
drwxr-xr-x. 2 root root    6 5月  12 14:29 音乐
drwxr-xr-x. 2 root root    6 5月  12 14:29 桌面
-rw-------. 1 root root 1247 5月  12 14:24 anaconda-ks.cfg
-rw-r--r--. 1 root root 1526 5月  12 14:29 initial-setup-ks.cfg
1
2
3
4
5
6
7
8
9
10
11
12
13

#### 例五：执行最后一次以his开头的命令

**命令：!his**

  !代表的是字符串,这个String可以随便输，Shell会从最后一条历史命令向前搜索，最先匹配的一条命令将会得到执行。

[root@localhost ~]# !his
history 10
  417  mkdir test1
  418  mkdir test2
  419  ll
  420  ln -sv /usr/games/test/test/test1 /usr/games/test/test/test2
  421  cd test2
  422  ll
  423  history
  424  history 10
  425  ll
  426  history 10

### vim命令

 ![img](../../image/vi-vim-cheat-sheet-sch.gif) 