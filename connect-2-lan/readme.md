R1

```bash
sysname R1
sys
int g0/0/0
ip add 10.0.0.1 8

int g0/0/1
ip add 196.168.0.1 16

ip route-static 0.0.0.0 0 10.0.0.2
```

R2 

```bash
sysname R2
sys
int g0/0/0
ip add 10.0.0.2 8

int g0/0/1
ip add 172.16.0.1 16

ip route-static 0.0.0.0 0 10.0.0.1
```