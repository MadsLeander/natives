---
ns: MISC
---
## GET_WIND_DIRECTION

```c
// 0x1F400FEF721170DA 0x89499A0D
Vector3 GET_WIND_DIRECTION();
```

## Return value
Returns a vector3 with x and y being the rotation in 2d space. Z is seemingly not used.

Gets the wind direction, use math.atan (or equivalent) to get the rotation in radians.

## Examples
```lua
CreateThread(function()
    while true do
        local windDirection = GetWindDirection()

        -- Gets the wind direction in degrees
        local degrees = math.deg(math.atan(windDirection.x, windDirection.y))
        print("wind direction in degrees:", degrees)

        -- Draws an airplane marker above the player's head to show the wind direction
        local coords = GetEntityCoords(PlayerPedId())
        DrawMarker(7, coords.x, coords.y, coords.z + 1.0, windDirection.x, windDirection.y, 0.0, 0.0, 0.0, 0.0, 2.0, 2.0, 2.0, 255, 128, 0, 50, false, false, 2, false, nil, nil, false)

        -- Heading calculation example
        local heading = ((degrees % 360) - 360.0) * -1
        print("wind direction in world heading:", heading)

        Wait(0)
    end
end)
```
