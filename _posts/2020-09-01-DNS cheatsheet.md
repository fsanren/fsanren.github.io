---
layout:     post
title:      DNS cheatsheet
subtitle:
date:       2020-09-01
author:     fsanren
header-img: img/lyx-h-01.jpg
catalog: true
tags:
    - DNS
    - Devops
---

## What is DNS

### 1.
To get to www.example.com, your computer needs to know where on the Internet that server is

That means: it has to know what IP address to talk to

The way it finds out is the Domain Name System (DNS)

<p align="center">
  <img width="800" src="https://res.cloudinary.com/practicaldev/image/fetch/s--YFSTIFiU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/o60vlffckjreoux3q8p3.png">
</p>

### 2.
When you register a domain, you can set many types of DNS Records

Each record has a Type, a Host, and a Value

- "Types" are predefined
- "Host" represents the root (@) or a subdomain (www)
- "Value" is an IP or web address, or other value

<p align="center">
  <img width="800" src="https://res.cloudinary.com/practicaldev/image/fetch/s--cHVwQPWB--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/pmhvmi1bfavxw65h37zh.png">
</p>

### 3.
The A record maps a subdomain to an IPv4 address

This is most commonly used at the root, so it tells your browser where example.com lives

The AAAA record does the same for IPv6

<p align="center">
  <img width="800" src="https://res.cloudinary.com/practicaldev/image/fetch/s--cwCN_Qh4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/46bx3zbixp0ul68iukvb.png">
</p>



### cheat sheet
But there's a problem with CNAME!

Once you define a CNAME record for a subdomain (host), you CAN'T DEFINE another record for that same subdomain

Because of this, you can't use CNAME at the root level (where you need other records to exist)

<p align="center">
  <img width="900" src="https://note.youdao.com/yws/public/resource/a11f97a29715e209f916f1a240d79957/xmlnote/6190390D23A0460F8DB0DDDF627383BD/5661">
</p>

