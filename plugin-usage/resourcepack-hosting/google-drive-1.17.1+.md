---
cover: ../../.gitbook/assets/Google-Drive.jpg
coverY: 0
---

# 🗂 Google Drive (1.17.1+)

## Как использовать Google Drive

{% hint style="warning" %}
Этот метод имеет некоторые проблемы на некоторых ПК в версиях Minecraft до 1.17 из-за ошибки в Minecraft, подробнее читайте здесь: [https://bugs.mojang.com/browse/MC-143768](https://bugs.mojang.com/browse/MC-143768)

Этот метод работает в 100% случаев на Minecraft 1.17.1 и выше.
{% endhint %}

### Этап 1

Нажмите ПКМ по zip-файлу ресурспака и нажмите "Получить ссылку".

![](<../../.gitbook/assets/immagine (153) (1).png>)

### Этап 2

Важно: Установите разрешение "Любой, у кого есть ссылка".

![](<../../.gitbook/assets/immagine (145).png>)

Нажмите "Скопировать ссылку"

![](<../../.gitbook/assets/immagine (149).png>)

### Этап 3

Посетите этот веб-сайт: [http://a.devs.beer/gdrive-direct](http://a.devs.beer/gdrive-direct)

Вставьте ссылку и нажмите "Получить прямую ссылку".

![](<../../.gitbook/assets/immagine (144).png>)

### Этап 4

Сайт автоматически добавляет сгенерированную ссылку в буфер обмена.

![](<../../.gitbook/assets/immagine (147).png>)

Теперь вы можете вставить ссылку в конфигурационный файл **ItemsAdder** `config.yml`, а затем использовать команду `/iareload`.

{% code title="config.yml" %}
```yaml
external-host:
  enabled: true
  url: 'http://drive.google.com/uc?export=view&id=10g3whim95Hab40KZNjUkwY9FUuqKMGh5'
```
{% endcode %}

### Готово!

Теперь вы можете видеть, что ресурспак корректно загружается игрой.

## Распространенные проблемы

### Долгое время на "Делаем запрос... 100%"

### ![](<../../.gitbook/assets/immagine (146).png>)

Это нормально. Это происходит потому, что Google Drive выполняет некоторые действия перед авторизацией загрузки ресурспака.

Это произойдет только тогда, когда игрок впервые загрузит ресурспак, и займет от 5 до 10 секунд.

### Ресурспак не загружается вообще

Этот метод имеет некоторые проблемы на некоторых ПК в версиях Minecraft до 1.17 из-за ошибки в Minecraft, подробнее читайте здесь: [https://bugs.mojang.com/browse/MC-143768](https://bugs.mojang.com/browse/MC-143768)

Этот метод работает в 100% случаев на Minecraft 1.17.1 и выше.
