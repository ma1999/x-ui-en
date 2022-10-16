# x-ui
xray panel with multi-protocol multi-user support

# Features
- System Status Monitoring
- Support multi-user multi-protocol, web page visualization operation
- Supported Protocols：vmess、vless、trojan、shadowsocks、dokodemo-door、socks、http
- Support for configuring more transport configurations
- Traffic statistics, limit traffic, limit expiration time
- Customizable xray configuration templates
- Support https access panel (bring your own domain name + ssl certificate)
- For more advanced configuration items, please refer to the panel

# Install & Upgrade
```
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

## Manual install & upgrade
1. First from https://github.com/vaxilu/x-ui/releases Download the latest compressed package, generally choose`amd64`Architecture
2. Then upload the compressed package to the server`/root/`directory, and use`root`user login server

> if your server cpu Architecture is not`amd64`, replace the command in the`amd64`Replace with other schema

```
cd /root/
rm x-ui/ /usr/local/x-ui/ /usr/bin/x-ui -rf
tar zxvf x-ui-linux-amd64.tar.gz
chmod +x x-ui/x-ui x-ui/bin/xray-linux-* x-ui/x-ui.sh
cp x-ui/x-ui.sh /usr/bin/x-ui
cp -f x-ui/x-ui.service /etc/systemd/system/
mv x-ui/ /usr/local/
systemctl daemon-reload
systemctl enable x-ui
systemctl restart x-ui
```

## suggestion system
- CentOS 7+
- Ubuntu 16+
- Debian 8+

# common problem
## and v2-ui relation
x-ui equivalent to v2-ui The enhanced version of , more functions will be added in the future. x-ui After the function is stabilized, v2-ui Updates will no longer be provided

x-ui can coexist with v2-ui, the data is not interoperable, and does not affect the operation of the other party

## Migrating from v2-ui
First install the latest version of x-ui on the server where v2-ui is installed, and then use the following command to migrate, which will migrate the native v2-ui`All inbound account data`to x-ui，`Panel settings and username passwords are not migrated`
> After the migration is successful, please`close v2-ui` and`reboot x-ui`,otherwise v2-ui The inbound will be the same as the inbound of x-ui will produce`port conflict`
```
x-ui v2-ui
```

## Stargazers over time

[![Stargazers over time](https://starchart.cc/vaxilu/x-ui.svg)](https://starchart.cc/vaxilu/x-ui)
