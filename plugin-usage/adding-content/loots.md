# 🎁 Лут

Лут можно использовать для указания времени, когда нужно бросить определенный предмет.\
Вы можете решить создать различные типы добычи:&#x20;

* Блоки
* Мобы
* Рыбалка

Например, это категория лута в файле .yml, который я создал.

```yaml
loots:
  blocks:
    ruby_ore:
      type: itemsadder:ruby_ore
      items:
        ruby:
          item: itemsadder:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
    nether_quartz_ore:
      type: NETHER_QUARTZ_ORE
      drop_only_first: true
      items:
        crystal:
          item: itemsadder:crystal
          min_amount: 1
          max_amount: 2
          chance: 10
        knowledge_fragment:
          item: itemsadder:knowledge_fragment
          min_amount: 1
          max_amount: 2
          chance: 15
```

В этом примере есть два лута в категории **blocks**.

Первый называется **ruby\_ore** (вы можете называть их по своему усмотрению), он будет выпадать в виде предмета **itemsadder:ruby**, когда вы сломаете пользовательский **блок** типа **itemsadder:ruby\_ore** с минимальным **количеством** **1** и **максимальным** количеством **2** с **100% шансом**.

Второй - это лут из ванильного **блока**. Как вы понимаете, он будет выпадать в виде **кристалла** или **knowledge\_fragment**, когда игрок сломает **NETHER\_QUARTZ\_ORE**.\
Эти **выпадения** определяются **ItemsAdder** на основе **шанса**, который вы установили.&#x20;

{% hint style="info" %}
Особое свойство: **drop\_only\_first**\
Это позволяет **остановить** **плагин** от **сбрасывания каждого** из **предметов**, которым удалось извлечь **правильный** шанс быть **сброшенными**. \
**ВНИМАНИЕ**: это сделает ваши предметы **труднее** для того, чтобы их **выбросили**.
{% endhint %}

## Выпадения только в определенных биомах

```yaml
loots:
  blocks:
    ruby_ore:
      type: itemsadder:ruby_ore
      biomes:
        - PLAINS
        - SUNFLOWER_PLAINS
        - MOUNTAINS
      items:
        ruby:
          item: itemsadder:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
```

## Игнорировать фортуну

Вы можете сделать так, чтобы лут игнорировал удачу, добавив свойство **ignore\_fortune**.

```yaml
loots:
  blocks:
    ruby_ore:
      type: itemsadder:ruby_ore
      items:
        ruby:
          item: itemsadder:ruby
          min_amount: 1
          max_amount: 2
          chance: 100
          ignore_fortune: true # <----- здесь
```

## Другие виды добычи

Как я уже говорил, есть и другие виды лута: мобы и рыбалка.\
Вот несколько примеров:

### Рыбалка

```yaml
loots:
  fishing:
    loot_blue_parrotfish:
      biomes:
        - WARM_OCEAN
      items:
        item_1:
          item: itemsadder:blue_parrotfish
          min_amount: 1
          max_amount: 1
          chance: 5
    loot_green_sunfish:
      items:
        item_1:
          item: itemsadder:green_sunfish
          min_amount: 1
          max_amount: 1
          chance: 5
    loot_goldfish:
      items:
        item_1:
          item: itemsadder:goldfish
          min_amount: 1
          max_amount: 1
          chance: 5
```

### Мобы

```yaml
loots:
  mobs:
    villager:
      type: VILLAGER
      nbt:
        profession:
          path: VillagerData.profession
          value: minecraft:farmer
          type: string
      items:
        item_1:
          item: itemsadder:straw_hat
          min_amount: 1
          max_amount: 1
          chance: 100
    ender_dragon:
      type: ENDER_DRAGON
      items:
        item_1:
          item: itemsadder:ender_dragon_wings
          min_amount: 1
          max_amount: 1
          chance: 100
```

{% hint style="info" %}
### Пользовательские луты для мобов ([метод старых существ](mobs/old-method/))
{% endhint %}

Для того чтобы ItemsAdder выпадал предмет в зависимости от того, когда вы убиваете пользовательского моба (созданного с помощью ItemsAdder), необходимо использовать атрибут метаданных `ItemsAdderMob`. Пример:

```yaml
loots:
  mobs:
    soul:
      type: HUSK
      metadata:
        ItemsAdderMob:
          name: "ItemsAdderMob"
          value: "creaturesplus:soul"
          type: "string"
      items:
        ruby:
          item: ruby
          min_amount: 1
          max_amount: 1
          chance: 100
```

Как вы видите, я установил атрибут `ItemsAdderMob` **** и указал моего пользовательского моба **namespace:id** (в этом примере я использовал моба **creaturesplus:soul**).

{% hint style="info" %}
### Пользовательские предметы добычи
{% endhint %}

Чтобы позволить ItemsAdder сбрасывать предмет на основе того, когда вы убиваете пользовательскую сущность (созданную с помощью ItemsAdder), вы должны использовать атрибут метаданных `ItemsAdderEntity`. Пример:

```yaml
loots:
  mobs:
    soul:
      type: HUSK
      metadata:
        ItemsAdderEntity:
          name: "ItemsAdderEntity"
          value: "custom:ninja_skeleton"
          type: "string"
      items:
        ruby:
          item: ruby
          min_amount: 1
          max_amount: 1
          chance: 100
```

Как вы видите, я установил атрибут `ItemsAdderEntity` **** и указал моего пользовательского моба **namespace:id** (в этом примере я использовал моб **custom:ninja\_skeleton**).

{% hint style="info" %}
### Профессии жителей (и любые другие атрибуты НБТ, которые вы хотите сопоставить)
{% endhint %}

```yaml
loots:
  mobs:
    villager:
      type: VILLAGER
      nbt:
        profession:
          path: VillagerData.profession
          value: minecraft:farmer
          type: string
      items:
        item_1:
          item: itemsadder:straw_hat
          min_amount: 1
          max_amount: 1
          chance: 100
```

Как вы видите, я установил атрибут **profession** и указал путь **NBT атрибута**, который в данном случае **VillagerData.profession**.\\
Затем я установил значение **minecraft:farmer**, это говорит ItemsAdder, что он будет искать только **жителей** с атрибутом **VillagerData.profession**, установленным на **minecraft:farmer**.

{% hint style="warning" %}
Атрибут type в **nbt** и **metadata** действительно **важен**, не **забывайте** о нем, иначе совпадения могут не произойти.
{% endhint %}

{% hint style="info" %}
### Падение на основе данных NBT объекта Tile (например, Spawner)
{% endhint %}

```yaml
loots:
  blocks:
    change_me:
      enabled: true
      type: SPAWNER
      nbt:
        spawner_type:
          path: SpawnData.entity.id
          value: minecraft:zombie
          type: string
      items:
        change_me:
          item: ACACIA_BOAT
          min_amount: 1
          max_amount: 1
          chance: 100
          ignore_fortune: false
```

{% hint style="warning" %}
Вы должны включить эту настройку, если хотите иметь возможность получать предметы из спавнеров, используя зачарованный предмет с помощью silktouch.

```yaml
loots:  
    allow-loots-drop-from-spawners-using-silk-touch: true
```
{% endhint %}
