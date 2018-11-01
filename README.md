# examples
<p>Цели поиска внешней фермы:</p>
<ul>
  <li>точечное использование устройств, которых нет в штабе для ручных тестов и воспроизведения проблем пользователей</li>
  <li>использование устройств/эмуляторов для автотестирования в случае экономической целесообразности</li>
</ul>
<p>Драйвер - <ac:link>
    <ri:user ri:userkey="8ac0a2185d7f7ef4015d82efd88e0003"/>
  </ac:link>
</p>
<ac:task-list>
<ac:task>
<ac:task-id>1</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Подготовка и формализация критериев, согласно которым будут оцениваться облачные фермы. Приведение данных в формат таблицы.<ac:task-list>
<ac:task>
<ac:task-id>2</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Формирование списка критериев.</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>3</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Формирование списка сервисов.</ac:task-body>
</ac:task>
</ac:task-list>
    </ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>4</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Сбор и внесение в таблицу данных по наиболее важным критериям (согласно решению, принятому совместно с <ac:link>
        <ri:user ri:userkey="2c91c78b4c93be86014c93f29db70002"/>
      </ac:link>, это будут списки устройств и возможность запуска эмуляторов).<ac:task-list>
<ac:task>
<ac:task-id>5</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Сбор информации по командам, какие устройства являются наиболее необходимыми.</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>6</ac:task-id>
<ac:task-status>complete</ac:task-status>
<ac:task-body>Ранжирование сервисов в таблице в порядке удовлетворения требованиям, полученным на предыдущем этапе.</ac:task-body>
</ac:task>
<ac:task>
<ac:task-id>8</ac:task-id>
<ac:task-status>incomplete</ac:task-status>
<ac:task-body>Сбор и внесение в таблицу данных по прочим критериям.</ac:task-body>
</ac:task>
</ac:task-list>
    </ac:task-body>
</ac:task>
</ac:task-list>
<p>
  <br/>
</p>
<table class="relative-table wrapped" style="width: 82.9402%;">
  <colgroup>
    <col style="width: 9.72866%;"/>
    <col style="width: 14.8908%;"/>
    <col style="width: 10.3905%;"/>
    <col style="width: 12.3097%;"/>
    <col style="width: 8.93448%;"/>
    <col style="width: 17.4719%;"/>
    <col style="width: 14.957%;"/>
    <col style="width: 11.317%;"/>
  </colgroup>
  <tbody>
    <tr>
      <th rowspan="2" style="text-align: center;">Название</th>
      <th colspan="3" style="text-align: center;">Информация об устройствах</th>
      <th rowspan="2" style="text-align: center;">Наличие эмулятора</th>
      <th colspan="2" style="text-align: center;">Цена</th>
      <th rowspan="2" style="text-align: center;">Комментарий</th>
    </tr>
    <tr>
      <th class="highlight-grey" colspan="1" data-highlight-colour="grey" style="text-align: center;">Общая информация</th>
      <th colspan="1" style="text-align: center;">Наличие специфичных устройств</th>
      <th colspan="1" style="text-align: center;">Наличие устройств, требущихся для нужд штаба</th>
      <th colspan="1" style="text-align: center;">Общие данные по цене</th>
      <th colspan="1" style="text-align: center;">Стоитмость автоматизации <span>при переводе </span>в облако</th>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">AWS Device Farm</span>
      </td>
      <td class="highlight-green" data-highlight-colour="green">355 устройств. 90% устройств - популярные (Nexus, Pixel, Samsung Galaxy S, Ipxones)</td>
      <td colspan="1">Есть. Но немного (5-10 шт)</td>
      <td colspan="1">Motorola Moto G4</td>
      <td style="text-align: center;">-</td>
      <td class="highlight-red" data-highlight-colour="red" style="text-align: center;">Есть три ценовых практики:<ul>
          <li>Оплата по факту использования - 0,17$ в минуту</li>
          <li>Неограниченное тестирование - от 250$ в месяц за устройство</li>
          <li>Частные устройства - от 200$ в месяц</li>
        </ul>
      </td>
      <td colspan="1">От 2500$ (за 10 слотов автотестирования) в месяц</td>
      <td colspan="1">Дорого</td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Firebase Test Lab</span>
      </td>
      <td class="highlight-green" data-highlight-colour="green">Приблизительно 200 устройст Только самые популярные модели самых распространенных производителей.</td>
      <td colspan="1">1-2 устройства, которых нет в штабе</td>
      <td colspan="1">Motorola Moto G4</td>
      <td style="text-align: center;">+</td>
      <td class="highlight-red" data-highlight-colour="red">
        <ul>
          <li>Бесплатно: 10 тестов в день на виртуальных устройствах, 5 тестов в день для физических устройств</li>
          <li>25$ в месяц: 10 тестов в день на виртуальных устройствах, 5 тестов в день для физических устройств</li>
          <li>1$ в день за виртуальное устройство в час/5$ за физическое устройство в час</li>
        </ul>
      </td>
      <td colspan="1">
        <ul>
          <li>От 1400$ за виртуальные устройства в месяц<br/>
            <br/>
          </li>
          <li>От 7000$ за физические устройства</li>
        </ul>
      </td>
      <td colspan="1">Сильно дорого</td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Testbirds</span>
      </td>
      <td class="highlight-green" data-highlight-colour="green">Заявлено более 200 тысяч физических устройств, по факту - <a href="https://confluence.kaspersky.com/pages/viewpage.action?spaceKey=Mobile&amp;title=TestBirds+Global+Real+Device+Network+devices">704</a> всего, в среднем доступно не более 30 устройств</td>
      <td colspan="1">более 10 устройств, которых нет в штабе, но 95% из них недоступны</td>
      <td colspan="1">MediaPad M3</td>
      <td style="text-align: center;">+</td>
      <td class="highlight-red" data-highlight-colour="red">
        <ul>
          <li>71 евро в месяц (1 слот, 500 минут)</li>
          <li>639 евро в месяц (4 слота, 4000 минут)</li>
          <li>2399 евро в месяц (8 сдлотов, 16000 минут)</li>
          <li>Enterprice (цена и условия по результатам общения с менеджером)</li>
        </ul>
      </td>
      <td class="highlight-red" colspan="1" data-highlight-colour="red">Дима, посчитай свои хотелки плз</td>
      <td colspan="1">
        <p>Высокая стоимость.</p>
        <p>Список доступных устройств непредсказуем, необходимое устройство может быть недоступно в нужный момент.</p>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Perfecto</span>
      </td>
      <td class="highlight-green" data-highlight-colour="green">Чуть более 3000 устройств, но это только самые популярные модели самых распространенных производителей.</td>
      <td colspan="1">На момент изучения устройств, отсутствующих в штабе замечено не было</td>
      <td colspan="1" style="text-align: center;">-</td>
      <td style="text-align: center;">-</td>
      <td class="highlight-red" data-highlight-colour="red">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <p>Не принесет никакой пользы для штаба:</p>
        <ul>
          <li>Нет эмулятора устройств;</li>
          <li>Очень узкий пулл устройств.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Kobiton</span>
      </td>
      <td class="highlight-green" data-highlight-colour="green">249 устройств. Только самые популярные.</td>
      <td colspan="1" style="text-align: center;">Небольшое количество устройств, котрых нет в штабе. В основном, эти устройства официально продаются на территории РФ.</td>
      <td colspan="1">Motorola Moto G4</td>
      <td style="text-align: center;">-</td>
      <td class="highlight-red" data-highlight-colour="red">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">Крайне мало устройств, нет эмулятора.</td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Experitest</span>
      </td>
      <td class="highlight-green" data-highlight-colour="green">Очень скромный список устройств (порядка 200), тольько самые популярные устройства.</td>
      <td colspan="1" style="text-align: center;">-</td>
      <td colspan="1" style="text-align: center;">-</td>
      <td style="text-align: center;">-</td>
      <td class="highlight-red" data-highlight-colour="red">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">Крайне мало устройств, нет эмулятора.</td>
    </tr>
    <tr>
      <td colspan="1">
        <span style="color: rgb(0,0,0);">Bitbar</span>
      </td>
      <td class="highlight-green" colspan="1" data-highlight-colour="green">300+ устройст, но только самые популярные.</td>
      <td colspan="1">Не более 5 устройств, отсутствующих в штабе</td>
      <td colspan="1">Motorola Moto G4</td>
      <td colspan="1" style="text-align: center;">-</td>
      <td class="highlight-red" colspan="1" data-highlight-colour="red">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">Крайне мало устройств, нет эмулятора.</td>
    </tr>
  </tbody>
</table>
<p>
  <br/>
</p>
<p>Ориентировачная нагрузка на устройства в день от одного проекта - 10 часов(BVT, Accept, Regress, отладка, снятие скриншотов) </p>
<p>Минимальный бюджет - 2500$ в месяц без учета нужд ручного тестирования. Считаю, что использование устройств в облаке для нужд автотестирования не целесообразно. Необходимо развивать внутреннюю ферму.</p>
<p>
  <br/>
</p>
<p>Сводная таблица с информацией по сервисам:</p>
<table class="fixed-table wrapped">
  <colgroup>
    <col style="width: 268.0px;"/>
    <col style="width: 188.0px;"/>
    <col style="width: 186.0px;"/>
    <col style="width: 134.0px;"/>
    <col style="width: 95.0px;"/>
    <col style="width: 324.0px;"/>
    <col style="width: 146.0px;"/>
    <col style="width: 76.0px;"/>
    <col style="width: 100.0px;"/>
    <col style="width: 127.0px;"/>
    <col style="width: 98.0px;"/>
    <col style="width: 91.0px;"/>
    <col style="width: 69.0px;"/>
  </colgroup>
  <tbody>
    <tr>
      <th rowspan="2" style="text-align: center;">Название сервиса</th>
      <th colspan="3" style="text-align: center;">Информация по устройствам</th>
      <th rowspan="2">Наличие эмулятора</th>
      <th rowspan="2">
        <h6>
          <span style="color: rgb(128,128,128);">Pricing</span>
        </h6>
      </th>
      <th rowspan="2">Ожидаемая стоимость в месяц при переводу автоматизации в облако</th>
      <th rowspan="2">
        <h6>Время отклика</h6>
      </th>
      <th rowspan="2">
        <h6>Дефолтное состояние устройств</h6>
      </th>
      <th rowspan="2">
        <h6>Встроенные возможности для автоматизации тестирования</h6>
      </th>
      <th rowspan="2">
        <h6>CI system support/api features</h6>
      </th>
      <th rowspan="2">
        <h6>Reporting, debug features</h6>
      </th>
      <th rowspan="2">
        <h6>STF Support</h6>
      </th>
    </tr>
    <tr>
      <th>Общая информация</th>
      <th>Устройства, отсутвующие в мобильном штабе</th>
      <th>Специфичные устройства, требующиеся командам</th>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">AWS Device Farm</span>
      </td>
      <td>
        <p>355 устройств:<br/>iPhone 4s - iPhone X;<br/>iPad 2 - iPad Pro 9.7";<br/>Nexus 5,6,7,10;<br/>Pixel, Pixel 2, Pixel XL, Pixel 2XL<br/>Samsung Galaxies (alot)</p>
        <p>Full device list: <a href="http://awsdevicefarm.info/">http://awsdevicefarm.info/</a>
        </p>
      </td>
      <td>Asus memo Pad 8<br/>
        <span style="color: rgb(68,68,68);">HTC One A9 (Unlocked)<br/>Lava Iris X8<br/>Motorola DROID Turbo<br/>Motorola DROID Ultra<br/>Motorola moto G (1-4 gen)<br/>etc</span>
      </td>
      <td>Motorola Moto G4</td>
      <td>
        <p>Отсутствует</p>
      </td>
      <td colspan="1">
        <a href="https://aws.amazon.com/ru/device-farm/pricing/">https://aws.amazon.com/ru/device-farm/pricing/</a>
        <br/>Есть три ценовых практики:<ul>
          <li>Оплата по факту использования - 0,17$ в минуту</li>
          <li>Неограниченное тестирование - от 250$ в месяц за 1 слот</li>
          <li>Частные устройства - от 200$ в месяц</li>
        </ul>
      </td>
      <td colspan="1">От 2500$ (за 10 слотов автотестирования)</td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Visual Studio App Center</span>
      </td>
      <td>ОТСУТСТВУЕТ РУЧНОЕ ТЕСТИРОВАНИЕ</td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Firebase Test Lab</span>
      </td>
      <td>Pretty poor device list:<br/>iphones 6s-x<br/>only nexuses, most popular samsung, sony, motorola and Lg models</td>
      <td>
        <br/>
      </td>
      <td>Motorola Moto G4</td>
      <td>+</td>
      <td colspan="1">
        <p>
          <a href="https://firebase.google.com/pricing/">https://firebase.google.com/pricing/</a>
          <br/>Есть три ценовых практики:</p>
        <ul>
          <li>Бесплатно: 10 тестов в день на виртуальных устройствах, 5 тестов в день для физических устройств</li>
          <li>25$ в месяц: 10 тестов в день на виртуальных устройствах, 5 тестов в день для физических устройств</li>
          <li>1$ в день за виртуальное устройство в час/5$ за физическое устройство в час</li>
        </ul>
        <p>
          <br/>
        </p>
      </td>
      <td colspan="1">
        <p>От 1400$ за виртуальные устройства из расчета 7 проектов по 10 часов в рабочие дни.</p>
        <p>От 7000$ за физические устройства из расчета 7 проектов по 10 часов в рабочие дни.</p>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Perfecto</span>
      </td>
      <td>More than 3000+ devices<br/>but most of them are typical one:<br/>iPhones 4-X<br/>iPads 2-pro (9.7)<br/>nexus 5,6,7,9<br/>Google Pixel<br/>Htc One (A9, M8, M9)<br/>Samsung Galaxy (Note, S3-9)Sony Xperia (Z1-5, M4)</td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td>Отсутствует</td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Sauce Labs</span>
      </td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Kobiton</span>
      </td>
      <td>
        <p>249 devices total<br/>All popular devices from samsung, LG, Motorola, Oneplus, Google, Huawei,Sony, HTC, Apple<br/>Devices Xiaomi, Meizu and others are not presented<br/>Full device list: <a href="https://docs.kobiton.com/devices-list/">https://docs.kobiton.com/devices-list/</a>
        </p>
      </td>
      <td>HTC U11<br/>Samsung Galaxy J7pro<br/>Motorola Moto G Plus<br/>Motorola Moto G4<br/>Blackberry KEYone<br/>Nokia 6<br/>etc</td>
      <td>Motorola Moto G4</td>
      <td>Отсутствует</td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <span style="color: rgb(0,0,0);">Experitest</span>
      </td>
      <td>Apple ipads, iphones (5-10)<br/>Samsung Galaxy S5-9<br/>Honor magic, P8 Lite<br/>HTC 10, A9, M9<br/>Nexus 5,5x,6p,6,7,9<br/>Pixel (only one)<br/>LG G5, V10, G3, V20, K10<br/>Couple Meizu, Xiaomi and other manufactureres models<br/>
        <a href="https://experitest.com/real-devices/">https://experitest.com/real-devices/</a>
      </td>
      <td>
        <br/>
      </td>
      <td>
        <br/>
      </td>
      <td>Отсутствует</td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td colspan="1">
        <span style="color: rgb(0,0,0);">Bitbar</span>
      </td>
      <td colspan="1">
        <p>Apple ipads, iphones (4s-10)<br/>Nexus (galaxy nexus-6p, tablets)<br/>Pixels: 1,2,XL (android 7-9)<br/>Alot of Samsung, LG, Motorola, HTC, huawei<br/>Few xiaomi, meizu and others</p>
        <p>
          <a href="https://cloud.bitbar.com/#public/devices">https://cloud.bitbar.com/#public/devices</a>
        </p>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">Motorola Moto G4</td>
      <td colspan="1">Отсутствует</td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <span style="color: rgb(0,0,0);">Testbirds</span>
        </p>
      </td>
      <td>Тут все сложнее, чем обычно: у них есть такая утилита, как Global Real Device Network Вот что она из себя представляет: The Global Real Device Network (GRDN) is a newly developed testing solution by testing provider Testbirds. The GRDN combines both crowd and cloud based testing principles. (See box Crowd and Cloud Based Testing.) The solution leverages the smart devices in a crowd of 200,000 testers in 193 countries to create remote testing possibilities. By connecting their Android smartphones and tablets, crowdtesters grant access to clients looking to test apps, websites and other software on real world mobile devices.</td>
      <td>
        <br/>
      </td>
      <td>
        <a href="https://www.testbirds.com/prices/prices-device-cloud/">https://www.testbirds.com/prices/prices-device-cloud/</a>
      </td>
      <td>+</td>
      <td colspan="1">
        <p>
          <a href="https://www.testbirds.com/prices/prices-device-cloud/">https://www.testbirds.com/prices/prices-device-cloud/<br/>
          </a>С доступом к реальным девайсам (GRDN) имеется только один вариант:<br/>71/639/2399 евро в месяц</p>
        <p>
          <span style="color: rgb(0,118,114);">Concurrent slots: </span>
          <strong>1/4/8</strong>
        </p>
        <p>
          <span style="color: rgb(0,118,114);">Real devices:<br/>
            <span>Manual &amp; Automated (minutes): 500/</span>
            <span>4000/16000</span>
          </span>
        </p>
        <p>
          <span style="color: rgb(0,118,114);">Virtual devices:</span>
        </p>
        <ul>
          <li>
            <span>Manual minutes: unlimited; </span>
          </li>
          <li>
            <span>Automated minutes: 0/8000/unlimited</span>
          </li>
        </ul>
        <p>
          <br/>
        </p>
        <p>
          <br/>
        </p>
        <p>Так же, можно купить enterprice, но на сайте нет конкретной информации, необходимо связываться с менеджерами тестбёрдс (<a href="https://www.testbirds.com/company/about-us/contact/">https://www.testbirds.com/company/about-us/contact/</a>).</p>
      </td>
      <td colspan="1">13000$ в месяц.</td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
      <td colspan="1">
        <br/>
      </td>
    </tr>
  </tbody>
</table>
<p>
  <br/>
</p>
<p>
  <br/>
</p>
