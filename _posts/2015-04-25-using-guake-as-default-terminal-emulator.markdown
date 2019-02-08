---
layout: default
title: "Using guake as the default terminal emulator"
date: '2015-04-25 10:36:45'
categories: ubuntu
---

# Using guake as the default terminal emulator

```bash
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator /usr/bin/guake 80
sudo update-alternatives --config x-terminal-emulator
```
