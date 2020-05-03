# Задание к занятию "Иерархия и подчинение"

## Задача 1 "Номенклатура"

### Описание задачи

Создать иерархический справочник "Номенклатура" для хранения сведений о товарах и услугах.

### Требования к результату

Справочник "Номенклатура":
* с неограниченной иерархией групп и элементов;
* с реквизитами Тип и ПолноеНаименование, определенными только для элементов;
* с формой списка, разделенной на дерево групп (в режиме "Дерево") и список элементов (в режиме "Список");
* с отбором элементов по принадлежности к активной группе.

### Процесс выполнения

* Создать перечисление ТипыНоменклатуры со значениями Товар, Услуга.
* Создать справочник "Номенклатура" (синоним "Товар, услуга"):
  * С неограниченной иерархией групп и элементов.
  * С реквизитами ПолноеНаименование (строка неограниченной длины) и Тип (ПеречислениеСсылка.ТипыНоменклатуры), определенными только для элементов. Сделать тип обязательным к заполнению.
* Создать форму списка, в которой:
  * Отключить автозаполнение общей командной панели (у списка элементов будет своя командная панель).
  * Создать общую группу с горизонтальной группировкой элементов, в которой разместить две группы с вертикальным расположением, правую - для групп номенклатуры, левую - для элементов.
  * В существующем динамическом списке Список установить отбор по условию ЭтоГруппа = Ложь, а соответствующую таблицу формы перетащить в левую группу.
  * Выбрать для таблицы "Список" режим отображения "Список".
  * Создать в левой группе командную панель с источником команд "Список" и исключить из состава команд команду "Создать группу".
  * Создать динамический список Группы с основной таблицей Справочник.Номенклатура и отбором по условию ЭтоГруппа = Истина.
  * Перетащить динамический список Группы на форму, в правую группу.
  * Для таблицы Группы выбрать режим отображения "Дерево".
  * Исключить из состава ее команд команду "Создать" (элемент).
  * Реализовать для таблицы Группы обработчик события ПриАктивизацииСтроки, в котором установить отбор по значению текущей группы. Для установки использовать коллекцию элементов отбора компоновки данных (Список.Отбор.Элементы), в которой:
    * Сперва попытаться найти ранее установленный отбор по свойству ЛевоеЗначение.
    * При его наличии - установить ПравоеЗначение, а в отсутствие - добавить новый элемент отбора. Обратите внимание: в качестве вида сравнения следует указывать элемент предопределенного перечисления ВидСравненияКомпоновкиДанных, а не ВидСравнения.

## Задача 2 "Упаковки"

Создать справочник "Упаковки", подчиненных справочнику "Номенклатура" и хранящий сведения о возможных упаковках товаров.

### Описание задачи

Справочник "Упаковки", подчиненный номенклатуре, хранящий сведения о возможных упаковках с коэффициентами.

### Требования к результату

Справочник "Упаковки":
* подчиненный Номенклатуре как владельцу;
* с синонимом стандартного реквизита "Владелец" - "Товар";
* с числовым реквизитом "Коэффициент";
* со списком, открывающимся по ссылке в панели навигации формы элемента справочника "Номенклатура".

### Процесс выполнения

* Создать справочник "Упаковки" (синоним "Упаковка"):
  * Подчиненный номенклатуре как владельцу (задать синоним стандартного реквизита - "Товар").
  * С числовым реквизитом "Коэффициент", имеющим достаточную точность для упаковок штучного и весового товара.
  * Не выводить его в общий командный интерфейс конфигурации.
  * Удостовериться в том, что для него автоматически отображается команда перехода в панели навигации формы элемента справочника "Номенклатура".