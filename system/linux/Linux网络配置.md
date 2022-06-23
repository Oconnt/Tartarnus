# Linux网络配置

### 网卡配置

```
/etc/sysconfig/network-scripts/
```

```shell
GATEWAY=200.201.175.254
DEVICE=eth0
BOOTPROTO=none
NETMASK=255.255.248.0
TYPE=Ethernet
IPADDR=200.201.175.204
NM_CONTROLLED=no
ONBOOT=yes
USERCTL=no
PEERDNS=no
IPV6INIT=no
~
```

域名解析

```shell
/etc/hosts
```

```

127.0.0.1       localhost.localdomain localhost
::1             localhost.localdomain localhost

127.0.0.1       api.cloud.vt
::1             api.cloud.vt
127.0.0.1       ntp.cloud.vt
::1             ntp.cloud.vt
127.0.0.1       mq.cloud.vt
::1             mq.cloud.vt
127.0.0.1       appcenter.local.cloud.scp
::1             appcenter.local.cloud.scp
127.0.0.1       mysql.cloud.vt
::1             mysql.cloud.vt
127.0.0.1       mongodb.cloud.vt
::1             mongodb.cloud.vt
127.0.0.1       keystone.cloud.vt
::1             keystone.cloud.vt
127.0.0.1       redis.cloud.vt
::1             redis.cloud.vt
127.0.0.1       memcache.cloud.vt
::1             memcache.cloud.vt
127.0.0.1       gnocchi.cloud.vt
::1             gnocchi.cloud.vt
127.0.0.1       vmware.cloud.vt
::1             vmware.cloud.vt
127.0.0.1       barbican.cloud.vt
::1             barbican.cloud.vt
127.0.0.1       apm-satellite
::1             apm-satellite
127.0.0.1       eventbridge-api
::1             eventbridge-api
127.0.0.1       eventbridge-runtime
::1             eventbridge-runtime
127.0.0.1       pluto-api
::1             pluto-api
127.0.0.1       cloudmanager-api
::1             cloudmanager-api
127.0.0.1       rubik-api
::1             rubik-api

200.200.42.194 artifacts.sangfor.com
200.200.42.194 docker.sangfor.com
127.0.0.1       acmp-fefcfef4a00b
::1             acmp-fefcfef4a00b

```

### ping不通网关？

```shell
# 首先清空路由信息
ip route flush dev eth0(网卡名)
# 重启网卡
systemctl restart network
# 查看网卡的配置文件， 保证onboot为yes
/etc/sysconfig/network-scripts/ifcfg-eth0
# 进行arp校验
arp -a
# ping网关
```

