# [⌂](../README.md) › [Languages](../README.md#languages) › Minecraft › **Datapacks**

- usefull mcfunction commands

### Create leash between two entities
```
data modify entity @e[type=chicken,sort=nearest,limit=1] Leash set from entity @e[type=bat,sort=nearest,limit=1] {}
```

### Select mobs that aren't leashed
```
say @e[nbt=!{Leash:{}}]
```

### Create stack of entities
```
summon bat ~ ~ ~ {Passengers:[{id:armor_stand}]}
```

### Kill specific item entities
```
kill @e[type=item,nbt={Item:{id:"minecraft:wool"}}]
```

## Entity data
Nbt Data | Description
:--- | :---
`CustomName:"\"_NAME_\""` | Entity custom name
`display:{Name:'[{"text":"_NAME_","color":"_COLOR_","italic":false}]'}` | Item display name
`ActiveEffects:[{Id:14b,Duration:999999,ShowParticles:0b}]` | Invisible (via effect)
`Glowing:true` | Glowing (permanently)
`PersistenceRequired:true` | Never naturally despawn
`Silent:true` | Disable sound
`DeathLootTable:"invalid"` | No loot / mob drops
`NoAI:true` | Not moving on their own
`Invulnerable:true` | 