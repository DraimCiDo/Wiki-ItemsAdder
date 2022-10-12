---
description: Как установить плагин
---

# ⚙ Первая установка

{% hint style="info" %}
**Вы должны следовать** эту первую настройку **на** вашем **тестовом сервере** на вашем ПК, чтобы **избежать ошибок** и слишком частых перезапусков... игроки не любят, когда сервер находится в автономном режиме.\
Вы можете загрузить файлы на ваш реальный сервер после того, как закончите здесь.
{% endhint %}

{% hint style="danger" %}
Вы **должны** выполнить ВСЕ шаги установки. Не только первый.
{% endhint %}

## Шаг 1 - Установка плагина и API

* Установить [**ProtocolLib**](https://www.spigotmc.org/resources/protocollib.1997/)
* Установить [**LoneLibs**](https://www.spigotmc.org/resources/lonelibs.75974/)
* (необязательно) Установить **LightAPI** ([1.14, 1.15, 1.16](http://a.devs.beer/lightapi-old) | [1.17, 1.18](http://a.devs.beer/lightapi-new))
* (необязательно) Установить [**Lib's Disguises**](https://www.spigotmc.org/resources/libs-disguises-free.81/) если вы планируете создавать пользовательских мобов в будущем.
* Поместите файл **ItemsAdder.jar** в папку plugins.
* Запустите сервер
* Дождаться пока ItemsAdder завершит загрузку **всего**

Первый шаг выполнен.\
Теперь вы должны выполнить **шаг 2** для настройки ресурспака (не волнуйтесь, это не очень сложно).

## Шаг 2 - Первая установка ресурспака

#### Определите способ размещения ресурспака:

{% content-ref url="plugin-usage/resourcepack-hosting/" %}
[resourcepack-hosting](plugin-usage/resourcepack-hosting/)
{% endcontent-ref %}

## Дополнительные шаги

### Добавление официального содержимого ItemsAdder

![](.gitbook/assets/items\_showcase\_gif.apng)

**ItemsAdder** поставляется с большим количеством пользовательского контента, уже созданного для вас.\
Он не включен автоматически в загруженный плагин, потому что некоторые люди не хотят, чтобы каждый элемент/функция автоматически добавлялась на их сервер.

#### Пакет по умолчанию

![](<.gitbook/assets/image (47).png>)

* Загрузить последнюю версию DefaultPack [здесь](https://github.com/ItemsAdder/DefaultPack/releases/latest)&#x20;
* Извлеките содержимое в папку **ItemAdder** и перезапишите файлы, если потребуется
* Выполните команду `/iazip` (и следуйте своему [методу хостинга](plugin-usage/resourcepack-hosting/) если вы не используете **self-host**).

#### Другие пакеты (по желанию)

![](<.gitbook/assets/image (50).png>)

* Если вы хотите, вы можете скачать OtherPacks [здесь](https://github.com/ItemsAdder/OtherPacks/releases/latest), который добавляет еще больше содержания
* Извлеките содержимое в папку **ItemAdder** и перезапишите файлы, если потребуется
* Выполните команду `/iazip` (и следуйте своему [методу хостинга](plugin-usage/resourcepack-hosting/) если вы не используете **self-host**).

Если вы используете версию 1.17 или ниже, вам нужно изменить генерацию руды:

* Откройте эти файлы и установите `enabled: true`.\
  `ItemsAdder\data\items_packs\iaalchemy\worlds_populators_old.yml`\
  `ItemsAdder\data\items_packs\iasurvival\ores\worlds_populators_old.yml`
* Откройте эти файлы и установите `enabled: false`.\
  `ItemsAdder\data\items_packs\iaalchemy\worlds_populators_1_18.yml`\
  `ItemsAdder\data\items_packs\iasurvival\ores\worlds_populators_1_18.yml`

### Удаление элементов по умолчанию

{% content-ref url="faq/removing-default-stuff/" %}
[removing-default-stuff](faq/removing-default-stuff/)
{% endcontent-ref %}

### Как избегать глючных блоков

{% content-ref url="faq/blocks-minerals-issues/custom-blocks-glitch-texture/avoid-glitched-blocks.md" %}
[avoid-glitched-blocks.md](faq/blocks-minerals-issues/custom-blocks-glitch-texture/avoid-glitched-blocks.md)
{% endcontent-ref %}
