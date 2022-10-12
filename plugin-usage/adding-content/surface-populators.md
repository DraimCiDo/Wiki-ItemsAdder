# 🍄 Декорации в мире

## Создание декораций на поверхности мира

С помощью ItemsAdder вы можете генерировать декорации по всему миру, чтобы сделать ваш сервер более профессиональным и оригинальным.

Например, вы можете создавать новые грибы, новые маленькие растения, камни и украшения.

![](../../.gitbook/assets/leaves.png)

![](../../.gitbook/assets/desert\_rose.png)

## Создание декораций в мире

### Создание конфигурации

Например, давайте создадим розу, которая будет спавниться по всему миру.

```yaml
info:
  namespace: myitems
surface_decorators:
  rose:
    block: rose
    bottom_blocks:
    - DIRT
    - GRASS_BLOCK
    biomes:
    - PLAINS
    - SUNFLOWER_PLAINS
    - RIVER
    - MOUNTAINS
    - MOUNTAIN_EDGE
    - BIRCH_FOREST
    - BIRCH_FOREST_HILLS
    - TALL_BIRCH_FOREST
    - TALL_BIRCH_HILLS
    worlds:
      - world
    chance: 10
    max_height: 255 
    min_height: 0
    amount: 1
```

Как вы можете видеть, я установил некоторые свойства:

`block` это блок ItemsAdder, который будет заспавнен в качестве украшения.

`bottom_blocks` свойство используется для определения типов блоков, на которых может заспавниться украшение.

`biomes` свойство используется для определения допустимых биомов, в которых может заспавниться украшение.

`worlds` Свойство определяет миры, в которых может заспавнить украшение.

`chance` это сколько декораций может заспавниться в чанке.

`max_height` это максимальная высота мира, на которой может появиться украшение.

`min_height` это минимальная высота мира, на которой может появиться украшение.

`amount` свойство используется для определения кол-во заспавненых декораций, например если ввести 5, то заспавниться 5 декораций возле друг друга.

## Создание блока

Теперь вам нужно просто создать блок, следуя руководству. Вы можете использовать блоки `REAL_NOTE`, `REAL_WIRE` `REAL_TRANSPARENT` и `REAL`, в зависимости от ваших потребностей.

{% content-ref url="creating-a-custom-item/blocks/block.md" %}
[block.md](creating-a-custom-item/blocks/block.md)
{% endcontent-ref %}

## Пример

Полностью рабочий аддон можно скачать здесь:

{% embed url="https://www.spigotmc.org/resources/deco-worlddeco-add-autogenerating-decorations-on-your-world-surface.95207" %}

![](../../.gitbook/assets/worlddeco\_ia.png)
