# Shadowsocks-rinetd Dockerfile
This Dockerfile build an image for [shadowsocks-libev](https://github.com/shadowsocks/shadowsocks-libev/) with [simple-obfs](https://github.com/shadowsocks/simple-obfs) and [rinetd-bbr](https://github.com/linhua55/lkl_study), based on Alpine Linux.

Current version:
- shadowsocks-libev: v3.1.0
- simple-obfs: v0.0.3

## Quick Start

Get the docker image by running the following commands:

```bash
docker pull lentin/shadowsocks-rinetd
```

Start a instance:

```bash
docker run -d --name=shadowsocks-libev -p 3389:8388/tcp -p 3389:8388/udp --restart=always lentin/shadowsocks-rinetd
```

## Default configration

Server host: `0.0.0.0`  
Server port: `8388`  
Password: `shadowsocks`  
Encrypt method: `chacha20-ietf-poly1308`  
Timeout: `60`  
DNS: `8.8.8.8`  
Plugin: `obfs-server`  
Plugin options: `obfs=http`

## Setting a specific configration

You can use environment variables to specific configration.

For example with password `MyPassword`:

```bash
docker run -e PASSWORD=MyPassword  -d --name=shadowsocks-rinetd -p 443:8388/tcp -p 443:8388/udp --restart=always lentin/shadowsocks-rinetd
```

### For more directions 
https://github.com/Acris/docker-shadowsocks-libev#shadowsocks-libev-dockerfile
