---
description: Руководство по созданию FRAMES HUD
---

# FRAMES HUD

## Как создать свой первый HUD (тип FRAMES)

FRAMES HUD позволяет создавать HUDы, которые имеют различные текстуры для каждого из своих возможных значений.

### Создание файла конфигурации

Первым шагом будет создание файла конфигурации в папке [namespace](../../basic-concepts/namespace/). В этом примере я создам файл под названием `hud.yml`.

{% code title="hud.yml" %}
```yaml
info:
  namespace: myitems
huds:
  example_hud:
    enabled: true
    show:
      auto: true
      creative: true
    type: FRAMES
    x_position_pixels: 120
    value:
      player_stat_name: example_stat
      start: 0
      min: 0
      max: 5
    images:
      frames:
      - myitems:example_hud_0
      - myitems:example_hud_1
      - myitems:example_hud_2
      - myitems:example_hud_3
      - myitems:example_hud_4
      - myitems:example_hud_5
```
{% endcode %}

Как вы можете видеть, я создал файл конфигурации с некоторыми настройками для нового HUD.

`type: FRAMES` используется для создания HUD, который имеет различные текстуры, по одной для каждого значения, которое он может иметь.

`x_position_pixels: 120` используется для того, чтобы HUD располагался на 120 пикселей правее (начиная от центра экрана).

`value` - Атрибут используется для определения того, сколько значений может иметь HUD, в данном случае от 0 до 5, а начальное значение равно 0.

`player_stat_name` это атрибут, который прикрепляет HUD к пользовательскому атрибуту игрока, который будет содержать значение HUD между перезагрузками сервера, это пользовательский атрибут, а не ванильный атрибут, назовите его по своему усмотрению.

`images frames` это список текстур [font\_images](../../font-images/), по одной для каждого значения, которое может иметь HUD.

{% hint style="warning" %}
Важно: убедитесь, что для каждого возможного значения вашего HUD есть допустимая текстура. В данном случае значения от 0 до 5, поэтому у меня есть 6 изображений, по одному для каждого значения HUD.&#x20;
{% endhint %}

### Создание изображений

Создайте новый файл yml и добавьте в него этот код, он используется для того, чтобы ItemsAdder знал, где находятся ваши изображения HUD и как показать их на экране.

Как вы можете видеть, они имеют те же имена, которые были объявлены ранее в файле `hud.yml`.

{% code title="hud_images.yml" %}
```yaml
info:
  namespace: myitems
font_images:
  example_hud_0:
    suggest_in_command: false
    path: example_hud/0.png
    y_position: -15
  example_hud_1:
    suggest_in_command: false
    path: example_hud/1.png
    y_position: -15
  example_hud_2:
    suggest_in_command: false
    path: example_hud/2.png
    y_position: -15
  example_hud_3:
    suggest_in_command: false
    path: example_hud/3.png
    y_position: -15
  example_hud_4:
    suggest_in_command: false
    path: example_hud/4.png
    y_position: -15
  example_hud_5:
    suggest_in_command: false
    path: example_hud/5.png
    y_position: -15
```
{% endcode %}

Теперь нужно создать по одному файлу изображения для каждого из тех, которые мы указали в предыдущем файле.

Создайте их по этому пути (как установлено в конфигурации) `ItemsAdder\data\resource_pack\assets\myitems\textures\example_hud\`

![](<../../../../.gitbook/assets/image (50) (1) (1) (1) (1).png>)

Готово!

### Посмотрите на HUD в действии

Чтобы увидеть HUD в действии, достаточно запустить `/iazip` (и при необходимости следовать [документации по хостингу](../../../resourcepack-hosting/)), чтобы начать видеть новый HUD в игре.

![](<../../../../.gitbook/assets/image (47) (1) (1).png>)

Теперь попробуйте написать эту команду (измените `LoneDev` на имя вашего игрока), чтобы изменить значение HUD: `/iaplayerstat write LoneDev example_stat float 2`.

![](<../../../../.gitbook/assets/image (40) (1).png>)

Как вы можете видеть, значение HUD изменилось на 2! Очень хорошо!

### Сделать так, чтобы значение HUD автоматически изменялось в течение времени

Чтобы HUD автоматически увеличивался в течение времени, можно просто использовать [триггеры](../trigger-value-change.md).

### Измените значение HUD

Чтобы заставить значение HUD измениться, вы можете просто использовать предыдущую команду `write` в любом месте, в событиях элементов, в других плагинах, везде.

## Чтение HUD с заполнителями PAPI

{% content-ref url="../../../placeholderapi.md" %}
[placeholderapi.md](../../../placeholderapi.md)
{% endcontent-ref %}
