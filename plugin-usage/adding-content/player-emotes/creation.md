# Создание

## Установка расширения Blockbench

{% hint style="warning" %}
### Прежде чем продолжить:

* Убедитесь, что вы используете **Blockbench 4.2.5** или **более позднюю версию**.
* Убедитесь, что вы используете последнюю версию ItemsAdder и последнее расширение ItemsAdder Blockbench
{% endhint %}

[Скачать Blockbench](https://www.blockbench.net/) (не используйте веб-приложение).

![](<../../../.gitbook/assets/image (98) (1).png>)

\
[Скачать zip](https://github.com/LoneDev6/itemsadder-entity/releases) `iaentitymodel.zip`

![](<../../../.gitbook/assets/image (61).png>)

Распакуйте его куда-нибудь, затем откройте **Blockbench** и нажмите на File -> Plugins.

![](<../../../.gitbook/assets/image (48) (1) (1).png>)

Нажмите на значок загрузки плагинов из файла, затем выберите файл `iaentitymodel.js`.

![](<../../../.gitbook/assets/image (74) (1) (1).png>)

Нажмите OK

![](<../../../.gitbook/assets/image (71).png>)

## Включение эмоций

Откройте `config.yml` ItemsAdder и включите эти две опции, затем выполните команду `/iazip`.

{% code title="config.yml" %}
```yaml
entities:
  custom-entitites:
    enabled: true
    emotes: true
```
{% endcode %}

## Открытие редактора анимации

Откройте файл `player.iaentitymodel` с помощью Blockbench, вы можете найти этот файл после первого запуска `/iazip`.

`ItemsAdder\data\resource_pack\assets\minecraft\animations\player.iaentitymodel`

Вы можете заметить множество примеров анимации слева.

![](<../../../.gitbook/assets/image (51) (3).png>)

### Создание собственного файла анимации

Вы можете создать столько файлов анимации, сколько захотите (**ItemsAdder 3.2.1+**).

![](<../../../.gitbook/assets/image (62).png>)

![](<../../../.gitbook/assets/image (82).png>)

Удалите все эмоти и отредактируйте/переименуйте те, которые вам нужны. Они полезны только в качестве основы для ваших личных эмодзи.

![](<../../../.gitbook/assets/image (68).png>)

Теперь создайте эмота и сохраните файл проекта `.iaentitymodel` в этой папке:\
`ItemsAdder\data\resource_pack\assets\minecraft\animations\`

![](<../../../.gitbook/assets/image (95).png>)

Затем продолжите следовать руководству, чтобы узнать, как экспортировать эмоти в ItemsAdder.

### Примените изменения к ItemsAdder

Перейдите на вкладку **ItemsAdder** и нажмите **Export**.

![](<../../../.gitbook/assets/image (100).png>)

Вы должны получить сообщение об успехе.

![](<../../../.gitbook/assets/image (81) (1).png>)

{% hint style="success" %}
Используйте команду `/iareload` для загрузки новой анимации.\
<mark style="color:green;">Нет необходимости</mark> использовать `/iazip`!
{% endhint %}

## Воспроизведение анимации

Используйте команду emote: `/iaemote <emote> [player]` или `/emote <emote> [player]`.

## Разрешение на использование эмоций

Использование команды `/iaemote`: `ia.user.iaemote`.

Использование эмоции: `ia.user.iaemote.use.<emote>`\
``Пример" `ia.user.iaemote.use.yes`
