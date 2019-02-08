---
layout: default
title: "Proxy Settings Registry Generator"
date: '2016-11-27 02:03:14'
categories: proxy, reg, registry, windows, hex, hexadecimal, generator
---

# Proxy Settings Registry Generator

A year or so ago while I was studying I came across a problem with the computers in the University computer lab. I was unable to connect to the web application I was working on via localhost.

I found that this was caused by the proxy settings. Specifically the checkbox "Bypass proxy server for local addresses" was not selected. Unfortunately, there was a group policy preventing me from changing this setting.

Luckily, you can get around this policy by bypassing the UI and changing the settings directly via the registry. But there is one problem, the key to edit looks like this.

```regedit
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\Connections]
"DefaultConnectionSettings"=hex:46,00,00,00,00,00,00,00,09,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
```

If your lucky enough and have access to another machine without this policy you can set the settings on that machine then export the key. Otherwise, you are suck with editing the hexadecimal. Therefore, I started creating an application that would generate the hexadecimal for me.

Like most projects it got forgotten about until just recently when I started revisiting my old abandoned projects. Lately, I've been doing some development is [AngularJS](https://angularjs.org/) so I thought why not finish this project using that.

So I did. A copy of the application has been embedded below. You can also checkout the code on [github](https://github.com/geeknz/internet-settings).

<script src="//cdn.rawgit.com/davidjbradshaw/iframe-resizer/v3.5.5/js/iframeResizer.min.js"></script>
<iframe src="//cdn.rawgit.com/geeknz/internet-settings/1d395a/index.html" class="iframe-resizer" width="100%" scrolling="no" frameborder="0" onLoad="iFrameResize();"></iframe>

I hope that you find it useful.

_Disclaimer, make sure this is OK with your system administrator/company or whatever. Also you should probably backup your registry before making changes. I'm just saying it's not my fault if you get in trouble or break something._
