# Исследование объявлений о продаже квартир

## Описание проекта

В нашем распоряжении данные сервиса — архив объявлений о продаже квартир в Санкт-Петербурге и соседних населённых пунктах за несколько лет. 

По каждой квартире на продажу доступны два вида данных. Первые вписаны пользователем, вторые получены автоматически на основе картографических данных. Например, расстояние до центра, аэропорта, ближайшего парка и водоёма.

## Стек
Python, Pandas, Matplotlib, исследовательский анализ данных, визуализация данных, предобработка данных

## Цель исследования

* Найти, какие факторы больше всего влияют на стоимость квартиры? 
* Выяснить, какая область входит в центр. 

## Ход исследования

1. Изучение данных из файла.  
2. Предобработка данных.  
    * Обработка пропусков
    * Замена типа данных] 
    * Обработка дубликатов  
3. Расчеты и добавление результатов в таблицу.
4. Исследовательский анализ данных.
5. Общий вывод.

## Общий вывод
1. Удалили пропуски, составляющие данные менее 1%, в столбцах  floors_total и locality_name.


2. Для автоматизации процесса, при заполнении объявлений о продаже квартиры, можно порекомендовать:

* Сделать так, чтобы не было возможности поставить в количестве комнат - 0. Сделать кнопки 1,2,3 и т.д и кнопку аппартаменты. Так данные будут достовернее и с ними легче будет работать.

* Так же при заполнении данных пользователем о количестве балконов, поставить кнопку "нет балкона", таким образом с данными будет работать проще и они будут достовернее.

* Сказать коллегам, кто отвечает за выгрузку данных, чтобы они обратили внимание на столбец days_exposition, количество пропусков составляет более 13%, что достаточно много. Возможно они смогут проработать этот вопрос и уменьшить количество пропусков.

* Из выгрузки картографических данных, можно брать, только информацию, расстояние до центра города и аэропорта.
Наличе парков и прудов и их расстояние, не самые важные данные для исследования, а если человеку очень они важны, он с легкостью может сам посмотреть в яндекс.картах введя адрес квартиры.

3. Исследовав квартиры по всей выборке, можно сделать следующие выводы:

* Чаще всего встречаются квартиры с площадью от 35 до 60 м2;

* Больше всего предложений со стоимостью квартир от 3 до 5 млн. руб;

* Самые популярные 1 и 2 - комнатные квартиры;

* Обычное время продажи квартир составляет до 100 дней, самыми быстрыми продажами можно считать продажи до 30 дней, самыми долгими - выше 550 дней.

* По высоте этажа - самые низкие цены у квартир на первом этаже

* Можно проследить зависимость стоимости квартиры от ее площади. Чем больше площадь, тем дороже квартира. Но если посмотреть на стоимость квадратного метра квартиры, то у однокомнатных квартир квадратный метр стоит дороже.

* Прямой связи стоимости квартиры от расстояния до центра не обнаружено. Квартиры в центре могут иметь и самую большую цену и одновременно самую низкую цену. В отдаленных районах мы можем так же наблюдать наличие высоких цен за квартиры.

* Проанализировав по дате размещения объявлений, было установлено: самые низкие цены на квартиры, размещенные в июле, самые большие цены с августа по ноябрь; был спад на рынке недвижимости в 2016-2018 годах, с 2019 можно наблюдать опять подъем цен.

4. Было найдено 10 населленых пунктов с самым большим числом объявлений. Самая большая стоимость за 1м2 составила 103484 руб в Санкт-Петербурге, самая низкая - 56707 м2 в Выборге.

5. Выбрав из столбца locality_name только Санкт-Петербург, построили график, где указана средняя стоимость для каждого км и нашли резкое понижение цены в районе 7км. Исходя их этого, обозначили центром, зону до 7 км и проанализировали только ее.

6. Из данного анализа обнаружили:

* Стоимость квартир в центральной зоне выше. Минималные цены в центре и за его пределами, очень сильно отличается, 1686тыс.ру. и 12,19тыс.руб.

* Квартиры с площадью до 80м2 в центре стоят дороже, чем на периферии. После 80м2 можно наблюдать, что квартиры, находящиеся за центром, тоже стоят дорого.

* В центре чаще всего встречаются 2ух комнатные квартиры, по всем населенным пунктам более популярные 1-комнатные квартиры. 6ти комнатные квартиры встречаются только в центре.

* Средняя высота потолка 2,65м встречается в основном как в центре, так и за его пределами. А вот потолки - 2,5м, чаще встречаются за пределами центра.

* Квартиры на первых этажах в центре стоят дороже даже чем средний этаж по всем населенным пунктам. В целом первые этажи стоят дешевле, чем последние как в центре так и за его пределами. Но можно отметить, что в центре разница между средним и последним этажем почти минимальная, в то время как по всей выборке видно, что средний этаж в разы дороже чем последний.

* Можно отметить, что в центре и за его пределами очень слабая зависимость между удаленностью от центра и стоимостью квартир. Мы наблюдаем, что в самом центре есть как очень дорогие, так и одни из самых дешевых квартир. По всей выборке зависимость цены от растояния, чуть сильнее.

* Относительно дня публикации объявления по всей выборке идет более стабильное распределение публикаций, к выходным количество чуть снижается. В центре количество публикаций примерно в 1,5 раза больше. В понедельник и четверг количество уменьшается, всех больше размещают объявления в воскресение. 

* По месяцу размещения объявлений. Общее у графиков то, что всех меньше размещают объявления в июне, к августу идет рост и длится до сентября, далее в центре идет на спад, а на периферии держится до ноябряь, но к новому году и там, и там идет на спад.

* По году размещения объявлений. Мы можем наблюдать интересную особенность, в то время как по всем населенным пунктам шел спад по количеству размещаемых объявлений с 2016 по 2018 года, в центре же наоборот в данные годы шел подъем продаж квартир. И наоброт в то время как к 2019 шло увеличение количества объвлений по всей выборке, в центре случился значительный их спад.