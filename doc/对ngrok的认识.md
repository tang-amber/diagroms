# 对ngrok的认识

**1.ngrok是一个exe可执行文件,下载后配置密钥authtoken,即可使用**

**2.执行命令映射外网**

执行命令可以cmd到安装目录,不过我选择配置一个环境变量(打开终端就能用ngrok,命令)

- 暴露本地8000端口到公网

```bash
ngrok http 8000
```

- 新学了一个bat脚本(点击执行)

``` bash
@echo off
ngrok http 8000
```

运行后可以在控制台查看响应状态

ngrok的作用是把本地端口暴露到公网上去,使得公网可以通过这个暴露的地址访问到本地,也就是内网穿透,主要用于开发调试阶段中外网调用内网.

**3.多端口映射**

在ngrok.yml配置文件中加上:

```bash
tunnels:
  a:
    addr: 9001
    proto: http
  b:
    addr: 9002
    proto: http
```

执行 `ngrok  start --all`可以映射多个端口,或者指定端口`ngrok start a`

