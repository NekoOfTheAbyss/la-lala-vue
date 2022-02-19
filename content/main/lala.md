---
title: Lala
description: 'A collection of random useful (probably) javascript classes and functions. '
url: main
creat: 2022-01-26T14:15:00.735Z
---

**As of 19th February 2022, Lala has dropped CJS support and is now a pure ESM module. You can find older versions (before v2.0.0) as [releases](https://github.com/NekoOfTheAbyss/lala/releases/tag/v1.2.2) which support CJS (I suggest moving to ESM tho).**

A collection of random useful (probably) javascript classes and functions.
For ease of explaining, this is the structure of lala:

```js
Lala: {
    Time, // Time class from @retraigo/duration.js
    Trash: {
        Decider, // idk what this even does
    },
    util: {
        randomFromArr, // get random element from array
    }
    random: {
        genString, // generate random string
        genName, // generate random name
        genEmail, // generate random email
        genMonster, // generate random fantasy name
        genChain, // generate random chain mail
        genStory, // generate random fantasy plot
        genCharacter, // generate a weird character title
    }
}
```

Lala exports the following classes and functions directly:

```js
[
  Time,
  Collection,
  Decider,
  capitalize,
  reverseString,
  randomFromArr,
  owoify,
  genString,
  genName,
  genEmail,
  genMonster,
  genChain,
  genStory,
  genCharacter,
]

```

They can be imported through

```js
import { myFunction } from '@nekooftheabyss/lala'
```

Where `myFunction` is the part of the module you want to import.

Some of these may be undocumented so you're on your own. You can find certain documentations below tho.