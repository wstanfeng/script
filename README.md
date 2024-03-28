# Some script

## rcloned

Linux automatically mount any of [Rclone](https://rclone.org/)'s cloud storage systems as a file system with FUSE

[Read the details in my blog (in Chinese) | 中文教程](https://p3terx.com/archives/linux-vps-uses-rclone-to-mount-network-drives-such-as-onedrive-and-google-drive.html)

开机自动挂载

下载并编辑自启脚本
```
wget -N git.io/rcloned && nano rcloned
```

修改内容：
```
NAME="Onedrive" #Rclone配置时填写的name
REMOTE=''  #远程文件夹，网盘里的挂载的一个文件夹，留空为整个网盘
LOCAL='/Onedrive'  #挂载地址，VPS本地挂载目录
```

设置开机自启
```
mv rcloned /etc/init.d/rcloned
chmod +x /etc/init.d/rcloned
update-rc.d -f rcloned defaults # Debian/Ubuntu
chkconfig rcloned on # CentOS
bash /etc/init.d/rcloned start
```
看到 [信息] rclone 启动成功 ! 即可。

管理
```
开始挂载 bash /etc/init.d/rcloned start
停止挂载 bash /etc/init.d/rcloned stop
重新挂载 bash /etc/init.d/rcloned restart
查看日志 tail -f /$HOME/.rclone/rcloned.log
```
卸载自启挂载
```
bash /etc/init.d/rcloned stop
update-rc.d -f rcloned remove # Debian/Ubuntu
chkconfig rcloned off # CentOS
rm -f /etc/init.d/rcloned
```

取消挂载：
```
fusermount -qzu /Onedrive
```
## tmate.sh

Install the latest version [tmate](https://github.com/tmate-io/tmate)

- Install tmate
```
curl -fsSL git.io/tmate.sh | bash
```

- Uninstall tmate
```
[sudo] rm -f /usr/local/bin/tmate
```

## oh-my-tmux.sh

Install [Oh My Tmux](https://github.com/gpakosz/.tmux)

```
curl -fsSL git.io/oh-my-tmux.sh | bash
```

## oh-my-zsh.sh

Install a simple [Oh-My-Zsh](https://github.com/ohmyzsh/ohmyzsh) environment using [Antigen](https://github.com/zsh-users/antigen)

```
curl -fsSL git.io/oh-my-zsh.sh | bash
```

## bashtop.sh

Install the latest version [bashtop](https://github.com/aristocratos/bashtop)

- Download & Install bashtop
```
curl -fsSL git.io/bashtop.sh | bash
curl -fsSL git.io/bashtop.sh | bash -s install
```

- Uninstall bashtop
```
[sudo] rm -f /usr/local/bin/bashtop
```

## gotop.sh

Install the latest version [gotop](https://github.com/xxxserxxx/gotop)

- Install gotop
```
curl -fsSL git.io/gotop.sh | sudo bash
```

- Uninstall gotop
```
sudo rm -f /usr/local/bin/gotop
```

## ctop.sh

Install the latest version [ctop](https://github.com/bcicen/ctop)

- Install ctop
```
curl -fsSL git.io/ctop.sh | sudo bash
```

- Uninstall ctop
```
sudo rm -f /usr/local/bin/ctop
```

## ffsend.sh

Install the latest version [ffsend](https://github.com/timvisee/ffsend)

- Download & Install ffsend
```
curl -fsSL git.io/ffsend.sh | bash
curl -fsSL git.io/ffsend.sh | bash -s install
```

- Uninstall ffsend
```
[sudo] rm -f /usr/local/bin/ffsend
```

## github-actions-trigger.sh

GitHub Actions trigger script

See details：[GitHub Actions Docs: Events that trigger workflows](https://help.github.com/en/actions/reference/events-that-trigger-workflows#external-events-repository_dispatch)

```
sh <(curl -fsSL git.io/trigger.sh) "TOKEN" "REPO_NAME" "EVENT_TYPE"
```

## fclone.sh

Install the latest version [fclone](https://github.com/mawaya/rclone/releases/latest)

- Install fclone
```
curl -fsSL git.io/fclone.sh | bash
```

- Uninstall fclone
```
[sudo] rm -f /usr/bin/fclone
```

## docker-compose.sh

Install latest version [Docker Compose](https://github.com/docker/compose)

- Install Docker Compose
```
curl -fsSL git.io/docker-compose.sh | sudo bash
```

- Uninstall Docker Compose
```
sudo rm -f /usr/local/bin/docker-compose
```

## lazydocker.sh

Install latest version [lazydocker](https://github.com/jesseduffield/lazydocker)

- Install lazydocker
```
curl -fsSL git.io/lazydocker.sh | sudo bash
```

- Uninstall lazydocker
```
sudo rm -f /usr/local/bin/lazydocker
```

## wgcf.sh

Install latest version [wgcf](https://github.com/ViRb3/wgcf/releases/latest)

- Install wgcf
```
curl -fsSL git.io/wgcf.sh | sudo bash
```

- Uninstall wgcf
```
sudo rm -f /usr/local/bin/wgcf
```

## wireguard-go.sh

Install latest version [wireguard-go](https://github.com/P3TERX/wireguard-go-builder/releases/latest)

- Install wireguard-go
```
curl -fsSL git.io/wireguard-go.sh | sudo bash
```

- Uninstall wireguard-go
```
sudo rm -f /usr/local/bin/wireguard-go
```

## duf.sh

Install latest version [duf](https://github.com/muesli/duf/releases/latest)

- Install duf
```
curl -fsSL git.io/duf.sh | sudo bash
```

- Uninstall duf
```
sudo rm -f /usr/local/bin/duf
```

## speedtest-cli.sh

Install [Ookla Speedtest CLI](https://www.speedtest.net/apps/cli)

- Install Ookla Speedtest CLI
```
curl -fsSL git.io/speedtest-cli.sh | sudo bash
```

- Uninstall Ookla Speedtest CLI
```
sudo rm -f /usr/local/bin/speedtest
```

## lsd.sh

Install latest version [LSD](https://github.com/Peltoche/lsd/releases/latest)

- Install lsd
```
curl -fsSL git.io/lsd.sh | sudo bash
```

- Uninstall lsd
```
sudo rm -f /usr/local/bin/lsd
```

## nali.sh

Install latest version [Nali](https://github.com/zu1k/nali/releases/latest)

- Install Nali
```
curl -fsSL git.io/nali.sh | sudo bash
```

- Uninstall Nali
```
sudo rm -f /usr/local/bin/nali
```

## gping.sh

Install latest version [gping](https://github.com/orf/gping/releases/latest)

- Install gping
```
curl -fsSL git.io/gping.sh | sudo bash
```

- Uninstall gping
```
sudo rm -f /usr/local/bin/gping
```

## hostname.sh

Modify hostname

```
curl -fsSL git.io/hostname.sh | sudo bash -s <HOSTNAME>
```

## cpufetch.sh

Install latest version [cpufetch](https://github.com/Dr-Noob/cpufetch/releases/latest)

- Install cpufetch
```
curl -fsSL git.io/cpufetch.sh | sudo bash
```

- Uninstall cpufetch
```
sudo rm -f /usr/local/bin/cpufetch
```

## btop.sh

Install latest version [btop](https://github.com/aristocratos/btop/releases/latest)

- Install btop
```
curl -fsSL git.io/btop.sh | sudo bash
```

- Uninstall btop
```
sudo rm -f /usr/local/bin/btop
```

## Lisence

[MIT](https://github.com/P3TERX/script/blob/master/LICENSE) © P3TERX
