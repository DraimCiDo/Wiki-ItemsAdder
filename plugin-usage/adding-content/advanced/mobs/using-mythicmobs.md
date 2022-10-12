# Использование MythicMobs

## Как заставить MythicMobs обрабатывать моих пользовательских мобов

Если вы хотите заставить MythicMobs работать с вашим пользовательским мобом, чтобы иметь более продвинутые возможности и контроль, это очень просто!

Например, у меня есть такая конфигурация MythicMobs:

```yaml
StaticallyChargedSheep:
  Type: SHEEP
  Display: '&aСтатически заряженная овца'
  Health: 100
  Damage: 2
  Options:
    MovementSpeed: 0.3
  DamageModifiers:
  - LIGHTNING 0
  - FIRE 0.5
  Skills:
  - lightning @LivingInRadius{r=10} ~onTimer:100
```

  
Откройте файл ItemsAdder .yml, в котором вы создали моба, и отредактируйте правило **replace rule** следующим образом:

```yaml
        replace_mobs_spawn:
          mob1:
            replace_mythicmob:
              name: StaticallyChargedSheep
              always: true
            type: SHEEP
```

{% hint style="warning" %}
Важно установить **replace\_mythicmob** `name` - на название вашего моба из **mythicmob**.
{% endhint %}

### Случайный шанс

Если вы хотите заменять Mystic моба только иногда \(это позволяет вам создавать больше вариантов скинов для имени mythicmob\), вам просто нужно установить `always: false` и задать свои правила спавна.  
Пример:

```yaml
    replace_mobs_spawn:
      mob1:
        replace_mythicmob:
          name: StaticallyChargedSheep
          always: false
        type: SHEEP
        reason: CUSTOM
        chance: 20
        max_sky_light: 0
        time:
          start: MIDNIGHT
```

{% hint style="warning" %}
Не забудьте установить `reason: CUSTOM`, иначе он не будет работать, так как MythicMobs устанавливает резонанс спавна на `CUSTOM`, а не на `NATURAL`.
{% endhint %}



