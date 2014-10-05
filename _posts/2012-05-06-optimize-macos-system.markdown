---
title: 'MAC OS X 系统优化'
layout: post
tags:
    - macos
---

####1. 安装brew
Mac下打开Terminal, 复制并粘贴以下指令：
```shell
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```
brew安装常用软件 
```shell
brew install cmake git wget htop fping curl pigz mtr
```
####2. 安装Xcode

  * 网上直接下载安装Xcode,也可以从App Store中下载安装,访问网址：
https://developer.apple.com/downloads/index.action
  * 安装Xcode中的Command Line Tools:打开Xcode设置,在Downloads选项卡中点击Install"Command Line Tools"

####3. 配置终端&设置alias
设置 alias，可以在/etc/bashrc或者/etc/profile添加一下内容。

``` shell
cat >> /etc/profile << EOF
export CLICOLOR=1
export GREP_OPTIONS="--color=auto"
#PS1="\u@\h:\w $"
PS1="\e[32;1m\]\u@\h:\w $ \[\e[0m\]"

alias l.='ls -d .*'
alias ll='ls -l'
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'
alias vi='vim'
alias grep='grep --color'
alias du1='du -d 1 -h'
alias du2='du -d 2 -h'
alias du3='du -d 3 -h'
alias chosts="cat /etc/hosts"
alias mhosts="sudo vim /etc/hosts"

HISTFILESIZE=5000
HISTSIZE=5000
HISTTIMEFORMAT="%Y%m%d %T "
EOF

source /etc/profile
```
####4. 安装pip
``` shell
sudo easy_install pip
``` 

####5. 安装sshpt
``` shell
brew install gcc
sudo easy_install pip
sudo su -
ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future pip install pycrypto
wget http://sshpt.googlecode.com/files/sshpt-1.2.0.tar.gz
tar zxvf sshpt-1.2.0.tar.gz
cd sshpt
sudo python setup.py install
```
