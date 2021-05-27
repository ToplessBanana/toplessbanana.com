---
layout: post
title: "Configure WiFi Access on Ubuntu Server"
description: ""
tags: [linux]
---

Sometimes it's necessary to connect Ubuntu Server to a wireless network, which may be challenging without a GUI installed. Thankfully _netplan_ allows us to do this from the command line.

## Create Configuration File

{% highlight bash %}
sudo touch /etc/netplan/wireless.yaml
{% endhighlight %}

## Populate Settings

Enter the following key/value pairs into your configuration file.

{% highlight yaml %}
network:
  version: 2
  wifis:
    wlan0:
      dhcp4: yes
      dhcp6: no
      access-points:
        "<NETWORK-SSID>":
          password: "<NETWORK-PASSWORD>"
{% endhighlight %}

## Apply Configuration

{% highlight bash %}
sudo netplan try
{% endhighlight %}
