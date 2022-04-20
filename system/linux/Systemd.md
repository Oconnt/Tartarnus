# Systemd

### 1、systemd简介

 systemd 是 system deamon 的简称，是一个 Linux 系统基础组件的集合，提供了系统与服务的管理，是 pid 为 1 的 init 进程，是所有进程的父进程。 

系统架构图：

![](../../../../Desktop/UserssangforworkspaceTartarnusimage/20170822152214591.png)

### 2、systemd类型

**.service:**  一般服务类型(service unit) , 主要为系统服务类型

**.socket:** 内部程序数据交换的[插槽](https://so.csdn.net/so/search?q=插槽&spm=1001.2101.3001.7020)服务 (socket unit) 

**.target:** 执行环境类型(target unit)  其实是一群 unit 的 集合 

**.mount  .automount** :   文件系统挂载相关的服务 (automount unit / mount unit)：例如来自网络的动挂载、 NFS 文件系统挂载等与文件系统相关性较高的程序管理。 

**.path:** 侦测特定 文件 或目录类型 (path unit)：某些服务需要侦测特定的目录来提供队列，例如最常见的打印服务，就是透过侦测队列目录来启动功能！这时就得要 .path的服务类型支持了！ 

**.timer:** 循环执行的服务 (timer unit) 

### 3、systemctl

| **指令**                                                     | **任务**             |
| ------------------------------------------------------------ | -------------------- |
| systemctl enable httpd.service                               | 使某服务自动启动     |
| systemctl disable httpd.service                              | 使某服务不自动启动   |
| systemctl status httpd.service （服务详细信息） systemctl is-active httpd.service （仅显示是否 Active) | 检查服务状态         |
| systemctl list-units --type=service                          | 显示所有已启动的服务 |
| systemctl start httpd.service                                | 启动服务             |
| systemctl stop httpd.service                                 | 停止服务             |
| systemctl restart httpd.service                              | 重启服务             |
| systemctl reload httpd.service                               | 重载服务             |
| systemctl cat httpd.service                                  | 查看服务配置文件     |

