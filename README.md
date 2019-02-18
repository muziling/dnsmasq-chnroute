Add dnsmasq for support chnroute file.
===

编译/Compile
---

```bash
cd openwrt
cd package/network/services/dnsmasq/patches
wget https://raw.githubusercontent.com/muziling/dnsmasq-chnroute/0000-Add-feature-to-support-chnroutes.patch --no-check-certificate
cd ../../../../../

make package/network/services/dnsmasq/clean
make package/network/services/dnsmasq/compile V=s
```

使用/How to use
---

```Dnsmasq config file example:
no-resolv
all-servers
server=114.114.114.114,0
server=8.8.8.8,1
chnroutes-file=/root/chnroute.txt

server with ",0" is polluted dns, only accept ip in chnroute.
server with ",1" is clean dns, only accept ip not in chnroute.
```
