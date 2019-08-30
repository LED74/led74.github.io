---
layout: post
title: "Basic Commands for TCP/IP Utilities"
subtitle: "Test"
categories: Network
tags: Network, CCNA
---

## 실무에서 자주쓰는 Network 명령어 (Ping, Tracert, Nslookup, Netstat..)

## **1. Ping** <br>
The Ping utility tests connectivity between two hosts. <br>
Ping uses a special protocol called the <u>Internet Control Message Protocol (ICMP)</u>.

Also a great way to verify whether you have TCP/IP installed and your Network Card is working.

> Even though Server/Computer is on, we can find easily that ping doesn't work. <br>
  Because Server/Computer can block the ping from outside to prevent from DDOS attack. (Block ICMP Protocol) <br>
  Also, ICMP Protocol is belonged to OSI Layer 3. so Ping cannot check a port alive <br>

In case of that you want to check any service (port), you can use <u>Telnet or Tcping</u> <br>

Reference :
[https://www.pluralsight.com/blog/it-ops/top-7-tcpip-utilities-every-networking-pro-should-know](https://www.pluralsight.com/blog/it-ops/top-7-tcpip-utilities-every-networking-pro-should-know) , [https://ojava.tistory.com/126](https://ojava.tistory.com/126)
