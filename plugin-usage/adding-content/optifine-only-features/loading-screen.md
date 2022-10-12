# Загрузочный экран

## Ванильный экран загрузки

![](<../../../.gitbook/assets/immagine (44).png>)

## Пользовательский экран загрузки

![](<../../../.gitbook/assets/immagine (51).png>)

## Как это сделать?

### До выхода Minecraft 1.16

![](<../../../.gitbook/assets/immagine (49).png>)

Вы можете получить [GIMP ](https://www.gimp.org/downloads/) пример [здесь](https://github.com/LoneDev6/SpigotUtilities/blob/master/ItemsAdder/various\_files/mojang\_template.xcf).

* Отредактируйте мой файл:`plugins\ItemsAdder\data\resource_pack\assets\minecraft\textures\gui\title\mojang.png`
* Сохраните файл в том же месте

### После выхода Minecraft 1.16

![](<../../../.gitbook/assets/immagine (48).png>)

{% hint style="warning" %}
**Предупреждение**: известная проблема заключается в том, что при использовании `/iazip` или `/iatexture` для наложения текстуры в игре, логотип отображается с ошибкой.\
Логотип будет отображаться без проблем только при присоединении к серверу, по какой-то причине, возможно, это ошибка Optifine.
{% endhint %}

Немного сложно:\
в основном вам нужно разделить изображение пополам, как это сделал я, поэтому вы должны знать, как использовать программы для редактирования изображений (Photoshop, GIMP или Paint.net).\
Вы можете получить [GIMP ](https://www.gimp.org/downloads/)пример [здесь](https://github.com/LoneDev6/SpigotUtilities/blob/master/ItemsAdder/various\_files/mojangstudios\_template.xcf).

* Отредактируйте мой файл: `plugins\ItemsAdder\data\resource_pack\assets\minecraft\textures\gui\title\mojangstudios.png`
* Сохраните файл в том же месте

{% hint style="warning" %}
**ВАЖНО**\
Расположение деталей должно быть точным.\
Левая часть текстуры должна касаться правого верхнего угла холста, а правая - левого центра холста.

Это **всегда** так, независимо от размера фактической текстуры!
{% endhint %}

### Как изменить цвет фона (только 1.16+)

Создайте новый файл (или отредактируйте уже созданный): `plugins\ItemsAdder\data\resource_pack\assets\minecraft\optifine\color.properties`

Поместите это содержание:

```yaml
###############################################################################
# Экран загрузки ресурсов
###############################################################################
# Цвет фона
screen.loading=14181c
# Цвет фона панели загрузки
screen.loading.bar=14181c
# Контур полосы загрузки
screen.loading.outline=303336
# Цвет переднего плана панели загрузки
screen.loading.progress=1f17ce
# Режим наложения логотипа
# Где src, dst, srcA м dstA являются одними из: 
#   ZERO, ONE, SRC_COLOR, ONE_MINUS_SRC_COLOR, DST_COLOR, ONE_MINUS_DST_COLOR, 
#   SRC_ALPHA, ONE_MINUS_SRC_ALPHA, DST_ALPHA, ONE_MINUS_DST_ALPHA, SRC_ALPHA_SATURATE
screen.loading.blend=DST_COLOR
```

Вы можете редактировать цвета с помощью [HEX color picker](https://www.w3schools.com/colors/colors\_picker.asp)

{% hint style="warning" %}
Не включайте `#` в начало кода цвета.
{% endhint %}
