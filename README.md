# Factorio Brain Dump
As I have been playing Factorio there are some commands and such that I want to remember.

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


[OilPatchCommands]: https://forums.factorio.com/viewtopic.php?t=15494
[ConsoleCommands]: https://wiki.factorio.com/index.php?title=Console
[ItemList]: https://github.com/ingmar/factorio-trees/blob/master/recipes.lua