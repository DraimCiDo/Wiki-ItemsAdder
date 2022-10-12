# 😁 Эмодзи

### Введение

Например, я хочу создать пакет эмодзи с именем "myemojis", поэтому мой [namespace ](../basic-concepts/namespace/)был бы `myemojis`

### Создание папки textures

1. Открыть папку plugins\ItemsAdder\data\resource\_pack\assets\\
2. Создайте папку с именем `myemojis`
3. Создайте папку `textures`, затем внутри нее создайте папку `font`, а затем папку `emoji`.
4. Теперь у вас должен быть такой путь: **plugins\ItemsAdder\data\resource\_pack\assets\myemojis\textures\font\emoji**
5. Внутри этой папки вы должны поместить свои эмодзи, вы должны сделать их 72x72, чтобы убедиться, что они не слишком большие и не пикселированные. Но вы можете выбрать размер по своему усмотрению (главное, чтобы высота и ширина не превышали 256).
6. В этом примере я поместил изображение с именем **smile.png**

### Создание конфигурации ItemsAdder для ваших эмодзи

1. Теперь нужно создать папки для конфигураций эмодзи. В данном примере вы должны создать папку с именем **myemojis** внутри **plugins\ItemsAdder\data\items\_packs\\**
2. внутри **plugins\ItemsAdder\data\items\_packs\myemojis** создайте файл с именем **emoji\_images.yml** (вы можете назвать его как угодно)
3. Теперь вам нужно открыть файл .yml и прописать&#x20;

```yaml
info:
  namespace: "myemojis"
```

Затем добавьте свой эмодзи (в этом примере я сделал **smile** emoji) в список font\_images, чтобы ваш файл выглядел следующим образом:

```yaml
info:
  namespace: "myemojis"
font_images:
  smile:
    permission: 0
    show_in_gui: true
    path: "font/emoji/smile.png"
    scale_ratio: 9
    y_position: 8
```

**scale\_ratio** - это конечная высота эмодзи в пикселях, так как 72x72 пикселей слишком много, вам придется изменить масштаб, но вы можете установить 9, и Minecraft будет обрабатывать его автоматически.\
**y\_position** - это положение в пикселях, 8 должно быть хорошим значением, если вы сохраните размер 72x72 и scale\_ratio равным 9. Если у вас другой размер, вам придется подстроить положение y\_position, основываясь на ваших тестах.

{% hint style="danger" %}
`scale_ratio` ВСЕГДА должно быть больше, чем `y_position`, иначе Minecraft это не понравится. Я не могу исправить эту проблему, это ограничение **Minecraft**.
{% endhint %}

## Вид в игре

![](<../../../.gitbook/assets/immagine (116) (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (2).png>)

### Использование /e

![](<../../../.gitbook/assets/immagine (112).png>)

![](<../../../.gitbook/assets/immagine (111).png>)

![](<../../../.gitbook/assets/immagine (113).png>)
