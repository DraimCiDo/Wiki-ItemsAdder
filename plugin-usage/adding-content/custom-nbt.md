# Пользовательские NBT

## Добавление пользовательских атрибутов NBT к предмету

Вы можете указать пользовательские атрибуты **NBT**, которые будут объединены в пользовательский предмет

## Пример

Например, я хочу объединить эти теги в мой предмет

&#x20;`{my-custom-nbt-tag:"привет, это пользовательский тег", another-tag:"useless"}`

```yaml
items:
  custom_nbt_item:
    display_name: "Просто пример"
    permission: examples.custom_nbt_item
    nbt: '{my-custom-nbt-tag:"привет, это пользовательский тег", another-tag:"useless"}'
    resource:
      material: DIAMOND_SWORD
      generate: true
      model_path: "minecraft:item/diamond"
    durability:
      max_custom_durability: 1324
```

{% hint style="danger" %}
## Предупреждение

Убедитесь, что вы предоставили действительный **NBT** (**json**), иначе он не будет работать.

### Эта функция требует **ItemsAdder 2.4.18+** 
{% endhint %}
