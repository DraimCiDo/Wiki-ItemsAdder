# iaconfig

## Функции

### Удалить предмет из конфигурации

`/iaconfig item delete <item>`

Право: `ia.admin.iaconfig.item.delete`

Полностью удаляет предмет из его конфигурационного файла. Пожалуйста, будьте осторожны.

### Отключить предмет в конфигурации

`/iaconfig item disable <item>`

Право: `ia.admin.iaconfig.item.disable`

Отключает предмет из его конфигурационного файла. Пожалуйста, будьте осторожны.

### Удалить рецепты, в которых используется/создается предмет

`/iaconfig recipes deleteofitem <item>`

Право: `ia.admin.iaconfig.recipes.deleteofitem`

Удаляет ПОЛНОСТЬЮ все рецепты, содержащие предмет, из всех файлов конфигурации. Пожалуйста, будьте осторожны.

### Отключить рецепты, в которых используется/создается предмет

`/iaconfig item disableofitem <item>`

Право: `ia.admin.iaconfig.recipes.disableofitem`

Отключает все рецепты, содержащие предмет, из всех файлов конфигурации. Пожалуйста, будьте внимательны.

### Удалить все предметы namespace`а и рецепты этих предметов

`/iaconfig namespace delete <namespace>`

Право: `ia.admin.iaconfig.namespace.delete`

Полностью удаляет все предметы namespace`а и рецепты этих предметов. Пожалуйста, будьте осторожны.

### Отключает все премедты в namespace`е

`/iaconfig namespace disable <namespace>`

Право: `ia.admin.iaconfig.namespace.disable`

Отключает каждый предмет namespace`а и рецепты этих предметов. Пожалуйста, будьте осторожны.
