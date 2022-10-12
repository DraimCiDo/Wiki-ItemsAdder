# Конфигурация мобов

## Создайте своего первого моба

Вы должны создать .yml файл в вашей папке [namespace ](../../beginners/basic-concepts/namespace.md) \(проверьте [это руководство ](../../beginners/creating-your-namespace.md)для получения дополнительной информации\).

{% hint style="info" %}
Рассмотрите возможность использования[ официального онлайн-инструмента](../../../../files-editor.md) для редактирования файлов ItemsAdder. Он облегчает вам жизнь, так как имеет автозаполнение\(нажмите CRTL+SPACE\), которое поможет вам избежать ошибок.
{% endhint %}

Это пример для пользовательских имен мобов Soul.  
Как вы видите, я настроил его как обычный элемент, но с особым [behaviours ](../item-properties/behaviours.md)с свойством **mob**.

```yaml
info:
  namespace: creaturesplus
items:
  soul:
    display_name: Soul
    permission: creaturesplus
    click_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/soul"
    behaviours:
      mob:
        ai: HUSK
        hit_color: ff7e7e
        max_health: 40
        y_offset: 0
        lock_head_rotation:
          y: 0
        animation:
          attack: soul_attack
          walk: soul_walking
        replace_mobs_spawn:
          mob1:
            type: ZOMBIE
            reason: NATURAL
            chance: 20
            max_sky_light: 0
            time:
              start: MIDNIGHT
            biomes:
             - DESERT
             - DESERT_HILLS
             - DESERT_LAKES
```

Это поведение указывает ItemsAdder заменить любого естественно порожденного `ZOMBIE` на 20% `chance`, в `полуночное время` и только в пещерах \(`max_sky_light: 0`\).  
У моба также будет заблокирован поворот головы \(только по оси Y\), это позволит ему не выглядеть глупо, когда он смотрит на игрока, находясь в более высоком положении.

`hit_color` это цвет, который будет иметь моб при получение урона от игрока.   
Вы можете получить действительный цвет на этих сайтах:  
[https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Color.html)  
[https://minecraftcommand.science/armor-color](https://minecraftcommand.science/armor-color)  
[https://misode.github.io/worldgen/biome/](https://misode.github.io/worldgen/biome/) \(используйте одну из панелей выбора цвета и скопируйте значение из правой панели\)

{% hint style="info" %}
Примечание: Я **пропустил** свойство `material` в `resource`, потому что **это не нужно** для **mobs**, ItemsAdder автоматически обработает его.
{% endhint %}

### Анимация

Вы, вероятно, заметили, что есть еще два атрибута анимации: `attack` и `walk`.  
На самом деле это другие элементы, которые вы должны создать подобным образом:

```yaml
  soul_walking:
    display_name: soul_walking
    permission: creaturesplus
    show_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/walking"
    behaviours:
      mob_animation: true
  soul_attack:
    display_name: soul_attack
    permission: creaturesplus
    show_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/attack"
    behaviours:
      mob_animation: true
```

## Финальный результат

```yaml
info:
  namespace: creaturesplus
items:
  soul:
    display_name: Soul
    permission: creaturesplus
    click_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/soul"
    behaviours:
      mob:
        ai: HUSK
        hit_color: ff7e7e
        max_health: 40
        lock_head_rotation:
          y: 0
        animation:
          attack: soul_attack
          walk: soul_walking
        replace_mobs_spawn:
          mob1:
            type: ZOMBIE
            reason: NATURAL
            chance: 20
            max_sky_light: 0
            time:
              start: MIDNIGHT
  soul_walking:
    display_name: soul_walking
    permission: creaturesplus
    show_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/walking"
    behaviours:
      mob_animation: true
  soul_attack:
    display_name: soul_attack
    permission: creaturesplus
    show_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/attack"
    behaviours:
      mob_animation: true
```

![](../../../../.gitbook/assets/image%20%2816%29.png)

## Создавайте мобов естественным образом

Для естественного спавна мобов необходимо установить свойство `replace_mobs_spawn`.

```yaml
  soul:
    display_name: Soul
    permission: creaturesplus
    click_in_ia_gui: false
    resource:
      generate: false
      model_path: "mob/soul/soul"
    behaviours:
      mob:
        ai: HUSK
        hit_color: ff7e7e
        max_health: 40
        lock_head_rotation:
          y: 0
        animation:
          attack: soul_attack
          walk: soul_walking
        replace_mobs_spawn:
          mob1:
            type: ZOMBIE
            reason: NATURAL
            chance: 20
            max_sky_light: 0
            time:
              start: MIDNIGHT
```

Вы можете создать столько правил замены, сколько захотите, например, если вы хотите заменить `ZOMBIE` и `SKELETON`, вы можете создать второе правило

```yaml
        replace_mobs_spawn:
          rule1:
            type: ZOMBIE
            reason: NATURAL
            chance: 20
            max_sky_light: 0
            time:
              start: MIDNIGHT
          rule2:
            type: SKELETON
            reason: NATURAL
            chance: 50
            max_sky_light: 0
            time:
              start: NOON
```

Вы можете решить, **заменить** моба или **заспавнить** пользовательского моба, не заменяя **оригинального**.  
Вы должны использовать свойство `spawn_another`.

```yaml
          rule3:
            type: ZOMBIE
            spawn_another: true
            reason: NATURAL
            chance: 10
            max_sky_light: 0
            time:
              start: MIDNIGHT
```

