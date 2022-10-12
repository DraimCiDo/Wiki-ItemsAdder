# Размер мебели

## Как можно отрегулировать положение мебели при установке?

Если вы хотите настроить его, вам просто нужно использовать [Blockbench](creating-3d-models.md):

![](../../../../../.gitbook/assets/immagine%20%289%29.png)

1. нажмите на **display** справа
2. нажмите на значок **armorstand** слева
3. нажмите на **simle face** \(**head**\) слева
4. **переместите** вашу модель на стойку **bottom** \(это **ground**\).

### Слишком маленькая мебель

Если ваша мебель **слишком маленькая**, вы хотите, чтобы она была **больше** и с большим **хитбоксом**, просто установите значение **false**.  
Если вместо этого вы хотите **маленькую мебель** с маленьким хитбоксом, просто установите значение true.

{% tabs %}
{% tab title="Big furniture" %}
```yaml
behaviours:
  furniture:
    small_hitbox: false
```
{% endtab %}

{% tab title="Small furniture" %}
```
behaviours:
  furniture:
    small_hitbox: true
```
{% endtab %}
{% endtabs %}

#### и установить значения ниже в [BlockBench](creating-3d-models.md)

{% tabs %}
{% tab title="Big furniture" %}


![](../../../../../.gitbook/assets/immagine%20%288%29.png)
{% endtab %}

{% tab title="Small furniture" %}


![](../../../../../.gitbook/assets/immagine%20%2810%29.png)
{% endtab %}
{% endtabs %}

