# 🎨 Разноцветные модели

{% hint style="warning" %}
Доступно только в **ItemsAdder 2.3.11+**.
{% endhint %}

{% hint style="info" %}
Если вы хотите сделать цветной предмет (например, цветную мебель) или цветной автомобиль, вам не нужно создавать отдельную модель для каждого элемента с разным цветом.
{% endhint %}

## Как мне это сделать?

### 1. Откройте вашу модель в blockbench

![](<../../../.gitbook/assets/immagine (79).png>)

### 2. Выберите face, которое вы хотите раскрасить

![](<../../../.gitbook/assets/immagine (80).png>)

### 3. Используйте белую/серую текстуру, для лучшего окрашивания

### 4. Включить скрытую функцию "Тонирование"

![](<../../../.gitbook/assets/immagine (81).png>)

![](<../../../.gitbook/assets/immagine (83).png>)

### 5. Включите раскраску для каждого лица, которое вы хотите раскрасить

![](<../../../.gitbook/assets/immagine (85).png>)

### 6. Установить определенный атрибут цвета в вашем файле .yml.

В данном примере я использовал `leather_horse_armor` но вы также можете использовать `potion`.

```yaml
  orange_modern_lamp:
    display_name: "Оранжевая современная лампа"
    specific_properties:
      leather_horse_armor:
        color: ORANGE
    resource:
      material: LEATHER_HORSE_ARMOR
      generate: false
      model_path: item/template_modern_lamp
```

{% hint style="info" %}
Если вы хотите использовать определенный цвет, вы можете использовать этот [выбор цвета](https://www.mathsisfun.com/hexadecimal-decimal-colors.html).\
Скопируйте **десятичный** цвет (hex-цвет).
{% endhint %}

### 7. Теперь вы можете создать столько предметов мебели, сколько захотите, просто измените цвет, и они будут автоматически раскрашены игрой

![](<../../../.gitbook/assets/immagine (86).png>)



