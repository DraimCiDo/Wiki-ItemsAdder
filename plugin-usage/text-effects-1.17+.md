---
description: Анимация текста
---

# Эффекты текста (1.17+)

## Что такое эффекты текста?

ItemsAdder ***2.4.19** предлагает несколько классных декоративных текстовых эффектов, которые вы можете использовать в своем сервере, чтобы сделать его более профессиональным.

{% hint style="danger" %}
## Эта функция работает только на клиенте **Minecraft 1.17**, версия сервера не имеет значения.
{% endhint %}

{% hint style="warning" %}
Вам нужно прописать `/iazip`, чтобы включить/выключить эту функцию.\
Не забудьте также включить ее в `config.yml`.

```yaml
effects:
  text-effects:
    enabled: true
    replace-in-customitems-name-and-lore: true
    chat:
      enabled: true
    sign:
      enabled: true
    book:
      enabled: true
    anvil:
      enabled: true
```
{% endhint %}



## Разрешения

* Использование **text-effects** в **chat**
  * `ia.user.text_effect.chat`
* Использование **text-effects** в**signs**
  * `ia.user.text_effect.sign`
* Использование **text-effects** в **books**
  * `ia.user.text_effect.book`
* Использование **text-effects** в **anvil**
  * `ia.user.text_effect.anvil`
* Использование **text-effect**
  * `ia.user.text_effect.use.<effect>`

## Список эффектов

### Радуга

![](../.gitbook/assets/rainbow.gif)

![](<../.gitbook/assets/immagine (128).png>)

![](<../.gitbook/assets/immagine (129).png>)

![](../.gitbook/assets/rainbow\_item.gif)

Разрешение: `ia.user.text_effect.use.r`\
Использование: `<r text>`

### Колебания

![](../.gitbook/assets/wobble.gif)

![](../.gitbook/assets/wobble\_item.gif)

Разрешение: `ia.user.text_effect.use.w`\
Использование: `<w text>`

### Прыжки

![](../.gitbook/assets/jump\_chat.gif)

![](../.gitbook/assets/jump.gif)

![](../.gitbook/assets/jump\_boss.gif)

Разрешение: `ia.user.text_effect.use.j`\
Использование: `<j text>`

### Радуга + Колебание

![](../.gitbook/assets/rw\_chat.gif)

Разрешение: `ia.user.text_effect.use.rw`\
Использование: `<rw text>`

### Радуга + Прыжки

![](../.gitbook/assets/rj.gif)

Разрешение: `ia.user.text_effect.use.rj`\
Использование: `<rj text>`

## Где можно использовать эти эффекты?

* Имя предмета (в файле .yml)
* Лор предметов (в файле .yml)
* Чат
* Табличка
* Книга
* Босс-бар
* Префикс-Суффикс(На пример в LuckPerms)
* _Скоро...._

![](../.gitbook/assets/rainbow\_wobble\_lore.gif)

## Как создать анимированный префикс (Luckperms)

![](<../.gitbook/assets/immagine (133).png>)

`/lp group admin meta setprefix "<rw ADMIN >"`

![](../.gitbook/assets/prefix.gif)

Нажмите, чтобы прочитать[ Официальную документацию LuckPerms](https://luckperms.net/wiki/Prefixes,-Suffixes-&-Meta) если вы не знаете, как работает префикс.
