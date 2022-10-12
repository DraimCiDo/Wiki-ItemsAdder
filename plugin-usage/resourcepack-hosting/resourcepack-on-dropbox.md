---
cover: >-
  ../../.gitbook/assets/Dropbox_(service)-Blue&White-Dark-Background-Logo.wine.svg
coverY: 0
---

# 📦 Хост текстур через DropBox

## Видео-гайд

{% embed url="https://www.youtube.com/embed/GKGnlF4zZVg?start=78&end=189&rel=0&autoplay=0&showinfo=0" %}

## Учебник по работе с текстом

* Откройте [DropBox](https://dropbox.com), зарегистрируйтесь/залогиньтесь.
* Используйте команду `/iazip`\ (**это важно**, потому что `/iazip` перезагружает конфиги и обновляет файл **pack.zip**)
* Откройте папку: `plugins/ItemsAdder/data/resource_pack/`
* **Перетащите** в **DropBox** файл **pack.zip**
* Нажмите **Share**

![](<../../.gitbook/assets/immagine (20).png>)

* Нажмите **Создать**

![](<../../.gitbook/assets/immagine (21).png>)

* Нажмите **Копировать ссылку**
* Например, если ваша ссылка [https://www.dropbox.com/blablabla?dl=0](https://www.dropbox.com/blablabla?dl=0)
* Откройте `config.yml` из **ItemsAdder**
* Установите его следующим образом(**Я использовал пример URL, пожалуйста, используйте свой собственный**)

```yaml
resource-pack:
  apply-on-join: true
  kick-player-on-decline: false
  delay-ticks: 1
  self-host:
    enabled: false
    server-ip: '127.0.0.1'
    pack-port: 8163
  external-host:
    enabled: true
    url: 'https://www.dropbox.com/blablabla?dl=0'
```

* **ЭТО ОЧЕНЬ ВАЖНО**: **Используйте команду** `/iareload` для **перезагрузки** \*\*плагина после того, как вы **изменили** что-то в `config.yml` \ (в данном случае для перезагрузки ссылки на загрузку ресурспака)
* **Используйте команду** `/iatexture` на вашей игре, чтобы обновить текущую текстуру игры внутри игры или используйте `/iatexture all`, чтобы обновить ее для каждого игрока.

{% hint style="danger" %}
ПОЖАЛУЙСТА, используйте `/iazip` **каждый раз**, когда редактируете **текстуру**, 3D **модель**, **звук**... затем **перезагрузите** пакет на **Dropbox** и используйте **/iareload**, иначе вы не увидите никаких изменений.
{% endhint %}

{% hint style="warning" %}
**Изменяйте** имя **файла каждый раз, когда** вы **загружаете** **новую версию** **пакета ресурсов**, чтобы **заставить** игру **перезагрузить** **новую версию**.\
Если вы **перезагрузите** **zip** файл с тем же именем и сохраните **одинаковый URL**, он **не будет обновляться** для каждого игрока.
{% endhint %}

## Но это так медленно! Мне приходится перезагружать на DropBox слишком много раз!

Да, это так, поэтому вы должны использовать функцию self host вместо DropBox. Но некоторые хостинги\ (дешевые) не обеспечивают открытие портов, поэтому вы должны использовать DropBox.

{% content-ref url="resourcepack-self-hosting.md" %}
[resourcepack-self-hosting.md](resourcepack-self-hosting.md)
{% endcontent-ref %}