---
description: Этот рецепт позволяет вашим игрокам готовить/плавить материалы
---

# Переплавка в печи

## Пример

```yaml
  cooking:
    cooked_sausage:
      permission: itemsadder.cooked_sausage
      ingredient:
        item: itemsadder:sausage
      machines:
      - FURNACE
      - BLAST_FURNACE
      exp: 1
      cook_time: 200
      result:
        item: itemsadder:cooked_sausage
        amount: 1
```

В этом примере я создал рецепт `cooking` под названием `cooked_sausage `.

`machines` список ванильных машин, которые могут плавить/готовить данный предмет\
`exp` опыт, получаемый игроком при завершении приготовления пищи\
`cook_time` время, необходимое для завершения процесса приготовления (**в тиках**)
