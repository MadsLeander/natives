---
ns: MISC
---
## SET_WIND_DIRECTION

```c
// 0xEB0F4468467B4528 0x381AEEE9
void SET_WIND_DIRECTION(float direction);
```

Sets the wind direction. Using this native will stop the game from changing the wind direction by itself. Passing in a negative value (in radians) seems to make the game change the direction again at its own will.

## Parameters
* **direction**: the [wind direction](https://en.wikipedia.org/wiki/Wind_direction) in radians

## Examples
```lua
-- 180 degrees, wind will blow from the south
SetWindDirection(math.rad(180.0))

-- Makes the game change the direction again by itself
SetWindDirection(math.rad(-1.0))
```

```cs
// 180 degrees, wind will blow from the south
SetWindDirection(3.1415f);

// Makes the game change the direction again by itself
SetWindDirection(-0.0174f);
```
