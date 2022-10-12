# Использование MythicMobs

## Как заставить MythicMobs обрабатывать моих пользовательских мобов

Если вы хотите заставить **MythicMobs** работать с вашим пользовательским мобом, чтобы иметь более продвинутые возможности и контроль, это очень просто!

Например, у меня есть такая конфигурация MythicMobs:

```yaml
StaticallyChargedSheep:
  Type: SHEEP
  Display: '&aStatically Charged Sheep'
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

\
Откройте файл **ItemsAdder** `.yml`, в котором вы создали моба, и отредактируйте правило **replace rule** следующим образом:

```yaml
        replace_mobs_spawn:
          mob1:
            replace_mythicmob:
              name: StaticallyChargedSheep
              always: true
            type: SHEEP
```

{% hint style="warning" %}
Важно установить свойство **replace\_mythicmob** `name` на ваше **имя mythicmob**.
{% endhint %}

### Случайный шанс

Если вы хотите создать пользовательскую логику спавна для вашего моба, вы не должны использовать правила **ItemsAdder**, используйте конфигурацию **Mythicmobs**: [https://www.mythicmobs.net/manual/doku.php/tutorials/randomspawns](https://www.mythicmobs.net/manual/doku.php/tutorials/randomspawns)

{% hint style="warning" %}
### Предупреждение:

**ItemsAdder** яйца и команда /iasummon **не работает** для пользовательских мобов Mythicmobs, вы должны породить их с помощью **команды Mythicmobs**, если вы хотите породить их вручную.\
`/mythicmobs mobs spawn StaticallyChargedSheep`
{% endhint %}

## Полный пример

### ItemsAdder конфигурация mobs.yml

```yaml
  glow_squid:
    display_name: "Glow Squid"
    permission: iamobs
    click_in_ia_gui: false
    lore:
      - lore-1-glow_squid
      - lore-life-glow_squid
      - lore-2-glow_squid
      - lore-3-glow_squid
      - lore-4-glow_squid
      - lore-5-glow_squid
    resource:
      generate: false
      model_path: "mob/glow_squid/glow_squid"
    behaviours:
      mob:
        ai: SQUID
        hit_color: ff7e7e
        max_health: 20
        animation:
          walk: glow_squid_walking
        replace_mobs_spawn:
          mob1:
            replace_mythicmob:
              name: StaticallyChargedSheep
              always: true
            type: SHEEP
```

### Конфигурация Mythicmobs Mobs\example.yml

```yaml
StaticallyChargedSheep:
  Type: SHEEP
  Display: '&aStatically Charged Sheep'
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

### Конфигурация Mythicmobs RandomSpawns\example.yml

```yaml
RandomStaticallyChargedSheep:
  MobType: StaticallyChargedSheep
  Worlds: world
  Chance: 0.25
  Priority: 1
  Action: REPLACE
```
