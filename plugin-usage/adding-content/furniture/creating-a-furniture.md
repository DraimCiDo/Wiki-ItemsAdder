---
description: Руководство по созданию вашей первой мебели
---

# Создание мебели

## Что такое мебель?

Мебель - это декоративный предмет, который может быть твердым, излучать свет, использоваться в качестве кресла и иметь другие характеристики.

## Создание простой мебели

### Создание файла конфигурации

Первым шагом будет создание файла конфигурации в папке [namespace](../basic-concepts/namespace/). В этом примере я назвал его `furniture_example.yml`.

{% code title="furniture_example.yml" %}
```yaml
info:
  namespace: myitems
items:
  lamp:
    display_name: "Лампа"
    permission: myitems.decorative.lamp
    lore:
    - lore-decorative-item
    resource:
      material: PAPER
      generate: false
      model_path: lamp
    behaviours:
      furniture:
        small: true
        light_level: 13
```
{% endcode %}

Как вы можете видеть, я создал предмет с некоторыми специальными свойствами.

Атрибут `behaviours` имеет специальный податрибут `furniture`, этот атрибут сообщает ItemsAdder, что этот предмет является размещаемой моделью мебели.

Давайте добавим к нему еще несколько параметров:

{% code title="furniture_example.yml" %}
```yaml
  lamp:
    display_name: "Лампа"
    permission: myitems.decorative.lamp
    lore:
    - lore-decorative-item
    resource:
      material: PAPER
      generate: false
      model_path: lamp
    behaviours:
      furniture:
        light_level: 13
        solid: true
        small: true
        placeable_on:
          floor: true
          ceiling: false
          walls: false
        hitbox:
          height: 1
        sound:
          place:
            name: block.metal.fall
          break:
            name: block.metal.break
```
{% endcode %}

Я добавил некоторые свойства, в данном случае я указал, где мебель может быть размещена (только на `floor`), размер [`hitbox`](furniture-collisions.md) и звуки `place`/`break`.

{% hint style="info" %}
По умолчанию хитбокс имеет размер 1x1x1, поэтому нет необходимости указывать эти опции.

Указывайте их только в том случае, если модель больше, чем 1x1x1.

Например, если у вас есть мебель размером 1x2x1, вы можете задать ее так:

```yaml
    hitbox:
      height: 2
      length: 1
      width: 1
```
{% endhint %}

Окончательный результат:

{% code title="furniture_example.yml" %}
```yaml
info:
  namespace: myitems
items:
  lamp:
    display_name: "Лампа"
    permission: myitems.decorative.lamp
    lore:
    - lore-decorative-item
    resource:
      material: PAPER
      generate: false
      model_path: lamp
    behaviours:
      furniture:
        light_level: 13
        solid: true
        small: true
        placeable_on:
          floor: true
          ceiling: false
          walls: false
        hitbox:
          height: 1
        sound:
          place:
            name: block.metal.fall
          break:
            name: block.metal.break
```
{% endcode %}

### Создание файла модели

Теперь откройте [BlockBench](.../item-properties/resource/creating-3d-models.md) и создайте _"Java Block/Item"_.

![](<../../../.gitbook/assets/image (49) (1) (1) (1).png>)

Теперь создайте модель, в этом примере я моделирую современную лампу.

![](<../../../.gitbook/assets/image (47) (1) (1) (1).png>)

{% hint style="warning" %}
Важно: убедитесь, что север находится напротив того места, куда вы хотите повернуть модель лицом.

Или добавьте свойство в конфигурацию YML `opposite_direction: true`.
{% endhint %}

Отредактируйте, как модель отображается на руке игрока:

![](<../../../.gitbook/assets/image (46) (1) (1).png>)

![](<../../../.gitbook/assets/image (48) (1) (1) (1).png>)

### Настройка отображения модели в игре

#### Использование стойки для брони

Вы должны выбрать **значок головы**, а затем **маленькую стойку под броню:**.

![](<../../../.gitbook/assets/image (41) (1) (1) (1).png>)

Затем нужно сдвинуть модель вниз, пока она не совпадет с основанием стойки:

![](<../../../.gitbook/assets/image (42) (1).png>)

#### Использование рамки

Вы должны выбрать иконку **Изображение** и затем установить Z-смещение на `-16`.\
Это отобразит модель немного ниже блока, к которому прикреплена рамка, но при использовании невидимой рамки она будет бесшовной. Это связано с тем, что элементы в невидимых рамок находятся немного ниже, чем обычно.

### Экспорт модели

Теперь давайте сохраним файл модели в нужную папку, в данном случае я установил это свойство в конфигурационном файле yml: `model_path: lamp`, поэтому вы должны сохранить .json файл внутри этого пути: `ItemsAdder\data\resource_pack\assets\myitems\models\lamp.json`.

Для этого нажмите "Файл", затем "Экспорт модели" и, наконец, "Экспорт модели блока/предмета". В новом окне перейдите по пути, по которому вы хотите сохранить модель, дайте ей правильное имя и подтвердите изменения.

### Сохранение изменений

Теперь запустите `/iazip` (и следуйте [документации по хостингу](../../resourcepack-hosting/), если необходимо), затем получите элемент и поместите его: `/iaget myitems:lamp`.

![](<../../../.gitbook/assets/image (50) (1) (1) (1) (1) (1).png>)

![](<../../../.gitbook/assets/image (44) (1) (1).png>)
