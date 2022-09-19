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

#### **例一：查看历史执行记录**

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

**常用命令：**

**删除：**

d - 删除当前行

行号 + d - 删除指定行

行号， 行号 + d - 删除指定多行



**回滚：**

 u  - 撤销上一步的操作
Ctrl+r - 恢复上一步被撤销的操作 





### grep命令

Linux grep 命令用于查找文件里符合条件的字符串。

grep 指令用于查找内容包含指定的范本样式的文件，如果发现某文件的内容符合所指定的范本样式，预设 grep 指令会把含有范本样式的那一列显示出来。若不指定任何文件名称，或是所给予的文件名为 **-**，则 grep 指令会从标准输入设备读取数据。

**参数**：

- **-a 或 --text** : 不要忽略二进制的数据。
- **-A<显示行数> 或 --after-context=<显示行数>** : 除了显示符合范本样式的那一列之外，并显示该行之后的内容。
- **-b 或 --byte-offset** : 在显示符合样式的那一行之前，标示出该行第一个字符的编号。
- **-B<显示行数> 或 --before-context=<显示行数>** : 除了显示符合样式的那一行之外，并显示该行之前的内容。
- **-c 或 --count** : 计算符合样式的列数。
- **-C<显示行数> 或 --context=<显示行数>或-<显示行数>** : 除了显示符合样式的那一行之外，并显示该行之前后的内容。
- **-d <动作> 或 --directories=<动作>** : 当指定要查找的是目录而非文件时，必须使用这项参数，否则grep指令将回报信息并停止动作。
- **-e<范本样式> 或 --regexp=<范本样式>** : 指定字符串做为查找文件内容的样式。
- **-E 或 --extended-regexp** : 将样式为延伸的正则表达式来使用。
- **-f<规则文件> 或 --file=<规则文件>** : 指定规则文件，其内容含有一个或多个规则样式，让grep查找符合规则条件的文件内容，格式为每行一个规则样式。
- **-F 或 --fixed-regexp** : 将样式视为固定字符串的列表。
- **-G 或 --basic-regexp** : 将样式视为普通的表示法来使用。
- **-h 或 --no-filename** : 在显示符合样式的那一行之前，不标示该行所属的文件名称。
- **-H 或 --with-filename** : 在显示符合样式的那一行之前，表示该行所属的文件名称。
- **-i 或 --ignore-case** : 忽略字符大小写的差别。
- **-l 或 --file-with-matches** : 列出文件内容符合指定的样式的文件名称。
- **-L 或 --files-without-match** : 列出文件内容不符合指定的样式的文件名称。
- **-n 或 --line-number** : 在显示符合样式的那一行之前，标示出该行的列数编号。
- **-o 或 --only-matching** : 只显示匹配PATTERN 部分。
- **-q 或 --quiet或--silent** : 不显示任何信息。
- **-r 或 --recursive** : 此参数的效果和指定"-d recurse"参数相同。
- **-s 或 --no-messages** : 不显示错误信息。
- **-v 或 --invert-match** : 显示不包含匹配文本的所有行。
- **-V 或 --version** : 显示版本信息。
- **-w 或 --word-regexp** : 只显示全字符合的列。
- **-x --line-regexp** : 只显示全列符合的列。
- **-y** : 此参数的效果和指定"-i"参数相同

### yum命令

- 1. 列出所有可更新的软件清单命令：**yum check-update**
- 2. 更新所有软件命令：**yum update**
- 3. 仅安装指定的软件命令：**yum install **
- 4. 仅更新指定的软件命令：**yum update **
- 5. 列出所有可安裝的软件清单命令：**yum list**
- 6. 删除软件包命令：**yum remove **
- 7. 查找软件包命令：**yum search **

- 8. 清除缓存命令:

  - **yum clean packages**: 清除缓存目录下的软件包
  - **yum clean headers**: 清除缓存目录下的 headers
  - **yum clean oldheaders**: 清除缓存目录下旧的 headers
  - **yum clean, yum clean all (= yum clean packages; yum clean oldheaders)** :清除缓存目录下的软件包及旧的 headers

### chattr

Linux chattr命令用于改变文件属性。

这项指令可改变存放在ext2文件系统上的文件或目录属性，这些属性共有以下8种模式：

1. a：让文件或目录仅供附加用途。
2. b：不更新文件或目录的最后存取时间。
3. c：将文件或目录压缩后存放。
4. d：将文件或目录排除在倾倒操作之外。
5. i：不得任意更动文件或目录。
6. s：保密性删除文件或目录。
7. S：即时更新文件或目录。
8. u：预防意外删除。

**参数**

-R 递归处理，将指定目录下的所有文件及子目录一并处理。

　　-v<版本编号> 设置文件或目录版本。

　　-V 显示指令执行过程。

　　+<属性> 开启文件或目录的该项属性。

　　-<属性> 关闭文件或目录的该项属性。

　　=<属性> 指定文件或目录的该项属性

### tee

Linux tee命令用于读取标准输入的数据，并将其内容输出成文件。

tee指令会从标准输入设备读取数据，将其内容输出到标准输出设备，同时保存成文件。

**语法**

```
tee [-ai][--help][--version][文件...]
```

**参数**：

- -a或--append 　附加到既有文件的后面，而非覆盖它．
- -i或--ignore-interrupts 　忽略中断信号。
- --help 　在线帮助。
- --version 　显示版本信息。



### rpm

Linux rpm 命令用于管理套件。

rpm（英文全拼：redhat package manager） 原本是 Red Hat Linux 发行版专门用来管理 Linux 各项套件的程序，由于它遵循 GPL 规则且功能强大方便，因而广受欢迎。逐渐受到其他发行版的采用。RPM 套件管理方式的出现，让 Linux 易于安装，升级，间接提升了 Linux 的适用度。

**参数说明**：

- -a 　查询所有套件。
- -b<完成阶段><套件档>+或-t <完成阶段><套件档>+ 　设置包装套件的完成阶段，并指定套件档的文件名称。
- -c 　只列出组态配置文件，本参数需配合"-l"参数使用。
- -d 　只列出文本文件，本参数需配合"-l"参数使用。
- -e<套件档>或--erase<套件档> 　删除指定的套件。
- -f<文件>+ 　查询拥有指定文件的套件。
- -h或--hash 　套件安装时列出标记。
- -i 　显示套件的相关信息。
- -i<套件档>或--install<套件档> 　安装指定的套件档。
- -l 　显示套件的文件列表。
- -p<套件档>+ 　查询指定的RPM套件档。
- -q 　使用询问模式，当遇到任何问题时，rpm指令会先询问用户。
- -R 　显示套件的关联性信息。
- -s 　显示文件状态，本参数需配合"-l"参数使用。
- -U<套件档>或--upgrade<套件档> 升级指定的套件档。
- -v 　显示指令执行过程。
- -vv 　详细显示指令执行过程，便于排错。
- -addsign<套件档>+ 　在指定的套件里加上新的签名认证。
- --allfiles 　安装所有文件。
- --allmatches 　删除符合指定的套件所包含的文件。
- --badreloc 　发生错误时，重新配置文件。
- --buildroot<根目录> 　设置产生套件时，欲当作根目录的目录。
- --changelog 　显示套件的更改记录。
- --checksig<套件档>+ 　检验该套件的签名认证。
- --clean 　完成套件的包装后，删除包装过程中所建立的目录。
- --dbpath<数据库目录> 　设置欲存放RPM数据库的目录。
- --dump 　显示每个文件的验证信息。本参数需配合"-l"参数使用。
- --excludedocs 　安装套件时，不要安装文件。
- --excludepath<排除目录> 　忽略在指定目录里的所有文件。
- --force 　强行置换套件或文件。
- --ftpproxy<主机名称或IP地址> 　指定FTP代理服务器。
- --ftpport<通信端口> 　设置FTP服务器或代理服务器使用的通信端口。
- --help 　在线帮助。
- --httpproxy<主机名称或IP地址> 　指定HTTP代理服务器。
- --httpport<通信端口> 　设置HTTP服务器或代理服务器使用的通信端口。
- --ignorearch 　不验证套件档的结构正确性。
- --ignoreos 　不验证套件档的结构正确性。
- --ignoresize 　安装前不检查磁盘空间是否足够。
- --includedocs 　安装套件时，一并安装文件。
- --initdb 　确认有正确的数据库可以使用。
- --justdb 　更新数据库，当不变动任何文件。
- --nobulid 　不执行任何完成阶段。
- --nodeps 　不验证套件档的相互关联性。
- --nofiles 　不验证文件的属性。
- --nogpg 　略过所有GPG的签名认证。
- --nomd5 　不使用MD5编码演算确认文件的大小与正确性。
- --nopgp 　略过所有PGP的签名认证。
- --noorder 　不重新编排套件的安装顺序，以便满足其彼此间的关联性。
- --noscripts 　不执行任何安装Script文件。
- --notriggers 　不执行该套件包装内的任何Script文件。
- --oldpackage 　升级成旧版本的套件。
- --percent 　安装套件时显示完成度百分比。
- --pipe<执行指令> 　建立管道，把输出结果转为该执行指令的输入数据。
- --prefix<目的目录> 　若重新配置文件，就把文件放到指定的目录下。
- --provides 　查询该套件所提供的兼容度。
- --queryformat<档头格式> 　设置档头的表示方式。
- --querytags 　列出可用于档头格式的标签。
- --rcfile<配置文件> 　使用指定的配置文件。
- --rebulid<套件档> 　安装原始代码套件，重新产生二进制文件的套件。
- --rebuliddb 　以现有的数据库为主，重建一份数据库。
- --recompile<套件档> 　此参数的效果和指定"--rebulid"参数类似，当不产生套件档。
- --relocate<原目录>=<新目录> 　把本来会放到原目录下的文件改放到新目录。
- --replacefiles 　强行置换文件。
- --replacepkgs 　强行置换套件。
- --requires 　查询该套件所需要的兼容度。
- --resing<套件档>+ 　删除现有认证，重新产生签名认证。
- --rmsource 　完成套件的包装后，删除原始代码。
- --rmsource<文件> 　删除原始代码和指定的文件。
- --root<根目录> 　设置欲当作根目录的目录。
- --scripts 　列出安装套件的Script的变量。
- --setperms 　设置文件的权限。
- --setugids 　设置文件的拥有者和所属群组。
- --short-circuit 　直接略过指定完成阶段的步骤。
- --sign 　产生PGP或GPG的签名认证。
- --target=<安装平台>+ 　设置产生的套件的安装平台。
- --test 　仅作测试，并不真的安装套件。
- --timecheck<检查秒数> 　设置检查时间的计时秒数。
- --triggeredby<套件档> 　查询该套件的包装者。
- --triggers 　展示套件档内的包装Script。
- --verify 　此参数的效果和指定"-q"参数相同。
- --version 　显示版本信息。
- --whatprovides<功能特性> 　查询该套件对指定的功能特性所提供的兼容度。
- --whatrequires<功能特性> 　查询该套件对指定的功能特性所需要的兼容度。



### w

Linux w命令用于显示目前登入系统的用户信息。

执行这项指令可得知目前登入系统的用户有哪些人，以及他们正在执行的程序。

单独执行 w 指令会显示所有的用户，您也可指定用户名称，仅显示某位用户的相关信息。

**参数说明**：

- -f 　开启或关闭显示用户从何处登入系统。
- -h 　不显示各栏位的标题信息列。
- -l 　使用详细格式列表，此为预设值。
- -s 　使用简洁格式列表，不显示用户登入时间，终端机阶段作业和程序所耗费的CPU时间。
- -u 　忽略执行程序的名称，以及该程序耗费CPU时间的信息。
- -V 　显示版本信息。

### awk

 AWK 是一种处理文本文件的语言，是一个强大的文本分析工具。 

**选项参数说明：**

- -F fs or --field-separator fs
  指定输入文件折分隔符，fs是一个字符串或者是一个正则表达式，如-F:。
- -v var=value or --asign var=value
  赋值一个用户定义变量。
- -f scripfile or --file scriptfile
  从脚本文件中读取awk命令。
- -mf nnn and -mr nnn
  对nnn值设置内在限制，-mf选项限制分配给nnn的最大块数目；-mr选项限制记录的最大数目。这两个功能是Bell实验室版awk的扩展功能，在标准awk中不适用。
- -W compact or --compat, -W traditional or --traditional
  在兼容模式下运行awk。所以gawk的行为和标准的awk完全一样，所有的awk扩展都被忽略。
- -W copyleft or --copyleft, -W copyright or --copyright
  打印简短的版权信息。
- -W help or --help, -W usage or --usage
  打印全部awk选项和每个选项的简短说明。
- -W lint or --lint
  打印不能向传统unix平台移植的结构的警告。
- -W lint-old or --lint-old
  打印关于不能向传统unix平台移植的结构的警告。
- -W posix
  打开兼容模式。但有以下限制，不识别：/x、函数关键字、func、换码序列以及当fs是一个空格时，将新行作为一个域分隔符；操作符**和**=不能代替^和^=；fflush无效。
- -W re-interval or --re-inerval
  允许间隔正则表达式的使用，参考(grep中的Posix字符类)，如括号表达式[[:alpha:]]。
- -W source program-text or --source program-text
  使用program-text作为源代码，可与-f命令混用。
- -W version or --version
  打印bug报告信息的版本。