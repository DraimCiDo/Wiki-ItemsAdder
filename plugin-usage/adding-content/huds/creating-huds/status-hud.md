---
description: Tutorial on how to create a STATUS HUD
---

# STATUS HUD

## Как создать свой первый HUD (тип STATUS)

STATUS HUD позволяет создавать HUD, которые имеют одну текстуру для представления их заполненного состояния, пустого состояния и полузаполненного состояния.

Например, ванильный Minecraft **hunger bar** использует тот же метод.

В ItemsAdder есть пример использования этого типа HUD, **thirst bar**.

### Пожалуйста, прочитайте [предыдущию документацию](frames-hud.md), прежде чем приступить к этому.

## Создание необходимой конфигурации

Отличие от [FRAMES HUD](frames-hud.md) заключается в том, что вам не придется создавать по одной текстуре для каждого из возможных значений.

```yaml
info:
  namespace: myitems
huds:
  thirst_bar:
    enabled: true
    show:
      auto: true
      creative: false
      underwater: false
      riding: false
    type: STATUS
    x_position_pixels: 10
    direction: LEFT
    value:
      player_stat_name: thirst
      start: 10
      min: 0
      max: 10
    images:
      positive: myitems:thirst_bar_positive
      half: myitems:thirst_bar_half
      negative: myitems:thirst_bar_negative

```

```yaml
info:
  namespace: myitems
font_images:
  thirst_bar_positive:
    suggest_in_command: false
    path: font/hud/thirst_bar/positive.png
    y_position: -15
  thirst_bar_negative:
    suggest_in_command: false
    path: font/hud/thirst_bar/negative.png
    y_position: -15
  thirst_bar_half:
    suggest_in_command: false
    path: font/hud/thirst_bar/half.png
    y_position: -15

```

## Создание текстур

![](<../../../../.gitbook/assets/image (49) (1) (1).png>)

Как вы можете видеть, я создал 3 текстуры, одну для **половинного** состояния, одну для **отрицательного** состояния и одну для **положительного** состояния.

## Окончательный результат

![](<../../../../.gitbook/assets/image (52) (1) (1) (1) (1) (1).png>)
