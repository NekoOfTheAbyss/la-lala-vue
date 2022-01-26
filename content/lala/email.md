---
title: Email Generator
description: 'Random Email generator'
url: email
creat: 2022-01-26T14:15:00.735Z
---

Random email generator. Uses the random name generator as always.

## Usage
```js
lala.random.email([common])
```
Accepts an optional `common` parameter. When true, it uses popular email service names instead generating a random email service name.

Returns a string in lowercase.

Example,
```js
lala.random.email(true); // Something like esterzhost@yahoo.com
lala.random.email(false); // Something like esterzhost@vext.to
lala.random.email(); // Same as with "false"
```

