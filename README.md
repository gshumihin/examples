## examples
1. [Basic (url) rules](http://gshumihin.github.io/examples/filterrules/01_basic_rules.html#)
 * [Blocking](http://gshumihin.github.io/examples/filterrules/01_basic_rules.html#)
 * [Exceptions](http://gshumihin.github.io/examples/filterrules/01_2_Exceptions.html#)
 * [Options](#options)
    * $image, $stylesheet, $xmlhttprequest
    * $empty
    * $popup
    * $mp4
  * $replace rules
  * RegExp rules
2. [Elemhide](http://gshumihin.github.io/examples/filterrules/02_Elemhide.html#)
3. CSS injections
4. JS rules
5. HTML filtering rules

#### Options

Соответствие началу/концу адреса

Обычно Adguard обрабатывает каждое правило так, как если бы оно имело символ обобщения * в начале и в конце. Например, нет разницы между правилами ad и &#42;ad&#42;. Обычно это не является проблемой, но иногда вы можете захотеть, чтобы ваше правило соответствовало в начале или в конце адресов. Например, вы можете захотеть заблокировать весь Flash, но если вы добавите правило swf, адрес <code>http://example.ru/swf/index.html</code> также будет заблокирован.

Решение проблемы: добавьте к правилу символ <code>|</code>, чтобы показать, что конец адреса находится в этой точке. Например, правило <code>swf|</code> будет блокировать <code>http://example.ru/annoyingflash.swf</code> , но не <code>http://example.ru/swf/index.html</code>. А правило <code>|http://baddomain.example/</code> будет блокировать <code>http://baddomain.example/banner.gif</code> , но не <code>http://gooddomain.example/analyze?http://baddomain.example</code>.

Иногда нужно заблокировать не только <code>http://domain.ru</code>, но и <code>http://www.domain.ru</code>, или <code>http://adv.domain.ru</code>. Это может быть достигнуто добавлением двух символов <code>|</code> в начало правила, который соответствует началу доменного имени: <code>||example.com/banner.gif</code> будет блокировать все эти адреса, но не тронет <code>http://gooddomain.ru/banner.gif</code> или <code>http://gooddomain.ru/analyze?http://domain.ru/banner.gif</code>.

Разделительные символы

Часто вам нужно будет применить в правиле любой разделительный символ. Например, вы можете написать правило, которое блокирует <code>http://domain.com/</code> , но не <code>http://domain.com.ua/</code>. Здесь символ <code>^</code> может быть использован как указатель для одного разделительного символа: <code>http://domain.com^</code>.

Разделитель — это любой символ кроме букв, цифр или одного из следующих символов: <code>— . %</code>, а также это может быть конец адреса. 

Комментарии

Любое правило, начинающееся с восклицательного знака содержит комментарий. Оно отображается в списке правил серым цветом. Adguard будет игнорировать это правило при блокировании, так что можете спокойно писать там всё, что хотите. Вы можете, например, расположить комментарий выше реального правила, чтобы описать для чего оно нужно.

Расширенные возможности

Возможности, описанные в этом разделе, обычно используются опытными пользователями. Они расширяют возможности «Общих правил», но для их применения необходимо иметь начальное представление о работе браузера.

Вы можете изменить поведение «общего правила», используя дополнительные параметры. Список этих параметров располагается в конце правила за знаком доллара $ и разделяется запятыми. Например:

<code>||domain.ru$match-case,third-party</code>.
Здесь <code>||domain.ru</code> - это само правило, а <code>match-case</code> и <code>third-party</code> - его параметры.
