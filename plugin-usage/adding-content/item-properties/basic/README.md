---
description: Коллекция основных свойств предмета
---

# Основной

## Включенение

```yaml
enabled: true
```

С помощью этой настройки можно полностью отключить элемент.

{% hint style="warning" %}
**Если у игрока есть предмет в инвентаре, он не будет удален.**\
**То же самое для блоков, но если их сломать, они больше не будут падать.**\.
{% endhint %}

## Отображаемое имя

```yaml
display_name: "Test"
```

Это имя, которое пользователь будет видеть на предмете

## Разрешение

```yaml
permission: myitem
```

{% content-ref url="item-permission.md" %}
[item-permission.md](item-permission.md)
{% endcontent-ref %}

## Описание предмета

```yaml
lore:
- '&7When you mine a block'
- '&7it drops exp orbs'
- '&750% of times.'
```

Строки описания предмета

## Зачарования

```yaml
enchants:
  - ARROW_FIRE:1
  - anger_artifact:1
  - my_custom_plugin:custom_enchant:6
```

Зачарования предмета.\
Вы можете установить [ванильные зачарования](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html) и пользовательские энчанты других плагинов (например, [EcoEnchants](https://www.spigotmc.org/resources/%E2%9A%A1-1-16-1-16-5-ecoenchants-%E2%9C%A8-220-custom-enchantments-%E2%9C%85-essentials-cmi-support.79573/), [GoldenEnchants](https://www.spigotmc.org/resources/goldenenchants-%E2%80%A2-more-vanilla-like-enchantments-1-14-1-16.61693/)...).\
Поддерживает также **namespace** (если вы создаете пользовательские энчанты с использованием ключей с распределенными именами).

## Модификаторы атрибутов

```yaml
attribute_modifiers:
  mainhand:
    attackDamage: 19
    attackSpeed: 1.1
    maxHealth: 1.1
    movementSpeed: -1
    armor: 1.1
    armorToughness: 1.1
    attackKnockback: 1.1
    luck: 1.1
  offhand:
    attackDamage: 19
    attackSpeed: 1.1
    maxHealth: 1.1
    movementSpeed: 1.1
    armor: 1.1
    armorToughness: 1.1
    attackKnockback: 1.1
    luck: 1.1
```

Это ванильные модификаторы атрибутов, более подробную информацию вы можете получить здесь [https://minecraft.gamepedia.com/Attribute#Attributes\_available\_on\_all\_living\_entities](https://minecraft.gamepedia.com/Attribute#Attributes\_available\_on\_all\_living\_entities)

## Прочность

```yaml
durability:
  max_custom_durability: 200
  custom_durability: 32
  disappear_when_broken: false
  unbreakable: false
  usages: 5
```

Это довольно простое объяснение.\
`usages` - это специальное свойство, которое позволяет вам установить количество использований для текущего предмета. Не забудьте уменьшить его с помощью событий (смотрите документацию по событиям).

`custom_durability` это количество прочности, которое предмет имеет при обработке (если не указано, это то же, что и `max_custom_durability`)

`max_custom_durability` максимальная прочность, которую может достичь предмет

## Флаги предметов

```yaml
item_flags:
  - HIDE_ATTRIBUTES
  - HIDE_DESTROYS
  - HIDE_ENCHANTS
  - HIDE_PLACED_ON
  - HIDE_POTION_EFFECTS
  - HIDE_UNBREAKABLE
```

Специальные флаги предметов, которые могут скрыть некоторую ванильную информацию о предмете.\
Вы можете найти подробный список информации здесь: [https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/inventory/ItemFlag.html)

## blocked\_enchants

Специальное свойство предмета, которое отключает зачарование этого предмета, так что ваши пользователи не смогут его зачаровать.

{% tabs %}
{% tab title="Disable some enchants" %}
```yaml
blocked_enchants:
      - DAMAGE_UNDEAD
      - DAMAGE_ALL
      - DAMAGE_ARTHROPODS
      - KNOCKBACK
      - DURABILITY
      - SWEEPING_EDGE
```
{% endtab %}

{% tab title="Disable all enchants" %}
```yaml
blocked_enchants:
      - ALL
```
{% endtab %}
{% endtabs %}

## events\_cooldown

Специальный атрибут для ограничения спама событий игроками. Выражается в тиках, поэтому 20 = 1 секунда.

```yaml
  healing_crystals:
    display_name: display-name-healing_crystals
    permission: healing_crystals
    resource:
      material: IRON_SWORD
      generate: true
      textures:
      - item/healing_crystals.png
    durability:
      max_custom_durability: 6
      custom_durability: 6
      disappear_when_broken: true
    item_flags:
    - HIDE_ATTRIBUTES
    events_cooldown: 1200 ########### <-- ПРИМЕР - 60 секунд
    events:
      interact:
        right:
          play_particle:
            name: HEART
          decrement_durability:
            amount: 1
          potion_effect:
            type: REGENERATION
            duration: 70
            amplifier: 4
```

## events\_needed\_player\_stats

Специальный атрибут, заставляющий события работать только в том случае, если стата игрока удовлетворяет заданному правилу.

You can set it to `>`, `<` ad `=`

#### Пример:

{% content-ref url="../../creating-a-custom-item/magic-wand.md" %}
[magic-wand.md](../../creating-a-custom-item/magic-wand.md)
{% endcontent-ref %}

```yaml
  magic_wand:
    display_name: "Magic wand"
    permission: magic_wand
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - item/example_item.png
    durability:
      max_custom_durability: 512
    attribute_modifiers:
      mainhand:
        attackDamage: 0.1
    blocked_enchants:
    - ALL
    events_needed_player_stats:
      mana: ">0" ### <---- например. Можно также установить значение <5 или =1.
    events:
      interact:
        entity:
          target_potion_effect:
            type: GLOWING
            duration: 70
            amplifier: 15
          decrement_player_stat:
            name: mana
            amount: 1
```

## glow

Вы можете сделать предмет светящимся при падении на землю.\
Очень полезно для **редких предметов**.

{% hint style="warning" %}
Для того чтобы воспользоваться функцией свечения, необходимо установить два API.

[GlowAPI](https://www.spigotmc.org/resources/api-glowapi.19422/) и [PacketListenerAPI](https://www.spigotmc.org/resources/api-packetlistenerapi.2930/)

Они нужны, потому что эту функцию невозможно реализовать без написания чрезвычайно длинного кода, кто-то уже сделал это, и мы можем использовать их API.
{% endhint %}

Пример

![](<../../../../.gitbook/assets/immagine (114).png>)

```yaml
items:
  glowing_item:
    display_name: Светящийся предмет
    resource:
      material: DIAMOND
      generate: true
      textures:
      - item/glowing_item.png
    drop:
      glow:
        enabled: true
        color: DARK_RED
```

## show\_name

Вы можете заставить дроп показывать свое имя.\
Очень полезно для **редких предметов**.\
Пример:

![](<../../../../.gitbook/assets/immagine (118) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png>)

```yaml
  glowing_item:
    display_name: Светящийся предмет
    resource:
      material: DIAMOND
      generate: true
      textures:
      - item/glowing_item.png
    drop:
      show_name: true
```

## template

{% content-ref url="templates-and-variants.md" %}
[templates-and-variants.md](templates-and-variants.md)
{% endcontent-ref %}

## variant\_of

{% content-ref url="templates-and-variants.md" %}
[templates-and-variants.md](templates-and-variants.md)
{% endcontent-ref %}
