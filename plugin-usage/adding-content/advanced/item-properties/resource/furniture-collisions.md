# Столкновения с мебелью

### Как сделать мебель из массива?

Вы можете сделать мебель сплошной, добавив атрибут "solid".

```yaml
  table:
    display_name: display-name-table
    permission: table
    lore:
      - 'lore-decorative-item'
    resource:
      material: OAK_WOOD
      generate: false
      model_path: item/table
    behaviours:
      furniture:
        small_hitbox: true
        solid: true
```

![](../../../../../.gitbook/assets/image%20%2815%29.png)

