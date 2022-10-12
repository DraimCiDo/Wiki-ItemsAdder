# 🍳 Рецепты

Чтобы создать рецепт для ваших элементов в вашем [namespace ](../basic-concepts/namespace/), вы должны создать специальный раздел в одном из ваших .yml файлов (или в каждом, вы решаете, как вы хотите организовать плагин).

## Пример рецепта 3х3

![](<../../../.gitbook/assets/immagine (42).png>)

```yaml
info:
  namespace: myitems
recipes:
  crafting_table:
    deadmau5_hat:
      permission: myitems.deadmau5_hat
      enabled: true
      pattern:
      - BXB
      - XBX
      - XXX
      ingredients:
        B: LIGHT_BLUE_WOOL
      result:
        item: myitems:deadmau5_hat
        amount: 1
```

Как вы видите, я создал секцию рецептов в .yml файле, эта секция может содержать каждый тип рецепта.\
В этом примере я создал рецепт `crafting_table` под названием `deadmau5_hat`.

## Пример рецепта 2х2

![](<../../../.gitbook/assets/immagine (41).png>)

![](<../../../.gitbook/assets/immagine (43).png>)

```yaml
taco:
  permission: itemsadder.taco
  enabled: true
  pattern:
  - XXX
  - XSC
  - XPB
  ingredients:
    B: itemsadder:baguette
    C: itemsadder:sliced_roast_beef
    P: itemsadder:potato_sticks
    S: itemsadder:lettuce
```

{% hint style="warning" %}
Вы должны установить первую строку на XXX, а каждый ингредиент внизу справа.
{% endhint %}

{% hint style="success" %}
Вы можете создать **много шаблонов** для одного рецепта, просто убедитесь, что атрибут **начинается** с текста '**pattern**'. Например, pattern\_2.

```yaml
turquoise_sword:
  permission: itemsadder.turquoise_sword
  enabled: true
  pattern:
  - XRX
  - XRX
  - XSX
  pattern_2:
  - XXX
  - XRX
  - XSX
  ingredients:
    R: itemsadder:turquoise
    S: STICK
  result:
    item: itemsadder:turquoise_sword
    amount: 1
```
{% endhint %}
