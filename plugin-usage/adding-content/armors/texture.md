---
description: Пользовательская текстура брони на теле
---

# Текстура

{% hint style="danger" %}
Функция `vanilla_1_17` требует ItemsAdder 2.4.22+ и Minecraft 1.17.\
Она не может работать в Minecraft 1.16 и предыдущих версиях.\
Чтобы клиенты 1.16 видели пользовательскую броню, вы можете включить атрибут `optifine`, это позволит старым клиентам видеть доспехи в любом случае.
{% endhint %}

{% hint style="warning" %}
Если вы видите **забагованные** текстуры и у вас установлен **OptiFine**, пожалуйста, [прочитайте здесь](../../../faq/armors-bugs/textures-broken-by-shaders-mod.md).
{% endhint %}

## Создание рендеринга брони

{% hint style="info" %}
Рендерер брони - это параметр, который содержит информацию о том, как отображать броню в игре на теле игрока.

Примечание: для каждого цвета может быть только один рендерер брони.
{% endhint %}

```yaml
info:
  namespace: myitems
armors_rendering:
  my_armor:
    color: "#d60000"
    layer_1: armor/my_armor/layer_1
    layer_2: armor/my_armor/layer_2
    use_color: false
```

Это конфигурация, которая определяет, как игра будет показывать броню.

{% hint style="warning" %}
Вы должны выбрать цвет! Даже если броня не будет цветной. Цвет - это как ID (идентификатор) для пользовательского рендера брони.
{% endhint %}

`use_color` отключает перекрашивание брони с использованием указанного `color: "#d60000"`. В некоторых случаях вы можете захотеть перекрасить броню, используя указанный `color`, поэтому вам придется установить значение `true`. Эта опция также заставит предмет (в инвентаре) больше не окрашиваться автоматически.

`color` это атрибут цвета этой брони. Он действует как уникальный идентификатор брони (и окрашивает броню, если `use_color` - `true`). Используйте этот сайт, чтобы получить действительный цвет: [https://minecraftcommand.science/armor-color](https://minecraftcommand.science/armor-color)

Теперь я создаю два файла PNG внутри папки `data/resource_pack/assets/myitems/textures/armor/my_armor/`.

![](<../../../.gitbook/assets/image (45) (1) (1) (1) (1).png>)

{% hint style="info" %}
### HD текстуры брони

Вы также можете создавать доспехи с высоким разрешением HD!&#x20;

Только убедитесь, что они имеют те же пропорции, что и оригинал.&#x20;

Например 64x32, 128x64, 256x128, 512x256..... <mark style="color:red;">это очень важно! Размер должен быть равен 2.</mark>
{% endhint %}

### Создание элемента доспехов

Для примера создадим нагрудник (остальные детали вы будете создавать самостоятельно, следуя тому же методу).

```yaml
  my_armor_chestplate:
    display_name: "Мой нагрудник"
    permission: my_armor_chestplate
    resource:
      generate: true
      textures:
      - item/my_armor/chestplate
    durability:
      max_custom_durability: 602
    specific_properties:
      armor:
        slot: chest
        custom_armor: my_armor
    attribute_modifiers:
      chest:
        armor: 8
        armorToughness: 3
```

Свойство `custom_armor` очень важно, оно заставляет плагин использовать предыдущую настройку текстур (`armors_renderer`) для этой части брони.

В данном случае я не стал указывать `color` в поле `specific_properties` части брони, потому что он уже указан в свойстве `custom_armor`.

Теперь я создаю текстуру предмета и помещаю ее в папку `data\resource_pack\assets\myitems\textures\item\my_armor\` (в этом примере я также создал новую папку `my_armor` для лучшей организации ресурспака).

![](<../../../.gitbook/assets/image (40) (1) (1).png>)

![](<../../../.gitbook/assets/image (42) (1) (1).png>)

### Анимированные текстуры

Вы также можете создавать анимированую броню!

![](<../../../.gitbook/assets/ezgif-7-3b3a255fe802 (1).gif>)

Чтобы создать анимированную броню, необходимо создать изображение со всеми кадрами анимации.

Каждый кадр должен быть ниже предыдущего. В качестве примера можно привести анимацию из 3 кадров:

![layer\_1](../../../.gitbook/assets/layer\_1.png)

![layer\_2](../../../.gitbook/assets/layer\_2.png)

Теперь давайте отредактируем свойства рендеринга для поддержки анимации.

```yaml
info:
  namespace: myitems
armors_rendering:
  my_armor:
    color: "#d60000"
    layer_1: armor/my_armor/layer_1
    layer_2: armor/my_armor/layer_2
    use_color: false
    animation:
      interpolation: true
```

В данном случае я установил `interpolation: true`, потому что хочу, чтобы анимация была плавной.

Скорость по умолчанию равна 24, но вы можете настроить ее, пока не найдете подходящее значение скорости:

```yaml
    animation:
      speed: 30
      interpolation: true
```

### Излучающие текстуры (светящиеся в темноте)

Можно также создавать излучающие текстуры, которые светятся в темноте. (Можно одновременно создавать анимированные и излучающие текстуры!)

```yaml
info:
  namespace: myitems
armors_rendering:
  my_armor:
    color: "#d60000"
    layer_1: armor/my_armor/layer_1
    layer_2: armor/my_armor/layer_2
    emissive_1: armor/my_armor/emissive_1
    emissive_2: armor/my_armor/emissive_2
    use_color: false
```

В данном случае я хочу сделать предыдущую анимацию излучающей, чтобы она светилась в темноте.\
Вам нужно сделать 2 текстуры, чтобы заставить текстуры светиться. \
Прозрачная часть **не будет светиться**, а цветная часть будет светиться.

Вам нужно просто скопировать и вставить свою текстуру и стереть те части, которые не хотят светиться.
