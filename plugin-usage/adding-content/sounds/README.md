# 🔊 Звуки

### Шаг 1

{% content-ref url="convert-sound-to-.ogg.md" %}
[convert-sound-to-.ogg.md](convert-sound-to-.ogg.md)
{% endcontent-ref %}

* открыть папку **plugins\ItemsAdder\data\resource\_pack\assets**
* откройте папку **пространство имен**.
* создайте новую папку под названием **sounds**.
* поместите туда свой файл **.ogg** (вы также можете создать другую папку для организации звуков, например, папку "effects", папку "sound"...)

например, у меня есть файл **cdk\_sunday.ogg** и я помещаю его в новую папку **music\_disc**.\
Так что теперь у меня `plugin\ItemsAdder\data\resource_pack\assets\NAMESPACE\sounds\music_disc\cdk_sunday.ogg`

### Шаг 2

* открыть папку **plugins\ItemsAdder\data\resource\_pack\assets**
* откройте папку **пространство имен**.
* создайте новый файл с именем `sounds.json` (или откройте его, если он уже создан)
* этот файл является json-файлом, вы ДОЛЖНЫ написать его правильно, иначе он не будет работать. Если вам нужна информация о файлах Json, пожалуйста, поищите в Интернете.

Чтобы добавить свой звук в файл, нужно сделать следующее:

```javascript
{
	"music_disc.cdk_sunday":{
		"sounds":[
			"myitems:music_disc/cdk_sunday"
		]
	}
}
```

Теперь я объясню каждую часть кода, который я написал.\
Это название звука, вы будете использовать его в каждой части плагина, а также в Minecraft vanilla [/playsound ](https://www.digminecraft.com/game\_commands/playsound\_command.php)

```javascript
"music_disc.cdk_sunday":{
```

Это список звуковых файлов, которые Minecraft будет воспроизводить, когда вы вызовете название звука.\
Minecraft будет воспроизводить один из этих звуков случайным образом (только если вы задали более одного звука).\
⚠️ Помните, что вы должны изменить `myitems` на ваше собственное имя пространства имен.

```javascript
"sounds":[
			"myitems:music_disc/cdk_sunday"
		]
```

Например, если вы хотите иметь случайные звуки для одного и того же имени звука, вам просто нужно создать несколько файлов .ogg и разместить их следующим образом:

```javascript
"sounds":[
			"myitems:music_disc/cdk_sunday_1",
			"myitems:music_disc/cdk_sunday_2",
			"myitems:music_disc/test_file"
		]
```

## Как добавить несколько звуков в файл sounds.json?

Это просто, в следующий раз, когда вы захотите добавить звук, просто добавьте запятую в конце, вот так.\
(Я имею в виду запятую в строке 6)

```javascript
{
    "music_disc.cdk_sunday":{
        "sounds":[
            "itemsadder:music_disc/cdk_sunday"
        ]
    },
    "music_disc.vidian_aether_theories":{
        "sounds":[
            "itemsadder:music_disc/vidian_aether_theories"
        ]
    }
}
```

{% hint style="warning" %}
Если вы хотите не ошибиться, воспользуйтесь этим сайтом, чтобы проверить, хорош ли ваш Json-файл или в нем есть ошибки: [https://jsonformatter.curiousconcept.com/](https://jsonformatter.curiousconcept.com/)
{% endhint %}
