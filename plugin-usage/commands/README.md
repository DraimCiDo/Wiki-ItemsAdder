# 🖥 Команды

* iatexture:
  * описание: Заставить клиента перезагрузить ресурс-пак (игрока или всех)
  * использование: /iatexture \[all or player]
  * разрешение: "ia.user.iatexture"
* iaget:
  * описание: Получить кастомный предмет по имени или по id.
  * использование: /iaget \<item> \[amount]
  * разрешение: "ia.admin.iaget"
* iagive:
  * описание: Дать игроку кастомный предмет
  * использование: /iagive \<item> \[amount] \[silent]
  * разрешение: "ia.admin.iagive"
* iadrop:
  * описание: Бросить кастомный предмет в координатах или в местоположении игрока
  * использование: /iadrop \<item> \[amount]
  * разрешение: "ia.admin.iadrop"
* iaremove:
  * описание: Удалить кастомный предмет из инвентаря игрока
  * использование: /iaremove \<item> \[amount] \[silent]
  * разрешение: "ia.admin.iaremove"
* iatag:
  * описание: Показать отладочную информацию о кастомном предмете
  * использование: /iatag
  * разрешение: "ia.admin.iatag"
* iacustommodeldata:
  * описание: Показать CustomModelData кастомного предмета
  * использование: /iacustommodeldata
  * разрешение: "ia.admin.custommodeldata"
* iaplayerstat:
  * описание: Установить кастомные значения статистики игрока (и обновление HUD)
  * использование: /iaplayerstat \<read|write|increment|decrement> \<player> \<attribute> \<int|float|string> \[value]
  * разрешение: "ia.admin.iaplayerstat"
* ia:
  * описание: Открыть GUI с информацией об предметах
  * использование: /ia
  * разрешение: "ia.user.ia"
* iarepair:
  * описание: Отремонтировать текущий предмет (ванильный или кастомный)
  * использование: /iarepair
  * разрешение: "ia.admin.iarepair"
* iarename
  * описание: Переименовать текущий предмет (ванильный или кастомный). Поддерживает эмодзи (font\_images) и текстовые эффекты ItemsAdder.
  * использование: /iarename \<name>
  * разрешение: "ia.admin.iarename"
* iadurability:
  * описание: Изменить прочность текущего предмета (ванильного или кастомного)
  * использование: /iadurability
  * разрешение: "ia.admin.iadurability"
* iareload:
  * описание: Перезагрузить файлы items\_packs
  * использование: /iareload
  * разрешение: "ia.admin.iareload"
* iazip:
  * описание: Выполнить /iareload и сгенерировать файл pack.zip
  * использование: /iazip
  * разрешение: "ia.admin.iazip"
* iablock:
  * описание: Показать информацию о просматриваемом блоке
  * использование: /iablock
  * разрешение: "ia.admin.iablock"
* ialiquid:
  * описание: Показать информацию о жидкости, на которую вы смотрите
  * использование: /ialiquid \[x] \[y] \[z]
  * разрешение: "ia.admin.ialiquid"
* e:
  * описание: Показать список изображений шрифтов (эмодзи, худы...). Также может использоваться для отправки сообщений с автозаполнением эмодзи.
  * использование: /iaimage
  * разрешение: "ia.user.image.gui"
* iarecipe:
  * описание: Показать GUI с информацией о рецептах предмета
  * использование: /iarecipe \[item]
  * разрешение: "ia.user.iarecipe"
* iahud:
  * описание: Принудительное отображение/скрытие HUD вручную по идентификатору с именем
  * использование: /iahud \[name]
  * разрешение: "ia.admin.iahud"
* iaconvert:
  * описание: Преобразует старый мир 1.0 в мир 2.0 (блоки), вы можете решить удалить руды (камень) или сохранить их
  * использование: /iaconvert \[world] \[deleteores]
  * разрешение: "ia.admin.iaconvert"
* iainfo:
  * описание: Показывать информацию о плагине
  * использование: /iainfo
  * разрешение: "ia.admin.iainfo"
* iakill:
  * описание: Убить кастомных мобов
  * использование: /iakill
  * разрешение: "ia.admin.iakill"
* iasummon:
  * описание: Создать кастомных мобов
  * использование: /iasummon \[amount]
  * разрешение: "ia.admin.iasummon"
* iaexport:
  * описание: Экспорт namespace в файл .zip
  * использование: /iaexport \<namespace>
  * разрешение: "ia.admin.iaexport"
* iaspawntree:
  * описание: Создать кастомное дерево
  * использование: /iaspawntree
  * разрешение: "ia.admin.iaspawntree"
* iaplaytotemanimation:
  * описание: Показать анимацию Тотема бессмертия
  * использование: /iaplaytotemanimation
  * разрешение: "ia.admin.iatotemanimation"
* iaplaysound:
  * описание: Воспроизвести звуки плагина. Полезно в консоли, так как ванильный /playsound не работает в консоли.
  * использование: /iaplaysound
  * разрешение: "ia.admin.iaplaysound"
* iacleancache:
  * описание: Очистить неиспользуемые id из кэша, чтобы их могли использовать будущие добавленные блоки/предметы.
  * использование: /iacleancache
  * разрешение: "ia.admin.iacleancache"
* iasha1:
  * описание: Вычислить sha1 текущего ресурс-пака.
  * использование: /iasha1
  * разрешение: "ia.user.iasha1"
* iahitbox:
  * описание: Показывать хитбокс расставленных предметов мебели.
  * использование: /iahitbox
  * разрешение: "ia.admin.iahitbox"
* iaconfig:
  * описание: Основная команда для выполнения некоторых операций над конфигурациями плагина.
  * разрешение: "ia.admin.iaconfig"
* iaentity:
  * описание: Основная команда для управления пользовательскими сущностями.
  * разрешение: "ia.admin.iaentity"
* iaemote
  * описание: Воспроизвести кастомную анимацию игрока.
  * использование: /iaemote \<emote> \[player]
  * разрешение: "ia.user.iaemote"
    * others: "ia.user.iaemote.others"
