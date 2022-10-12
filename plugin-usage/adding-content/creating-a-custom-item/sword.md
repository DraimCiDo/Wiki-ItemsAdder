# Sword

{% hint style="danger" %}
### Namespace

If you didn't create your namespace please follow the [namespace tutorial](../basic-concepts/namespace/creating-your-namespace.md).
{% endhint %}

{% hint style="danger" %}
### Resourcepack hosting

Remember to **decide** a **resourcepack hosting** method **before** you **start**.\
I **advise** you to use **self-host** which is **easier** and **faster**, but you can also use **Dropbox** and similar
{% endhint %}

## Мой первый меч

### Создание файла мечей

{% hint style="warning" %}
Это пример меча (не забудьте изменить `myitems` [namespace](../basic-concepts/namespace/) на тот, который вам нужен).
{% endhint %}

Например, я создал **файл**, который будет содержать все мои **кастомные мечи**:

![](<../../../.gitbook/assets/immagine (16).png>)

В этом файле (`myswords.yml`) я начинаю создавать простой меч под названием `mysword`.

```yaml
info:
  namespace: myitems
items:
  mysword:
    display_name: My Sword
    permission: mysword
    durability:
      max_custom_durability: 1324
  
```

## Текстура предмета

### Создание файла текстуры

Теперь самое интересное, давайте установим текстуру меча.\
Для этого вам нужно поместить файл текстуры меча `.png` в нужную папку.\
В данном случае ваше **namespace** - `myitems`, поэтому вы должны поместить его сюда:

![](<../../../.gitbook/assets/immagine (14).png>)

### Применение файла текстуры к предмету

Теперь снова откройте файл `myswords.yml` и добавьте часть `resource`, как это сделал я.\
Как вы видите, я установил `generate: true` и задал текстуры для предмета.\
Это говорит плагину автоматически генерировать 3D модель, используя ваши текстуры.

```yaml
info:
  namespace: myitems
items:
  mysword:
    display_name: My Sword
    permission: mysword
    durability:
      max_custom_durability: 1324
    resource:
      material: DIAMOND_SWORD
      generate: true
      textures:
      - item/example_item.png
```

## Заключительная часть

Теперь вам просто нужно указать плагину загрузить только что добавленный предмет.\
Для этого вам необходимо:\
\- присоединиться к серверу\
\- убедитесь, что вы приняли ресурспаки\
\- используйте команду `/iazip`\
\- если вы используете внешний хост (DropBox), прокрутите вниз и следуйте инструкциям.\
\- получить предмет с помощью `/iaget mysword`\
\- ГОТОВО!

### Теперь возьмите свой предмет

![](<../../../.gitbook/assets/immagine (18).png>)

![](<../../../.gitbook/assets/immagine (19).png>)

## Если вы используете внешний хост (Dropbox), читайте здесь:

Не забудьте загрузить новый сгенерированный .zip файл на ваш хостинг (Dropbox)!\
1\. Возьмите его из этой папки:

![](<../../../.gitbook/assets/immagine (96) (2) (3) (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (10) (5).png>)

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

{% content-ref url="../../resourcepack-hosting/resourcepack-on-dropbox.md" %}
[resourcepack-on-dropbox.md](../../resourcepack-hosting/resourcepack-on-dropbox.md)
{% endcontent-ref %}

