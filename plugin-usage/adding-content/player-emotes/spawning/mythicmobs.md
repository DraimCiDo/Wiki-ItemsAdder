---
description: Пользовательские 3D-модели для мобов Mythicmobs
---

# Mythicmobs

## Рескин моба из Mythicmob

Вы можете использовать пользовательский скин игрока для любого моба Mythicmob.

{% hint style="success" %}
Для работы этого плагина не требуется Mythicmobs, но некоторым серверам может потребоваться его использование для создания пользовательских боссов и тому подобного.
{% endhint %}

### Изменение модели

Создайте новый файл конфигурации Mythicmobs mob по этому пути:   `plugins/MythicMobs/Mobs/custom_player.yml`\
``(you can decide the filename).

{% hint style="warning" %}
Не используйте `PLAYER` в качестве типа, это вызывает проблемы с поворотом головы/тела.
{% endhint %}

{% code title="custom_player.yml" %}
```yaml
custom_player:
  Type: ZOMBIE
  Display: '&aCustom Player'
  Health: 10
  Damage: 2
  Options:
    MovementSpeed: 0
    Silent: true
  Skills:
  - customentity{playerskin=https://minesk.in/5f1e7ff6409e428bb500cc9315bf7ffb} @self ~onSpawn
```
{% endcode %}

В этом примере я меняю скин моба Mythicmobs на скин **Notch**.

![](<../../../../.gitbook/assets/image (74).png>)

### Пользовательский скин

{% content-ref url="../custom-skin.md" %}
[custom-skin.md](../custom-skin.md)
{% endcontent-ref %}

### Скиллы

* `customentity{playerskin=SKIN}` Изменить скин игрока
* `customentity{idle=ANIMATION}` Чтобы изменить анимацию бездействия
* `customentity{walk=ANIMATION}` Чтобы изменить анимацию ходьбы
* `customentity{attack=ANIMATION}` Чтобы изменить анимацию атаки
* `customentity{death=ANIMATION}` Чтобы изменить анимацию смерти
* `customentity{play=ANIMATION}` Для воспроизведения анимации прямо сейчас
* `customentity{stop=ANIMATION}` Чтобы остановить текущую анимацию

### Готово

![](<../../../../.gitbook/assets/ezgif.com-gif-maker (1).webp>)
