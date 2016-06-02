# Factorio Brain Dump
As I have been playing Factorio there are some commands and tips that I want to remember. 

[HypnoBunny Gaming][HypnoBunny] has some awesome videos that show off some cool designs.

## Trains ##
After a lot of head scratching [this set of images][TrainHints] helped a lot. Here is information on [Block Signals][BlockSignal] and [Chain Signals][ChainSignal].

## Console Commands ##
There are lots of good console commands [here][ConsoleCommands].

### New resource Patch ###
```
/c local surface = game.local_player.surface;
for y=-2,2 do
 for x=-2,2 do
  surface.create_entity({name="stone", amount=5000, position={game.local_player.position.x+x, game.local_player.position.y+y}})
 end
end
```
Change the name to any of the following:

* copper-ore
* crude-oil
* iron-ore
* stone
* raw-wood
* water

### Insert item into inventory ###
[Here are some items you can add][ItemList]. Just change name and count to suit your needs.
```
/c game.local_player.insert{name="iron-plate", count=100}
```

### Oil Patch Commands[*][OilPatchCommands] ###
```
Spawn a new patch at player location:
/c game.local_player.surface.create_entity{name="crude-oil", position=game.player.position, amount=100000}

Refil a patch:
/c game.local_player.selected.amount = 100000
```

### Peaceful mode and kill all units ###
```
/c game.peaceful_mode = true
/c game.forces["enemy"].kill_all_units()
```

### Remove all enemeys within 250 units
```
/c radius = 250;
  p = game.player.position;
  for _,type in pairs{"unit", "unit-spawner", "turret"} do;
    enemies = game.get_surface(1).find_entities_filtered{area={{p.x-radius,p.y-radius},{p.x+radius,p.y+radius}}, type=type, force=game.forces.enemy};
  for _,enemy in pairs(enemies) do enemy.destroy(); end;
  end;
```


[OilPatchCommands]: https://forums.factorio.com/viewtopic.php?t=15494
[ConsoleCommands]: https://wiki.factorio.com/index.php?title=Console
[ItemList]: https://github.com/ingmar/factorio-trees/blob/master/recipes.lua
[TrainHints]: http://imgur.com/a/zG13U#0
[BlockSignal]: https://wiki.factorio.com/index.php?title=Railway/Signal/Block_signal
[ChainSignal]: https://wiki.factorio.com/index.php?title=Railway/Signal/Chain_signal
[HypnoBunny]: https://www.youtube.com/channel/UCQOrrjulwm51geoEOzynmJw