# unix-time
Unix time in various languages - A reference

### What is [Unix time](https://en.wikipedia.org/wiki/Unix_time)?
Unix time (also known as POSIX time or erroneously as Epoch time) is a system for describing instants in time, defined as the number of seconds that have elapsed since 00:00:00 Coordinated Universal Time (UTC), Thursday, 1 January 1970, not counting leap seconds.

### Examples

#### How to get current unix time

_C_

```c
#include <stdio.h>
#include <time.h>

int main(int argc, char **argv) {
  unsigned int unix_time = (unsigned) time(NULL);
  fprintf(stdout, "%u\n", unix_time);
  return 0;
}
```

_C++_

```cpp
#include <iostream>
#include <ctime>

using namespace std;

int main(int argc, char **argv) {
  unsigned int unix_time = (unsigned) time(NULL);
  cout << unix_time << endl;
  return 0;
}
```

_Elixir_

```elixir
# first way
DateTime.utc_now |> DateTime.to_unix

# second way
System.system_time(:second)
```

_Erlang_

```erlang
os:system_time(second).
```

_Golang_

```go
now := time.Now()
unixTs := now.Unix()
```

_Java_

```java
long timestamp = System.currentTimeMillis()/1000;
System.out.println(timestamp);
```

Java 8 brings a new API to work with date and times, [Instant](http://docs.oracle.com/javase/8/docs/api/java/time/Instant.html). A good read about why [JSR-310 is not same as joda-time](http://blog.joda.org/2009/11/why-jsr-310-isn-joda-time_4941.html). You can get current unix time on Java 8 by doing something like below:

```java
long timestamp = Instant.now().getEpochSecond();
System.out.println(timestamp);
```

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

_Python_

```python
from time import time
print(int(time()))

import datetime
print(int(datetime.datetime.utcnow().timestamp()))
```
