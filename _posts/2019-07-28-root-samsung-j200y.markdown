---
layout: default
title: "Root the Samsung Galaxy J2 (J200Y)"
date: '2019-07-28 19:19:00'
categories: root, samsung, galaxy, j200y, android, ubuntu, linux, heimdall, recovery.img
---

# Root the Samsung Galaxy J2 (SM-J200Y)

The following notes explain how I "rooted" my Samsung Galaxy J2. Take care, and do not blame me if you brick your phone.

## Download and Extract the Recovery Image

Download the TWRP recovery twrp-3.2.3-0-j2lte.img.tar (md5sum:f93103ac126117744321bf514abbcb5f) from [https://dl.twrp.me/j2lte/twrp-3.2.3-0-j2lte.img.tar.html](https://dl.twrp.me/j2lte/twrp-3.2.3-0-j2lte.img.tar.html)

```bash
tar -xvf twrp-3.2.3-0-j2lte.img.tar
```

## Put phone into Download Mode and Flash the Recovery Image

Power off the phone and then press and hold Volume Down + Power + Home

```bash
sudo heimdall flash --RECOVERY recovery.img
```

## Restore to Factory Default

Download the stock firmware J200YDOU2ARC2_J200YXNZ2ARD1_XNZ.zip (md5sum:cfe674416ed69476b31b88367b631cc) from https://samsung-firmware.org/en/download/Galaxy__J2__/044c/XNZ/J200YDOU2ARC2/J200YXNZ2ARD1/

```bash
unzip -d . J200YDOU2ARC2_J200YXNZ2ARD1_XNZ.zip
sudo hemdall flash --SYSTEM system.img --RECOVERY recovery.img --BOOT boot.img --CACHE cache.img --HIDDEN hidden.img
```