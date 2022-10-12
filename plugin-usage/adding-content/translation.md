# 🇬🇧 🇬🇧 Перевод

Вы можете перевести все в ItemsAdder, это очень просто.

## Перевести предметы

### Перевод предметов ItemsAdder

Если вы хотите перевести предметы IA по умолчанию, вы можете это сделать, вам просто нужно скопировать мой словарь и создать свой собственный.\


* откройте папку plugins\ItemsAdder\data\items\_packs\dictionaries\ia\_default\_items
* скопируйте и вставьте файл en.yml
* измените `dictionary-lang` с `en` на идентификатор вашего языка (например, `ru`)
* переводите все, что хотите
* откройте config.yml и установите `dictionaries-lang` на идентификатор вашего языка (пример `ru`)
* перезагрузите плагин или перезапустите сервер

### Создайте свой собственный перевод для новых предметов

Чтобы создать собственные переводы для своих предметов (скорее всего, вам это не понадобится, но если вы хотите в будущем делиться своими предметами в Интернете, лучше сделать их переводимыми), вам просто нужно создать новый файл в любом месте (я бы поместил его в папку `dictionaries` для более простой организации, но вы можете поместить его в любое место в `items_packs`).

Вот как это выглядит:

```yaml
info:
  namespace: special_items_lang
  dictionary-lang: "fr"
dictionary:
  display-name-my_sword: épée de saleté
  display-name-my_item: j'aime la baguette
```

А вот так выглядит мой файл с элементами:

```yaml
info:
  namespace: special_items
items:
  my_sword:
    display_name: display-name-my_sword
    permission: my_sword
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - item/my_sword.png
    durability:
      max_custom_durability: 1324
```

{% hint style="info" %}
Как вы видите, я установил `display_name` в "display-name-my\_sword", это позволит IA заменить текст на текст из словаря, поэтому меч будет называться "épée de saleté".
{% endhint %}

{% hint style="warning" %}
Вы можете **пропустить** часть **перевода** и сделать это напрямую, **но** это не позволит вам легко **перевести** элементы в **будущем**, если вам это понадобится.

```yaml
info:
  namespace: special_items
items:
  my_sword:
    display_name: "épée de saleté"
    permission: my_sword
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - item/my_sword.png
    durability:
      max_custom_durability: 1324
```
{% endhint %}

## Перевод команд и сообщений

Вам просто нужно открыть папку lang и скопировать и вставить en.yml, затем перевести его и изменить настройку lang в config.yml на имя вашего файла.
