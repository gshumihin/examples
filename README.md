## examples
1. [Basic (url) rules](http://gshumihin.github.io/examples/filterrules/01_basic_rules.html)
 * [Blocking](http://gshumihin.github.io/examples/filterrules/01_basic_rules.html)
 * [Exceptions](http://gshumihin.github.io/examples/filterrules/01_2_Exceptions.html)
 * [Options](#options)
 	* [old $](#Основные-параметры)
    * [$image, $stylesheet, $xmlhttprequest](#Параметры-image-stylesheet-xmlhttprequest)
    * [$empty](#Параметр-empty)
    * $popup
    * [$mp4](#Параметр-mp4)
  * $replace rules
  * [RegExp rules](#Использование-регулярных-выражений)
2. [Elemhide](http://gshumihin.github.io/examples/filterrules/02_Elemhide.html)
3. [CSS-injections](#css-injections)
4. [JS rules](#Правила-для-вставки-javascript-кода)
5. [HTML filtering rules](#Правила-фильтрации-html-кода)


#### Options
---

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


### Параметры image stylesheet xmlhttprequest
<ul>
	<li>
		<tt>image</tt> - позволяет блокировать загрузку картинок. Например, правило <code>||example.com$image</code> будет блокировать загрузку всех картинок на домене <code>example.com</code> 
			<br>С помощью параметра <code>$image</code>  можно, наоборот, разблокировать показ всех картинок. 
			<br><code>@@||exmple.ru/mainpage$image</code> - такое правило разблокирует загрузку картинок на странице <code>http://example.ru/mainpage</code>
	</li>
	<li>
		<tt>stylesheet</tt> - позволяет бловировать загрузку css-стилей. Например, правило <code>||example.com$stylesheet</code> будет блокировать загрузку всех стилей на домене example.com. 
		<br>А правило <code>@@||exmple.com$stylesheet</code> наоборот, разблокирует загрузку заблокированных другими правилами стилей.
	</li>
	<li>
		<tt>xmlhttrequest</tt> - блокирует xmlhttpsrequest-запрос (запрос, который браузер загружает без обновления страницы). Такими запросами зачастую пользуются интернет-магазины при применении выбранных вами фильтров. 
			 <br>Представим, что на домене <code>example.com</code> расположен интернет магазин, и одним из правил нарушена работа фильтров в этом магазине. Правило <code>@@||example.com^*$xmlhttprequest</code> позволит восстановить корректную работу сайта в таком случае.
	</li>
</ul>


### Параметр empty
<p>
	<b>TBD</b>
</p>


### Параметр mp4
<p>
	<b>TBD</b>
</p>

### Использование регулярных выражений

Если вы хотите еще большей гибкости при составлении правил, вы можете использовать регулярные выражения. Например, фильтр /banner\d+/ подойдет для banner123 или banner321, но не для banners.

Важно: с точки зрения производительности рекомендуется по возможности избегать использования регулярных выражений.


### Основные параметры

<p>Типы параметров:</p>
<ul class="param-types">
<li>
<tt>domain</tt> &mdash;&nbsp;ограничивает действия правила списком доменов. Параметр <tt>domain=example.ru</tt>
означает, что правило
должно быть применено только на&nbsp;страницах домена <tt>"example.ru"</tt>. Множество доменов можно установить,
используя &laquo;|&raquo; как разделитель:
с&nbsp;параметром <tt>domain=example.ru|example.net</tt> правило будет применяться только на&nbsp;страницах доменов
<tt>"example.ru"</tt> или <tt>"example.ru"</tt>.
Если доменное имя начинается с &laquo;~&raquo;, правило не&nbsp;должно применяться на&nbsp;страницах этого домена. Например, <tt>domain=~example.ru</tt>
показывает,
что правило должно применяться на&nbsp;страницах любого домена, кроме <tt>"example.ru"</tt>.
А <tt>domain=example.ru|~foo.example.ru</tt> ограничивает правило доменом <tt>"example.ru"</tt> исключая
поддомен <tt>"foo.example.ru"</tt>.
</li>
<li>
<tt>third-party</tt> &mdash;&nbsp;ограничение на&nbsp;сторонние/собственные запросы. Если указан параметр
<tt>third-party</tt>, то&nbsp;правило применяется лишь
к&nbsp;запросам ресурсов из&nbsp;внешних источников. Аналогично, <tt>~third-party</tt> ограничивает правило запросами
из&nbsp;того&nbsp;же источника,
что и&nbsp;открытая страница. Приведем пример. Правило <tt>||domain.com$third-party</tt> применяется на&nbsp;всех
сайтах кроме самого <tt>domain.com</tt>.
Если переписать его как <tt>||domain.com$~third-party</tt>, то&nbsp;оно будет применяться только на&nbsp;самом <tt>domain.com</tt>,
но&nbsp;не&nbsp;на&nbsp;других сайтах.
</li>
<li>
<tt>popup</tt> &mdash;&nbsp;Adguard будет пытаться закрыть браузерную вкладку для
любого адреса, который подходит под правило с&nbsp;этим модификатором.
</li>
<li>
<tt>match-case</tt> &mdash;&nbsp;определяет правило, которое применяется только к&nbsp;адресам с&nbsp;совпадением регистра букв,
например правило
<tt>*/BannerAd.gif$match-case</tt> будет блокировать <tt>http://example.com/BannerAd.gif</tt>, но&nbsp;не <tt>http://example.com/bannerad.gif</tt>.
По-умолчанию регистр символов не&nbsp;учитывается.
</li>
<li>
<tt>elemhide</tt> &mdash;&nbsp;<em>этот параметр имеет смысл указывать только для правил-исключений</em>. Запрещает
правила сокрытия элементов на&nbsp;страницах,
подходящих под правило. О&nbsp;правилах сокрытия элементов речь пойдет ниже.
</li>
<li>
<tt>content</tt> &mdash;&nbsp;<em>этот параметр имеет смысл указывать только для правил-исключений</em>. Запрещает
правила фильтрации HTML-элементов на&nbsp;страницах,
подходящих под правило. О&nbsp;правилах фильтрации HTML-элементов речь пойдет ниже.
</li>
<li>
<tt>jsinject</tt> &mdash;&nbsp;<em>этот параметр имеет смысл указывать только для правил-исключений</em>. Запрещает
добавление javascript-кода на&nbsp;страницу.
Javascript-код добавляется для блокировки баннеров по&nbsp;размерам, а&nbsp;также для работы &laquo;помощника Adguard&raquo;.
</li>
<li>
<tt>urlblock</tt> &mdash;&nbsp;<em>этот параметр имеет смысл указывать только для правил-исключений</em>. Запрещает
блокировку запросов, отправленных со&nbsp;страниц подходящих под это правило.
</li>
<li>
<tt>document</tt> &mdash;&nbsp;<em>этот параметр имеет смысл указывать только для правил-исключений</em>.
Полностью запрещает фильтрацию на&nbsp;страницах, подходящих под правило.
Эквивалентно одновременному использованию модификаторов <tt>elemhide</tt>, <tt>content</tt>, <tt>urlblock</tt> и <tt>jsinject</tt>.
</li>
</ul>
<p>
<em>Если у&nbsp;вас со&nbsp;включенной защитой страница открывается неправильно, или не&nbsp;работает какой-то функционал,
попробуйте создать для нее</em>
<em>правило-исключение вида <tt>||domain.com$documet</tt>. В&nbsp;случае, если ошибка
связана с&nbsp;фильтрацией контента страницы&nbsp;&mdash; она должна исчезнуть.</em>
</p>



### css injections

Иногда нам недостаточно просто скрыть какой-либо элемент, чтобы заблокировать рекламу. Например, блокировка рекламного элемента может просто сломать верстку сайта. Для таких случаев Adguard позволяет использовать гораздо более гибкие правила, чем обычные правила сокрытия.

С помощью правил вставки CSS-стилей, вы сможете добавить на любой сайт любой CSS-стиль.

Рассмотрим пример подобного правила: <code>example.com#$#body</code> <code>{ background-color: #333!important; }</code>. Это правило означает, что в код всех страниц <code>example.com</code> будет добавлен новый CSS-стиль: <code>body { background-color: #333!important; }</code>.

Обратите внимание, что правила вставки CSS-стилей поддерживают синтаксис для ограничения правил определенными доменами, аналогично [правилам сокрытия контента](http://gshumihin.github.io/examples/filterrules/02_Elemhide.html).

### Исключения для правил для вставки CSS-стилей

По аналогии с правилами сокрытия контента, существует возможность «выключить» отдельные правила вставки CSS-стилей. Например, правило <code>#$#body { background-color: #333!important; }</code> можно выключить на домене <code>example.com</code>, добавив исключение <code>example.com#@$#body { background-color: #333!important; }</code>.

Важно, чтобы тексты правил после маркеров <code>#@$#</code> и <code>#$#</code> должны полностью совпадать.

Применять такие исключения рекомендуется только в случае, когда изменить само правило вставки CSS-стилей не представляется возможным. Во всех остальных случаях лучше изменить само правило.




### Правила для вставки javascript-кода

Adguard поддерживаем специальный тип правил, позволяющий вставить любой javascript-код на страницы интернет-сайтов.

Рассмотрим пример подобного правила: <code>example.com#%#$('#somebanner').remove();</code>. Это правило означает, что в код всех страниц сайта <code>example.com</code> будет добавлен javascript-код:

</p>
<span class="code">
<pre class="code-rule">
<tt><span class="code-tag">&lt;script type="text/javascript"&gt;</span>
    <span class="code-quote">$('#somebanner').remove();</span>
<span class="code-tag">&lt;/script&gt;</span></tt>
</pre>
</span>
Обратите внимание, что правила вставки javascript-кода поддерживают синтаксис для ограничения правил определенными доменами, аналогично правилам сокрытия контента.




### Правила фильтрации html кода

<p>
В&nbsp;большинстве случаев достаточно перечисленных правил. Но&nbsp;иногда для фильтрации
рекламы необходимо изменять HTML-код самой страницы.
Для того, чтобы сделать это применяются правила фильтрации HTML-контента.
Они позволяют указать, какие HTML-элементы необходимо вырезать
из&nbsp;страницы перед тем как отдать ее&nbsp;браузеру.
</p>
<p>Рассмотрим следующий пример кода страницы.</p>
<span class="code">
<pre class="code-rule">
<tt><span class="code-tag">&lt;script type=<span class="code-quote">"text/javascript"</span>&gt;</span>
    document.write('<span class="code-tag">&lt;div&gt;</span>Покупайте пельмешки <span class="code-tag">&lt;a href=<span class="code-quote">"http://pelmeshki.com"</span>&gt;</span>Здесь!<span class="code-tag">&lt;/a&gt;</span><span class="code-tag">&lt;/div&gt;</span>" /&gt;');
<span class="code-tag">&lt;/script&gt;</span></tt>
</pre>
</span>
<p>
В&nbsp;данном случае рекламный слоган появляется на&nbsp;странице не&nbsp;сразу, а&nbsp;после загрузки страницы. Для вывода
используется Javascript.
Используя первые два вида правил мы&nbsp;ничего сделать не&nbsp;можем. Тут нам на&nbsp;помощь и&nbsp;приходят правила фильтрации
HTML-контента.
Для того, чтобы избавиться от&nbsp;рекламы, нам нужно вырезать из&nbsp;страницы весь элемент <tt>script</tt>. Но&nbsp;все
элементы <tt>script</tt>
вырезать нельзя&nbsp;&mdash; они могут быть нужны для работы сайта. Используем следующее правило:
</p>
<span class="code">
<pre class="code-rule"><tt>$$script[type=<span class="code-quote">"text/javascript"</span>][tag-content=<span class="code-quote">"pelmeshki.com"</span>]</tt></pre>
</span>
<p>
Это правило расшифровывается следующим образом: удаляются все элементы <tt>script</tt>, атрибут <tt>type</tt>
которых равен <tt>text/javascript</tt>,
а&nbsp;внутри элемента встречается строка <tt>pelmeshki.com</tt>.
</p>
<p>
Но&nbsp;это правило достаточно общее, и, если применять его ко&nbsp;всем сайтам,
мы&nbsp;можем нарушить их&nbsp;работоспособность. Для этого вы&nbsp;можете ограничить
применение правила выбранными сайтами. Ограничение на&nbsp;домены выглядит также,
как и&nbsp;для правил сокрытия элементов.
То&nbsp;есть, правило
<tt>example.com,~foo.example.com$$script[type="text/javascript"][tag-content="pelmeshki.com"]</tt>
будет применено только для сайта <tt>example.com</tt>,
исключая его поддомен <tt>foo.example.com</tt>.
</p>
</div>
<div class="tour-item">
<a name="htmlFilterAdvancedAttributes"></a>
<h3>Дополнительные атрибуты правил фильтрации HTML</h3>
<p>
Правила фильтрации HTML-элементов могут быть расширены за&nbsp;счет применения дополнительных атрибутов.
Список этих атрибутов приведен ниже.
</p>
<ul class="param-types">
<li>
<tt>loaded-script</tt> &mdash;&nbsp;позволяет применять правило не&nbsp;только к&nbsp;элементам <tt>script</tt>
на&nbsp;странице, но&nbsp;также и&nbsp;к&nbsp;подгружаемым скриптам. Иногда это необходимо, так как скрипты рекламных
сетей хранят в&nbsp;закриптованном виде на&nbsp;самом сайте. Пример такого правила:
<tt>$$script[tag-content="crypted script"][loaded-script="true"]</tt>. Важно, чтобы правило,
применяемое к&nbsp;подгружаемым скриптам, не&nbsp;содержало никаких атрибутов кроме: <tt>tag-content, loaded-script,
max-length, min-length</tt>.
</li>
<li>
<tt>max-length</tt> &mdash;&nbsp;задает максимальную длину содержимого HTML-элемента. Если этот параметр задан,
и&nbsp;длина содержимого превышает заданное значение&nbsp;&mdash; правило не&nbsp;применяется к&nbsp;элементу.
</li>
<li>
<tt>min-length</tt> &mdash;&nbsp;задает минимальную длину содержимого HTML-элемента. Если этот параметр задан,
и&nbsp;длина содержимого меньше заданного значения&nbsp;&mdash; правило не&nbsp;применяется к&nbsp;элементу.
</li>
<li>
<tt>parent-elements</tt> &mdash;&nbsp;очень важный атрибут. Он&nbsp;сильно изменяет&nbsp;то, как работает это правило. Суть
в&nbsp;том, что вырезается теперь не&nbsp;тот элемент, который найден, а&nbsp;заданный родительский элемент. Рассмотрим
пример:
<span class="code">
<pre class="code-rule">
<tt><span class="code-tag">&lt;table style="background: url(<span class="code-quote">'http://domain.com/banner.gif'</span>)"&gt;</span>
    <span class="code-tag">&lt;tr&gt;</span>
        <span class="code-tag">&lt;td&gt;</span>
            <span class="code-tag">&lt;a href=<span class="code-quote">"http://pelmeshki.com"</span>&gt;</span>Купил пельмешки БЫСТРО<span class="code-tag">&lt;/a&gt;</span>
        <span class="code-tag">&lt;/td&gt;</span>
    <span class="code-tag">&lt;/tr&gt;</span>
<span class="code-tag">&lt;/table&gt;</span></tt>
</pre>
</span>
Проблема этого HTML-кода в&nbsp;том, что нам недостаточно вырезать ссылку на&nbsp;рекламу. Сам баннер показывается с
помощью родительской таблицы (как ее&nbsp;background).
Тут нам и&nbsp;приходит на&nbsp;помощь атрибут <tt>parent-elements</tt>. Мы&nbsp;используем вот такое правило, чтобы
заблокировать всю таблицу:
<tt>$$a[href="pelmeshki.com"][parent-elements="table"]</tt>. Когда Adguard найдет на&nbsp;странице ссылку на
&laquo;pelmeshki.com&raquo;, вместо того, чтобы вырезать ее -
он&nbsp;будет искать ближайший родительский элемент <tt>table</tt>, и, если найдет&nbsp;&mdash; вырежет его. Вы&nbsp;можете
указать несколько искомых родительских элементов через
запятую. Заблокирован будет ближайший.
</li>
<li>
<tt>parent-search-level</tt> &mdash;&nbsp;задает максимальную глубину поиска родительского элемента. По&nbsp;умолчанию
максимальная глубина поиска равна <tt>3</tt>.
Это сделано для того, чтобы не&nbsp;вырезать лишнего, если HTML страницы поменяется. Не&nbsp;ставьте слишком большие
значения для этого атрибута.
</li>

