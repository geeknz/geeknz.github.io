---
layout: default
title: "Mount Partclone Image"
date: '2019-04-10 21:36:00'
categories: ubuntu, linux, partclone, mount, clonezilla
---

# Mount Partclone Image

Today I needed to extract some files from a backup I created using [Clonezilla](https://clonezilla.org/). It's an ext4 partition compressed with bzip2, here are the commands I used.

```bash
cat sda1.ext4-ptcl-img.bz2.* | bzip2 -d -c | partclone.ext4 -C -r -W -s - -O sda1.img
mount -o loop -t ext4 sda1.img /mnt
```
