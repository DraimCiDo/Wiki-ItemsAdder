# Листья и деревья

## Создание листьев и деревянных блоков

Чтобы создать пользовательское дерево, необходимо создать два блока для каждого дерева: leaves и wood.

### Следуйте этому руководству для создания блоков&#x20;

{% content-ref url="../creating-a-custom-item/blocks/block.md" %}
[block.md](../creating-a-custom-item/blocks/block.md)
{% endcontent-ref %}

Например, я создал 2 блока, следуя руководству: `my_leaves`, `my_log`.

```yaml
info:
  namespace: myitems
items:
  my_leaves:
    display_name: "My Leaves"
    permission: myitems.my_leaves
    resource:
      material: PAPER
      generate: true
      textures:
      - block/my_leaves.png
    specific_properties:
      block:
        hardness: 0.2
        cancel_drop: true
        placed_model:
          type: REAL_TRANSPARENT
          break_particles: ITEM
  my_log:
    display_name: "My Log"
    permission: myitems.my_log
    resource:
      material: PAPER
      generate: true
      textures:
      - block/my_log/log_top.png
      - block/my_log/log.png
      - block/my_log/log.png
      - block/my_log/log.png
      - block/my_log/log_top.png
      - block/my_log/log.png
    specific_properties:
      block:
        hardness: 1.7
        placed_model:
          type: REAL
          break_particles: ITEM
        break_tools_whitelist:
        - _AXE
        - _axe
        - HAND
```
