# Файлы перевода Minecraft

{% hint style="info" %}
С помощью ItemsAdder вы можете легко перезаписать файлы перевода Minecraft по умолчанию.  
\(версия 2.1.35+\)
{% endhint %}

### Пример использования

В этом примере я изменю текст "Return to game" в меню ESC.

![](../../../.gitbook/assets/image%20%2831%29.png)

```yaml
info:
  namespace: ia_various_configs
minecraft_lang_overwrite:
  esc_menu_texts:
    entries:
      "menu.returnToGame": "Return to &aSurvival &fGamemode"
    languages:
      - ALL
```

### languages

Свойство languages используется для перечисления всех языков, на которых вы хотите изменить текст.  
Вы должны установить его только на языки вашей базы игроков, но я решил установить его на ALL, чтобы вы были уверены, что все смогут увидеть пользовательский текст, несмотря на выбранный язык клиента.

### entries

Это список переведенных текстов. Вы можете найти [полный список здесь](https://gist.github.com/LoneDev6/1df03fd853b2b244a7348216c8fa909d).



