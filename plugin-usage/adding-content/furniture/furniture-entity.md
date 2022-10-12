# Мебельный субъект

## Поддерживаемые субъекты

### armor\_stand

Этот тип мебельной сущности полезен, когда вы хотите создать стулья, растения, колонны, лампы и подобные украшения среды, которым не нужно вращаться в зависимости от поверхности, на которой вы их размещаете.

![](<../../../.gitbook/assets/image (47) (1) (1) (1) (2).png>)

```yaml
behaviours:
  furniture:
    entity: armor_stand
    small: true
    solid: true
    fixed_rotation: true
    hitbox:
      length: 1
      width: 2
      height: 1
      width_offset: 0.5
    placeable_on:
      walls: false
      ceiling: false
      floor: true
  furniture_sit:
    sit_height: 0.5
```

### item\_frame

Этот тип сущности мебели полезен, когда вы хотите заставить мебель вращаться в зависимости от поверхности, на которой вы ее размещаете.

Например, если у вас есть декоративная лампа, вы можете разместить ее на стенах, потолке и земле и сделать так, чтобы она автоматически ориентировалась в зависимости от наклона поверхности.&#x20;

![](<../../../.gitbook/assets/image (43) (1) (1) (1) (1).png>)



```yaml
behaviours:
  furniture:
    entity: item_frame
    light_level: 15
    solid: false
    hitbox:
      length: 1
      width: 1
      height: 1.5
    placeable_on:
      walls: true
      ceiling: true
      floor: true
```
