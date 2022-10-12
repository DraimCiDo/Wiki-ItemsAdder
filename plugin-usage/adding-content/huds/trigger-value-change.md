---
description: >-
  Как использовать триггеры для автоматического увеличения/уменьшения значения HUD во время
  игрового процесса.
---

# Изменение значения триггера

## Сделать значение HUD динамичным

С помощью ItemsAdder вы можете легко заставить значение HUD автоматически изменяться во время игры, например, вы можете заставить значение HUD постепенно уменьшаться.

В этом примере я объясню, как работает HUD **жажда**.

## Как работает HUD жажды?

HUD жажды автоматически уменьшается в зависимости от некоторых факторов: биома, нахождения внутри дома или снаружи, а также в целом во время игрового процесса без каких-либо конкретных факторов.

{% hint style="info" %}
Я знаю, что этой системе HUD не хватает некоторых функций, и она может быть немного запутанной, в будущем я переделаю ее, чтобы добавить больше функций и сделать ее лучше.

Если вы хотите иметь больше контроля над HUD, вам следует использовать [Java API](../../../developers/java-api/).
{% endhint %}

Это файл конфигурации HUD:

```yaml
info:
  namespace: realcraft
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
      triggers:
        decrement:
          generic_over_time_60_minutes_inside:
            min_sky_light: 0
            max_sky_light: 13
            every_ticks: 30000
            amount: 0.5
          generic_over_time_45_minutes_outside:
            min_sky_light: 14
            max_sky_light: 15
            every_ticks: 30000
            amount: 0.5
          biome_over_time_desert_30_minutes_outside:
            min_sky_light: 14
            max_sky_light: 15
            biome: DESERT
            every_ticks: 30000
            amount: 0.5
          food_level_change:
            amount: 0.1
        increment:
          food_level_change:
            amount: 0.1
          player_respawn:
            amount: 10
        on_min_value:
          damage_player:
            every_ticks: 100
            damage: 0.5
          potion_effect:
            every_ticks: 100
            type: SLOW
            amplifier: 1
            duration: 100
    images:
      positive: realcraft:thirst_bar_positive
      half: realcraft:thirst_bar_half
      negative: realcraft:thirst_bar_negative

```

## Триггеры

В ItemsAdder вы можете использовать триггеры, чтобы решить, как изменить значение HUD, и есть два триггера: `decrement`, `increment` и `on_min_value`.

Триггер `decrement` уменьшает значение HUD, а триггер `increment` увеличивает его.

`on_min_value` - это специальный триггер, который заставляет свои правила выполняться, когда значение HUD достигло своего минимального значения.

Каждый триггер имеет список возможных правил, который сообщает ItemsAdder, может ли он изменить значение HUD или нет.

## Правила

У `triggers` есть некоторые специфические правила, и они не доступны для каждого из триггеров, поэтому, пожалуйста, обратитесь к этому списку:

### Триггер `decrement`

```yaml
      triggers:
        decrement:
          generic_over_time:
            min_sky_light: 0
            max_sky_light: 13
            every_ticks: 30000
            amount: 0.5
          biome_over_time:
            min_sky_light: 14
            max_sky_light: 15
            biome: DESERT
            every_ticks: 30000
            amount: 0.5
          food_level_change:
            amount: 0.1
```

* `generic_over_time` делает уменьшение значения HUD на 0.5 каждые 30000 тиков, если свет неба находится между 0 и 13 (что означает, что игрок находится внутри структуры).
* `biome_over_time` уменьшает значение HUD на 0.5 каждые 30000 тиков, если освещенность неба находится между 14 и 15 (что означает, что игрок находится снаружи, в дикой природе), а также проверяет, является ли биом `DESERT`.
* `food_level_change` уменьшает значение HUD на 0,1, когда уровень пищи уменьшается (ваниль).

### Триггер `increment`

```yaml
  triggers:
    increment:
      generic_over_time:
        min_sky_light: 0
        max_sky_light: 13
        every_ticks: 30000
        amount: 0.5
      biome_over_time:
        min_sky_light: 14
        max_sky_light: 15
        biome: DESERT
        every_ticks: 30000
        amount: 0.5
      food_level_change:
        amount: 0.1
      player_respawn:
        amount: 10
```

* `generic_over_time` увеличивает значение HUD на 0,5 каждые 30000 тиков, если свет неба находится между 0 и 13 (что означает, что игрок находится внутри структуры).
* `biome_over_time` увеличивает значение HUD на 0.5 каждые 30000 тиков, если свет неба находится между 14 и 15 (что означает, что игрок находится снаружи, в дикой природе), а также проверяет, является ли биом `DESERT`.
* `food_level_change` делает значение HUD уменьшенным на 0.1, когда уровень еды увеличивается (ваниль, когда игрок что-то ест).
* `player_respawn` увеличивает значение HUD на 10, когда игрок возрождается после смерти, в данном случае это полезно для того, чтобы жажда игрока увеличивалась до максимального значения при возрождении.

### Триггер `on_min_value`

Это специальный триггер, который не изменяет значение HUD, но используется для того, чтобы что-то произошло, когда значение HUD достигает минимального значения.

```yaml
  triggers:
    on_min_value:
      damage_player:
        every_ticks: 100
        damage: 0.5
      potion_effect:
        every_ticks: 100
        type: SLOW
        amplifier: 1
        duration: 100
```

* `damage_player` наносит игроку урон в размере 0,5 за каждые 100 тиков.
* `potion_effect` накладывает на игрока эффект SLOW с усилителем 1 и длительностью 100, каждые 100 тиков (в данном случае это означает, что игрок получает бесконечную медлительность, пока его значение HUD не увеличится каким-либо образом).
