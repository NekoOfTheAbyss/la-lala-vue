---
title: Email Generator
description: 'Random Email generator'
url: email
creat: 2022-01-26T14:15:00.735Z
---

Random email generator. Uses the random name generator as always.

## Usage
```js
lala.random.genEmail([common])
```
Accepts an optional `common` parameter. When true, it uses popular email service names instead generating a random email service name.

Returns a string in lowercase.

Example,
```js
lala.random.genEmail(true); // Something like esterzhost@yahoo.com
lala.random.genEmail(false); // Something like esterzhost@vext.to
lala.random.genEmail(); // Same as with "false"
```

