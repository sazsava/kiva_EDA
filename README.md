# Exploratory data analysis -Kiva.org
##  1. Kiva и ее деятельность
***
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/Kiva.org_logo_2016.svg/640px-Kiva.org_logo_2016.svg.png" width="500" height="200" />

Kiva - это некоммерческая организация, которая позволяет нуждающимся более чем в 80 странах мира получать финансирование под различного рода проекты и нужды.

Девиз Kiva - **Make a loan, change a life**

В основном деятельность Kiva связана с поддержкой населения, развитием малого бизнеса, а также финансированием социальных проектов. 
Список заявок, назанчений и стран, нуждающихся в финансировании можно посмотреть на сайте [kiva.org](https://www.kiva.org).
Это темы, так или иначе связанные с Сельским хозяйством, Питанием, Здоровьем и гигиеной, Розничной торговлей и поддержкой малого бизнеса.

## 1.1. Задача
***
Целью было рассмотреть данные по займам, предсатвленным компанией Kiva, провести EDA и, на его основе, сделать выводы и рекомендации, которые позволили бы компании работать эффективнее и больше понимать специфику потребностей и уровень бедности в разных странах и регионах. 
Что было сделано?
- Рассмотрена вероятность наличия корреляции между странами, полом заёмщика и суммой займа
- Изучены данные по займам на предмет присутствия аномалий
- Выявлена зависимость уровня бедности от региона проживания пользователей
- Произведена оценка влияния многомерного индекса бедности в разных странах на суммы займов и сроки погашения
- Сформулованы основные выводы и составлены визуальные материалы, подкрепляющие их.
## 1.2. Набор данных от Kiva
***
Данные находятся по ссылке:
https://drive.google.com/file/d/1gTMkmMmWnfEwaKdCD7w91iC0x9OYt3A5/view

**kiva_loans** - это набор данных, который содержит большую часть информации о займах:
- id - Уникальный идентификатор для кредита
- funded_amount - Сумма, выплаченная Kiva агенту на местах (USD)
- loan_amount - Сумма, выплаченная полевым агентом заемщику (USD)
- sector - Сектор использования займа
- activity - Более гранулированная категория
- use - Назначение использования суммы кредита
- country_code - ISO код страны страны, в которой был выдан заем
- country - Полное название страны, в которой был выдан кредит
- posted_time - Время, в которое заявка была опубликована на Kiva
- disbursed_time - Время, когда кредитный агент выдал заемщику сумму
- funded_time - Время, когда заявка полностью финансируется кредиторами
- term_in_months - Срок, на который был выдан кредит в месяцах
- lender_count - Общее количество кредиторов, которые внесли свой вклад в этот кредит
- loaner_genders - Разделенные запятыми буквы M, F, где каждый экземпляр представляет одного мужчину / женщину в группе

**kiva_mpi_region_locations** - набор данных, содержащий данные о регинах и показатели MPI:
(Global Multidimensional Poverty Index - глобальный индекс бедности) ряда регионов (субнациональных) в мире.  Чем больше это значение, тем выше бедность в соответствующем регионе 
- country - страна
- region - регион в стране
- world_region - часть света
- MPI - многомерный индекс бедности
- geo - координаты (широта, долгота)
