---
title: Time
description: 'A time class.'
url: time
creat: 2022-01-26T14:15:00.735Z
---

Time class. Yes, Time. Ain't gonna give it a better name with my crappy naming sense as you can see in the name of this repo. Formerly `@retraigo/duration.js`. 

```js
const { Time } = require('lala') // Just an example, lala is not my npm package or something
```

## Usage
```js
new Time(duration)
```
Where `duration` is any number, the milliseconds.

Example,
```js
new Time(); // Get duration since midnight

new Time(3545346); // A random duration

new Time(0); // Just 0

new Time(-1); // Negative duration returns 0 too
```

## Properties
```js
Time { 
    raw: 0 // Original milliseconds passed to the constructor
    d: 0, // Days
    h: 0, // Hours
    m: 0, // Minutes
    s: 0, // Seconds
    ms: 0 // Milliseconds
};
```

## Methods

#### toString()
`toString()` returns a simplified version of `stringify()` despite not looking nice at all. Simply exists.
```js
new Time(261174).toString();
// `[Time 0d 0h 4m 21s]`
```

### stringify([values] [,short])
`stringify()` returns a formatted string of the duration object. It has two optional parameters.
`values` - An array of values to include. Should be one of `['d', 'h', 'm', 's', 'ms']`. Defaults to the array I mentioned a few words ago.
`short` - `true` if the function should return letters instead of words (I suck at explaining). Defaults to false.

```js
new Time(165684).stringify();
// `0 days, 0 hours, 2 minutes, 45 seconds, 684 milliseconds`
new Time(165684).stringify(['s', 'h']);
// `0 hours, 45 seconds`
new Time(165684).stringify(['s', 'h'], true);
// `0h 45s`

```

### get json()
Returns a JSON version of the class with just the main stuff.
```js
new Time(114750).json;
// `{ d: 0, h: 0, m: 1, s: 54, ms: 750 }`
```

### get array()
Returns an array of objects with type and value.
```js
new Time(245074).array;
/* 
   [
       { type: 'd', value: 0 },
       { type: 'h', value: 0 },
       { type: 'm', value: 4 },
       { type: 's', value: 5 },
       { type: 'ms', value: 74 }
   ]
*/
```
