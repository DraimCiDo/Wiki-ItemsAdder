---
description: Слияние других ресурспаков (также ресурспаков пользовательских плагинов)
---

# 🗃 Слияние ресурс-паков

## Зачем объединяться?

**Minecraft** поддерживает **только 1 серверный ресурспак**, поэтому если у вас несколько ресурспаков, вам нужно объединить их.

## Как объединить?

### Шаг 1

Скопируйте папку `assets` вашего ресурспака.

### Шаг 2

Вставьте папку `assets` вашего ресурспака в папку **ItemsAdder**: `plugins\ItemsAdder\data\resource_pack\`

### Шаг 3

Откройте `config.yml` файла **ItemsAdder** и установите этот параметр:

```yaml
overwrite-vanilla-models: false
```

### Шаг 4

Используйте команду `/iazip` для сжатия ресурспака ItemsAdder.\
(Обязательно следуйте [докуматация по хостингу](../resourcepack-hosting/) на основе метода хостинга, который вы выбрали)

### Выполнено.

## Примеры

{% content-ref url="../../compatibility-with-other-plugins/compatible/modelengine.md" %}
[modelengine.md](../../compatibility-with-other-plugins/compatible/modelengine.md)
{% endcontent-ref %}

{% content-ref url="../../compatibility-with-other-plugins/compatible/nova.md" %}
[nova.md](../../compatibility-with-other-plugins/compatible/nova.md)
{% endcontent-ref %}

{% content-ref url="../../compatibility-with-other-plugins/compatible/space.md" %}
[space.md](../../compatibility-with-other-plugins/compatible/space.md)
{% endcontent-ref %}
