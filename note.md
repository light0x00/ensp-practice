路由器命令行
sys   进入系统视图
sysname xuetu 更改路由器名称
int gx/x/x 进入网络接口ip设置界面
ip address  x.x.x.x 掩码  设置网络接口ip
dis cur 展示当前路由器配置
ip route-static x.x.x.x mask x.x.x.x  把发往指定网段的数据包的目的地址映射到指定地址
ip route-static 0.0.0.0 0.0.0.0 x.x.x.x 如果目的ip不能匹配路由表，则将ip报文转到地址 `x.x.x.x`
undo ip route-static 196.168.0.0 255.255.0.0 x.x.x.x 删除静态路由
q+save,退出系统视图，并保存配置


A类地址：10.0.0.0--10.255.255.255
B类地址：172.16.0.0--172.31.255.255
C类地址：192.168.0.0--192.168.255.255

需要注意： 不论是路由器接口ip 还是 终端的ip，主机位不能设置为全1和全0。 比如 192.0.0.1


192.168.0.0--192.168.127.255
192.168.128.0--192.168.255.255


## NAT


nat server protocol tcp global 10.0.0.3 www inside 192.168.0.4 www