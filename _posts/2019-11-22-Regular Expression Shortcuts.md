
---
layout:     post
title:      Regular Expression Shortcuts
subtitle:   
date:       2019-11-26
author:     fsanren
header-img: img/lyx-h-05.jpg
catalog: true
tags:
    - Regular Expressions

---

### Create

> A regular expression is a type of object. It can be either constructed with the **RegExp constructor** or written as a literal value by enclosing a pattern in forward slash (/) characters.

```
let re1 = new RegExp("abc");
let re2 = /abc/;
```

### Shortcuts 

>  A number of common character groups have their own built-in shortcuts.  
( e.g. \d 相当于 [0-9] / [0123456789] )

```
\d	Any digit character 
\w	An alphanumeric character (“word character”)
\s	Any whitespace character (space, tab, newline, and similar)
\D	A character that is not a digit
\W	A nonalphanumeric character
\S	A nonwhitespace character
.	Any character except for newline
```
