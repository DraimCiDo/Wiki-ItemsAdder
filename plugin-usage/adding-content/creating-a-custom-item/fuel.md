# Топливо

## Как сделать предмет пригодным для использования в качестве топлива?

Это очень просто!\
Вы просто должны использовать топливо [behaviours](../item-properties/behaviours.md).

## Example

```yaml
      fuel: 
        burn_ticks: 20
        machines:
          - BLAST_FURNACE
```

Например, при такой конфигурации этот предмет будет использоваться в **BLAST\_FURNACE** и сгорит за **20 тиков** (**1 секунда**)..&#x20;

### Полный пример предмета

```yaml
  magic_fuel:
    display_name: "%#FE5A00%magic_fuel"
    permission: fuel.magic_fuel
    resource:
      material: COAL
      generate: true
      textures:
      - "minecraft:item/diamond.png"
    behaviours:
      fuel: 
        burn_ticks: 20
        machines:
          - BLAST_FURNACE
```
