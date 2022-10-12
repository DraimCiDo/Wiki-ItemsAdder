# 🔖 Ранги текстур (теги)

## Придайте своему серверу профессиональный вид с помощью пользовательских рангов

![](<../../.gitbook/assets/image (27) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png>)

{% hint style="warning" %}
#### Вам необходимо использовать [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/) и [TAB](https://www.mc-market.org/resources/14009/) чтобы следовать этому руководству, метод может отличаться, если вы используете другие разрешения и плагины на таб.

#### Если вы используете другой префиксный плагин, вам может понадобиться использовать [данный метод](font-images/using-font\_images-emojis-everywhere.md) чтобы показывать ранги
{% endhint %}

## Как создать свои ранги?

### Скачать пример рангов

* Обновитесь до **ItemsAdder 2.1.30** или до последней версии
* Загрузите [примеры рангов здесь ](https://www.spigotmc.org/resources/ranks-betterranks-with-custom-textures-itemsadder-addon.84852/)

### Создайте новую конфигурацию ранга

Откройте файл `plugins\ItemsAdder\data\items_packs\betterranks\ranks.yml`, **скопировуйте** и **вставьте** один из них.\
Затем переименуйте его в свой ранг, также определите новое **.png** имя файла, например `custom`.

```yaml
  custom:
    permission: "ranks.custom"
    show_in_gui: true
    suggest_in_command: false
    path: "font/rank/custom.png"
    scale_ratio: 9
    y_position: 8
```

{% hint style="warning" %}
Не изменяйте `scale_ratio` и `y_position`. Это приведет к тому, что звания будут выглядеть пикселированными
{% endhint %}

### Создание изображения в формате png

**Скопируйте** один из моих рангов **.png** и отредактируйте его из папки `plugins\ItemsAdder\data\resource_pack\assets\betterranks\textures\font\rank\` \
\
Вы можете редактировать его с помощью **Photoshop**, **GIMP**, **Paint.NET** или любой другой программы для редактирования, которую вы используете.\
Например, скопируйте файл `admin.png`, назовите его `custom.png` и отредактируйте его.

{% hint style="danger" %}
### Не изменяйте высоту изображения ранга! Изменяйте только ширину, иначе изображение будет выглядеть пиксельным!
{% endhint %}

### Example:

Например, чтобы сделать ранг, аналогичный моему аддону **BetterRanks**, вам нужно просто использовать [Minecraftia ](https://www.dafont.com/andrew-tyler.d2526)шрифт и вырезать несколько пикселей.

![](<../../.gitbook/assets/image (36).png>)

![](<../../.gitbook/assets/image (37).png>)

![](<../../.gitbook/assets/image (38).png>)

![](<../../.gitbook/assets/image (39).png>)

## Использование ранга в игре

### LuckPerms

#### Создание группы, администратор

Используйте эту команду `/lp creategroup admin`

#### Добавьте префикс

Используйте эту команду, чтобы получить редактор: `/lp editor`\
Теперь нажмите на ссылку и откройте веб-редактор.

Выберите роль, в данном случае `admin`.

![](<../../.gitbook/assets/image (77).png>)

Напишите `prefix.100.`, за которым следует префикс в нижнем поле ввода, в этом примере я буду использовать `:admin:`.

&#x20;`prefix.100.:admin:` (убедитесь, что вы пишете правильно).

![](<../../.gitbook/assets/image (80) (1).png>)

Нажмите <mark style="color:green;">**`+Add`**</mark>

![](<../../.gitbook/assets/image (74) (1).png>)

Как вы видите, в списке разрешений появилась новая строка - это настройка префикса.

![](<../../.gitbook/assets/image (70).png>)

Теперь сохраните изменения

![](<../../.gitbook/assets/image (44).png>)

#### Назначить группу игроку

Используйте эту команду (измените `LoneDev` на имя вашего игрока) `/lp user LoneDev group add admin`.

![](<../../.gitbook/assets/immagine (40).png>)

### Плагин TAB

{% hint style="warning" %}
Убедитесь, что вы установили [PlaceholderAPI](font-images/using-font\_images-emojis-everywhere.md)
{% endhint %}

#### Редактирование config.yml плагина TAB

**Добавьте** это в категорию `groups` или отредактируйте, если она уже существует.\
(Вы должны использовать `%img_admin%` вместо `:admin:`, потому что **TAB** распознает только **PlaceholderAPI**, но не **ItemsAdder**. Это может быть работать и для **других плагинов**)

```yaml
  Admin:
    tabprefix: '%img_admin%  '
    tagprefix: '%img_admin%  '
```

Затем используйте команду `/tab reload`

![](<../../.gitbook/assets/immagine (38).png>)

![](<../../.gitbook/assets/immagine (39).png>)
