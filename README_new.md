# Examples
1. [Basic (url) rules](#Базовые-правила)
  * [Синтаксис](#Синтаксис)
    * [Pattern special characters](#Спецсимволы,-используемые-в-паттерне)
    * [Примеры](#Примеры)
  * [Модификаторы](#Модификаторы)
 	  * [Базовые модификаторы](#Базовые-модификаторы)
    * [Параметры для правил-исключений](#Модификаторы-правил-исплючений)
    * [Replace rules](#advanced-modifiers)
    * [RegExp rules](#regexp-support)
2. [Elemhide](#elemhide)
  * [Синтаксис](#syntax-2)
  * [Примеры](#examples-1)
3. [CSS-injections](#css-injections)
  * [Синтаксис](#syntax-3)
  * [Примеры](#examples-2)
4. [JS rules](#javascript-rules)
  * [Синтаксис](#syntax-4)
  * [Примеры](#examples-3)
5. [HTML filtering rules](#html-filtering-rules)
  * [Синтаксис](#syntax-5)
  * [Примеры](#examples-4)
  * [Атрибуты](#attributes)


##  Базовые правила

Так называемые _"Основные правила"_ - самый простой вид правил. Эти правила предназначены для блокировки запросов на определенный URL. 
Основной принцип для этого типа правил достаточно прост: необходимо указать адрес, где необходимо убрать рекламу + дополнительные параметры.
В общем виде правило будет выглядеть следующим образом:

### Синтаксис

```
rule = [@@] pattern [ "$" modifiers ]
modifers = $modifier1,modifier2, ...
```

* **pattern** - паттерн состоит из URL-адреса и необязательных специальных символов. Возможные символы и их описание приведены [ниже](#pattern-special-chars)
* **@@** - модификатор, который используется для обозначения правил-исключений. С такого модификатора должны начинаться правила, отключающие фильтрацию.
* **modifiers** - Параметры, используемые для "уточнения" общего правила. Параметр начинается с символа "`$`".

#### Спецсимволы, используемые в паттерне

* **`||`** - Domain name anchor. Указывается перед URL-адресом, где будет блокироваться реклама. Позволяет не указывать все поддомены, на которых необходимо заблокировать рекламу. 
* **`*`** - Wildcard character. Символ, обозначающий "произвольный набор символов"
* **`^`** - указатель для разделительного символа
* **`|`** - указатель на конец адреса. Например, правило `swf|` будет блокировать `http://example.com/annoyingflash.swf` , но не `http://example.com/swf/index.html` .

#### Примеры

* `||example.com/ads/*`  - самое простое правило, которое просто блокирует запрос на URL.

* `@@||example.com$document` - наиболее общее правило-исключение. Именно это правило отключает всю возможную фильтрацию на example.com и всех поддоменах. Есть ряд параметров, которые так же можно использовать в правилах-исключения. Более подробно о правилах-исключениях и параметрах, которые могут в таких правилах использоваться, написано [ниже](#exception-rules-modifiers).
___

### Модификаторы

_Возможности, описанные в этом разделе, обычно используются опытными пользователями. Они расширяют возможности «Общих правил», но для их применения необходимо иметь начальное представление о работе браузера._

Вы можете изменить поведение «общего правила», используя дополнительные модификаторы. Список этих параметров располагается в конце правила за знаком доллара `$` и разделяется запятыми. 
Например:
```
||domain.com$popup,third-party
```


#### Базовые модификаторы

Приведенные ниже модификаторы являются наиболее простыми (для понимания) и часто применяемыми. Они не могут быть использованы в правилах-исключениях.

**domain**

Модификатор `domain` ограничивает действия правила списком доменов. 
Для того, чтобы указать множество доменов в одном правиле, можно использовать символ `|` как разделитель.
Чтобы правило _не применялось_ на определенных доменах, перед доменным именем необходимо добавить символ `~`.


_Examlples:_

* `||baddomain.com/ads/banners*^$domain=example.com|example.ru` - блокировка контента на доменах `example.com` и `example.ru` 
* `||baddomain.com/ads*^$domain=~example.ru` - контент будет блокироваться на всех доменах, кроме `example.ru`
* `||baddomain.com/ads*^$domain=example.com|~foo.example.com` - в данном примере контент будет блокирвоаться на домене `example.com`, но не будет блокироваться на `foo.example.com`

**third-party**

Ограничение на сторонние/собственные запросы. Если указан модификатор `third-party`, то правило применяется лишь к запросам ресурсов из внешних источников.
`~third-party` ограничивает правило запросами из того же источника, что и открытая страница.

_Examlples:_

* `||domain.com$third-party` - правило применяется на всех сайтах, кроме самого `domain.com`
* `||domain.com$~third-party` - такое правило уже будет применяться только на самом `domain.com`, но не на других сайтах

**popup**

Adguard будет пытаться закрыть браузерную вкладку для любого адреса, который подходит под правило с этим модификатором.

_Examlples:_

* `||domain.com*^$popup` - при попытке перехода на сайт `http:\\domain.com` с любой страницы в браузере, новая вкладка, в которой должен открыться указанный сайт, будет закрыта  

**match-case**

Определяет правило, которое применяется только к адресам с совпадением регистра букв. По умолчанию регистр символов не учитывается.

_Examlple:_

* `*/BannerAd.gif$match-case` - такео правило будет блокировать `http://example.com/BannerAd.gif`, но не `http://example.com/bannerad.gif`.

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

#### Exception rules modifiers

Модификаторы, используемые только в правилах-исключениях.

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


## Elemhide

TBD: Some words about elemhide rules

### Syntax

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

### Examples

```
||example.com##textad
```

More examples [here](http://gshumihin.github.io/examples/filterrules/02_Elemhide.html#)


## CSS-injections

TBD: текст про вот это вот все

### Syntax

```
rule = pattern { options }
```

**Pattern:**

* URL
* special chars

**Options:**

TBD: some text about options

### Examples

```
example.com#@$#body { background-color: #333!important; }
```

## Javascript rules

TBD: text about it

### Syntax

```
rule = pattern [ "$" (js-code) ]
```

* patten
* `@` usage (for exception js-rules)

### Examples

```
example.com#%#$('#somebanner').remove();
```


## HTML filtering rules

TBD: text

### Syntax

```
rule = pattern [ attribute ]
attribute = ....
```

### Examples

TBD: example

### Attributes

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