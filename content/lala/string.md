---
title: String Generator
description: 'Random string generator'
url: string
creat: 2022-01-26T14:15:00.735Z
---


String generator. Generates an alphanumeric string.


## Usage
```js
lala.random.genString(length)
```
Where `length` is any number, representing the length of the name.

Returns a string in mixed case. Alphanumeric btw.

Example,
```js
lala.random.genString(10); // Something like 9kum9XpGDr

lala.random.genString(0); // Just a single character, like "a" or "3"

lala.random.genString(-1); // Negative length works the same as 0
```

