# Тонкий шрифт (юникод)

## Тонкий шрифт

Обычно в Minecraft вы устанавливаете **Force Unicode Font: ON**, чтобы получить _"тонкий шрифт"_.

![](<../../../.gitbook/assets/immagine (5).png>)

\
С **ItemsAdder** это невозможно, потому что это заставит emoji, GUI, HUD больше не работать. Это ограничение Minecraft.

{% hint style="warning" %}
Вы должны установить **Force Unicode Font: OFF**&#x20;
{% endhint %}

![](<../../../.gitbook/assets/immagine (6).png>)

и **установить это** в `config.yml`.

```yaml
  thin-font:
    enabled: true
```

Это позволяет вам установить **Force Unicode Font: OFF**, но при этом включить тонкий шрифт.

{% hint style="warning" %}
Помните, что после этого изменения вы должны заново создать файл pack.zip. \
Проверьте [документацию по Ресурс-Паку](../../resourcepack-hosting/)
{% endhint %}

### Вот результат

![](<../../../.gitbook/assets/immagine (7).png>)

{% hint style="success" %}
Теперь вы можете видеть "тонкий шрифт", а графические интерфейсы, эмодзи, HUD не будут ломаться (белые квадраты с ошибками).
{% endhint %}
