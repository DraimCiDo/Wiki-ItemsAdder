# Тонкий шрифт

## Тонкий шрифт

Обычно в Minecraft вы устанавливаете **Force Unicode Font: ON**, чтобы получить _"тонкий шрифт"_.

![](../../../.gitbook/assets/immagine%20%284%29.png)

  
С **ItemsAdder** это невозможно, потому что это сделает emoji, GUI, HUD больше не работающими. Это баг Minecraft.

{% hint style="warning" %}
Вы должны установить **Force Unicode Font: ВЫКЛ** 
{% endhint %}

![](../../../.gitbook/assets/immagine%20%283%29.png)

и **установить это** в `config.yml`.

```yaml
  thin-font:
    enabled: true
```

Это позволяет вам установить **Force Unicode Font: OFF**, но при этом включить тонкий шрифт.

{% hint style="warning" %}
Помните, что после этого изменения вы должны заново создать файл pack.zip.   
Проверьте [документацию по Ресурс-Паку](../../resourcepack-hosting/)
{% endhint %}

### Вот результат

![](../../../.gitbook/assets/immagine%20%286%29.png)

{% hint style="success" %}
Теперь вы можете видеть "тонкий шрифт" и графические интерфейсы, эмодзи, HUD'ы не будут ломаться\(ошибка белых квадратов\).
{% endhint %}

