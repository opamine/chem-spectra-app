### 基础运行环境安装

最新版本安装，请参考 [Anaconda](https://www.anaconda.com/docs/getting-started/anaconda/install#linux-installer) 和 [Docker](https://docs.docker.com/install/) 官网。

## Anaconda for Linux

```
$ cd /tmp
$ curl -O https://repo.anaconda.com/archive/Anaconda3-2025.06-0-Linux-x86_64.sh
$ bash Anaconda3-2025.06-0-Linux-x86_64.sh
```

上术第三行命令会自动变更 ` ~/.bashrc` 文件，但是需要手动更新下命令组：

```
$ source ~/.bashrc
```

验证 Anaconda 是否安装完成（出现版本号即代表成功）：

```
$ conda --version
```

追加行 `export PATH=~/anaconda3/bin:$PATH` 到 `~/.bashrc` 文件中, 见 [这里](https://www.oryoy.com/news/ubuntu-xi-tong-qing-song-shang-shou-jiao-ni-ru-he-tian-jia-anaconda-lu-jing-dao-huan-jing-bian-liang.html)。


## Docker for Ubuntu

前置条件

```
$ sudo apt-get update
$ sudo apt-get install curl ca-certificates gnupg lsb-release apt-transport-https ca-certificates software-properties-common
$ curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
```

开始安装 docker

```
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

将当前用户添加到 docker 用户组，以用户名 `ubuntu` 为例：

```
$ sudo usermod -a -G docker ubuntu
```


运行 docker：

```
$ systemctl start docker
```

重启docker

```
# service docker restart
```
