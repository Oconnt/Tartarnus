# 如何让GitHub不卡

### 文章目录

- [第一步：修改hosts权限](https://blog.csdn.net/qq_49821869/article/details/112974977?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-1-112974977.pc_agg_new_rank&utm_term=github如何不卡&spm=1000.2123.3001.4430#hosts_10)
- [第二步：查找github的IP地址](https://blog.csdn.net/qq_49821869/article/details/112974977?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-1-112974977.pc_agg_new_rank&utm_term=github如何不卡&spm=1000.2123.3001.4430#githubIP_28)
- [第三步：增加hosts文件内容](https://blog.csdn.net/qq_49821869/article/details/112974977?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-1-112974977.pc_agg_new_rank&utm_term=github如何不卡&spm=1000.2123.3001.4430#hosts_47)
- [第四步：刷新DNS](https://blog.csdn.net/qq_49821869/article/details/112974977?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-1-112974977.pc_agg_new_rank&utm_term=github如何不卡&spm=1000.2123.3001.4430#DNS_60)



每次打开[github](https://so.csdn.net/so/search?q=github&spm=1001.2101.3001.7020)的网站都特别卡，加载速度很慢，下面的解决办法亲测有效。

# 第一步：修改hosts权限

1、进入电脑C:\Windows\System32\drivers\etc目录，找到hosts文件。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234324157.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

2、右键选择属性–安全–点击编辑

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021012123433839.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

3、选择Users，将Users的权限允许框框全部打钩，然后应用确定。
在这里插入图片描述

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234353584.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

# 第二步：查找github的IP地址

1、进入网址：www.ipaddress.com
在搜索框内分别输入github.com和github.global.ssl.fastly.net查询他们的IP地址。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234413489.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

2、我查询到的结果是（注意：IP地址时间长了可能会变化，一定要自己去查）
github.com的IP地址：140.82.113.3

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234425565.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

github.global.ssl.fastly.net的IP地址是199.232.69.194

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234432859.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

# 第三步：增加hosts文件内容

打开第一步中的hosts文件（记事本形式打开），在最后添加如下信息：

\#Github
140.82.113.3 https://github.com
199.232.69.194 https://github.global.ssl.fastly.net

如图所示，保存即可。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234454460.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ5ODIxODY5,size_16,color_FFFFFF,t_70)

# 第四步：刷新DNS

打开cmd（同时按下win+R，输入cmd并回车），进入cmd后输入命令：ipconfig /flushdns
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210121234504111.png)

大功告成！现在打开github的网页都是飞快的，再也不卡了！！！