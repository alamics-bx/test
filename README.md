Кандидату предлагается выполнить тестовое задание из "Экзамена №2 - Основные технологии и расширение типовых возможностей системы". Кандидату предлагается выполнить тестовое задание из "Экзамена №2 - Основные технологии и расширение типовых возможностей системы".

[https://academy.1c-bitrix.ru/certification/exams.php]()

Для решения задания требуется установка «1С-Битрикс: Управление сайтом» редакции «Стандарт», решение «Корпоративный сайт производственной компании».

**Общие условия для решения заданий**
* Создать копию шаблона furniture_pale-blue в local, шаблоны компонентов размещать в этом шаблоне.
* Максимально приветствуется использование API D7 и файла /component_name/class.php вместо файла /component_name/component.php.

Разработать простой компонент «Каталог товаров»
-------------------------

**Общие требования**
* У созданного компонента задать код: simplecomp.exam, название: «Мой компонент», раздел для отображения компонента в визуальном редакторе: «Экзамен №2».
* Работу решения продемонстрировать в разделе сайта /ex2/simplecomp/, добавить пункт в главное меню «Экзамен2», и пункт в левом меню «Простой компонент».

**Решаемая задача**
* Компонент должен выводить список товаров, сгруппированных по альтернативному классификатору. Альтернативный классификатор – новости.
* Будет использоваться множественная привязка разделов каталога товаров к альтернативному классификатору – новостям. Привязка элементов к разделам в инфоблоке
* Продукция остается по умолчанию, задавать множественную - не нужно.
* Используется только один уровень разделов, вложенности – не будет.
* Большой объем разделов и элементов не предполагается (не более 20 разделов и 100 элементов), лимиты на выборку и постраничная навигация – не нужны.

**Технические требования**
* Использовать при решении метод GetMixedList – нельзя.
* Компонент должен иметь только такие параметры:
* ID инфоблока с каталогом товаров, строка.
* ID инфоблока с новостями, строка.
* Код пользовательского свойства разделов каталога, в котором хранится привязка к новостям, строка.
* Типовые настройки кеширования: авто+управляемое, кешировать, не кешировать, и время кеширования.
* Выбор шаблона.
* Условия кеширования результата работы компонента - по умолчанию, не зависит от дополнительных данных.
Инфоблоки, получаемые данные
* Использовать существующий информационный блок Продукция.
* У разделов в инфоблоке Продукция создать множественное пользовательское свойство: код UF_NEWS_LINK, тип – привязка к элементам инфоблока, инфоблок – новости.
* Каждому разделу в инфоблоке Продукция задать привязку к нескольким новостям.
* Используемые в шаблоне данные разделов каталога товаров:
    * Поля: название.
* Используемые в шаблоне данные элементов:
    * Поля: название.
    * Свойства: материал, артикул, цена.
* Используемые в шаблоне данные новостей:
    * Поля: название, дата активности.
* Должны выбираться только активные разделы и элементы из обоих инфоблоков.
* Сортировка при отборе не задается.

**Установка заголовка страницы**
* В компоненте устанавливать заголовок страницы: «В каталоге товаров представлено товаров: [Количество]» где Количество – количество отображаемых товаров.
* Заголовок должен устанавливаться в файле component.php. Этот функционал является логикой компонента и не должен «теряться» при смене шаблона.

**Отображение данных**
* Строится дерево разделов альтернативного классификатора и элементов, относящихся к нему.
* Рядом с названием альтернативного классификатора отображаются:
  * Дата активности.
  * Название связанных разделов каталога.

