Minetest digibuilder
======

![](https://github.com/BuckarooBanzay/digibuilder/workflows/luacheck/badge.svg)


State: **WIP**

# Commands

## Get node

```lua
digiline_send("digibuilder", {
  command = "getnode",
  pos = { x=1, y=0, z=0 }
})

if event.type == "digiline" and event.channel == "digibuilder" then
  -- { error = true, message = "..." }
  -- { pos = { x=1, y=0, z=0 }, name = "default:stone" }
  -- { pos = { x=1, y=0, z=0 }, name = "stairs:stair_stone", param2 = 3 }
end
```

## Set node

```lua
digiline_send("digibuilder", {
  command = "setnode",
  pos = { x=1, y=0, z=0 },
  param2 = 3,
  name = "stairs:stair_stone"
})

if event.type == "digiline" and event.channel == "digibuilder" then
  -- { error = true, message = "..." }
  -- { pos = { x=1, y=0, z=0 }, success = true, name = "default:stone" }
  -- { pos = { x=1, y=0, z=0 }, success = true, name = "stairs:stair_stone", param2 = 3 }
end
```
