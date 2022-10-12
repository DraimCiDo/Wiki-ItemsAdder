# Behaviours

Что такое поведение?

Поведение - это **уже закодированный** набор **действий**, которые будет выполнять предмет, и которые **не являются ванильными**.\
Эти **поведения** уже включены в плагин и позволят вам добавить некоторую уже закодированную функциональность к вашему предмету.

### Список моделей поведения, включенных в плагин

* `block_trade_machine`
* `furniture_trade_machine`
* `fuel`
* `furniture`
* `furniture_sit`
* `gun`
* `hat`
* `keep_on_death`
* `liquid_analyzer`
* `liquid_bucket`
* `mob_animation`
* `mob`
* `music_disc`
* `sapling`
* `spawn_egg`
* `vehicle`

{% hint style="info" %}
Вы можете получить предложения о том, как использовать модели поведения, используя официальный редактор:
{% endhint %}

```yaml
# Это поведение позволяет вам открыть графический интерфейс торговли со следующими элементами
# Например, black_fishing_rod и red_fishing_rod
block_trade_machine:
  title: "Your title"
  permission: "mypermission.trade.example" # <--- это необязательно
  gui_texture: ###ЭТО НЕОБЯЗАТЕЛЬНО, используйте его только для ретекстурирования GUI
    left: customization_table_left
    right: customization_table_right
  trades_list:
    black_fishing_rod:
      ingredients:
        slot1:
          item: FISHING_ROD
          amount: 1
        slot2:
          item: BLACK_DYE
          amount: 1
      result:
        item: black_fishing_rod
        amount: 1
    red_fishing_rod:
      ingredients:
        slot1:
          item: FISHING_ROD
          amount: 1
        slot2:
          item: RED_DYE
          amount: 1
      result:
        item: red_fishing_rod
        amount: 1
        
furniture_trade_machine:
# ....... это то же самое, что и block_trade_machine

   
# Когда вы нажмёте ПКМ по этому предмету, он будет помещен на землю с
# стойкой брони. На подставке будет лежать предмет в виде шлема и она будет невидима.
furniture:
  entity: armor_stand # вы также можете использовать item_frame (лучше работает в 1.16+)
  small: true
  gravity: true
  fixed_rotation: false
  light_level: 7  
  solid: false
  opposite_direction: false #заставляет модель поворачиваться на 180 при размещении
  hitbox:
    length: 2
    width: 2.3
    height: 1
    length_offset: 0.5
    width_offset: 0.5
    height_offset: 0.5
  placeable_on:
    walls: false
    ceiling: false
    floor: true

# Если вы добавите это поведение и поведение "furniture", вы сможете сидеть
# на мебели на определенной высоте.
furniture_sit:
  sit_height: 0.9
  opposite_direction: true #по умолчанию - true
  # Садитесь на каждый БАРЬЕРНЫЙ блок мебели (для многоместных кресел)
  sit_all_solid_blocks: false
  

# Позволяет использовать этот предмет в качестве оружия. Вы можете решить, какой снаряд должен
# держать в левой руке, чтобы выстрелить.
gun:
  projectile: itemsadder:clip
  

# Позволяет использовать текущий предмет в качестве шляпы (аналогично поведению ванильного шлема).
hat: true

# Позволяет сделать так, чтобы предмет оставался в инвентаре игрока после смерти
keep_on_death: true

# Позволяет использовать текущий элемент в качестве ванильного музыкального диска.
# Помните, что вам придется создать пользовательский звук, чтобы иметь возможность
# воспроизводить что-либо.
music_disc:
  song:
    name: "itemsadder:music_disc.cdk_sunday"
    description: "Cdk - Sunday"
    

# Позволяет использовать текущий предмет в качестве ездового транспортного средства
vehicle:
  fixed_rotation: false
  small: true
  sit_height: 0
  step_height: 0.1
  hitbox:
    length: 2
    width: 1.7
    height: 1
  speed:
    drive: 1
    jump: 0.3
    fly: 0
  fuel:
    start: 150
    max: 300
    items:
      COAL: 1
      CHARCOAL: 1
      COAL_BLOCK: 9
      "itemsadder:banana": 1
  smoke:
    amount: 2
    offset:
      x: 0
      y: 0
      z: -0.8
```





