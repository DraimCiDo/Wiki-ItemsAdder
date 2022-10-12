# 👌🏻Права (Permissions)

* Для пользователей

  * /ia
    * `ia.user.ia`
  * /iarecipe
    * `ia.user.iarecipe`
  * /iatexture
    * `ia.user.iatexture`
  * крафтинг
    * `ia.user.craft.PERMISSION` \(*или выдайте все права на крафты сразу одной строкой - `ia.user.craft`.*\)
    * чтобы получить больше информации о правах для предмета - [ознакомьтесь](adding-content/advanced/item-properties/basic/item-permission.md)
  * просмотр предметов в меню /ia
    * `ia.user.ia.PERMISSION` \(*или выдайте все права на /ia меню одной строкой - `ia.user.ia`*.\)
    * чтобы получить больше информации о правах для предмета - [ознакомьтесь](adding-content/advanced/item-properties/basic/item-permission.md)
    * `ia.user.iasearchgui` для выдачи права на функцию поиска в виде GUI для меню /ia
    * Также, плагин позволяет устанавливать права на категории предметов, можете ознакомиться с данной страницей - [/ia GUI ](ia.md)
  * Эмоджи, GUI и HUDы \(картинки юникода\)
    * **/iaimage /emoji, /iaemoji, /e** GUI на основе книги \(отображает список всех эмоджи/картинок юникода в форме книги\)
      * `ia.user.image.gui`
    * **/iaimage** **/emoji &lt;text&gt;, /iaemoji &lt;text&gt;, /e &lt;text&gt;** \(отображает все эмоджи на основе искового запроса\)
      * `ia.user.image.hints`
    * Использование эмоджи в чате
      * `ia.user.image.chat`
    * Использование эмоджи в командах
      * `ia.user.image.command`
    * Использование эмоджи на табличках
      * `ia.user.image.sign`
    * Использование эмоджи в книгах
      * `ia.user.image.book`
    * Использование эмоджи в именах предметов в наковальне
      * `ia.user.image.anvil`
    * Право использовать определенный эмоджи
      * `ia.user.image.use.<font image name>`
      * Пример: `ia.user.image.use.heart`

  ​

* Для администраторов
  * /iaget
    * `ia.admin.iaget`
  * /iagive
    * `ia.admin.iagive`
  * /iadrop
    * `ia.admin.iadrop`
  * /iaremove
    * `ia.admin.iaremove`
  * /iatag
    * `ia.admin.iatag`
  * /iareload
    * `ia.admin.iareload`
  * /iablock \(дает информацию о блоке, на который вы смотрите\)
    * `ia.admin.iablock`
  * /iadurability
    * `ia.admin.iadurability`
  * Право редактирования \(кнопка редактирование в меню /ia\)
    * `ia.admin.edit`
  * /iaplayerstat write \(установка значений статистик игрока плагина\)
    * `ia.admin.iaplayerstat.write`
  * /iaplayersta read \(считать значение статистики игрока плагина\)
    * `ia.admin.iaplayerstat.read`
  * /iainfo \(информация о количестве всех предметов, блоков, эмоджи и о самом плагине\)
    * `ia.admin.iainfo`
  * /iakill &lt;mob\|all&gt; \(убить сущность плагина\)
    * `ia.admin.iakill`
  * /iasummon &lt;mob&gt; \[количество\]
    * `ia.admin.iasummon`
  * /iaspawntree &lt;tree&gt;
    * `ia.admin.iaspawntree`
  * /iaplaytotemanimation &lt;totem&gt; &lt;player&gt;
    * `ia.admin.iatotemanimation`

* Прочее:
  * Право избежать отключение от сервера, если владелец права отказался от пакета ресурсов
    * `ia.resourcepack.bypasskick`
  * Право избежать отключенное выпадение предмета из блока для игрока
    * `ia.admin.bypassblockplaceloot`

