# Задание к занятию "Условия"

## Задача 1 "Поздравления"

### Описание задачи
При начале работы программы поздравлять пользователя с одной из праздничных дат, если она приходится на сегодня или на завтра.

### Требования к результату
Конфигурация, при запуске поздравляющая пользователя выводом сообщения или предупреждения, если сегодняшний или завтрашний день приходится на одну из нескольких праздничных дат (набор праздников - произвольный). Приветствие должно содержать название праздника и собираться функцией **СтрШаблон()**.

### Процесс выполнения
1. Используйте произвольную конфигурацию.
2. В модуле приложения создайте обработчик **ПриНачалеРаботыСистемы**, если его еще нет.
3. В обработчике:
* Проверьте условиями, приходится ли сегодняшняя или завтрашняя дата на праздник из небольшого произвольного набора.
* Соберите поздравление в локальную переменную, используя функцию **СтрШаблон()**, название праздника и указание на день ("сегодня" или "завтра").
* Выведите поздравление (например, "Поздравляем, сегодня - День монгольского флота!") вызовом **Сообщить()** или **ПоказатьПредупреждение()**.

## Задача 2 "Проверка введенных данных"

### Описание задачи
Реализовать проверку на заполненность и длину ИНН и КПП перед записью справочника **Контрагенты**.

### Требования к результату
Конфигурация, в которой есть справочник **Контрагенты** с ИНН, КПП и видом контрагента ("Юридическое лицо", "Физическое лицо"). Перед записью формы должна выполняться проверка на заполненность и длину ИНН и КПП в зависимости от вида контрагента.

### Процесс выполнения
1. Используйте конфигурацию **УправлениеИТФирмой** со справочником **Контрагенты** из предыдущего задания (https://github.com/netology-code/1c-homeworks/blob/master/homework-1-3.md).
2. В форме создайте обработчик события **ПередЗаписью**, в коде которого реализуйте проверку на заполненность и длину ИНН и КПП в зависимости от вида контрагента:
  * Для юридического лица ИНН и КПП должны быть заполнены; ИНН должен быть длиной 10 знаков, КПП - 9 знаков.
  * Для физического лица ИНН должен быть длиной 12 знаков, КПП - не заполнен.
  * Контрольную сумму ИНН и наличие только цифр в ИНН и КПП проверять пока не нужно.
  * Для получения значения перечисления на клиенте используйте функцию **ПредопределенноеЗначение()**.
  * При выявлении ошибок устанавливайте параметр обработчика **Отказ** в **Истина** и выводите разумное сообщение вызовом **Сообщить**.