# OneDrive

{% hint style="warning" %}
## Не рекомендуется.
{% endhint %}

### Шаг 1

![](<../../.gitbook/assets/image (52) (1) (1) (1) (1).png>)

### Шаг 2

![](<../../.gitbook/assets/image (43) (1) (1).png>)

### Шаг 3

![](<../../.gitbook/assets/image (53) (1) (1).png>)

### Шаг 4

Откройте `config.yml` из **ItemsAdder** и включите опцию `external-host` для вашего нового URL.

{% code title="config.yml" %}
```yaml
    external-host:
      enabled: true
      url: 'https://onedrive.live.com/yoururl.....'
      skip-url-file-type-check___DONT_ASK_HELP_IF_SET_TRUE: true
```
{% endcode %}

Это очень важно. Установите значение true.

```yaml
skip-url-file-type-check___DONT_ASK_HELP_IF_SET_TRUE: true
```

{% hint style="warning" %}
Имейте в виду, что это немного "рискованно", потому что сервер не может убедиться в достоверности URL.

Это может привести к тому, что ваши игроки застрянут на этапе входа в систему, если URL не действителен или OneDrive не обеспечивает прямую загрузку, иногда такое случается.
{% endhint %}
