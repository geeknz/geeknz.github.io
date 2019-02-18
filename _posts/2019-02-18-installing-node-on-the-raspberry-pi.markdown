---
layout: default
title: "Installing Node on the Raspberry Pi"
date: '2019-02-09 21:11:00'
categories: node, rpi, tar, local, linux
---

# Installing Node on the Raspberry Pi

First find the version of node you want to install at [https://nodejs.org/en/download/](https://nodejs.org/en/download/) . At the time of writing this the latest LTS is 10.15.1

Download it

```bash
wget https://nodejs.org/dist/v10.15.1/node-v10.15.1-linux-armv6l.tar.gz
```

Then extract it to _/usr/local_

```bash
sudo tar -C /usr/local --exclude=README.md --exclude=CHANGELOG.md --exclude=LICENSE --strip-components=1 -xzvf node-v10.15.1-linux-armv6l.tar.gz
```

Test it out

```bash
node --version
```