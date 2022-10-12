# Языки

### Доступные на данный момент языки

```
GUI: 
    Chinese zh_cn
    Czech cz
    German de
    English en
    Spanish es
    French fr
    Italian it
    Japanese jp
    Korean ko
    Dutch nl
    Polish pl
    Portuguese pt
    Russian ru
    Turkish tr
    Thai th

Items: 
    Chinese zh_cn
    Spanish es
    French fr
    Italian it
    Portuguese pt
    Russian ru
    Turkish tr
```

### Как изменить язык?

Откройте файл config.yml и измените настройки языка.

```yaml
config_files:
  lang: 'ru'
  dictionaries-lang: 'ru'
```

## Как редактировать или создавать новые языки?

Сообщения **плагина** каждого **языка** находятся в **этой папке**: `plugins\ItemsAdder\lang\`

**Предметы по умолчанию** и **языки меню** находятся в **этой папке**: `plugins\ItemsAdder\data\items_packs\dictionaries\`

{% hint style="warning" %}
Некоторые аддоны могут помещать свои файлы словарей в другие папки внутри items\_packs, вам придется искать их.
{% endhint %}
