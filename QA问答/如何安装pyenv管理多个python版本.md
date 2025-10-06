# Q: 如何安装pyenv管理多个python版本？

---
tags:
  - python
  - pyenv
  - setup
---
按照 https://github.com/pyenv/pyenv 的提示，按操作系统类型选择安装方式。

对于Linux例如Ubuntu，官网建议是
```shell
curl -fsSL https://pyenv.run | bash
```

但国内需要采用镜像源，所以可以从镜像链接下载安装脚本到本地；
```shell
wget https://gh-proxy.com/github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer
```

再把脚本中的`GITHUB="https://github.com/"`改为`"https://gh-proxy.com/github.com"`
```shell
bash pyenv-installer
```

修改shell的启动、登录脚本。并重启shell
```shell
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init - bash)"' >> ~/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
echo 'eval "$(pyenv init - bash)"' >> ~/.profile
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.profile
```

安装完后，不要马上用pyenv安装python，先要安装依赖包（以Ubuntu为例）
```shell
sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl git \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

```