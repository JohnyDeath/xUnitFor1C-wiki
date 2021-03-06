Скрипт <b>"Добавить описание тестовых случаев текущего модуля в метод ПолучитьСписокТестов - фреймворк xUnitFor1C"</b> (xUnitAddTestsDesc.js)

  *  Автор		: Артур Аюханов aka artbear

  *  Дата создания: 15.04.2014

Описание		: 

Скрипт позволяет дополнить модуль внешней обработки с набором тестов для  фреймворка xUnitFor1C</li>

Скрипт выполняет свою работу перед сохранением файла внешней обработки (т.е. полностью автоматизировано! )

Cейчас не нужно после написания определения метода/тестового случая (ТестДолжен_ПроверитьПроведениеДокументаПКОпоРегиструБухгалтерии) не нужно вставлять описание этого метода в спец.функцию.

Если в модуле с набором тестов есть тестовые случаи (экспортные процедуры без параметров, имя которых начинается на Тест, например, ТестДолжен_ПроверитьПроведениеДокументаПКОпоРегиструБухгалтерии), то в специальную функцию "ПолучитьСписокТестов" выполняется автовставка описания этих тестовых случаев.

<b>Тесты становится писать еще проще и быстрее.</b>

Также возможна работа по макросу - <b>"Вставить определения тестовых случаев xUnitFor1C"</b>

<li> Например, есть следующий модуль:

	Процедура ТестДолжен_ПроверитьПроведениеДокументаПКОпоРегиструБухгалтерии() Экспорт

		ВызватьИсключение "Тест не реализован";

	КонецПроцедуры


После вызова макроса скрипта модуль примет следующий вид

	Перем юТест;

	Функция ПолучитьСписокТестов(ЮнитТестирование) Экспорт

		юТест = ЮнитТестирование;

		ВсеТесты = Новый Массив;

		ВсеТесты.Добавить("ТестДолжен_ПроверитьПроведениеДокументаПКОпоРегиструБухгалтерии");

		Возврат ВсеТесты;

	КонецФункции

	Процедура ТестДолжен_ПроверитьПроведениеДокументаПКОпоРегиструБухгалтерии() Экспорт
	  ВызватьИсключение "Тест не реализован";
	КонецПроцедуры
</li>
<li>
Если функции "ПолучитьСписокТестов" в модуле внешней обработки не существует, то выполняется вставка кода этой функции с готовыми описаниями тестовых случаев.</li>
</ul>


<b>Ссылки</b>:
* [История версий](https://snegopat.ru/scripts/finfo?name=xUnitAddTestsDesc.js)

* [Обсуждение на форуме Снегопата](https://snegopat.ru/forum/viewtopic.php?f=3&t=607)