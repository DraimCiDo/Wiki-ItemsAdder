# Броня

## Пример пользовательской брони

Здесь вы можете увидеть пример конфигурации для создания полной брони со всеми его частями: шлемом, нагрудником, штанами и ботинками.

Это простая броня, которая создается автоматически без текстур, ItemsAdder сгенерирует ее из цвета, который вы выбрали.

![](<../../../.gitbook/assets/image (47) (1) (1) (1) (1).png>)



```yaml
items:
  ruby_head:
    display_name: Рубиновый шлем
    permission: rubyarmor
    resource:
      generate: true
    durability:
      max_custom_durability: 275
    specific_properties:
      armor:
        slot: head
        color: ff0000
    attribute_modifiers:
      head:
        armor: 9
        armorToughness: 1
  ruby_chest:
    display_name: Рубиновый нагрудник
    permission: rubyarmor
    resource:
      generate: true
    durability:
      max_custom_durability: 400
    specific_properties:
      armor:
        slot: chest
        color: ff0000
    attribute_modifiers:
      chest:
        armor: 7
        armorToughness: 1
  ruby_legs:
    display_name: Рубиновые штаны
    permission: rubyarmor
    resource:
      generate: true
    durability:
      max_custom_durability: 375
    specific_properties:
      armor:
        slot: legs
        color: ff0000
    attribute_modifiers:
      legs:
        armor: 5
        armorToughness: 1
  ruby_boots:
    display_name: Рубиновые ботинки
    permission: rubyarmor
    resource:
      generate: true
    durability:
      max_custom_durability: 325
    specific_properties:
      armor:
        slot: FEET
        color: ff0000
    attribute_modifiers:
      feet:
        armor: 3
        armorToughness: 1
```

## Пользовательская текстура - в инвентаре

Чтобы добавить пользовательскую текстуру для брони, необходимо указать текстуру или модель (как и для любого другого пользовательского предмета).

{% hint style="warning" %}
#### Обновитесь до ItemsAdder 2.4.17+
{% endhint %}

### Пользовательская текстура предмета

```yaml
items:
  custom_helmet:
    display_name: "Индивидуальный шлем"
    permission: armors.custom_helmet
    resource:
      generate: true
      textures:
       - "item/custom_helmet"
```

### Пользовательская модель предмета

```yaml
items:
  custom_helmet:
    display_name: "Индивидуальный шлем"
    permission: armors.custom_helmet
    resource:
      generate: false
      model_path: "item/custom_helmet"
```

## Пользовательская текстура - в игре

{% content-ref url="../armors/" %}
[armors](../armors/)
{% endcontent-ref %}

