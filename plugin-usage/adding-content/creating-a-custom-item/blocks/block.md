# Блоки

## Мой первый пользовательский блок

### Создание файла блоков

{% hint style="warning" %}
Это пример блока (не забудьте изменить `myitems` [namespace ](../../basic-concepts/namespace/) на тот, который вам нужен).
{% endhint %}

Например, я создал **файл**, который будет содержать все мои **блоки**:

В этом файле (`blocks.yml`) я начинаю создавать простой блок под названием `red_block`.

![](<../../../../.gitbook/assets/immagine (90).png>)

```yaml
info:
  namespace: myitems
items:
  red_block:
    display_name: Красный блок
    permission: red_block
    resource:
      material: PAPER
```

{% hint style="warning" %}
Очень важно использовать **неразмещаемый** ванильный **материал**. Например, **PAPER**.\
Если вы используете блок (например, STONE или DIRT), это приведет к глюкам при размещении.
{% endhint %}

## Текстуры блоков

### Создание файлов текстур

Теперь самое интересное, давайте установим текстуры!\
Для этого вам нужно поместить файл текстур `.png` в нужную папку.\
В данном случае ваше **namespace** - `myitems`, поэтому вы должны поместить их сюда:

![](<../../../../.gitbook/assets/image (52) (1) (1).png>)

### Применение файлов текстур к вашему предмету

Теперь снова откройте файл `blocks.yml` и добавьте часть `resource`, как это сделал я.\
Как вы видите, я установил `generate: true` и задал текстуры для элемента.\
Это говорит плагину автоматически генерировать 3D модель, используя ваши текстуры.

```yaml
info:
  namespace: myitems
items:
  red_block:
    display_name: Красный блок
    permission: red_block
    resource:
      generate: true
      material: PAPER
```

### Использование различных текстур для каждого лица

{% hint style="warning" %}
**Важно**: соблюдайте правильный порядок кардинальных направлений, как показано в примере.
{% endhint %}

```yaml
info:
  namespace: myitems
items:
  red_block:
    display_name: Красный блок
    permission: red_block
    resource:
      generate: true
      material: PAPER
      textures:
        - block/red_block_down.png
        - block/red_block_east.png
        - block/red_block_north.png
        - block/red_block_south.png
        - block/red_block_up.png
        - block/red_block_west.png
```

### Использование одной и той же текстуры для каждого лица

```yaml
info:
  namespace: myitems
items:
  red_block:
    display_name: Red Block
    permission: red_block
    resource:
      generate: true
      material: PAPER
      textures:
        - block/red_block.png
```

## Добавление функциональности размещения блоков

Вы должны добавить атрибут `specific_properties`, как в этом примере:

```yaml
info:
  namespace: myitems
items:
  red_block:
    display_name: Красный блок
    permission: red_block
    resource:
      generate: true
      material: PAPER
      textures:
        - block/red_block.png
    specific_properties:
      block:
        placed_model:
          type: REAL_NOTE
          break_particles: ITEM
```

{% hint style="info" %}
Нажмите на нижнюю ссылку, если вы хотите указать **инструменты**, которые могут сломать блок, добавить **твердость** и **другие атрибуты**.
{% endhint %}

## Заключительная часть

Теперь вам просто нужно указать плагину загрузить только что добавленный блок.

### Если вы используете [самостоятельный хост](../../../resourcepack-hosting/resourcepack-self-hosting.md) или [auto-external-host](../../../resourcepack-hosting/automatic-upload-hosting.md):

* запустите `/iazip`.

### Если вы пользуетесь [внешним хостом](../../../resourcepack-hosting/resourcepack-on-dropbox.md) (Dropbox) прочитайте это':

Не забудьте загрузить новый сгенерированный .zip файл на ваш хостинг (Dropbox)!\
1\. Возьмите его из этой папки:

![](<../../../../.gitbook/assets/immagine (96) (2) (3) (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png>)

2\. Загрузите его на свой хостинг (Dropbox)\
3\. Откройте `config.yml` ItemsAdder и обновите `external-host` url на вашу новую ссылку.

```yaml
  self-host:
    enabled: false
    server-ip: '127.0.0.1'
    pack-port: 8163
  external-host:
    enabled: true
    url: 'https://www.dropbox.com/blablabla?dl=0'
```

Если у вас остались вопросы, прочитайте полное руководство по **внешнему хосту** здесь:

{% content-ref url="../../../resourcepack-hosting/resourcepack-on-dropbox.md" %}
[resourcepack-on-dropbox.md](../../../resourcepack-hosting/resourcepack-on-dropbox.md)
{% endcontent-ref %}

## Получение блока в игре

Выполните команду `/iaget red_block`, чтобы получить предмет.

![](<../../../../.gitbook/assets/immagine (92).png>)

![](<../../../../.gitbook/assets/immagine (91).png>)

![](<../../../../.gitbook/assets/immagine (93).png>)
