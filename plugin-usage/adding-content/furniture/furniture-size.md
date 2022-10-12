# Размер мебели

{% hint style="warning" %}
### Рекомендуется использовать небольшую мебель (маленькую стойку для брони)
{% endhint %}

## Как можно отрегулировать положение мебели при установке?

Если вы хотите настроить его, вам просто нужно использовать [Blockbench](../item-properties/resource/creating-3d-models.md):

![](<../../../../.gitbook/assets/immagine (8).png>)

1. нажмите на **дисплей** справа
2. нажмите на значок **стойку для брони** слева
3. нажмите на **улыбающееся лицо** (**голову**) слева
4. **переместите** вашу модель на стойку для брони **снизу** (это **земля**).

### Слишком маленькая мебель

Если ваша мебель **слишком маленькая**, но вы хотите, чтобы она была **больше** и с большим **хитбоксом**, просто установите значение **false**.\
Если вы хотите иметь **маленькую мебель** с маленьким хитбоксом, просто установите значение true.

{% hint style="info" %}
Примечание: хитбокс не ограничен, вы можете установить больший хитбокс, который не будет связан с самой сущностью.

Установите атрибуты хитбокса:

```yaml
    hitbox:
      height: 2
      length: 3
      width: 3
```
{% endhint %}

{% tabs %}
{% tab title="Big furniture" %}
```yaml
behaviours:
  furniture:
    small: false
```
{% endtab %}

{% tab title="Small furniture" %}
```yaml
behaviours:
  furniture:
    small: true
```
{% endtab %}
{% endtabs %}

#### и установить это в [BlockBench](../item-properties/resource/creating-3d-models.md)

{% tabs %}
{% tab title="Big furniture" %}


![](<../../../../.gitbook/assets/immagine (9).png>)
{% endtab %}

{% tab title="Small furniture" %}


![](<../../../../.gitbook/assets/immagine (10).png>)
{% endtab %}
{% endtabs %}
