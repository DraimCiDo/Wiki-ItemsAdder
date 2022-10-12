---
description: /ia command menu
---

# 📃 Меню рецептов

## Настройки меню и категория "Все"

`ia_gui.yml` содержит настройки GUI команды `/ia`.\
Она также содержит категорию **"all"**, в которой отображается каждый предмет ItemsAdder.

{% hint style="info" %}
Категории пакетов ItemsAdder по умолчанию находятся тут: `plugins\ItemsAdder\data\items_packs\various_configs\ia_gui_default_categories.yml`
{% endhint %}

## Создание пользовательской категории

Если вы хотите создать свою собственную категорию, вы должны добавить ее в свой собственный файл `.yml` в вашем [namespace](adding-content/basic-concepts/namespace/).\
Вот пример:

```yaml
info:
  namespace: ваш_namespace
categories:
  armors:
    enabled: true
    icon: "itemsadder:ruby_head"
    name: 'Armors'
    permission: "ia.menu.armors"
    # ЯВЛЯЕТСЯ НЕОБЯЗАТЕЛЬНЫМ. Плагин примет значение, указанное в ia_gui.yml, если оно не задано.
    font_image:
      name: "mcguis:blank_menu"
      x_position_pixels: -16
    # ЯВЛЯЕТСЯ НЕОБЯЗАТЕЛЬНЫМ. Плагин примет значение, указанное в ia_gui.yml, если оно не задано.
    title_position_pixels: 0
    items:
      - "itemsadder:ruby_sword"
      - "itemsadder:ruby_head"
      - "itemsadder:ruby_chest"
      - "itemsadder:ruby_legs"
      - "itemsadder:ruby_boots"
      - "itemsadder:spinel_head"
      - "itemsadder:spinel_chest"
      - "itemsadder:spinel_legs"
```

Не забудьте дать пользователям разрешение для каждой категории, если вы хотите, чтобы они видели категории.\
Например, разрешение: **ia.menu.armors**

{% hint style="info" %}
**font\_image и title\_position\_pixels необязательны.**\
**Плагин будет использовать тот, который указан в `ia_gui.yml`, если он не установлен.**.

Этот вариант хорош, если вы хотите иметь разный фон для каждой категории.
{% endhint %}

{% hint style="success" %}
**Категории** с **одинаковыми именами** и разными namespace **будут объединены**, это **полезно**, если у вас есть две категории "Мечи". Это позволит вам открыть меню **/ia** и увидеть все мечи, организованные в одной категории, вместо того, чтобы иметь две категории мечей.
{% endhint %}
