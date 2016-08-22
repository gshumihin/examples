# Examples
1. [Basic (url) rules](#basic-rules)
  * [Options](#options)
 	  * [Базовые параметры](#basic-rule-modifiers)
    * [Параметры для правил-исключений](#exception-rules-modifiers)
    * [Replace rules](#advanced-modifiers)
    * [RegExp rules](#regexp-support)
2. [Elemhide](#Elemhide)
3. [CSS-injections](#css-injections)
4. [JS rules](#javascript-rules)
5. [HTML filtering rules](#html-filtering-rules)


## Basic rules

Так называемые _"Основные правила"_ - самый простой вид правил. Эти правила предназначены для блокировки запросов на определенный URL. 
Основной принцип для этого типа правил достаточно прост: необходимо указать адрес, где необходимо убрать рекламу + дополнительные параметры.
В общем виде правило будет выглядеть следующим образом:

#### Syntax

```
rule = [@@] pattern [ "$" modifiers ]
modifers = ....
```

* pattern - паттерн состоит из URL-адреса и необязательных специальных символов. Возможные символы и их описание приведены [ниже](#pattern-special-chars)
* @@ - модификатор, который используется для обозначения правил-исключений. С такого модификатора должны начинаться правила, отключающие фильтрацию.
* modifiers - Параметры, используемые для "уточнения" общего правила. Параметр начинается с символа "`$`".

#### Pattern special chars

* `||` - Domain name anchor. Указывается перед URL-адресом, где будет блокироваться реклама. Позволяет не указывать все поддомены, на которых необходимо заблокировать рекламу. 
* `*` - Wildcard character. Просто символ, обозначающий "произвольный набор символов"
* `^` - указатель для разделительного символа
* `|` - указатель на конец адреса. Например, правило `swf|` будет блокировать `http://example.com/annoyingflash.swf` , но не `http://example.com/swf/index.html` .

_Examples:_

* `||example.com/ads/*`  - самое простое правило, которое просто блокирует запрос на URL. В данном случае по указанному адресу хранятся картинки.

* `@@||example.com$document` - наиболее общее правило-исключение. Именно это правило отключает всю возможную фильтрацию на example.com и всех поддоменах. Есть ряд параметров, которые так же можно использовать в правилах-исключения. Более подробно о правилах-исключениях и параметрах, которые могут в таких правилах использоваться, написано [ниже](#exception-rules-modifiers).
___

### Options

TBD: добавить текст про доп. параметры, еще пара слов про комменты


### Basic rule modifiers

TBD: text about

#### Syntax

```
rule = pattern [ "$" modifiers ]
modifiers = ....
```

**domain**

TBD: текст

_Examlple:_

TBD: example

**third-party**

TBD: текст

_Examlple:_

TBD: example

**popup**

TBD: текст

_Examlple:_

TBD: example

**match-case**

TBD: текст

_Examlple:_

TBD: example

**image**

TBD: текст

_Examlple:_

TBD: example

**image**

TBD: текст

_Examlple:_

TBD: example

**stylesheet**

TBD: текст

_Examlple:_

TBD: example

**xmlhttprequest**

TBD: текст

_Examlple:_

TBD: example

**empty**

TBD: текст

_Examlple:_

TBD: example

**mp4**

TBD: текст

_Examlple:_

TBD: example

### Exception rules modifiers

TBD: text about this shit

#### Syntax

```
rule = [@@] pattern [ "$" modifiers ]
modifiers = ....
```

**elemhide**

TBD: текст

_Examlple:_

TBD: example

**content**

TBD: текст

_Examlple:_

TBD: example

**jsinject**

TBD: текст

_Examlple:_

TBD: example

**urlblock**

TBD: текст

_Examlple:_

TBD: example

**document**

TBD: текст

_Examlple:_

TBD: example

**generichide**

TBD: текст

_Examlple:_

TBD: example

**genericblock**

TBD: текст

_Examlple:_

TBD: example

### RegExp support

TBD: text about RegExp

#### Syntax

```
rule = [@@] pattern [RegExp]
```

_Exaple:_

### Advanced modifiers

TBD: text about *replace*

#### Syntax

```
rule = pattern [ "$" replace ]
```
_Example:_

TBD: примерчик


### Elemhide

TBD: Some words about elemhide rules

#### Syntax

```
rule = pattern
```

Pattern can include:

* `#`
* `.`
* `||URL`
* `~`

**About domains and elemhiding**

TBD: text

_Example:_

```
||example.com##textad
```

More examples [here](http://gshumihin.github.io/examples/filterrules/02_Elemhide.html#)


### CSS-injections

TBD: текст про вот это вот все

#### Syntax

```
rule = pattern { options }
```

**Pattern:**

* URL
* special chars

**Options:**

TBD: some text about options

_Example:_

```
example.com#@$#body { background-color: #333!important; }
```

### Javascript rules

TBD: text about it

#### Syntax

```
rule = pattern [ "$" (js-code) ]
```

* patten
* `@` usage (for exception js-rules)

_Example:_

```
example.com#%#$('#somebanner').remove();
```


### HTML filtering rules

TBD: text

#### Syntax

```
rule = pattern [ attribute ]
attribute = ....
```

_Example:_

TBD: example

#### Attributes

**loaded-script**

TBD: text

_Example_

TBD: example

**max-length**

TBD: text

_Example_

TBD: example

**min-length**

TBD: text

_Example_

TBD: example

**parent-elements**

TBD: text

_Example_

TBD: example

**parent-search-level**

TBD: text

_Example_

TBD: example