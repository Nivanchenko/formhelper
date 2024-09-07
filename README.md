# formhelper

Библиотека для программного управления элементами формы.

В составе расширение, и файл с шаблонами кода.

Вот небольшой пример.

```bsl

&НаСервере
Процедура ПриСозданииНаСервере(Отказ, СтандартнаяОбработка)
	
	РаботаСФормамиСервер.НовыйПостроительФорм(ЭтаФорма)
	
	// Реквизит строковый
	.РеквизитСтрока("РеквизитСтрока", 150)
	
	// ПолеВвода реквизита строка
	.ПолеВвода("РеквизитСтрока")
	.Заголовок("Реквизит строка")
	.ПутьКДанным("РеквизитСтрока")
	
	// Кнопка привет
	.Кнопка("КнопкаПривет")
	.Заголовок("Привет")
	.ИмяКоманды("Приветствие")
	
	//Команда простая
	.Команда("Приветствие", "ПриветствиеКлиент")
	
	// Еще кнопка
	.Кнопка("ЕщеКонманда")
	.ИмяКоманды("ЕщеКонманда")
	
	//Еще команда с атрибутами
	.Команда("ЕщеКонманда", "ЕщеКомандаНаКлиенте")
	.Заголовок("Команда еще")
	.Картинка(БиблиотекаКартинок.Документ)
	.Отображение(ОтображениеКнопки.КартинкаИТекст)
	.ИзменяетСохраняемыеДанные(Истина)
	.Подсказка("Команда с атрибутами")
	
	// Строковый реквизит с полем ввода
	.РеквизитСтрока("ЕщеСтроковыйРеквизит", 100)
	.ПолеВвода("ЕщеСтроковыйРеквизит")
	.Заголовок("Еще один строковый реквизит")
	.ПутьКДанным("ЕщеСтроковыйРеквизит")

	// Финализируем изменения
	.Применить();

КонецПроцедуры

&НаКлиенте
Процедура ЕщеКомандаНаКлиенте(Команда)
	Сообщить("Очень полезная команда выполнена");
КонецПроцедуры

&НаКлиенте
Процедура ПриветствиеКлиент(Команда)
	Сообщить(СтрШаблон("Привет %1", ЭтотОбъект["РеквизитСтрока"]));
КонецПроцедуры

```

![](https://infostart.ru/bitrix/templates/sandbox_empty/assets/tpl/abo/img/logo.svg)[Статья](https://infostart.ru/public/1979960/) 
