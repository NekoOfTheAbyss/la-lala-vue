---
title: Name Generator
description: 'Name generator'
url: name
creat: 2022-01-26T14:15:00.735Z
---

Name generator. Rather than calling it a name, it's just a word which can be pronounced.


## Usage
```js
lala.random.name(length)
```
Where `length` is any number, representing the length of the name.

Returns a string in uppercase.

Example,
```js
lala.random.name(10); // Something like GHEINSAOMA

lala.random.name(0); // Just a single character

lala.random.name(-1); // Negative length works the same as 0
```

