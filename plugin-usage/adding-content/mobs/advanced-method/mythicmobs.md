---
description: Пользовательские 3D-модели для мобов Mythicmobs
---

# Mythicmobs

## Повторное создание моба Mythicmob

Вы можете использовать пользовательскую модель в качестве скина для любого моба Mythicmob.

{% hint style="success" %}
Для работы этого плагина не требуется Mythicmobs, но некоторым серверам может потребоваться его использование для создания пользовательских боссов и тому подобного.
{% endhint %}

{% hint style="danger" %}
Для этого требуется **ItemsAdder 3.2.1-beta1** или выше
{% endhint %}

## Изменение модели

Создайте новый файл конфигурации мобов **Mythicmobs** по этому пути:   `plugins/MythicMobs/Mobs/ninja_skeleton.yml`\
``(имя файла вы можете выбрать сами).

{% hint style="warning" %}
Не используйте `PLAYER` в качестве типа, это вызывает проблемы с поворотом головы/тела.
{% endhint %}

{% code title="ninja_skeleton.yml" %}
```yaml
ninja_skeleton:
  Type: ZOMBIE
  Display: '&aСкелет ниндзя'
  Health: 10
  Damage: 2
  Options:
    MovementSpeed: 0
    Silent: true
  Skills:
  - customentity{model=custom:ninja_skeleton} @self ~onSpawn
  - customentity{play=attack} @self ~onAttack
  - customentity{walk=b_walk} @self ~onAttack
```
{% endcode %}

В этом примере я меняю скин моба **Mythicmobs** на скин `ninja_skeleton`.

```yaml
customentity{model=MODEL NAME} @self ~onSpawn
```

## Анимация

Как вы можете видеть, я также добавил несколько скиллов для динамической замены анимации мобов.\
`{play=attack}` используется для воспроизведения анимации атаки, в данном случае, когда сущность атакует.

\
`{walk=b_walk}` используется для замены анимации ходьбы моба `b_walk`, которая является анимацией "сердитой" ходьбы, поскольку моб только что атаковал другое существо и имеет цель.

### Анимация

* `customentity{idle=ANIMATION}` Чтобы изменить анимацию бездействия
* `customentity{walk=ANIMATION}` Чтобы изменить анимацию ходьбы
* `customentity{attack=ANIMATION}` Чтобы изменить анимацию атаки
* `customentity{death=ANIMATION}` Чтобы изменить анимацию смерти
* `customentity{play=ANIMATION}` Для воспроизведения анимации прямо сейчас
* `customentity{stop=ANIMATION}` Чтобы остановить текущую анимацию

## Кости

### Видимость

Скрыть/показать кость программно

```
- bone{name=BONE;visible=TRUE/FALSE} TARGETER ~EVENT
```

Пример: скрытие кости на ноге при определенном событии

```
- bone{name=leftLeg;visible=false} @self ~onDamaged
```

### Цвет

Изменение цвета кости программным способом

```
- bone{name=BONE;color=COLOR} TARGETER ~EVENT
```

Цвет по умолчанию (белый): `16777215`\
``[Color picker](https://minecraftcommand.science/armor-color)

Пример: изменение цвета кости при повреждении пользовательской сущности

```
- bone{name=leftLeg;color=16711790} @self ~onDamaged
```

### Enchant glint

Программное отображение эффекта зачарования на кости

```
- bone{name=BONE;enchant=TRUE/FALSE} TARGETER ~EVENT
```

Пример: показать эффект зачарования кости при повреждении пользовательского объекта

```
- bone{name=leftLeg;enchant=true} @self ~onDamaged
```

### Применяет предыдущие свойства к каждой кости

```
- bone{all=true;PROPERTY=VALUE} TARGETER ~EVENT
```

Пример: скрыть каждую кость, когда пользовательская сущность повреждена

```
- bone{all=true;visible=false} @self ~onDamaged
```

## Крепление кости

```
- mountentity{bone=BONE;locked=TRUE/FALSE;control=TRUE/FALSE} TARGETER ~EVENT
```

Пример: установка пользовательской сущности по правому клику, отключение SHIFT для демонтажа (не работает на клиентах < 1.16) и отключение управления сущностью с помощью WASD.

```
- mountentity{bone=mountbone;locked=true;control=false} @trigger ~onInteract
```

{% hint style="warning" %}
Внимание: если вы хотите вручную обрабатывать подобные ездовые механики, вы должны установить это свойство в конфигурации **ItemAdder** вашей пользовательской сущности:

`mount_on_interact: false`

```yaml
info:
  namespace: custom
entities:
  testmm:
    display_name: "testmm"
    type: ZOMBIE
    model_folder: entity/testmm
    speed:
      movement: 0.25
      flying: 0.25
    mount_on_interact: false
```
{% endhint %}

### Dismounting

Удаление пассажиров с некоторых костей

```
- dismountentity{bones=BONE1,BONE2,BONE3} TARGETER ~EVENT
```

Удаление пассажиров

```
- dismountentity{bones=BONE1} TARGETER ~EVENT
```

Удаление пассажиров из всех костей

```
- dismountentity{all=true} TARGETER ~EVENT
```

Примеры:

```
- dismountentity{bones=mount1,mount2} @self ~onDamaged
- dismountentity{all=true} @self ~onDamaged
```

### Bone Targeter

Bone targeter возвращает местоположение указанной кости.

```
@bone{bone=BONE}
```

Пример: воспроизведение частицы каждые 3 тика на центре кости.

```
- effect:particles{vd=50;p=end_rod;amount=10;speed=0;hS=0.2;vS=0.2;repeat=270;repeatInterval=1} @bone{bone=rightArm} ~onTimer:3
```

{% embed url="https://youtu.be/LYCWCtmCzLc" %}

### Окончательный результат

![](../../../../.gitbook/assets/ezgif.com-gif-maker\(1\).webp)
