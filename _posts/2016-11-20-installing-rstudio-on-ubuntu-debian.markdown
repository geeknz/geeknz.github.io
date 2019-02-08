---
layout: default
title: "Installing RStudio on Ubuntu/Debian"
date: '2016-11-20 09:14:40'
categories: ubuntu, debain, apt, aptitude, R, rstudio, repository, ppa
---

# Installing RStudio on Ubuntu/Debian

First add my proxy repository to your apt sources.

```bash
sudo sh -c "echo deb http://repo.colin.geek.nz/rstudio devel main > /etc/apt/sources.list.d/rstudio.list"
```

This repository does not host any of the RStudio packages but instead will redirect your apt client to the official packages hosted by RStudio.

You will also need to add a R repository to your apt sources. There are many mirrors, such as this one hosted by RStudio.

```bash
sudo sh -c "echo deb http://cran.rstudio.com/bin/linux/ubuntu xenial/ >> /etc/apt/sources.list.d/rstudio.list"
```

You will also need to add the public keys

```bash
wget -O - http://repo.colin.geek.nz/rstudio/rstudio-apt.asc | sudo apt-key add -
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9
```

Now finally, install rstudio and enjoy.

```bash
sudo aptitude update
sudo aptitude install rstudio
```
