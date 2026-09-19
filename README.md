# CreeperRecover
Recovers blocks destroyed by Creepers. This fork targets Paper 26.2 and is
preconfigured for the Towny Reborn Earth worlds.

## Towny Reborn defaults

- Paper 26.2 / Java 25
- automatic recovery without player chat messages
- Creeper explosions only
- enabled only in `earth`, `earth_nether` and `earth_the_end`
- five-second delay before recovery starts
- no explosion block drops, preventing duplicate items
- solid blocks placed during the delay are not overwritten

Place `creeper-recover-1.2.0-spigot.jar` in `plugins/` and restart the server. The
plugin creates `plugins/CreeperRecover/config.json` automatically.

# Images
![Example 1](https://i.postimg.cc/vHJMc4Qj/2021-12-31-17-53-38.gif)

# Commands
![Command 1](https://raw.githubusercontent.com/HttpRafa/CreeperRecover/master/images/command1.png)
![Command 2](https://raw.githubusercontent.com/HttpRafa/CreeperRecover/master/images/command2.png)

# Config
```
{
  "configVersion": 3,
  "plugin": {
    "enabled": true,
    "bStats": false,
    "ignoreUpdates": true
  },
  "recover": {
    "recoverSpeed": 150,
    "recoverDelay": 5000,
    "blockRecoverSound": "BLOCK.ROOTED_DIRT.PLACE",
    "blockBlacklist": []
  },
  "target": [
    {
      "type": "WORLD",
      "ignore": false,
      "whitelist": [
        "earth",
        "earth_nether",
        "earth_the_end"
      ],
      "blacklist": []
    },
    {
      "type": "ENTITY",
      "ignore": false,
      "entityTypes": [
        "CREEPER"
      ]
    },
    {
      "type": "HEIGHT_RANGE",
      "ignore": true,
      "from": -64,
      "to": 320
    },
    {
      "type": "HEIGHT_FIXED",
      "ignore": true,
      "fixed": 32
    }
  ]
}
```
## Options
```
configVersion: Is set to the current config version.
bStats: Whether anonymous bStats telemetry is enabled. It is disabled by default in this fork.
ignoreUpdates: If you don't want to receive a message in the console when the plugin has a update.
recoverSpeed: The time in milliseconds between each block that is being recovered.
recoverDelay: The time in milliseconds to wait before starting the recovery
blockRecoverSound: Is the sound played when the plugin places a block.
blockBlacklist: Blocks in this list are ignored by the plugin. 
target: In the list, rules are specified where the plugin should take effect.

all: If "all" is set to true all entities will be affected. So if you want only TNT to be recovered then set "all" to false and define TNT in the entityTypes setting.
```

### Example Entities
```
CREEPER
TNT
SMALL_FIREBALL
FIREBALL
WITHER_SKULL
DRAGON_FIREBALL
```

# Config Examples[target]
### Affect only some worlds
#### Whitelist: Only affect certain worlds
#### Blacklist: Affect all world except those in the blacklist
```
{
      "type": "WORLD",
      "ignore": false,
      "whitelist": [],
      "blacklist": []
}
```
### Affect only TnT and Creepers
```
{
      "type": "ENTITY",
      "ignore": false,
      "entityTypes": [
        "CREEPER",
        "TNT"
      ]
}
```

### Affect only from Y-0 to Y-320
```
{
      "type": "HEIGHT_RANGE",
      "ignore": false,
      "from": 0,
      "to": 320
}
```

### Affect only at Y-60
```
{
      "type": "HEIGHT_FIXED",
      "ignore": false,
      "fixed": 60
}
```

# Pages
#### [Modrinth](https://modrinth.com/plugin/creeper-recover)
#### [SpigotMC](https://www.spigotmc.org/resources/creeper-recover.98836/)
#### [DeinPlugin](https://deinplugin.net/storage/c97b3869-d8ec-4177-8d8c-b7792c96eedc)
