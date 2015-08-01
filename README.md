# unix-time
Unix time in various languages - A reference

### What is [Unix time](https://en.wikipedia.org/wiki/Unix_time)?
Unix time (also known as POSIX time or erroneously as Epoch time) is a system for describing instants in time, defined as the number of seconds that have elapsed since 00:00:00 Coordinated Universal Time (UTC), Thursday, 1 January 1970, not counting leap seconds.

### Examples

#### How to get current unix time

_Javascript_

```javascript
Math.floor(new Date() / 1000)
```

[Moment](https://github.com/moment/moment/) is very popular in javascript world for playing with dates in javascript. Below is the momentjs example.

```javascript
var moment = require('moment');
var unixtime = moment().unix();
```

_PHP_

```php
echo time();

//php5.3 and above
//OOP style
$date = new DateTime();
echo $date->getTimestamp();

//procedural style
$date = date_create();
echo date_timestamp_get($date);
```
