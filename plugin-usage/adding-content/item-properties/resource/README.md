---
description: Свойства, позволяющие настраивать графику предметов
---

# 🖼 Ресурс

{% hint style="danger" %}
Убедитесь, что вы не используете UPPERCASE или специальные символы в именах предметов, namespace, файлах текстур (png) и файлах моделей (json).
{% endhint %}

## Автоматическая генерация

Для того, чтобы указать ItemsAdder, какую текстуру/модель использовать для предмета, необходимо добавить атрибут `resource`.\
Вот пример:

```yaml
  resource:
    material: DIAMOND_SWORD
    generate: true
    textures:
    - item/example_item.png
```

`material` это материал ванилы, который этот предмет будет использовать в качестве основы.

`generate` сообщает IA, нужно ли ему автоматически генерировать модель предмета на основе перечисленных вами текстур

`textures` это список текстур, которые IA будет использовать для автоматической генерации модели.

### Куда поместить текстуры?

Текстуры, которые вы указали в атрибуте `textures`, должны быть помещены в нужную папку.\
Поэтому, если вы установили `textures`, как в примере, и ваше **namespace** (например, `myitems`), вам придется поместить `example_item.png` внутри этой папки: `plugins\ItemsAdder\data\resource_pack\assets\myitems\textures\item`

Если путь не существует, создайте все необходимые папки.

{% hint style="info" %}
Вы можете не устанавливать `.png` в атрибуте `textures`, IA распознает файл автоматически
{% endhint %}

## Используйте свою собственную пользовательскую 3D-модель (файл .json)

Если у вас есть пользовательская модель меча или предмета, вы можете указать IA не генерировать модель автоматически.\
Вот пример:

```yaml
  resource:
    material: DIAMOND_SWORD
    generate: false
    model_path: item/floating_sword

```

### Где я могу разместить свою модель?

Модель, которую вы задали в атрибуте `model_path`, должна быть помещена в правильную папку.\
Поэтому, если вы установите `model_path`, как в примере, и ваше **namespace** (например, `myitems`), вам придется поместить файл `floating_sword.json` в эту папку: `plugins\ItemsAdder\data\resource_pack\assets\myitems\models\item`

Если путь не существует, создайте все необходимые папки.

{% hint style="warning" %}
### Мои текстуры не работают!

Если текстуры вашей пользовательской модели не отображаются, вам нужно открыть файл модели и исправить путь к текстурам.\
Например, если у вас было следующее:

```yaml
  {
  "textures": {
    "4": "item/alchemy_candles/white_candle",
    "6": "item/alchemy_candles/candle_top",
    "7": "item/alchemy_candles/red_candle",
    "8": "item/alchemy_candles/fire"
  },
```

Вы должны изменить его на следующее ( `your_namespace` - это ваше [namespace ](../../basic-concepts/namespace/)folder):

```yaml
{
  "textures": {
    "4": "your_namespace:item/alchemy_candles/white_candle",
    "6": "your_namespace:item/alchemy_candles/candle_top",
    "7": "your_namespace:item/alchemy_candles/red_candle",
    "8": "your_namespace:item/alchemy_candles/fire"
  },
```
{% endhint %}

## Прозрачные текстуры (стекло и подобные)

{% content-ref url="../../../../faq/create-slabs-stairs-tridents-armors-etc/transparent-textured-furnitures.md" %}
[transparent-textured-furnitures.md](../../../../faq/create-slabs-stairs-tridents-armors-etc/transparent-textured-furnitures.md)
{% endcontent-ref %}

## Ручное определение custom\_model\_data

Если вы хотите принудительно использовать определенную custom\_model\_data (CustomModelData), вы можете это сделать:

```yaml
    resource:
      material: CLOCK
      model_id: 4000
      generate: false
      model_path: "item/multimeter"
```

Вы также должны создать файл модели с именем "multimeter" (в данном примере) внутри этой папки: `assets\YOUR_NAMESPACE\models\item`

Вы также можете указать IA автоматически генерировать модель на основе текстуры:

```yaml
info:
  namespace: slimefun
items:
  carbonado:
    resource:
      material: PLAYER_HEAD
      generate: true
      model_id: 4000
      textures:
      - slimefun/carbonado.png
```

{% hint style="warning" %}
### ВАЖНО

Если вы ранее создали этот предмет и уже использовали команду `/iazip`, а теперь изменили **model\_id**:\
то **очень важно** выполнить команду `/iacleancache items` для **удаления неиспользуемых ID** и **обновления** **измененного ID**.
{% endhint %}

