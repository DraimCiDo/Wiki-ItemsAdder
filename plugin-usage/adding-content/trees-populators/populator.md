# Populator

## Спавн деревьев случайным образом

Для того чтобы заставить деревья спавниться в мире, необходимо создать `tree_populator`.

```yaml
info:
  namespace: myitems
trees_populators:
  my_tree:
    worlds:
    - world
    bottom_blocks:
    - DIRT
    - GRASS_BLOCK
    - PODZOL
    chance: 40.0
    max_height: 100
    min_height: 50
    amount: 3
    iterations: 2
    tree_type: TREE
    leaves: myitems:my_leaves
    log: myitems:my_log
    biomes:
    - PLAINS
    - SUNFLOWER_PLAINS
    - MOUNTAINS
```

### worlds

Это свойство определяет миры, в которых дерево может спавниться.

### bottom\_block

Это свойство определяет, на каком блоке дерево может спавниться.

### chance

Шанс того, что дерево заспавниться в чанке.

### min\_height and max\_height

Определите интервал высоты, в котором вы хотите заспавнить дерево.

### amount

Сколько деревьев должно быть заспавниться в группе.

### iterations

Сколько групп должно быть заспавнено в текущем чанке, если **шанс** совпадает.

### tree\_type

Тип заспавненого дерева. Полный список можно найти [здесь](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/TreeType.html).\
Это свойство необязательно, дерево будет порождаться в каждом биоме, если вы его не зададите.

### leaves

Блок, который будет использоваться в качестве листьев для этого дерева.

### log

Блок, который будет использоваться в качестве древесины для этого дерева.

### biomes

Список биомов, в которых дерево может заспавниться. Полный список можно найти [здесь].(https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Biome.html).\
Это свойство необязательно, дерево будет порождаться в каждом биоме, если вы его не зададите.

## Пример

{% embed url="https://www.spigotmc.org/resources/trees-newtrees-itemsadder-addon.84604/" %}

![](<../../../.gitbook/assets/immagine (125).png>)
