---
layout:     post
title:      Cannot find module lodash.deepclone 
subtitle:   
date:       2019-11-26
author:     fsanren
header-img: img/lyx-h-04.jpg
catalog: true
tags:
    - TroubleShoot
    - NPM
---


When you install node-sass by npm install,node-sass required lodash.deepclone.   
npm will install the lodash.deepclone automatic.   

However, node-sass ususally install failed blame to network or GFW. And if you install it failed, you may just copy a node-sass to node_modules folder, but have not install lodash.deepclone. and you get a ==ERROR== in console `ERROR: Cannot find module lodash.deepclone` .  
So install lodash.deepclone by yourself.  