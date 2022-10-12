# Создание 3D-моделей

Для создания пользовательских моделей я использую [BlockBench ](https://blockbench.net/)- бесплатный, простой в использовании и удивительный инструмент для создания моделей Minecraft.

{% embed url="https://www.youtube.com/watch?v=aaJ8XgMAOno" %}

## Создание 3D-модели из текстуры

{% embed url="https://www.youtube.com/watch?v=CSWxrAqjrKA" %}

{% hint style="warning" %}
## Важно

Если вы используете **не-ванильную** текстуру (ваш **.png** файл), вам нужно открыть **.json** файл вашей модели и сделать небольшую правку.

Если ваша модель использует пользовательскую текстуру, вы должны убедиться, что перед именем текстуры указано ваше namespace.\
Например, если у вас есть 3D модель и текстура имеет такой путь: `plugins\ItemsAdder\data\resource_pack\assets\my_items\textures\item\custom_item_1.png`

```javascript
 "textures":{
      "0":"item/custom_item_1"
   },
```

вы должны добавить **namespace** перед ним (`my_items` в моем примере, вы должны использовать свое пространство имен).

```javascript
 "textures":{
      "0":"my_items:item/custom_item_1"
   },
```
{% endhint %}
