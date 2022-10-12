---
description: Как вручную редактировать файлы blockstates.json
---

# Ручное редактирование blockstates

## Редактирование note\_block.json

{% hint style="warning" %}
Обновленитесь до ItemsAdder 2.4.20
{% endhint %}

Вы можете вручную отредактировать файл `assets\minecraft\blockstates\note_block.json`, добавив в него свои собственные правила.

**ItemsAdder** автоматически объединит ваш пользовательский json-файл с пользовательскими блоками **ItemsAdder**, если вы их создали.

## Редактирование других blockstates .json

Вы можете редактировать любой файл блокчейна, но для редактирования некоторых из них вы должны прочитать следующее.

Чтобы редактировать некоторые файлы blockstates, вы должны отключить функцию пользовательских блоков ItemsAdder в зависимости от типа, который вы хотите редактировать. В будущем я могу разрешить ручное редактирование этих файлов без отключения функции блоков ItemsAdder (это нелегко реализовать, поэтому я пока не сделал такую возможность)..

### mushroom blockstates

Удалите файлы:&#x20;

* `assets\minecraft\blockstates\brown_mushroom_block.json`&#x20;
* `assets\minecraft\blockstates\mushroom_stem.json`
* `assets\minecraft\blockstates\red_mushroom_block.json`

Включите этот параметр:

{% code title="config.yml" %}
```yaml
  disable-REAL: true
```
{% endcode %}

### fire.json

Удалите файл `assets\minecraft\blockstates\fire.json`

Включите этот параметр:

{% code title="config.yml" %}
```yaml
  disable-FIRE: true
```
{% endcode %}

### chorus\_plant.json

Удалите файл `assets\minecraft\blockstates\chorus_plant.json`

Включите этот параметр:

{% code title="config.yml" %}
```yaml
  disable-REAL_TRANSPARENT: true
```
{% endcode %}

### tripwire.json

Удалите файл `assets\minecraft\blockstates\tripwire.json`

Включите этот параметр:

{% code title="config.yml" %}
```yaml
  disable-REAL_WIRE: true
```
{% endcode %}
