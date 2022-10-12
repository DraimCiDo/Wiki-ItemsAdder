# шрифт TTF

Этот метод позволяет добавлять шрифты, используя файлы шрифтов .ttf

## Пример пользовательского шрифта

![](<../../../.gitbook/assets/immagine (1).png>)

Для этого вам необходимо:

* скачать японский шрифт [здесь](http://matteodev.it/spigot/itemsadder/res/v2/font.zip)
* извлечь содержимое в `plugins\ItemsAdder\data\resource_pack\assets\minecraft\font`
* откройте файл config.yml и установите `custom-font enabled: true`
* и, очевидно, если вы используете [dropbox host](../../resourcepack-hosting/resourcepack-on-dropbox.md), вам нужно заново загрузить pack.zip после перезапуска сервера

{% hint style="warning" %}
В Minecraft есть ошибка, которая приводит к крашу игры при использовании пользовательских шрифтов TTF.

Это происходит только на некоторых интегрированных GPU Intel и старых версиях игры, я не могу исправить эту ошибку, [подробнее читайте здесь](https://bugs.mojang.com/browse/MC-180529?jql=text%20\~%20%22ttf%20crash%22).
{% endhint %}
