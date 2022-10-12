# Мебель выполняет действия

## Выполнение команд при взаимодействии

```yaml
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
    events:
      placed_armorstand:
        interact:
          execute_commands:
            the_first_command:
              command: help
              as_console: false
```

В данном случае вы видите мебель, которая заставит игрока выполнить команду `/help` при взаимодействии с мебелью.&#x20;

Очевидно, вы также можете добавить больше [actions](../item-properties/events/actions.md) для [placed\_armorstand](../item-properties/events/).interaction события, а не только в `execute_commands`.

## Открыть торговое меню при взаимодействии

```yaml
  energy_extractor:
    display_name: display-name-energy_extractor
    permission: energy_extractor
    resource:
      material: PAPER
      generate: false
      model_path: item/energy_extractor
    behaviours:
      furniture:
        solid: true
      furniture_trade_machine:
        title: Energy Extractor
        trades_list:
          cobblestone:
            ingredients:
              slot1:
                item: COBBLESTONE
                amount: 64
            result:
              item: energy_orb
              amount: 6
          cobblestone_slab:
            ingredients:
              slot1:
                item: COBBLESTONE_SLAB
                amount: 64
            result:
              item: energy_orb
              amount: 3
```

В этом примере вы можете увидеть, как прикрепить торговый графический интерфейс к вашей мебели. Это полезно для создания пользовательских механизмов.
