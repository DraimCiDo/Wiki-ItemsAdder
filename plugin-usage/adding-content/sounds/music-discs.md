# 🎹 Музыкальные диски

### Шаг 1 - создайте звук

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

### Шаг 2 - создание диска

Создайте новый элемент в вашем пространстве имен, это будет ваш музыкальный диск:

```yaml
  music_disc_cdk_sunday:
    display_name: display-name-music_disc_cdk_sunday
    permission: music_disc_cdk_sunday
    lore:
    - '&7Cdk - Sunday'
    resource:
      material: STICK
      generate: true
      textures:
      - item/music_disc_cdk_sunday.png
    behaviours:
      music_disc:
        song:
          name: itemsadder:music_disc.cdk_sunday
          description: Cdk - Sunday
```

Как вы можете видеть, я добавил специальное поведение под названием "music\_disc". Оно будет сообщать серверу Spigot, что этот предмет является пользовательским музыкальным диском.\
**name** - это звук, который будет воспроизводиться, вы добавили его в **шаге 1**.
