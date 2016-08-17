# Examples
1. [Basic (url) rules](#basic-rules)
 * [Blocking](#url-blocking)
 * [Exceptions](#exceptions)
 * [Options](#options)
 	* [old $](#Основные-параметры)
    * [Базовые параметры](#basic-rule-modifiers)
    * [Параметры для правил-исключений](#exception-rules-modofiers)
    * $[Replace rules](#advanced-modifiers)
    * [RegExp rules](#regexp-support)
2. [Elemhide](http://gshumihin.github.io/examples/filterrules/02_Elemhide.html)
3. [CSS-injections](#css-injections)
4. [JS rules](#Правила-для-вставки-javascript-кода)
5. [HTML filtering rules](#Правила-фильтрации-html-кода)


## Basic rules

TBD: some text

#### Syntax

```
rule = [@@] pattern [ "$" modifiers ]
modifers = ....
```

* pattern - описалово
* @@ - описалово
* modifiers - что это такое

#### Pattern special chars

* `||`
* `*`
* `^`
* `|`


### Url blocking

TBD: add some text about it 

#### Syntax

```
rule = pattern
```

Where pattern = URL to block

_Example:_

`http://example.com/ads/banner1.jpg`

Больше примеров [тут](http://gshumihin.github.io/examples/filterrules/01_basic_rules.html)


### Exceptions

TBD: скопипастить сюда тексты

#### Syntax

```
rule = [@@] pattern [ "$" modifiers ]
```

* `@@` описалово
* `pattern` - что тут может быть
* `modifiers` дать список модифаеров, более детальная инфа [тут](#exception-rules-modifiers)

_Example:_

```
||@@example.com/pics
```

More examples [here](http://gshumihin.github.io/examples/filterrules/01_2_Exceptions.html)

### Options

TBD: добавить текст про доп. параметры, еще пара слов про комменты


### Basic rule modifiers

TBD: text about

#### Syntax

```
rule = pattern [ "$" modifiers ]
modifiers = ....
```

*domain*

TBD: текст

_Examlple:_

TBD: example

*third-party*

TBD: текст

_Examlple:_

TBD: example

*popup*

TBD: текст

_Examlple:_

TBD: example

*match-case*

TBD: текст

_Examlple:_

TBD: example

*image*

TBD: текст

_Examlple:_

TBD: example

*image*

TBD: текст

_Examlple:_

TBD: example

*stylesheet*

TBD: текст

_Examlple:_

TBD: example

*xmlhttprequest*

TBD: текст

_Examlple:_

TBD: example

*empty*

TBD: текст

_Examlple:_

TBD: example

*mp4*

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

*elemhide*

TBD: текст

_Examlple:_

TBD: example

*content*

TBD: текст

_Examlple:_

TBD: example

*jsonjext*

TBD: текст

_Examlple:_

TBD: example

*urlblock*

TBD: текст

_Examlple:_

TBD: example

*document*

TBD: текст

_Examlple:_

TBD: example

*generichide*

TBD: текст

_Examlple:_

TBD: example

*genericblock*

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
