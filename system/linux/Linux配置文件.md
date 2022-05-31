# Linux配置文件

## 环境变量配置

| 环境变量名称 | 作用                                   |
| ------------ | -------------------------------------- |
| HOME         | 用户的主目录（也称家目录）             |
| SHELL        | 用户使用的 Shell 解释器名称            |
| PATH         | 定义命令行解释器搜索用户执行命令的路径 |
| EDITOR       | 用户默认的文本解释器                   |
| RANDOM       | 生成一个随机数字                       |
| LANG         | 系统语言、语系名称                     |
| HISTSIZE     | 输出的历史命令记录条数                 |
| HISTFILESIZE | 保存的历史命令记录条数                 |
| PS1          | Bash解释器的提示符                     |
| MAIL         | 邮件保存路径                           |
| TMOUT        | 客户端连接超时时间                     |

### 1、/etc/profile

建议配置环境变量文件/etc/profile.d

### 2、/etc/bashrc（全局）

该文件配置的环境变量将会影响全部用户使用的bash shell。但是，Linux也不建议在/etc/bashrc文件中设置系统环境变量。

### 3、/home/用户名/.bash_profile

当用户登录时执行，每个用户都可以使用该文件来配置专属于自己的环境变量。

 .bash_logout 

### 4、/home/用户名/bashrc

 当用户登录时以及每次打开新的Shell时该文件都将被读取，不推荐在里面配置用户专用的环境变量，因为每开一个Shell，该文件都会被读取一次，效率肯定受影响 

### 5、/home/用户名/.bash_logout

 当每次退出系统（退出bash shell）时执行该文件。 

### 环境变量脚本文件的执行顺序

 /etc/profile->/etc/profile.d->/etc/bashrc->用户的.bash_profile->用户的.bashrc 



## 网络配置