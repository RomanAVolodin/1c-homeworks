# Задание к занятию "Соединения"

## Задача "Информация по контрагенту"

### Описание задачи

Создать внешнюю обработку ИнформацияПоКонтрагенту. Обработка формирует и выводит на экран Текстовый документ с информацией по контрагенту. В обработке выбирается контрагент для формирования информации.

### Требования к результату

Прикрепить .epf файл внешней обработки для формирования информации по контрагенту.

### Процесс выполнения

1. Сформировать внешнюю обработку ИнформацияПоКонтрагенту.epf.
2. В обработку добавить реквизит формы Контрагент с типом Справочники.Контрагенты.
3. В конфигурацию добавить общий макет ИнформацияПоКонтрагенту типа текстовый документ.
4. Создать команду Вывести информацию и соответствующую кнопку на форму.
5. Перекрыть действие команды и реализовать следующее:
 * Если реквизит контрагент не заполнен то выдавать соответствующее сообщение и дальше не продолжать;
 * Создать текст запроса который будет посекционно выводить информацию по выбранному контрагенту в общий макет ИнформацияПоКонтрагенту;
 * В первую секцию выводить наименование контрагента, ИНН, и КПП из справочника контрагенты;
 * Во вторую секцию выводить контактную информацию по контрагенту из табличной части КонтактнаяИнформация из справочника Контрагенты;
 * Будем считат что контрагент является и поставщиком и покупателем. Поэтому в третью секцию выводить Товар, Количество проданного товара и Количество поступившего 
   товара из документов Поступление и Реализация;
 * При формировании текста запроса учитывать следующие особенности:
   - использовать один запрос;
   - для получения контактной информации использовать ВНУТРЕННЕЕ СОЕДИНЕНИЕ;
   - товар в запросе должен быть объединен в одну колонку как для продажи так и для поступления;
   - для получения количества проданного и поступившего товара использовать ПОЛНОЕ СОЕДИНЕНИЕ в подзапросе по товару;
   - При полном соединении не должны присутствовать значения Null;
   - Правильно использовать группировки и агрегатные функции в подзапросе;
   - для соединения с подзапросом установить связь со справочником Контрагенты используя ВНУТРЕННЕЕ СОЕДИНЕНИЕ;
   - Результат запроса можно обрабатывать только на свертку через таблицу значений;
6. Создать примеры в справочниках и документах. Протестировать формирование текстового документа. 
7. Для реализации и поступления тестировать на нескольких документах. Товары в табличной части должны отличаться.