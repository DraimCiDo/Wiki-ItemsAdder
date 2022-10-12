# 💎 Популяторы миров

### Пример: два популятора

```yaml
worlds_populators:
  custom_block:
    block: myitems:custom_block
    worlds:
    - world
    replaceable_blocks:
    - STONE
    - DIRT
    - ANDESITE
    - GRANITE
    - COBBLESTONE
    - GRAVEL
    biomes:
    - PLAINS
    chunk_chance: 70.0
    max_height: 45
    min_height: 25
    vein_blocks: 6
    chunk_veins: 1
  custom_block_2:
    block: myitems:custom_block_2
    worlds:
    - world
    replaceable_blocks:
    - DIRT
    chunk_chance: 100.0
    max_height: 64
    min_height: 40
    vein_blocks: 3
    chunk_veins: 1
```

Этот код позволяет вам указать ItemsAdder генерировать блок "myitems:custom\_block" в мире с именем "world" и заменять только блоки типов STONE, DIRT, ANDESITE, GRANITE, COBBLESTONE, GRAVEL и только в биоме PLAINS.\
Это породит 1 жилу, состоящую из 3 блоков в каждом чанке.

### vein\_blocks, chunk\_veins, chunk\_chance

{% hint style="warning" %}
Я предлагаю вам считать значения из файла `blocks.yml`, который я создал в папке **ItemsAdder**.\
Не ставьте слишком большие значения, иначе сервер может лагать.\
Возьмем мои значения в качестве примера.
{% endhint %}

**chunk\_veins**: количество жил, которые будут заспавнены в чанке\
**vein\_blocks**: количество блоков в каждой рудной жиле (или **размер жилы**)\
**chunk\_chance**: шанс того, что это генерация произойдет в чанке. Вы должны установить значение 100 для обычных руд и снизить его для более редких руд.

{% hint style="warning" %}
<mark style="color:red;">**Старый ItemsAdder**</mark> версии до **3.1.6** использовали эти свойства вместо этого:\
`chunk_veins` -> `iterations`

`vein_blocks` -> `amount`

`chunk_chance` -> `chance`
{% endhint %}

### Биомы

Вы можете убрать эту опцию, и плагин будет спавнить руды в каждом биоме.

```yaml
  custom_block:
    block: myitems:custom_block
    worlds:
    - world
    replaceable_blocks:
    - STONE
    - DIRT
    - ANDESITE
    - GRANITE
    - COBBLESTONE
    - GRAVEL
    chunk_chance: 70.0
    max_height: 45
    min_height: 25
    vein_blocks: 6
    chunk_veins: 1
```

### Заменяемые блоки

Вы можете удалить эту опцию, и плагин будет спавнить руду, заменяя каждый блок, вместо того, чтобы проверять, можно ли его заменить.

```yaml
  custom_block:
    block: myitems:custom_block
    worlds:
    - world
    chunk_chance: 70.0
    max_height: 45
    min_height: 25
    vein_blocks: 6
    chunk_veins: 1
```

