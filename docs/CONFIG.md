# Configure Ubuntu

## Update Source

备份现有sources.list
```bash
sudo mv /etc/apt/sources.list /etc/apt/sources.list.original
```
编辑新的source.list
```
sudo vi /etc/apt/sources.list
```

添加阿里云源
```
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
```

## Update

更新软件：
```bash
sudo apt update
```

## Clean

Remove unused apps
```bash
sudo apt-get remove libreoffice-common

sudo apt-get remove thunderbird totem rhythmbox empathy brasero simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku landscape-client-ui-install

sudo apt-get autoremove
```


## Update Grub

编辑grub配置文件
```bash
sudo vi /etc/default/grub
```

把文件中"...splash"引号内的文本添加一段改成"... splash acpi_osi=linux nomodeset"

保存退出， 然后执行

```bash
sudo update-grub
```
重启即可