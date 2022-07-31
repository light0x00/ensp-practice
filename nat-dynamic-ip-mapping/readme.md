1. 建立 acl 规则

```bash
acl 2000  # 创建acl 名字标识为 2000
rule permit source 192.168.0.0 0.0.255.255  # 将源地址为192.168开头的ip报文
q
```

2. 建立地址池

```bash
nat address-group 1 10.0.0.3 10.0.0.10 # 创建名字标识为1的地址池，地址范围为 10.0.0.3~10.0.0.10 
```

3. 为路由器接口设置NAT

```bash
nat outbound 2000 address-group 1 # 将满足acl规则 2000 的出方向报文的源地址地转换为地址池1的ip
```