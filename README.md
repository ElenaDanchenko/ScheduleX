# Система управления расписанием в медицинских учреждениях ScheduleX #

<img src="https://github.com/ElenaDanchenko/ScheduleX/blob/main/Logo/original.png" alt="Система управления расписанием" width="180" height="180" align="center">

## Описание проекта

Медицинские центры часто сталкиваются с проблемами при планировании расписания: ошибки, перегрузка врачей, неэффективное использование ресурсов.  Информационная система **ScheduleX** – это современное решение для автоматизации и оптимизации планирования в медицинских учреждениях. <br>

Система позволяет сотрудникам клиники легко управлять расписанием приёмов, контролировать загрузку врачей и эффективно распределять ресурсы.  С помощью ScheduleX можно формировать расписание как автоматически по заданным правилам, так и вручную, обеспечивая гибкость планирования.  Встроенные механизмы уведомлений мгновенно оповещают персонал обо всех изменениях, а функция согласования упрощает процесс внесения корректировок.<br>

Интеграция с 1С:Поликлиника обеспечивает автоматическое обновление данных о пациентах, сотрудниках и услугах, значительно сокращая ручную работу по ведению баз данных. Система работает круглосуточно, поддерживает многопользовательский доступ с разграничением прав и регулярно создает резервные копии информации для надежности.<br>

**ScheduleX** – это удобный инструмент, который помогает медицинским учреждениям оптимизировать работу, минимизировать ошибки в планировании и сосредоточиться на главном – заботе о пациентах.

## **Цель проекта**

Разработка комплекса требований к автоматизированной системе составления расписаний работы медицинского персонала с использованием современных методологий 
анализа и проектирования. 

Этапы сбора и анализа требований:
- исследование проблем ручного планирования графиков,
- сбор требований от  заинтересованных лиц,
- разработка полной спецификации (SRS) системы, с учетом особенностей медицинских учреждений и нормативных требования к организации работы персонала.

## **Подцели проекта**

- Оптимизация нагрузки на персонал и оборудование
- Снижение влияния человеческого фактора на 70% 
- Обеспечение соответствия нормативным требованиям

## Информационное обследование

На [контекстной диаграмме](#контекстная-диаграмма-основной-функции-ис) представлена главная бизнес-функция разрабатываемой системы – управление расписанием медицинской организации. <br>
При анализе данной бизнес-функции была принята точка зрения руководства медицинской организации как потенциального заказчика информационной системы.<br>
Среди всех правил и предписаний, которые влияют на данный бизнес-процесс были выделены наиболее важные и актуальные: <br>

1. Законы РФ (здравоохранение и трудовое законодательство):
*	Лицензионные требования (персонал, оборудование, помещения).
*	Нормы оказания медицинской помощи (стандарты лечения, время на услуги).
*	Защита персональных данных (ФЗ-152).
*	Трудовое законодательство (продолжительность рабочего дня, перерывы).

2. Внутренние регламенты медицинской организации:
*	Правила записи на прием.
*	Использование оборудования и помещений (доступность, резервирование).
*	Распределение времени (в зависимости от услуги, пациента).

3. Стандарты медицинской помощи и клинические рекомендации:
*	Протоколы ведения пациентов.


## Концепция системы
Информационная система ScheduleX предназначена для решения проблем, связанных с планированием работы медицинского персонала. 
Для выявления основных причин этих проблем был проведен анализ с использованием диаграммы Ишикавы: <br>

<img src="https://github.com/ElenaDanchenko/ScheduleX/blob/main/%D0%94%D0%B8%D0%B0%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D1%8B/Ishikava_v1.png" alt="Диаграмма Ишикавы" width="600" height="400"><br>

**Анализ проблем (Диаграмма Ишикавы):**

| Категория проблемы | Описание|
|---|---|
| **Проблема** | Сложности в создании расписаний работы медицинского персонала|
| **Затрагивает** | Медицинский персонал, административный персонал, пациенты|
| **Результаты** | Неравномерная нагрузка на персонал и оборудование; Задержки в обслуживании пациентов; Ошибки в расписании (человеческий фактор); Трудности с соблюдением нормативных требований.|
| **Выигрыш от SCHEDULEX** | Равномерное распределение нагрузки между сотрудниками; Снижение количества накладок в расписании за счет снижения влияния человеческого фактора; Сокращение времени, необходимого для составления расписаний; Возможность прогнозирования потребности в персонале, оборудовании; Снижение количества конфликтов с пациентами из-за задержек в обслуживании; Обеспечение соответствия нормативным требованиям к организации работы персонала. |

Анализ причин проблем с использованием диаграммы Ишикавы позволил выявить ключевые бизнес-правила.  <br>

**Ключевые бизнес-правила:** 

•	Все медицинские данные пациентов должны обрабатываться в соответствии с ФЗ-152 «О персональных данных». <br>
•	Запись пациента на прием разрешается только к врачам, у которых: действующая лицензия на указанный вид медицинской деятельности, сертификат специализации соответствует запрашиваемой услуге (проверка по реестру Минздрава). <br>
•	Медицинские данные шифруются по стандарту ГОСТ Р 57580. <br>
•	Пациенты распределяются в порядке приоритета: направления от других врачей — в течение 24 часов, плановые приемы — в порядке очереди. <br>
•	Система должна учитывать: для пациентов - предпочтительное время приема (±2 часа от запрошенного), для врачей - график работы, научная/административная нагрузка, личные пожелания. <br>
•	При отмене записи пациентом необходимо уведомить сотрудника и перераспределить слот. <br>
•	Длительность приема определяется стандартом Минздрава для каждой услуги (±10% корректировка по решению врача). <br>
•	Запрещено изменять запись другого врача без согласования с ним. <br>
•	Запрещена запись на процедуры, если: оборудование на техобслуживании, остаток ресурсов <10% (например, расходники для анализов). <br>

Основываясь на этих правилах, был выполнен [процесс моделирования бизнес-процессов](#моделирование-бизнес-процессов) в нотации BPMN. <br>

**Ожидаемые результаты внедрения ScheduleX:**

Внедрение системы позволит:

* Сократить время, затрачиваемое сотрудниками на составление расписаний, с 20 часов в неделю до 5 часов.
* Снизить количество ошибок в расписании до 1%, которые ранее возникали в среднем с частотой 5% (1 ошибка на сотрудника в месяц).
* Снизить количество случаев задержек приема пациентов на 70-85% (с 7 до 1-2 случаев в год) за счет предотвращения накладок в расписании и своевременного информирования пациентов об изменениях.
* Обеспечить сотрудникам возможность видеть расписание коллег для оперативной связи и организации взаимозаменяемости в случае необходимости через мобильное приложение или веб-интерфейс.
* Учитывать пожелания сотрудников при составлении расписаний, что позволит повысить средний балл удовлетворенности работой, согласно внутренним опросам, с 3 до 5 по 5-балльной шкале.<br>

**Диаграмма Парето до и после внедрения системы:** <br>
<br>
<img src="https://github.com/user-attachments/assets/baa32a30-79bf-4b59-82e4-be82bf919460" alt="Диаграмма Парето" width="400" height="550"><br>

## Ключевые заинтересованные лица
|Заинтересованное лицо | Ожидание |
|---|---|
|Медицинский специалист|Удобное предсказуемое расписание, учет личных пожеланий сотрудников, оптимальная загрузка, снижение очередей и конфликтов, удобный и понятный интерфейс|
|Менеджер, составляющий расписание|Удобный и интуитивно понятный интерфейс, снижение количества ошибок, автоматизация составления расписания|
|Администраторы рецепции|Быстрая обработка запросов, удобство работы, снижение ошибок|
|Главный врач|Оптимизация и адекватное распределение нагрузки медицинского персонала, высокое качество медицинской помощи|

## Профили пользователей

|Медицинский специалист||
|---|---|
|Краткое описание|Опасение низкой загруженности, низкой оплаты труда (при сдельной оплате), желание работать с большим количеством пациентов.|
|Ответственность|Оказывает медицинскую помощь и услуги планового порядка пациентам.|
|Критерии успеха|Стабильный поток пациентов и полная загрузка рабочего времени.  Прозрачная система оплаты труда и возможность влиять на свой доход. Удобный график работы, учитывающий личные потребности.  Современное оборудование и комфортные условия работы.|
|Комментарии/разногласия| Сомнения в справедливости распределения пациентов и нагрузки. Страх переработок и выгорания из-за высокой загрузки. Опасения по поводу прозрачности системы оплаты труда. Неуверенность в учете их пожеланий при составлении расписания. Боязнь конфликтов с пациентами из-за задержек или ошибок в расписании. Сомнения в том, что система учитывает их профессиональные навыки и квалификацию.|

|Менеджер, составляющий расписание||
|---|---|
|Краткое описание|Устает от рутинной работы, желает снизить сложность задачи, минимизировать количество ошибок и конфликтов.|
|Ответственность|Составляет и корректирует расписание, учитывая пожелания сотрудников и пациентов.|
|Критерии успеха|Автоматическое расписание освободит от рутины и ошибок, снизит нагрузку и конфликты. Удобная система позволит быстро вносить изменения и учитывать все нюансы, экономя время и нервы.|
|Комментарии/разногласия| Сомнения в учете всех нюансов и специфических требований (индивидуальные пожелания врачей, особенности работы отделений). Страх потери работы из-за автоматизации. Сложности с обучением и адаптацией к новой системе.|

|Главный врач||
|---|---|
|Краткое описание|Ощущает давление со стороны администрации по поводу дохода и качества услуг.|
|Ответственность|Несет ответственность за эффективную работу всего медицинского учреждения.|
|Критерии успеха|Высокие финансовые показатели клиники.Положительная репутация клиники и высокий уровень удовлетворенности пациентов.Соблюдение всех нормативных требований и отсутствие претензий со стороны контролирующих органов.Удовлетворенность и заинтересованность персонала.Эффективное использование ресурсов и оптимизированные процессы работы.|
|Комментарии/разногласия|Сомнения в возможности достижения баланса между прибыльностью и качеством услуг. Опасения по поводу нехватки ресурсов для обеспечения высокого уровня качества. Недоверие к системе автоматизации расписания и боязнь потери контроля над процессами. Сомнения в учете потребностей персонала при внедрении новых систем и технологий.Страх ухудшения репутации клиники из-за ошибок в расписании или нехватки персонала.|

|Администратор рецепции||
|---|---|
|Краткое описание|Недовольство из-за необходимости работать в стрессовых условиях и решать конфликтные ситуации.|
|Ответственность|Встречает пациентов, записывает на прием, отвечает на звонки, ведет документацию, координирует работу персонала.|
|Критерии успеха|Быстрая и эффективная запись пациентов на прием. Минимизация времени ожидания для пациентов. Отсутствие ошибок в расписании и документации. Четкая организация работы и координация действий с другими сотрудниками.|
|Комментарии/разногласия|Опасения по поводу перегруженности работой и нехватки времени.Страх совершить ошибку при записи пациентов или оформлении документов.Неуверенность в своих навыках работы с новой системой расписания.Сомнения в учете личных пожеланий при составлении графика работы.Боязнь конфликтов с пациентами из-за задержек или ошибок в расписании.|

## Границы системы
Разрабатываемая система взаимодействует со следующими внешними сущностями:<br>
•	Сотрудники МЦ. Входные данные: логин и пароль для авторизации, условия для составления расписания (предпочтения и ограничения). Выходные: расписание на день/неделю/месяц, уведомления, доступные слоты для записи.<br>
•	1C. Входные данные: данные о пациентах, сотрудниках, услугах.<br>

Границы системы и взаимодействия с внешними сущностями наглядно отображены на [диаграмме потоков данных](#диаграмме-потоков-данных) (DFD).<br>

## Возможности системы

1)	Авторизация каждого сотрудника по уникальному логину и паролю.<br>
2)	Добавление нового пациента через синхронизацию с существующей системой 1С: Поликлиника.<br>
3)	Добавление нового сотрудника через синхронизацию с существующей системой 1С: Поликлиника.<br>
4)	Добавление новой услуги через синхронизацию с существующей системой 1С: Поликлиника.<br>
5)	Редактирование карточки пациента и синхронизация с существующей системой 1С: Поликлиника.<br>
6)	Редактирование карточки сотрудника и синхронизация с существующей системой 1С: Поликлиника.<br>
7)	Редактирование карточки услуги и синхронизация с существующей системой 1С: Поликлиника.<br>
8)	Назначение различных прав доступа разным категориям сотрудников.<br>
9)	Создание, согласование и редактирование расписания для большого количества пациентов вручную и автоматически по заданным условиям.<br>
10)	Просмотр расписания в различных состояниях (действующее, согласованное, на согласовании, на этапе создания).<br>
11)	Возможность отфильтровать расписание по сотруднику или датам.<br>
12)	Возможность экспорта расписания в формате pdf.<br>

Для визуализации способов использования этих возможностей различными пользователями разработана [диаграмма вариантов использования](#диаграмма-вариантов-использования) (use case diagram).<br>

## Ограничения
•	Система должна работать под управлением операционных систем iOS 8 и выше, Android 6.0 и выше.<br>
•	Система должна предоставлять веб-интерфейс совместимый с десктопными и мобильными браузерами.<br>
•	Система должна быть совместима с СУБД на основе PostgreSQL 17.5.<br>
•	Система должна быть совместима с API 1С: Поликлиника 3.0.16.1 от 17.03.2025.<br>
•	Приложение должно занимать не более 200 МБ в памяти устройства.<br>

## Требования пользователей

**Спецификации ВИ**

**Создать запись**<br>

*Описание*: Данный вариант использования (ВИ) позволяет создать запись пациента в расписании сотрудника.

*Участвующий актёр*: Сотрудник МЦ (медицинского центра)

*Основной поток событий (сценарий)*:

1. Сотрудник МЦ выбирает свободный слот в расписании.
2. Система отображает форму создания записи.
3. Сотрудник МЦ вводит фамилию пациента в поле для ввода.
4. Система отображает выпадающий список подходящих пациентов.

   * 4.1 Требуемый пациент есть в списке:
      * 4.1.1 Сотрудник МЦ выбирает необходимого пациента и переходит к шагу 5.

   * 4.2 Требуемого пациента нет в списке:
      * 4.2.1 Сотрудник МЦ нажимает кнопку «добавить нового пациента».
      * 4.2.2 Система отображает форму добавления пациента.
      * 4.2.3 Сотрудник МЦ заполняет необходимые поля и нажимает «сохранить».
         * 4.2.3.1 Сохранение выполнено успешно, сотрудник МЦ переходит к шагу 5.
         * 4.2.3.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по ее устранению.
            * 4.2.3.2.1 Сотрудник устраняет причины, которые привели к ошибке, и возвращается к шагу 4.2.3.

5. Сотрудник МЦ вводит наименование услуги в поле для ввода.
6. Система отображает выпадающий список подходящих услуг.

   * 6.1 Требуемая услуга есть в списке:
      * 6.1.1 Сотрудник МЦ выбирает необходимую услугу и переходит к шагу 7.

   * 6.2 Требуемой услуги нет в списке:
      * 6.2.1 Сотрудник МЦ нажимает кнопку «добавить новую услугу».
      * 6.2.2 Система отображает форму добавления услуги.
      * 6.2.3 Сотрудник МЦ заполняет необходимые поля и нажимает «сохранить».
         * 6.2.3.1 Сохранение выполнено успешно, сотрудник МЦ переходит к шагу 7.
         * 6.2.3.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по ее устранению.
            * 6.2.3.2.1 Сотрудник устраняет причины, которые привели к ошибке, и возвращается к шагу 6.2.3.

7. Сотрудник МЦ вводит фамилию специалиста в поле для ввода.
8. Система отображает выпадающий список подходящих специалистов.

   * 8.1 Требуемый специалист есть в списке:
      * 8.1.1 Сотрудник МЦ выбирает необходимого специалиста и переходит к шагу 9.

   * 8.2 Требуемого специалиста нет в списке:
      * 8.2.1 Сотрудник МЦ нажимает кнопку «добавить нового специалиста».
      * 8.2.2 Система отображает форму добавления специалиста.
      * 8.2.3 Сотрудник МЦ заполняет необходимые поля и нажимает «сохранить».
         * 8.2.3.1 Сохранение успешно выполнено, система отправляет новому специалисту оповещение с учетными данными для авторизации в приложении, сотрудник МЦ переходит к шагу 9.
         * 8.2.3.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по ее устранению.
            * 8.2.3.2.1 Сотрудник МЦ устраняет причины, которые привели к ошибке, и возвращается к шагу 8.2.3.

9. Сотрудник МЦ нажимает «Сохранить запись».
  * 9.1 Сохранение успешно выполнено, система отсылает специалисту уведомление о новой записи.
  * 9.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по её устранению.
  * 9.3 Сотрудник устраняет причины, которые привели к ошибке, и переходит к шагу 9.

*Предусловия*:

*  Сотрудник МЦ должен быть аутентифицирован.
*  У сотрудника МЦ должны быть права для создания записи.

*Постусловия*:

1. Создана новая запись в расписании для указанного пациента, услуги и специалиста.
2. Уведомление отправлено специалисту.


**Создать шаблон расписания**<br>

*Описание*: Данный вариант использования (ВИ) позволяет создать шаблон расписания специалиста.

*Участвующий актёр*: Сотрудник МЦ (медицинского центра)

*Основной поток событий (сценарий)*:

1. Сотрудник МЦ нажимает «Создать новое расписание».
2. Система отображает форму для создания шаблона расписания.

   * 2.1 Сотрудник МЦ вводит фамилию специалиста в поле для ввода.
      * 2.1.1 Система отображает выпадающий список подходящих специалистов.
         * 2.1.1.1 Требуемый специалист есть в списке:
            * 2.1.1.1.1 Сотрудник МЦ выбирает нужного специалиста и переходит к шагу 2.2.
         * 2.1.1.2 Требуемого специалиста нет в списке:
            * 2.1.1.2.1 Сотрудник МЦ нажимает кнопку «добавить нового специалиста».
            * 2.1.1.2.2 Система отображает форму добавления специалиста.
            * 2.1.1.2.3 Сотрудник МЦ заполняет необходимые поля и нажимает «сохранить».
               * 2.1.1.2.3.1 Сохранение успешно выполнено, система отправляет новому специалисту оповещение с учетными данными для авторизации в приложении, сотрудник МЦ переходит к шагу 2.2.
               * 2.1.1.2.3.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по ее устранению.
                  * 2.1.1.2.3.2.1 Сотрудник МЦ устраняет причины, которые привели к ошибке, и возвращается к шагу 2.1.

   * 2.2 Сотрудник МЦ выбирает период работы.
   * 2.3 Сотрудник МЦ выбирает время начала и окончания работы.

3. Сотрудник МЦ нажимает кнопку "Сохранить".

   * 3.1 Система проверяет расписание на конфликты.
      * 3.1.1 Конфликтов нет - расписание сохраняется, отображается сообщение об успешном сохранении.
      * 3.1.2 Обнаружены конфликты - отображается предупреждение с вариантами решения.
         * 3.1.2.1 Сотрудник МЦ подтверждает сохранение с конфликтами.
         * 3.1.2.2 Сотрудник МЦ корректирует данные и повторяет шаг 3.

*Предусловия*:

Сотрудник МЦ должен быть аутентифицирован и иметь права на создание шаблона расписания.

*Постусловия*:

Создан шаблон расписания для выбранного специалиста.
**Генерация расписания**<br>

*Описание*: Данный вариант использования (ВИ) позволяет автоматически распределить пациентов по свободным периодам в расписании.

*Участвующий актёр*: Сотрудник МЦ (медицинского центра)

*Основной поток событий (сценарий)*:

1. Сотрудник МЦ выбирает опцию «Генерация расписания».
2. Система отображает форму создания записи.
3. Сотрудник МЦ вводит фамилию пациента в поле для ввода.
4. Система отображает выпадающий список подходящих пациентов.

   * 4.1 Требуемый пациент есть в списке:
      * 4.1.1 Сотрудник МЦ выбирает необходимого пациента и переходит к шагу 5.
   * 4.2 Требуемого пациента нет в списке:
      * 4.2.1 Сотрудник МЦ нажимает кнопку «добавить нового пациента».
      * 4.2.2 Система отображает форму добавления пациента.
      * 4.2.3 Сотрудник МЦ заполняет необходимые поля и нажимает «сохранить».
         * 4.2.3.1 Сохранение выполнено успешно, сотрудник МЦ переходит к шагу 5.
         * 4.2.3.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по ее устранению.
            * 4.2.3.2.1 Сотрудник устраняет причины, которые привели к ошибке, и возвращается к шагу 4.2.3.

5. Сотрудник МЦ вводит наименование услуги в поле для ввода.
6. Система отображает выпадающий список подходящих услуг.

   * 6.1 Требуемая услуга есть в списке:
      * 6.1.1 Сотрудник МЦ выбирает необходимую услугу и переходит к шагу 7.
   * 6.2 Требуемой услуги нет в списке:
      * 6.2.1 Сотрудник МЦ нажимает кнопку «добавить новую услугу».
      * 6.2.2 Система отображает форму добавления услуги.
      * 6.2.3 Сотрудник МЦ заполняет необходимые поля и нажимает «сохранить».
         * 6.2.3.1 Сохранение выполнено успешно, сотрудник МЦ переходит к шагу 7.
         * 6.2.3.2 Сохранение не удалось. Отображается сообщение об ошибке с рекомендациями по ее устранению.
            * 6.2.3.2.1 Сотрудник устраняет причины, которые привели к ошибке, и возвращается к шагу 6.2.3.

7. Сотрудник МЦ выбирает желаемое время посещения для пациента и желаемого специалиста.
8. Сотрудник МЦ выбирает периодичность оказания услуги и ее длительность.
9. Сотрудник МЦ нажимает «Найти свободное место».
10. Система отображает сообщение с информацией о дате и времени начала оказания услуг, а также специалистах, оказывающих эти услуги.

*Предусловия*:

1. Сотрудник МЦ должен быть аутентифицирован и иметь права на изменение расписания.
2. В системе должно быть доступно расписание сотрудников с указанными свободными временными слотами.
3. Должны быть настроены правила и ограничения для автоматического распределения (например, максимальное количество записей в день для врача, приоритет для определенных категорий пациентов).

*Постусловия*:

1. Пациенты автоматически распределены по доступным временным слотам в расписании, согласно заданным критериям и правилам.
2. Для каждого распределенного пациента создана запись в расписании.

## Пользовательские истории

**Как менеджер, я могу редактировать расписание сотрудников, чтобы учитывать пожелания пациентов.** <br>

**Тесты:**

* Тест 1: Редактирование расписания доступно только сотрудникам с соответствующими правами доступа.
* Тест 2: Система предотвращает наложение записей при редактировании расписания.
* Тест 3: При изменении расписания автоматически отправляется уведомление сотруднику.
* Тест 4: Все правки расписания сохраняются в журнале изменений с указанием автора и времени.
* Тест 5: Изменения в расписании мгновенно отражаются во всех связанных системах.

---

**Как администратор, я могу просмотреть историю записи пациента, чтобы помочь ему найти специалиста, к которому он записан.** <br>

**Тесты:**

* Тест 1: История записей отображается только для авторизованных сотрудников.
* Тест 2: При отсутствии записей система показывает сообщение "История записей отсутствует".
* Тест 3: Для каждого посещения отображается дата, время, ФИО врача и кабинет приема.
* Тест 4: Доступен экспорт полной истории пациента в формате PDF с сохранением структуры данных.
* Тест 5: Доступна фильтрация истории по специализации врача (терапевт, хирург и др.).

---

**Как массажист, я могу видеть историю процедур пациента, чтобы учитывать актуальные и предыдущие назначения.** <br>

**Тесты:**

* Тест 1: История записей отображается только для авторизованных сотрудников.
* Тест 2: При отсутствии записей система показывает сообщение "История записей отсутствует".
* Тест 3: Можно фильтровать историю по дате (последние 3/6/12 месяцев).
* Тест 4: Для каждой процедуры отображается дата, длительность и комментарии.


## Функции системы

**Функция «Добавить нового сотрудника»** <br>

*   **Описание:** Предназначена для регистрации нового сотрудника в системе ScheduleX в случае его отсутствия в 1С:Поликлиника.

*   **Входные данные:**
    *   a. Личные данные (ФИО, дата рождения).
    *   b. Контактная информация (номер телефона).
    *   c. Профессиональные данные (специализация, перечень услуг).
    *   d. Учетные данные (логин и пароль).

*   **На выход:**
    *   e. Новая запись в базе данных сотрудников.
    *   f. SMS-сообщение сотруднику с регистрационными данными.

*   **Дополнительные сведения:**
    *   Функция доступна исключительно сотрудникам с соответствующими правами доступа.
    *   Выполняет проверку уникальности логина.
    *   Проверяет соответствие данных установленным форматам и требованиям к сложности пароля.
    *   При возникновении ошибок система информирует пользователя о некорректных полях, предупреждает о занятых логинах и сохраняет введенные данные для последующего исправления.

*   **Приоритет:** Высокий

---

**Функция «Создать расписание»** <br>

*   **Описание:** Предназначена для формирования шаблона графика работы медицинского персонала на указанный период с учетом их специализации и доступности ресурсов клиники.

*   **Входные данные:**
    *   a. Период планирования (дата начала и окончания).
    *   b. Список сотрудников с указанием их специализации.
    *   c. Перечень доступных кабинетов и оборудования.
    *   d. Учетные данные ответственного сотрудника.

*   **На выход:**
    *   Шаблон расписания на указанный период.
    *   Автоматические уведомления для сотрудников о назначенных сменах.
    *   Отчет о возможных конфликтах и перегрузках.

*   **Дополнительные сведения:**
    *   Созданный шаблон расписания становится доступным для просмотра всем уполномоченным сотрудникам через веб-интерфейс и мобильное приложение.

*   **Приоритет:** Высокий

**Функция «Просмотр расписания»** <br>

*   **Описание:** Предназначена для просмотра актуального расписания сотрудников, поиска и фильтрации данных о запланированных приемах по различным параметрам.

*   **Входные данные:**
    *   a. Параметры фильтрации (дата/интервал дат, сотрудник, специализация, услуга, пациент, кабинет, оборудование).

*   **На выход:**
    *   a. Список запланированных приемов.
    *   b. Визуализация занятости (цветовая индикация свободных/занятых слотов).

*   **Дополнительные сведения:**
    *   Система предоставляет интуитивно понятный интерфейс для многофакторного поиска с возможностью комбинирования параметров фильтрации.
    *   Функция автоматически учитывает уровень доступа пользователя, отображая только разрешенные для просмотра данные.

*   **Приоритет:** Высокий

---

**Функция «Автоматическая генерация расписания»** <br>

*   **Описание:** Предназначена для автоматического заполнения шаблона расписания конкретными записями на основе заданных предпочтений пациентов.

*   **Входные данные:**
    *   a. Персональные предпочтения: желаемое время посещений пациентов.
    *   b. Параметры услуг: периодичность, необходимая длительность.
    *   c. Организационные параметры: график работы кабинетов, доступность оборудования, нормы нагрузки на персонал.

*   **На выход:**
    *   Персонализированное расписание.

*   **Приоритет:** Высокий

## Требования к внешнему интерфейсу

**Общие требования к графическому интерфейсу** <br>

*   **Простота и интуитивность:**
    *   Интерфейс должен иметь простое расположение элементов управления.
    *   Интерфейс не должен быть перегружен большим количеством UI-элементов (максимальное количество кнопок на экране: 5).

*   **Единая дизайн-система:**
    *   Приложение должно использовать единую [дизайн-систему](https://github.com/user-attachments/assets/4f32aca8-7a35-4b04-bd83-502e1b981df7)

*   **Навигация:**
    *   Мобильная версия: Навигация снизу.
    *   Десктопная версия: Навигация слева.
    
Для визуализации пользовательского интерфейса мобильного приложения ScheduleX были разработаны макеты основных окон, отражающие ключевые варианты использования. <br>

_Авторизация_

* [Макет окна авторизации](https://github.com/user-attachments/assets/d42c1b65-5c36-4c50-8587-bb706416a999)
  
_Окно загрузки_
* [Макет окна загрузки](https://github.com/user-attachments/assets/3763a996-a350-4500-8925-3ce87ad185f5)

_Просмотр расписания_

*   [Макет окна просмотра расписания](https://github.com/user-attachments/assets/3ed1f524-9666-400a-9b0e-b76a87c33835)

_Редактирование карточки сотрудника_

*   [Макет окна редактирования карточки сотрудника](https://github.com/user-attachments/assets/aeda745a-ec84-471b-89d8-f12027952821)
     
_Уведомления_
*   [Макет окна уведомлений](https://github.com/user-attachments/assets/dd700d67-daad-4e1e-9429-660c5a8018e4)
      
## Нефункциональные требования

_Атрибуты качества_

*   **1.1 Безопасность и конфиденциальность:**
    *   Система должна обеспечивать конфиденциальность и сохранность используемой информации.

*   **1.2 Доступность:**
    *   Система должна работать непрерывно (в режиме 24/7).
    *   Допускаются технические работы для обновления системы длительностью не более одного часа, не чаще одного раза в месяц.

*   **1.3 Производительность:**
    *   Время ответа от сервера при запросе данных не должно превышать в среднем 5 секунд.
    *   Система должна обладать высокой производительностью (требуется уточнение критериев производительности).

*   **1.4 Удобство использования (Usability):**
    *   Система должна быть проста в изучении и использовании.
      

## Глоссарий

| Термин                     | Описание                                                                                                                                                                |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Расписание                | График работы медицинского персонала, включающий запланированные приемы пациентов, время работы кабинетов и оборудования.                                                      |
| Слот                       | Временной интервал, выделенный для приема одного пациента (например, 09:00–09:30).                                                                                          |
| Шаблон расписания          | Предустановленные правила формирования графиков (например, стандартное время приема, перерывы).                                                                            |
| Администратор               | Сотрудник МЦ с правами управления расписанием, редактирования данных и настройки системы.                                                                                |
| Врач/Специалист            | Медицинский работник, для которого формируется расписание.                                                                                                                |
| Менеджер                   | Сотрудник, ответственный за запись пациентов и корректировку расписания.                                                                                                  |
| Автоматическая генерация   | Создание расписания системой на основе заданных правил (специализация, загруженность, доступность ресурсов).                                                               |
| Ручное редактирование      | Возможность корректировки автоматически созданного расписания.                                                                                                             |
| Конфликт расписания         | Ситуация, когда один временной слот пытаются занять несколько пациентов или сотрудников.                                                                                   |
| Оффлайн-режим             | Работа с локальной копией данных при отсутствии интернета с последующей синхронизацией.                                                                                    |
| 1С:Поликлиника            | Внешняя система, с которой синхронизируются данные о пациентах, услугах и сотрудниках.                                                                                       |
| JSON/XML                   | Форматы обмена информацией между модулями системы.                                                                                                                        |
| Кэш                        | Временное хранилище данных при отсутствии связи с сервером.                                                                                                               |
| Подтвержденная запись       | Прием, согласованный пациентом и врачом.                                                                                                                                 |
| Перенесенная запись        | Измененное время приема с сохранением в истории.                                                                                                                          |
| Экстренная отмена           | Автоматическая отметка в расписании при форс-мажоре. 

## Моделирование

**IDEF0**
<a id="контекстная-диаграмма-основной-функции-ис"></a>
Контекстная диаграмма основной функции "Управление расписанием"<br>
<img src="https://github.com/user-attachments/assets/cc42ba01-3ff0-4294-abb3-698cf695c14e" alt="IDEF0" width="500" height="250"><br>
Диаграмма декомпозиции процесса <br>
<img src="https://github.com/user-attachments/assets/63682799-1490-4386-890e-fa78767111c3" alt="IDEF0" width="700" height="300"><br>

**Процесс управления расписанием в нотации BPMN.**
<a id="моделирование-бизнес-процессов"></a>
<img src="https://github.com/user-attachments/assets/a0cb425a-dcd1-4bf8-a1bf-e4be815e4ce0" alt="BPMN" width="800" height="550"><br>

**UML**<br>
Use Case <br>
<a id="диаграмма-вариантов-использования"></a>
<img src="https://github.com/user-attachments/assets/69195552-39d9-41b2-a550-fcaded25f346" alt="Use Case" width="600" height="750"> <br>

Диаграмма состояний объекта «расписание»<br>
<img src="https://github.com/user-attachments/assets/dfe544dd-c511-4bdb-84a7-f62e9305a684" alt="State Diagram" width="800" height="400"> <br>

Диаграмма последовательности для процесса создания новой записи <br>
<img src="https://github.com/user-attachments/assets/357f2927-d100-4aed-832e-4f72f1e6d331" alt="Sequence Diagram" width="400" height="700"> <br>

**DFD**<br>
<a id="диаграмме-потоков-данных"></a>
![image](https://github.com/user-attachments/assets/d7125bc6-7112-4dbb-959e-5664ec512995)<br> 

**Figma**<br>

<a id="дизайн-система"></a>
![image](https://github.com/user-attachments/assets/4f32aca8-7a35-4b04-bd83-502e1b981df7) <br>

<img src="https://github.com/user-attachments/assets/d42c1b65-5c36-4c50-8587-bb706416a999" alt="Авторизация" width="300" height="650"><img src="https://github.com/user-attachments/assets/3763a996-a350-4500-8925-3ce87ad185f5" alt="Загрузка" width="300" height="650"><img src="https://github.com/user-attachments/assets/3ed1f524-9666-400a-9b0e-b76a87c33835" alt="Расписание" width="300" height="650"><img src="https://github.com/user-attachments/assets/aeda745a-ec84-471b-89d8-f12027952821" alt="Профиль" width="300" height="650"><img src="https://github.com/user-attachments/assets/dd700d67-daad-4e1e-9429-660c5a8018e4" alt="Уведомления" width="300" height="650"><br>

## Стек технологий и методологий, используемых для разработки требований

| Категория           | Инструменты                                      |
|--------------------|---------------------------------------------------|
| Методологии анализа | [Диаграмма Ишикавы](https://github.com/ElenaDanchenko/ScheduleX/blob/main/%D0%94%D0%B8%D0%B0%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D1%8B/Ishikava_v1.png)|                                  |
| Моделирование       | [BPMN](https://github.com/user-attachments/assets/a0cb425a-dcd1-4bf8-a1bf-e4be815e4ce0), [IDEF0](https://github.com/user-attachments/assets/cc42ba01-3ff0-4294-abb3-698cf695c14e), [UML](https://github.com/user-attachments/assets/69195552-39d9-41b2-a550-fcaded25f346), [DFD](https://github.com/user-attachments/assets/8008c1f5-5b20-479b-a0c2-ceb8a7f81d47) |
| Прототипирование    | [Figma](https://github.com/user-attachments/assets/d42c1b65-5c36-4c50-8587-bb706416a999)|  






