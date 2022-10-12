# Действия

## Что такое действия?

Действия - это то, что произойдет при наступлении [события](./).

### Список действий:

* `play_sound`
* `stop_sound`
* `execute_commands`
* `play_particle`
* `shoot_particle`
* `play_effect`
* `increment_durability`
* `decrement_durability`
* `decrement_usages`
* `increment_amount`
* `decrement_amount`
* `drop_exp`
* `feed`
* `replace_properties`
* `give_item`
* `replace_near_blocks`
* `replace_block`
* `glow_near_blocks`
* `multiple_break`
* `potion_effect`
* `remove_potion_effect`
* `explosion`
* `damage_near_entities`
* `damage_entity_in_sight`
* `damage_entity`
* `increment_player_stat`
* `decrement_player_stat`
* `cancel`
* `target_potion_effect`
* `target_remove_potion_effect`
* `play_totem_animation`
* `set_block`
* `place_furniture`
* `drop_item`

### Задержка

{% hint style="info" %}
У каждого действия есть специальный атрибут **delay**.\
Это **delay** в тиках перед началом действия.\
Например:

```yaml
items:
  chain_events:
    display_name: "%#FE5A00%chain_events"
    permission: test.chain_events
    resource:
      material: COAL
      generate: true
      textures:
      - "minecraft:item/diamond.png"
    events:
      interact:
        right:
          execute_commands:
            cmd1:
              command: 'tellraw {player} {"text":"Action 1","color":"gold"}'
              as_console: true
              delay: 0
            cmd2:
              command: 'tellraw {player} {"text":"Action 2","color":"gold"}'
              as_console: true
              delay: 20
            cmd3:
              command: 'tellraw {player} {"text":"Action 3","color":"gold"}'
              as_console: true
              delay: 40
          play_sound_1:
            name: minecraft:block.note_block.banjo
            delay: 0
          play_sound_2:
            name: minecraft:block.note_block.banjo
            pitch: 1.2
            delay: 20
          play_sound_3:
            name: minecraft:block.note_block.banjo
            pitch: 1.5
            delay: 40
```
{% endhint %}

### Несколько действий одного типа

{% hint style="info" %}
Вы можете задать одно и то же действие несколько раз. Вам просто нужно добавить `_anything` в конце.\
Например, если вы хотите воспроизвести два звука, вы должны написать следующее:

```yaml
play_sound_first:
  name: itemsadder:ambient.creepy
  volume: 1
  pitch: 1
play_sound_second:
  name: minecraft:ambient.cave
  volume: 1
  pitch: 1
play_sound_3:
  name: minecraft:ambient.cave
  volume: 1
  pitch: 1
```
{% endhint %}

### Разрешение на действия

{% hint style="info" %}
У каждого действия есть специальный атрибут **разрешение**.\
Это **разрешение**, которое игрок должен иметь перед началом **действия**.\
Например, игрок должен иметь разрешение `myitems.usage.secret_items_dispenser`, чтобы воспроизвести звук.\
В этом примере вы заметите "проблему". Звук воспроизводится, даже если у пользователя нет разрешения на событие give. Это потому что... ну, проверка разрешения происходит только на элементе give\_.

```yaml
  test_block:
    display_name: display-name-test_block
    permission: test_block
    resource:
      material: PAPER
      generate: true
      textures:
      - block/test_block.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          break_particles_material: SMITHING_TABLE
    events:
      placed_block:
        interact:
          give_item:
            permission: "myitems.usage.secret_items_dispenser"
            item: DIAMOND
          play_sound:
            name: itemsadder:ambient.creepy
            volume: 1
            pitch: 1
```

####

#### Установка одного и того же разрешения на каждое действие

Если вы хотите установить одинаковое разрешение для каждого действия без копирования и вставки, вы можете!\
Используйте специальный атрибут `all_actions_permission`.\
Например:

```yaml
  test_block:
    display_name: display-name-test_block
    permission: test_block
    resource:
      material: PAPER
      generate: true
      textures:
      - block/test_block.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          break_particles_material: SMITHING_TABLE
    all_actions_permission: "myitems.usage.secret_items_dispenser"
    events:
      placed_block:
        interact:
          give_item:
            item: DIAMOND
      play_sound:
        name: itemsadder:ambient.creepy
        volume: 1
        pitch: 1
```
{% endhint %}

## Список свойств действий

Используйте онлайн-редактор для упрощения создания файлов.

{% content-ref url="../../../../files-editor.md" %}
[files-editor.md](../../../../files-editor.md)
{% endcontent-ref %}

```yaml
play_sound:
  name: itemsadder:ambient.creepy
  volume: 1
  pitch: 1
  
  
stop_sound:
  name: "itemsadder:music_disc.cdk_sunday"
  
  
execute_commands:
  first_example:
    command: 'tellraw {player} {"text":"wow you did something!","color":"gold"}'
    as_console: true
  second:
    command: 'help'
    as_console: false
  third:
    command: 'give {player} diamond'
    as_console: true
    
    
play_particle:
  name: "ENCHANTMENT_TABLE"

# Стреляет частицами (полезно для жезлов и оружия)
shoot_particle:
  name: FLAME
  distance: 7
  
play_effect:
  name: SMOKE
  
increment_durability:
  amount: 10
  
  
decrement_durability:
  amount: 10
  
  
decrement_usages:
  amount: 1


increment_amount:
  amount: 1
          
          
decrement_amount:
  amount: 1    


drop_exp:
  chance: 50
  min_amount: 1
  max_amount: 3
    
# Значения ванильной насыщенности:
# https://minecraft.gamepedia.com/Hunger#Food_level_and_saturation_level_restoration
feed:
  amount: 6
  saturation: 2 # <--- необязательно, по умолчанию 0
    
# Заменяет свойства текущего предмета, копируя их из другого.
# Пока это можно сделать только с custom_model_data. Другие будут добавлены.
replace_properties:
  custom_model_data:
    copy_from_item: "itemsadder:closed_lightsaber"
    restorable: true


give_item:
  item: empty_cup
  amount: 1
  
# Заменяет блоки вокруг блока, с которым вы взаимодействовали или который сломали
replace_near_blocks:
  radius:
    x: 2
    y: 2
    z: 2
  from: LAVA
  to: OBSIDIAN
  decrement_durability: 8
  no_physics: false #по умолчанию - false
  
# Светящиеся блоки вокруг блока, с которым вы взаимодействовали или который сломали
glow_near_blocks:
  decrement_durability:
    amount: 1
  radius:
    x: 50
    y: 50
    z: 50
  material: DIAMOND_ORE
  
# Разбивает несколько блоков вокруг блока, с которым вы взаимодействовали или разбивали
multiple_break:
  keep_ores: true
  drop_all_blocks:
    enabled: true
    need_silk_touch: true
  size: 3
  depth: 3
  
  
potion_effect:
  type: UNLUCK
  duration: 100
  amplifier: 0


remove_potion_effect:
  type: GLOWING
  
  
explosion:
  power: 2
  fire: true
  break_blocks: true
  
# Позволяет наносить урон окружающим вас существам
damage_near_entities:
  entity_groups:
   - HOSTILE
   - PLAYERS
   - PASSIVE
  damage: 4
  range: 7
  
# Позволяет повредить объект, на который вы смотрите.
damage_entity_in_sight:
  damage: 4
  distance: 7
  
# Позволяет повредить объект этого события. Например, при взаимодействии или атаке
# или при событии item_hit_entity
damage_entity:
  damage: 4
  
# Специальное действие, позволяющее увеличить статистику игрока, связанную с hud.
#в данном случае hud называется: "itemsadder:mana_bar"
increment_player_stat:
  name: "itemsadder:mana_bar"
  amount: 1
  
# Специальное действие, позволяющее уменьшить статы игрока, связанные с hud'ом
#в данном случае худ называется: "itemsadder:mana_bar"
decrement_player_stat:
  name: "itemsadder:mana_bar"
  amount: 1
  
# Специальное действие для отмены события (событие, вызвавшее это действие)
cancel: true

# Добавляет эффект зелья к целевому объекту (атака, взаимодействие...).
target_potion_effect:
  type: GLOWING
  duration: 70
  amplifier: 15
  
# Снимает эффект зелья с цели (атака, взаимодействие...).
target_remove_potion_effect:
  type: GLOWING
  
play_totem_animation: animatedtitles:bruh

set_block:
  block: rocks
  target: RELATIVE
  decrement_amount: true
  
place_furniture:
  furniture: furniture
  decrement_amount: true

drop_item:
  item: 2d_furniture
  chance: 99.9
  max_amount: 3
  min_amount: 1
```

###
