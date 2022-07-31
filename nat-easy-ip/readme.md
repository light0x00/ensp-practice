https://support.huawei.com/enterprise/en/doc/EDOC1100055101/239afdb7/example-for-configuring-easy-ip-for-nat

```bash
# 
sysname NAT-Device 
# 
nat instance nat1 id 1 simple-configuration             
#
nat address-group address-group1 group-id 1 unnumbered interface GigabitEthernet 0/2/1
#
acl number 3001 
 rule 1 permit ip source 192.168.10.0 0.0.0.255

# 
interface GigabitEthernet 0/2/1 
 undo shutdown 
 ip address 11.2.3.4 255.255.255.0 
 nat bind acl 3001 instance nat1 
#
ip route-static 0.0.0.0 0.0.0.0 11.2.3.5
#
return
```