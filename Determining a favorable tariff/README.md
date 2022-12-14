# Определение перспективного тарифа для телеком-компании

## Описание проекта

Федеральный оператор сотовой связи, клиентам предлагает два тарифных плана. Чтобы скорректировать рекламный бюджет, коммерческий департамент хочет понять, какой тариф приносит больше денег.
Необходимо предварительно проанализировать тарифы на небольшой выборке клиентов:
* Описать поведение клиентов оператора, исходя из выборки. 
* Проверить гипотезы.

## Стек 
Python, Pandas, Matplotlib, NymPy, SciPy, описательная статистика, проверка статистических гипотез.

## Выводы:
1. Для оператора выгоднее клиенты тарифа ultra, не смотря на то, что они почти недоплачивают за сверхиспользования тарифа, они стабильно приносят компании абоненскую плату почти в 2 раза выше чем клиенты smart с доплатами. Так же их поведение более стабильно, что позволяет спрогнозировать доход от них на более длительный срок.
2. После проверки гипотез, можно сказать:
   - **Гипотеза №1**: средняя выручка пользователей тарифов «Ультра» и «Смарт» различаются.
   - **Гипотеза №2**: средняя выручка пользователей из Москвы не отличается от выручки пользователей из других регионов.  
