# Онлайн-магазин компьютерных игр

## Описание проекта

Интернет-магазине продаёт по всему миру компьютерные игры. Нам известны данные о продажах игр, оценки пользователей и экспертов, жанры и платформы.

## Цель исследований:

* Определить критерии успешности игры, чтобы сделать ставку на потенциально популярный продукт и спланировать рекламные кампании.
       
* Проверка гипотез

## Ход исследования:

1. Изучение данных из файла.  
2. Подготовка данных.  
    * Обработка пропусков
    * Замена типа данных
    * Обработка дубликатов  
3. Подготовка пользовательских данных
4. Исследовательский анализ данных.
5. Проверка гипотез.
6. Общий вывод.

## Общий вывод:

I. Перед анализом, мы подготовили данные, а именно:

* привели все названия столбцов к нижнему регистру;

* удалили строчки в столбцах (name, year_of_release и genre), где пропуски составили меньше 5 %;

* изменили тип данных у столбцов: year_of_release на int и user_score на float;

* изучили пропуски в столбце rating и заменили их и значение "К-А" на значения "RP".

* значение "tbd" в столбце user_score заменили на nan;

* на остальные пропущенные значения с рейтингами в столбцах critic_scor, user_score мы поставили заглушку - 0;

* проверили на наличие явных дубликатов, убедились, что они отсутствуют;

* для дальнейших расчетов, добавили новый столбец к таблице с суммой всех продаж по всем регионам sum_sales.

II. Исследовательский анализ данных:

1. После выбора топ-10 платформ с наибольшими суммарными продажами, было обнаружено:

    * Что в среднем платформа "живет" около 10 лет;
    * Выбрали актуальный период - 2 последних год (2015-2016 года)
    * Обновили нашу таблицу games и оставим данные только начиная с 2015 года.
    
    
2. Выявили платформы, лидирующие по продажам.

    * Исходя из общей суммы по продажам по каждой платформе, мы выбрали несколько потенциально прибыльных платформ. В их число вошли такие платформы как: PS4, XOne, 3DS, WiiU, PS3.
    
    
3. Обнаружили выбросы:

    * Из графика "ящик с усами" видно, что у всех пяти платформ присутствуют выбросы. 
    * У платформы PS4 всех больше выбросы, это говорит о том, что у данной платформы были большие продажи.
    * На втором графике видно, что распределение продаж среди платформ не сильно отличаются, медиана продаж у платформ PS4 и XOne ~ 0,1 миллиона проданных копий, у платформ 3DS и PS3 ~ 0,05 миллиона проданных копий, ну и лидер по медиане 0,2 миллиона проданных копий это платформа WiiU.
    
    
4. Рассмотрели влияние продаж от отзывов пользователей и критиков:

    * Посмотрев, как влияют на продажи внутри платформы PS2 отзывы пользователей и критиков, сделали предположение, что прямой зависимости от отзывов нет. Прослеживается связь по отзывам критиков, что чем ближе отзывы к макисмальной оценке, тем тем больше сумма продаж, но это связь не прямолинейная. После отметки больше 60 баллов появляются продажи свыше 1,5 млн. По отценкам пользователей зависимости оценок и продаж почти нет.
    * По таблице корреляции можно предположить, что зависимость продаж от оценки критиков есть, но она все ровно не большая.
    * При сравнении уже пяти платформ по отзывов, мы видим, что зависимость продаж от оценки пользователей нет. А зависимость продаж от оценки критиков, пусть и не большая, но присутствует у всех пяти платформ.
    
    
5. Из графика можно выделить:

    * топ-3 самых прибыльных жанров:

       * Shooter
       * Action
       * Sports

    * топ-3 самых не прибыльных жанров:

       * Simulation
       * Strategy
       * Puzzle

    * по медианам подтверждается, что лучший жанр это Shooter, а вот Sports обогнал Action. И по медиане тройка лидеров поменялась и стала: Shooter, Sports, Role-Playing

    * Action выиграл по графику распределения, благодаря выбросам.
      
      
6. Составили портреты пользователей каждого региона:

    * Портрет игрока из Северной Америке:

      - любимая платформа XOne
      - любимы жанр Action
      
    * Портрет игрока из Европы:

      - любимая платформа PS4
      - любимы жанр Action
      
    * Портрет игрока из Японии:

      - любимая платформа PSV
      - любимы жанр Action
      
III. Проверка гипотез:

1. Мы проверили две гипотезы при помощи ttest.

**Гипотеза №1**: cредние пользовательские рейтинги платформ Xbox One и PC одинаковые - получив P-значение 37.26% мы не отвергли нулевую гипотезу, и предположили, что различия между средними рейтингами платформ не велико. 

**Гипотеза №2**: средние пользовательские рейтинги жанров Action и Sports разные - получив P-значение  очень маленькое мы отвергли нулевую гипотезу о равенстве между рейтингами жанров Action и Sports.


IV. Успех игр:

После анализа, можно выявить ряд критериев успеха игр, а именно обратить внимание на:
   * платформы PS4, XOne, 3DS, WiiU, PS3;
   * жанры Action, Sports, Shooter, Role-Playing;
   * что высокие оценки критиков тоже могут повлиять на рост продаж;
   * не забывать о предпочтениях в регионах - они отличаются;
   * жанр Action и платформа PS3 и PS4 попали почти во все высокие рейтинги;
   * перед тем как планировать кампанию на какой-либо год, стоит брать в учет для анализа не более 2 предшествующих лет.