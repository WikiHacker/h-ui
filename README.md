<div align="center">

<a href="https://github.com/jonssonyan/h-ui"><img src="./docs/images/head-cover.png" alt="H UI" width="150" /></a>

<h1 align="center">H UI</h1>

English / [简体中文](README_ZH.md)

Just the panel for Hysteria2

仅仅是 Hysteria2 的面板

<p>
<a href="https://www.gnu.org/licenses/gpl-3.0.html"><img src="https://img.shields.io/github/license/jonssonyan/h-ui" alt="License: GPL-3.0"></a>
<a href="https://github.com/jonssonyan/h-ui/stargazers"><img src="https://img.shields.io/github/stars/jonssonyan/h-ui" alt="GitHub stars"></a>
<a href="https://github.com/jonssonyan/h-ui/forks"><img src="https://img.shields.io/github/forks/jonssonyan/h-ui" alt="GitHub forks"></a>
<a href="https://github.com/jonssonyan/h-ui/releases"><img src="https://img.shields.io/github/v/release/jonssonyan/h-ui" alt="GitHub release"></a>
<a href="https://hub.docker.com/r/jonssonyan/h-ui"><img src="https://img.shields.io/docker/pulls/jonssonyan/h-ui" alt="Docker pulls"></a>
</p>

![cover](./docs/images/cover.png)

</div>

## Features

- Lightweight, low resource usage, easy to deploy
- Monitor system status and Hysteria2 status
- Limit user traffic, user online status, force users to log off, number of online users
- Limit the number of users' online devices at the same time, the number of online devices
- User subscription link, node URL, import and export users
- Managing Hysteria2 configurations and Hysteria2 versions
- Change the Web port, modify the Hysteria2 traffic multiplier
- View, import, and export system logs and Hysteria2 logs
- I18n: English, 简体中文
- Page adaptation, support night mode, custom page themes

## Recommended OS

OS version: CentOS Stream 8/Ubuntu 20.04 LTS/Debian 11.1

CPU Architecture: x86_64/amd64

Memory: ≥ 128MB

## Deployment

Panel address: http://[your_ip/your_domain]:8081

Default administrator username: sysadmin Password: 123456. Please log in to the management backend to change the
password in time after deployment.

### Docker (Recommended)

1. Install Docker

   https://docs.docker.com/engine/install/

   ```bash
   bash <(curl -fsSL https://get.docker.com)
   ```

2. Start a container

   ```bash
   docker pull jonssonyan/h-ui

   docker run -d --name h-ui --restart always \
     --network=host \
     -v /h-ui/bin:/bin \
     -v /h-ui/data:/data \
     -v /h-ui/export:/export \
     -v /h-ui/logs:/logs \
     jonssonyan/h-ui
   ```

   Custom web port

   ```bash
   docker run -d --name h-ui --restart always \
     --network=host \
     -v /h-ui/bin:/bin \
     -v /h-ui/data:/data \
     -v /h-ui/export:/export \
     -v /h-ui/logs:/logs \
     jonssonyan/h-ui \
     ./h-ui -p [端口]
   ```

   Set the time zone, default is Asia/Shanghai

   ```bash
   docker run -d --name h-ui --restart always \
     --network=host \
     -e TZ=Asia/Shanghai \
     -v /h-ui/bin:/bin \
     -v /h-ui/data:/data \
     -v /h-ui/export:/export \
     -v /h-ui/logs:/logs \
     jonssonyan/h-ui
   ```

### Manual

Executable files: https://github.com/jonssonyan/h-ui/releases

```bash
mkdir h-ui && cd h-ui
curl -L -o h-ui https://github.com/jonssonyan/h-ui/releases/download/v0.0.1/h-ui-linux-amd64 && chmod +x ./h-ui && ./h-ui
```

## Performance Optimization

- Scheduled server restart

    ```bash
    0 4 * * * /sbin/reboot
    ```

- Install Network Accelerator
    - [Chikage0o0/Linux-NetSpeed](https://github.com/ylx2016/Linux-NetSpeed)
    - [ylx2016/Linux-NetSpeed](https://github.com/ylx2016/Linux-NetSpeed)
    - [teddysun/across#bbrsh](https://github.com/teddysun/across#bbrsh)

## Client

https://v2.hysteria.network/docs/getting-started/3rd-party-apps/

## Development

- frontend

   ```bash
   cd frontend
   pnpm install
   npm run dev
   ```

- backend

   ```bash
   go run main.go
   ```

## Build

- frontend

   ```bash
   npm run build:prod
   ```

- backend

  Windows: [build.bat](build.bat)

  Mac/Linux: [build.sh](build.sh)

## Other

you can contact me at YouTube: https://www.youtube.com/@jonssonyan

## Contributors

<a href="https://github.com/jonssonyan/h-ui/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=jonssonyan/h-ui" />
</a>

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=jonssonyan/h-ui&type=Date)](https://star-history.com/#jonssonyan/h-ui&Date)

## License

[GPL-3.0](LICENSE)