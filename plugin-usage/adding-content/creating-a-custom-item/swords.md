# Мечи

{% hint style="danger" %}
Если вы не создали свой namespace, пожалуйста, следуйте инструкции [руководству по namespace](../creating-your-namespace.md).
{% endhint %}

## Мой первый меч

Вот пример меча \(не забудьте изменить namespace myitems на то, которое вы хотите\)

```yaml
info:
  namespace: myitems
items:
  mysword:
    display_name: Мой меч
    permission: mysword
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - item/example_item.png
    durability:
      max_custom_durability: 1324
  
```

### Установка текстуры

{% page-ref page="../item-properties/resource/" %}



