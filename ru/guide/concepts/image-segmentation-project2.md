# Проект 2. Выделить объект на изображении

В этом [проекте](../../glossary.md#project-ru) исполнители будут выделять области изображений, содержащие дорожный знак. В качестве исходных изображений используйте результаты из [первого проекта](image-segmentation-project1.md).

## Создайте проект {#create-project}

#### В интерфейсе:

1. Выберите шаблон:

    1. Нажмите кнопку **Создать проект**.
    1. Выберите шаблон **Распознавание объектов и выделение областей**.
    1. Нажмите **Использовать решение**.

1. Заполните общую информацию:

    1. В поле **Название для исполнителей** проекта введите `Обведите дорожные знаки на изображении`.
    1. В поле **Описание для исполнителей** введите `Обведите прямоугольником все дорожные знаки на изображении`.
    1. По желанию добавьте **Приватный комментарий**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    #### Конструктор шаблонов

    1. Вы можете воспользоваться {% if locale == "ru-ru" %}[готовым кодом](https://clck.ru/TwQpa){% endif %} для этого проекта, где уже настроена валидация и внешний вид задания.

    Исполнитель не сможет отправить задание, если не выделит области изображений.

    Подробнее в Справке конструктора о шаблоне [Выделение объектов на картинке]({{ tb-select-areas }}) и о его настройках.

    1. Чтобы увидеть поля входных и выходных данных, в разделе {% if locale == "ru-ru" %}**Спецификация данных**{% endif %}{% if locale == "en-com" %}**Data specification**{% endif %} нажмите {% if locale == "ru-ru" %}**Показать спецификации**{% endif %}{% if locale == "en-com" %}**Show specifications**{% endif %}.

    - Поле входных данных: `image` — строка для загрузки картинки.

    - Поле выходных данных: `result` — поле, в которое будет занесена информация о разметке загруженного изображения.

    #### Редактор HTML/CSS/JS

    1. В блоке {% if locale == "ru-ru" %}**Интерфейс задания**{% endif %}{% if locale == "en-com" %}**Task interface**{% endif %} оставьте без изменений блок **HTML**.

    1. Отредактируйте блок **CSS**:

    1. Настройте инструменты выделения области. В этом шаблоне используется [Редактор для выделения области](t-components/image-annotation.md). Для него доступны инструменты прямоугольник и многоугольник (по умолчанию).

    Чтобы настроить выделение прямоугольником, замените код в блоке **CSS** на указанный:
    ```
    .image-annotation-editor__shape-polygon {
    display: none;
    }
    ```

    1. Введите код для настройки высоты интерфейса по размеру изображения:

    ```
    .image-annotation-editor__annotation-layer {
    height: max-content;
    }
    ```

    1. **(опционально)** Вы можете попросить исполнителей ввести аннотацию к выделенной области или выбрать ее из списка. Для этого в блоке **JS** добавьте элемент интерфейса. Например, текстовое поле или выпадающий список.

    Подробнее об [аннотации](t-components/image-annotation.md#annotation).

    1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.png) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

    {% note info %}

    В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

    {% endnote %}

    1. В открывшемся окне проверьте работу опций задания. И в правом нижнем углу нажмите кнопку {% if locale == "ru-ru" %}**Отправить**{% endif %}{% if locale == "en-com" %}**Submit**{% endif %}.

    1. Выйдите из режима предпросмотра. В нижнем левом углу нажмите кнопку {% if locale == "ru-ru" %}**Выйти**{% endif %}{% if locale == "en-com" %}**Exit**{% endif %}{% if locale == "ru-ru" %}** → Выйти**{% endif %}{% if locale == "en-com" %}**Exit**{% endif %} . Если при тестировании задания были ошибки — проверьте блоки кода, которые вы вводили.

1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. Напишите инструкцию для исполнителей:

    #### Текст инструкции
    Нажмите кнопку ![](../_images/tutorials/image-segmentation/rectangle-button.png) и обведите прямоугольником все дорожные знаки на изображении.

    {% note info %}

    Если вы хотите добавить в инструкцию примеры выполнения задания, выполните его самостоятельно в режиме предпросмотра. Сделайте скриншоты, загрузите их на фотохостинг{% if locale == "ru-ru" %}, ваш Яндекс Диск{% endif %} или в облачное хранилище и вставьте ссылки на изображения в инструкцию, нажав кнопку ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.png) на панели инструментов.

    {% endnote %}

    Нажмите кнопку **Завершить**.

## Создайте пул {#create-pool}

Пул — это набор оплачиваемых заданий, которые одновременно выдаются исполнителям.

1. Откройте страницу проекта **Обведите все дорожные знаки на картинке**.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить пул**{% endif %}{% if locale == "en-com" %}**Add a pool**{% endif %}.

1. Укажите {% if locale == "ru-ru" %}**Название пула**{% endif %}{% if locale == "en-com" %}**Pool name**{% endif %}.

1. {% if locale == "ru-ru" %}
    (опционально) Укажите **Приватный комментарий**{% if locale == "en-com" %}**Private comment**{% endif %}. Эта информация доступна только вам.
    {% endif %}
1. В блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} отфильтруйте исполнителей:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Добавьте фильтры {% if locale == "ru-ru" %}**Регион по номеру телефона**{% endif %}{% if locale == "en-com" %}**Region by phone number**{% endif %} и {% if locale == "ru-ru" %}**Языки**{% endif %}{% if locale == "en-com" %}**Languages**{% endif %}: выберите исполнителей из России, Украины, Казахстана и Беларуси, которые в своем профиле отметили знание русского языка.

    1. Добавьте новый навык. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить навык**{% endif %}{% if locale == "en-com" %}**Add skill**{% endif %}.

    1. В открывшемся окне в поле {% if locale == "ru-ru" %}**Название**{% endif %}{% if locale == "en-com" %}**Title**{% endif %} введите `Выделение областей`.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

    {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. {% include [contain_item-pool-speed-quality](../_includes/concepts/contain_item/id-contain_item/pool-speed-quality.md) %}

1. В блоке {% if locale == "ru-ru" %}**Цена**{% endif %}{% if locale == "en-com" %}**Price**{% endif %} в поле {% if locale == "ru-ru" %}**Цена за страницу заданий**{% endif %}{% if locale == "en-com" %}**Price per task suite**{% endif %} укажите цену. Например, `0.01`.

    #### Что такое страница заданий?

    На одной странице может отображаться одно или несколько заданий. Если задания простые, то можно добавлять 10–20 заданий на одну страницу. Не рекомендуем создавать длинные страницы, поскольку это снизит скорость загрузки данных у исполнителя.

    Исполнитель получит оплату, только если выполнил все задания на странице.

    Количество заданий на странице вы определите при [загрузке заданий](#smart-mixing).

    #### Как определить справедливую цену?

    Общее правило формирования цены — чем больше времени исполнитель тратит на выполнение, тем выше цена.

    Вы можете зарегистрироваться в Толоке как исполнитель и узнать, сколько платят другие заказчики за задания.

1. [Правила контроля качества](control.md) позволяют отсеивать невнимательных исполнителей. В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} задайте правила для пула:

    1. Включите опцию {% if locale == "ru-ru" %}**Отложенная приёмка**{% endif %}{% if locale == "en-com" %}**Non-automatic acceptance**{% endif %}.

    #### Что такое отложенная приемка?

    [Отложенная приемка](offline-accept.md) позволяет вам просматривать [выполненные страницы заданий](../../glossary.md#submitted-answers-ru) перед тем, как принять их и заплатить исполнителю. Задания, выполненные в несоответствии с инструкцией, можно отклонять. Максимальный срок проверки устанавливается в поле **Срок проверки**.

    В поле {% if locale == "ru-ru" %}**Срок проверки в днях**{% endif %}{% if locale == "en-com" %}**Review period in days**{% endif %} укажите количество дней на проверку задания.

    1. Добавьте следующие правила контроля качества:
    - {% if locale == "ru-ru" %}**Обработка отклоненных и принятых заданий**{% endif %}{% if locale == "en-com" %}**Recompletion of rejected assignments**{% endif %} — отправляет отклоненные вами задания другим исполнителям по заданным правилам.

    1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Обработка отклоненных и принятых заданий**{% endif %}{% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %}.

    1. Задайте правило для отклоненного задания: если {% if locale == "ru-ru" %}**задание становится отклоненным**{% endif %}{% if locale == "en-com" %}**assignment becomes rejected**{% endif %}, то {% if locale == "ru-ru" %}**увеличить перекрытие**{% endif %}{% if locale == "en-com" %}**extend overlap by**{% endif %} на **1**. А также включите опцию {% if locale == "ru-ru" %}**Открыть пул, если закрыт**{% endif %}{% if locale == "en-com" %}**Open pool if closed**{% endif %}.
    {% if locale == "ru-ru" %}![](../_images/other/rejected-accepted-tasks.png){% endif %}
    Это означает, что отклоненное задание будет возвращено в пул и показано еще одному исполнителю.

    - {% if locale == "ru-ru" %}**Выполненные задания**{% endif %}{% if locale == "en-com" %}**Submitted responses**{% endif %} — позволяет ограничить количество заданий, которое доступно исполнителю в пуле за сутки.

    1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Выполненные задания**{% endif %}{% if locale == "en-com" %}**Submitted responses**{% endif %}.

    1. Задайте правило для выполненного задания: если {% if locale == "ru-ru" %}**отправленных страниц заданий**{% endif %}{% if locale == "en-com" %}**submitted assignments**{% endif %} **≥ 1**, то {% if locale == "ru-ru" %}**установить значение навыка**{% endif %}{% if locale == "en-com" %}**assign skill value**{% endif %} **Выделение областей** равным **1**.
    {% if locale == "ru-ru" %}![](../_images/tutorials/image-segmentation/select-object-tutorial2.png){% endif %}
    Такие параметры позволят отметить исполнителя, выполнившего хотя бы одно задание в пуле.

    {% note info %}

    Если навык **Выделение областей** не отображается в списке, сохраните пул и откройте его заново для редактирования.

    {% endnote %}

    - {% if locale == "ru-ru" %}**Быстрые ответы**{% endif %}{% if locale == "en-com" %}**Fast responses**{% endif %} — отсеивает исполнителей, которые отвечают слишком быстро.

    1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Быстрые ответы**{% endif %}{% if locale == "en-com" %}**Fast responses**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Учитывать последних страниц заданий**{% endif %}{% if locale == "en-com" %}**Recent tasks suites to use**{% endif %} введите количество последних страниц заданий, выполненных исполнителем. Например, `5`.
    1. В поле {% if locale == "ru-ru" %}**Минимальное время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Minimum time per task suite**{% endif %} укажите время в секундах. Например, `20`.
    1. Задайте правило для быстрого ответа: если {% if locale == "ru-ru" %}**количество быстрых ответов**{% endif %}{% if locale == "en-com" %}**number of fast responses**{% endif %}**≥ 1**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**у меня**{% endif %}{% if locale == "en-com" %}**on requester**{% endif %} на {% if locale == "ru-ru" %}**10 дней**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В поле {% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} введите **Быстрые ответы**.
    {% if locale == "ru-ru" %}![](../_images/other/fast-answers2.png){% endif %}
    Это означает, что если исполнитель выполнит хотя бы одну [страницу заданий](../../glossary.md#task-page-ru) быстрее чем за 20 секунд, он будет заблокирован и не сможет больше выполнять ваши задания 10 дней.

    - {% if locale == "ru-ru" %}**Результаты проверки**{% endif %}{% if locale == "en-com" %}**Results of assignment review**{% endif %} — ограничивает доступ к пулу исполнителей, которые часто ошибаются.

    1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Результаты проверки**{% endif %}{% if locale == "en-com" %}**Results of assignment review**{% endif %}.

    1. Задайте правило для отклоненного задания: если {% if locale == "ru-ru" %}**количество проверенных ответов**{% endif %}{% if locale == "en-com" %}**total reviewed responses**{% endif %} **≥ 3** и {% if locale == "ru-ru" %}**процент отклоненных ответов**{% endif %}{% if locale == "en-com" %}**rejected responses (%)**{% endif %} **> 35** то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**у меня**{% endif %}{% if locale == "en-com" %}**on requester**{% endif %} на {% if locale == "ru-ru" %}**15 дней**{% endif %}{% if locale == "en-com" %}**15 days**{% endif %}.
    {% if locale == "ru-ru" %}![](../_images/other/offline-accept.png){% endif %}
    Это означает, что если 35% и более ответов исполнителя будут отклонены, он будет заблокирован и не сможет больше выполнять ваши задания 15 дней. Правило начинает действовать после проверки 3 ответов исполнителя.

    [Контрольные задания](../../glossary.md#control-task-ru) и [мнение большинства](../../glossary.md#majority-vote-ru) не используются для такого типа проектов, так как разметка областей, предоставленная исполнителями, должна совпадать (что практически невозможно). Подробнее о контроле качества читайте в разделе [Контроль качества](control.md).

    {% note info %}

    Вы можете скопировать настройки контроля качества из другого пула. Для этого в блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} нажмите кнопку {% if locale == "ru-ru" %}**перенесите их из другого пула**{% endif %}{% if locale == "en-com" %}**copy them from another pool**{% endif %}.

    {% endnote %}

1. В разделе {% if locale == "ru-ru" %}**Перекрытие задания**{% endif %}{% if locale == "en-com" %}**Task overlap**{% endif %} в поле {% if locale == "ru-ru" %}**Количество исполнителей, которые должны выполнить каждое задание **{% endif %}{% if locale == "en-com" %}**The number of performers to complete every task**{% endif %} установите перекрытие — количество исполнителей, которые должны выполнить задание. Для заданий выделения области на картинках, как правило, `1`.

1. В блоке {% if locale == "ru-ru" %}**Дополнительные настройки**{% endif %}{% if locale == "en-com" %}**Additional settings**{% endif %} укажите значение поля {% if locale == "ru-ru" %}**Время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Time per task suite**{% endif %}. Времени должно быть достаточно, в том числе для чтения инструкции и загрузки задания. Например, `1200` секунд.
1. Нажмите кнопку {% if locale == "ru-ru" %}**Создать пул**{% endif %}{% if locale == "en-com" %}**Create a pool**{% endif %}.


## Подготовьте и загрузите задания {#upload-file}

1. Подготовьте [файл с заданиями](../../glossary.md#tsv-file-definition-ru).

    1. Откройте в редакторе текста или электронных таблиц файл, полученный после агрегации результатов в [первом проекте](image-segmentation-project1.md).

    1. Выберите изображения, подходящие для текущего проекта (значение **OK**).

    {% note info %}

    Для отбора изображений на устройствах с Linux и MacOS вы можете воспользоваться командами awk:
    ```
    awk 'BEGIN {OFS = FS = "\t";} $2=/OK/ {print $1}' <aggregated_res>.tsv > <filtered_res>.tsv
    ```

    {% endnote %}

    1. Скопируйте столбец с выделенными ссылками на новый лист или в новый документ.

    1. Задайте имя столбца `INPUT:image`. Если вы хотите задать другое имя, переименуйте столбец и в исходном файле с результатами.

    1. Сохраните файл в формате `tsv`.

1. Загрузите получившийся файл с заданиями:

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне настройте параметры загрузки файла.

    1. Выберите {% if locale == "ru-ru" %}**Указать вручную**{% endif %}{% if locale == "en-com" %}**Set manually**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Заданий на странице**{% endif %}{% if locale == "en-com" %}**Tasks per page**{% endif %} укажите `1`.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}.

    1. В открывшемся окне выберите файл с заданиями для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

    1. В открывшемся окне проверьте количество заданий и нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

1. Нажмите кнопку ![](../_images/other/b-start-pool.png), чтобы запустить пул.

    {% note warning %}

    Поставленные задачи выполнят настоящие исполнители Толоки. Перепроверьте конфигурацию вашего проекта перед запуском пула.

    {% endnote %}


## Получите результаты {#get-results}

1. На странице пула нажмите кнопку {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %}. В открывшемся окне:

    1. В блоке {% if locale == "ru-ru" %}**Статус**{% endif %}{% if locale == "en-com" %}**Status**{% endif %} оставьте включенной только опцию {% if locale == "ru-ru" %}**Непроверенные**{% endif %}{% if locale == "en-com" %}**Submitted**{% endif %}.

    1. В блоке {% if locale == "ru-ru" %}**Поля**{% endif %}{% if locale == "en-com" %}**Columns**{% endif %} оставьте включенной только опцию {% if locale == "ru-ru" %}**id ответа**{% endif %}{% if locale == "en-com" %}**assignment ID**{% endif %}.

    1. Отключите опцию {% if locale == "ru-ru" %}**Разделять ответы пустой строкой**{% endif %}{% if locale == "en-com" %}**Separate assignments with empty row**{% endif %}.{% if locale == "ru-ru" %}![](../_images/tutorials/image-segmentation/wsdm-tutorial-part3-2.png){% endif %}

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %}.

1. Используйте файл с результатами в [третьем проекте](image-segmentation-project3.md).



## Что дальше {#what-next}

- Создайте [Проект 3](image-segmentation-project3.md) для проверки ответов.

{% include [contact-support](../_includes/contact-support-help.md) %}