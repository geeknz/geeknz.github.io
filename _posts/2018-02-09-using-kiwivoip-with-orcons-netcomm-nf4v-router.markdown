---
layout: default
title: "Using KiwiVoIP with Orcon's Netcomm NF4V Router"
date: '2018-02-09 23:30:20'
categories: orcon, netcomm, nf4v, router, modem, voip, javascript, unlock, god mode, kiwivoip, netcomm nf4v, hack
---

# Using KiwiVoIP with Orcon's Netcomm NF4V Router

I wanted to use [KiwiVoIP](http://www.kiwivoip.co.nz/) with my Netcomm NF4V router supplied by [Orcon](https://www.orcon.net.nz/). However, the fields to modify the settings are readonly. Luckily that can be solved a little JavaScript :)

Log on to the router and head to the Voice -> SIP Basic Setting. Once there run the following JavaScript in the developer console.

```javascript
(function() {
	var readonly = document
		.querySelectorAll('frame[name="basefrm"]')[0]
		.contentWindow
		.document
		.querySelectorAll('input[readonly]');

	for (var i = 0; i < readonly.length; i++)	{
		readonly[i].removeAttribute('readonly')
	}
})();
```

Now there are no more readonly fields and you can change the configuration to work with [KiwiVoIP](http://www.kiwivoip.co.nz/) as shown below.

![Kiwi VoIP Configuration](https://i.imgur.com/xMOH9oU.png)


You can check to see if it worked by going to Voice -> VoIP Status

![Kiwi VoIP Status](https://i.imgur.com/UM6d2zQ.png)

Hope someone finds this useful.

_Disclaimer, don't blame me if you do it wrong or get in trouble :)_
