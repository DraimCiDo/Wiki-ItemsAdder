# 2D иконки для блоков/мебели

{% hint style="warning" %}
Эта функция требует **ItemsAdder 3.1.6+**.
{% endhint %}

{% embed url="https://youtu.be/FOLoAAjV_oI" %}

## Блок

### Шаг 1

Создайте 2D-значок для блока

{% hint style="info" %}
Замените `my_items` на ваш [namespace](basic-concepts/namespace/#namespace)!
{% endhint %}

```yaml
info:
  namespace: my_items
items:
  rocks:
    display_name: Rocks
    permission: blocks.rocks
    lore:
     - 'lore-decorative-item'
    resource:
      material: PAPER
      generate: true
      textures:
      - item/rocks
    events:
      interact:
        right:
          set_block:
            block: rocks_placed
            target: RELATIVE
            decrement_amount: true
```

Теперь создайте файл `rocks.png` в папке `data\resource_pack\assets\my_items\textures\item`

### Шаг 2

Создайте предмет, который показывает размещенную модель скалы. Это другой предмет, чем тот, который вы видите в инвентаре (тот, который был создан в **шаге 1**).

```yaml
  rocks_placed:
    display_name: ""
    permission: admin.blocks.rocks_placed
    resource:
      material: PAPER
      generate: false
      model_path: block/rocks_placed
    specific_properties:
      block:
        placed_model:
          type: REAL_WIRE
        cancel_drop: true
        sound:
          place:
            name: block.stone.place
    events:
      placed_block:
        break:
          drop_item:
            item: rocks
```

Теперь создайте файл `placed_rocks.json` внутри папки `data\resource_pack\assets\my_items\models\block\`

### Готово!

Теперь попробуйте нажать ПКМ по предмету `rocks` и вы увидите, что он помещает модель `rocks_placed`.

## Мебель

### Шаг 1

Создайте 2D-значок для мебели

{% hint style="info" %}
Замените `my_items` на ваш [namespace](basic-concepts/namespace/#namespace)!
{% endhint %}

```yaml
info:
  namespace: my_items
items:
  2d_furniture:
    display_name: 2d_furniture
    permission: 2d_furniture
    resource:
      material: PAPER
      generate: true
      textures:
      - item/2d_furniture
    events:
      interact:
        right:
          place_furniture:
            furniture: furniture
            decrement_amount: true
```

Теперь создайте файл `2d_furniture.png` в папке `data\resource_pack\assets\my_items\textures\item\`

### Шаг 2

Создайте предмет, который показывает размещенную модель мебели. Это будет другой предмет, чем тот, который вы видите в инвентаре (тот, который был создан в **шаге 1**).

```yaml
  furniture:
    display_name: furniture
    permission: furniture
    lore:
    - 'lore-decorative-item'
    resource:
      material: PAPER
      generate: false
      model_path: decoration/furniture
    behaviours:
      furniture:
        solid: true
        cancel_drop: true
        hitbox:
          length: 1
          width: 1
          height: 1
    events:
      placed_armorstand:
        break:
          drop_item:
            item: 2d_furniture
```

Теперь создайте файл `furniture.json` внутри папки `data\resource_pack\assets\my_items\models\decoration\`

### Готово!

Теперь попробуйте нажать ПКМ по предмету `2d_furniture` и вы увидите, что он помещает модель `furniture`.
