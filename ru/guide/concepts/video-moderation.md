# Классификация видео

{% include [deprecate](../../_includes/deprecate.md) %}

{% note tip %}

Сначала запустите проект в [Песочнице]({{ sandbox }}). Так вы сможете избежать ошибок и потраченных средств, если окажется, что ваше задание не работает.

{% endnote %}

[Проекты](../../glossary.md#project) этого типа предназначены для классификации видео. Вы можете использовать их для:

- модерации контента;
- распределения видео по заданным категориям;
- оценки, насколько видео нравится исполнителям;
- оценки видео на наличие шумов и других визуальных недостатков.

Например, у вас есть много видеороликов, и нужно определить, какие из них более качественные. Для этого создайте задание, в котором исполнители посмотрят видео и оценят их качество.

## Перед началом {#before_start}

- Чтобы использовать в проекте свои видео, вам нужно загрузить их в хранилище, из которого вы сможете получить ссылки на файлы. Например, ваш сервер, видеохостинг или облачное хранилище:

    - [Инструкция](use-object-storage.md) по использованию файлов с Yandex Cloud.

    - {% if locale == "ru-ru" %}[Инструкция](prepare-data.md) по использованию файлов с Яндекс Диска.{% endif %}

    - Если вы используете видео с YouTube, замените ссылки вида `https://www.youtube.com/watch?v=example` на `https://www.youtube.com/embed/example`.

- Убедитесь, что видео отображаются одинаково в компьютерной и мобильной версиях Толоки. Видео может не воспроизводиться или воспроизводиться неверно в мобильной версии. В этом случае при создании пула ограничьте доступ исполнителям с мобильных устройств.

    Подробнее о [настройке заданий для мобильных устройств](mobile.md).

    {% note info %}

    Видеоплеер поддерживает только формат .mp4 с кодировкой H.264 или H.265.

    {% endnote %}

- Если у вас сложный проект, зарегистрируйтесь в [песочнице](sandbox.md) и создайте проект там. В ней вы сможете:

    1. Протестировать настройки проекта в качестве исполнителя.

    1. Затем [перенести](sandbox.md#export) их в {% if locale == "ru-ru" %}**основную версию Толоки**{% endif %}{% if locale == "en-com" %}**production version**{% endif %}.

    1. Запустить для реальных исполнителей.

    Так вы сможете избежать ошибок и напрасно потраченных средств, если окажется, что ваше задание не работает.

## Создайте проект {#create-project}

Откройте [Толоку для заказчика]({{ yandex-toloka }}).

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. Выберите пресет {% if locale == "ru-ru" %}**Классификация жестов рук**{% endif %}{% if locale == "en-com" %}**Hand gesture classification**{% endif %}.

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. {% include [toloka-requester-source-interface-def](../_includes/toloka-requester-source/id-toloka-requester-source/interface-def.md) %}

          Для этого проекта воспользуйтесь готовым шаблоном, где уже настроена валидация, горячие клавиши и внешний вид задания. Исполнитель не сможет отправить задание, если не выберет вариант ответа.

          Подробнее в Справке конструктора шаблонов:

          - [настройка условий](../../template-builder/best-practices/conditions.md);

          - настройка шаблона [Оценка видео](../../template-builder/templates/video-moderation.md).

      1. {% include [toloka-requester-source-tb-input-output_1](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output_1.md) %}

          В данном проекте:

          - Поле входных данных: `video` — ссылка для загрузки видео.

          - Поле выходных данных: `result` — строка, в которую будет записан ответ исполнителя.

    - Редактор HTML/CSS/JS

      1. {% include [toloka-requester-source-interface-html-block](../_includes/toloka-requester-source/id-toloka-requester-source/interface-html-block.md) %}

          #### Если вы используете видео с YouTube

          Добавьте в интерфейс элемент **Встроенный фрейм**:

          ```html
          <iframe src=not_var{{video}} width="560" height="315" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          ```

      1. В блоке **Спецификация данных** задаются поля входных и выходных данных.

          {% cut "Что такое входные и выходные данные?" %}

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

          {% include [toloka-requester-source-html-specification](../_includes/toloka-requester-source/id-toloka-requester-source/html-specification.md) %}

          {% endcut %}

          В данном проекте:

          - Поле входных данных: `video` — ссылка для загрузки видео.

          {% note warning %}

          Если вы используете видео с **YouTube**, для входного поля `video` укажите тип данных строка.

          {% endnote %}

          - Поле выходных данных: `result` — строка, в которую будет записан ответ исполнителя.

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

          {% note info %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. {% include [toloka-requester-source-test-item-1](../_includes/toloka-requester-source/id-toloka-requester-source/test-item-1.md) %}

      1. {% include [toloka-requester-source-exit-preview](../_includes/toloka-requester-source/id-toloka-requester-source/exit-preview.md) %}

      1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

    {% endlist %}

1. 1. Напишите краткую и ясную инструкцию. Опишите в ней, что надо сделать, и приведите примеры.

    Вы можете подготовить инструкцию в формате HTML и вставить ее в редактор. Чтобы переключиться в режим HTML, нажмите **<>**.

    1. Нажмите **Завершить**.

Подробнее о работе с проектом читайте в разделе [проект](project.md).

## Создайте пул {#create-pool}

Пул — это набор оплачиваемых заданий, которые одновременно выдаются исполнителям.

1. Откройте страницу проекта по оценке качества видео.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить пул**{% endif %}{% if locale == "en-com" %}**Add a pool**{% endif %}.

1. Укажите {% if locale == "ru-ru" %}**Название пула**{% endif %}{% if locale == "en-com" %}**Pool name**{% endif %}.

1. (опционально) Укажите приватное описание:

    1. Включите опцию {% if locale == "ru-ru" %}**Добавить приватное описание**{% endif %}{% if locale == "en-com" %}**Add a private description**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Приватное описание**{% endif %}{% if locale == "en-com" %}**Private description**{% endif %} введите описание пула. Эта информация доступна только вам.

1. В блоке **Аудитория** добавьте **Фильтры** для отбора исполнителей.

    - Чтобы задание было доступно только исполнителям, владеющим русским языком:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Добавьте фильтры {% if locale == "ru-ru" %}**Регион по номеру телефона**{% endif %}{% if locale == "en-com" %}**Region by phone number**{% endif %} и {% if locale == "ru-ru" %}**Языки**{% endif %}{% if locale == "en-com" %}**Languages**{% endif %}: выберите исполнителей из России, Украины, Казахстана и Беларуси, которые в своем профиле отметили знание русского языка.

    - {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. {% include [contain_item-pool-speed-quality](../_includes/concepts/contain_item/id-contain_item/pool-speed-quality.md) %}

1. В блоке **Цена** установите цену за страницу заданий, например 0,02 $.

    {% cut "Что такое страница заданий?" %}

    На одной странице может отображаться одно или несколько заданий. Если задания простые, то можно добавлять 10–20 заданий на одну страницу. Не рекомендуем создавать длинные страницы, поскольку это снизит скорость загрузки данных у исполнителя.

    Исполнитель получит оплату, только если выполнил все задания на странице.

    Количество заданий на странице вы определите при [загрузке заданий](#smart-mixing).

    {% endcut %}

    {% cut "Как определить справедливую цену?" %}

    Общее правило формирования цены — чем больше времени исполнитель тратит на выполнение, тем выше цена.

    Вы можете зарегистрироваться в Толоке как исполнитель и узнать, сколько платят другие заказчики за задания.

    {% endcut %}

1. [Правила контроля качества](control.md) позволяют отсеивать невнимательных исполнителей. В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} добавьте:

    - {% if locale == "ru-ru" %}**Контрольные задания**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %} — отсеивает исполнителей, которые часто ошибаются в контрольных заданиях.

    1. Нажмите {% if locale == "ru-ru" %}**Добавить блок контроля качества**{% endif %}{% if locale == "en-com" %}**Add Quality Control Rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Контрольные задания**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %}.

    1. Задайте правило для контрольного задания: если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %} на контрольные вопросы **≥ 3** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%)**{% endif %} на контрольные вопросы **< 60**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %} исполнителя {% if locale == "ru-ru" %}**на проекте на 10 дней**{% endif %}{% if locale == "en-com" %}**on project**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В качестве причины укажите **Контрольное задание**.

        {% if locale == "ru-ru" %}![](../_images/tutorials/image-segmentation/wsdm-tutorial-part1-2.png){% endif %}

        Это означает, что если исполнитель выполнил более трех контрольных заданий и дал неправильные ответы более чем в 60% из них, он будет заблокирован и не сможет выполнять задания на этом проекте в течение 10 дней.

    - {% if locale == "ru-ru" %}**Быстрые ответы**{% endif %}{% if locale == "en-com" %}**Fast responses**{% endif %} — отсеивает исполнителей, которые отвечают слишком быстро.

    1. В поле {% if locale == "ru-ru" %}**Учитывать последних страниц заданий**{% endif %}{% if locale == "en-com" %}**Recent values to use**{% endif %} введите количество последних страниц заданий, выполненных исполнителем. Например, `5`.

    1. В поле {% if locale == "ru-ru" %}**Минимальное время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Minimum time per task suite**{% endif %} укажите время в секундах. Например, `20`.

    1. Задайте правило для быстрого ответа: если {% if locale == "ru-ru" %}**количество быстрых ответов**{% endif %}{% if locale == "en-com" %}**number of fast responses**{% endif %}** ≥ 1**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**у меня**{% endif %}{% if locale == "en-com" %}**on requester**{% endif %} на {% if locale == "ru-ru" %}**10 дней**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В поле {% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} введите **Быстрые ответы**.

        {% if locale == "ru-ru" %}![](../_images/other/fast-answers2.png){% endif %}

        Это означает, что если исполнитель выполнит хотя бы одну страницу заданий быстрее, чем за 20 секунд, он не сможет выполнять ваши задания 10 дней.

    - {% if locale == "ru-ru" %}**Мнение большинства**{% endif %}{% if locale == "en-com" %}**Majority vote**{% endif %} — контроль на основе ответов большинства исполнителей.

    1. В поле {% if locale == "ru-ru" %}**Считать большинством**{% endif %}{% if locale == "en-com" %}**Accept as majority**{% endif %} укажите `2`.

    1. Задайте правило: если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %} **≥ 5** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%)**{% endif %} **< 50**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %} исполнителя {% if locale == "ru-ru" %}**на проекте на 10 дней**{% endif %}{% if locale == "en-com" %}**on project**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В качестве причины укажите **Не совпадает с большинством**.

        {% if locale == "ru-ru" %}![](../_images/tutorials/video-moderation/majority-vote2.png){% endif %}

        Это означает, что если исполнитель выполнил более десяти заданий, и его ответы не совпали с мнением большинства других исполнителей, он не сможет выполнять задания на этом проекте в течение 10 дней.

        {% note info %}

        Правило начинает действовать, когда количество ответов на задание равно перекрытию. Чтобы быстрее получить нужное число ответов, включите опцию {% if locale == "ru-ru" %}**Сохранять порядок заданий**{% endif %}{% if locale == "en-com" %}**Keep task order**{% endif %} в [настройках пула](#pool-parameters).

        {% endnote %}

    - {% if locale == "ru-ru" %}**Капча**{% endif %}{% if locale == "en-com" %}**Captcha**{% endif %} — предотвращает выполнение заданий роботами.

    1. В поле {% if locale == "ru-ru" %}**Учитывать последних вводов капчи**{% endif %}{% if locale == "en-com" %}**Recent values to use**{% endif %} введите количество последних страниц заданий, выполненных исполнителем. Например, `10`.

    1. Задайте правило для капчи: если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %}** ≥ 5** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%) **{% endif %}**< 65**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**на проекте**{% endif %}{% if locale == "en-com" %}**on project**{% endif %} на {% if locale == "ru-ru" %}**10 дней**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В поле {% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} введите **Капча**.

        Это означает, что если исполнитель верно вводит капчу менее чем в 65% случаев, он не сможет выполнять задания на проекте в течение 10 дней.

        {% note info %}

        Вы можете скопировать настройки контроля качества из другого пула. Для этого в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Users filter**{% endif %} нажмите кнопку {% if locale == "ru-ru" %}**Скопировать настройки из...**{% endif %}{% if locale == "en-com" %}**Copy settings from...**{% endif %}.

        {% endnote %}

1. Установите перекрытие — количество исполнителей, которые должны выполнить задание. В разделе {% if locale == "ru-ru" %}**Перекрытие**{% endif %}{% if locale == "en-com" %}**Overlap**{% endif %} укажите значение поля {% if locale == "ru-ru" %}**Перекрытие**{% endif %}{% if locale == "en-com" %}**Overlap**{% endif %}. Для заданий этого типа, как правило, `3-5`.

1. Укажите {% if locale == "ru-ru" %}**Дополнительные настройки**{% endif %}{% if locale == "en-com" %}**Additional settings**{% endif %} пула:

    1. Укажите значение поля {% if locale == "ru-ru" %}**Время на страницу заданий в секундах**{% endif %}{% if locale == "en-com" %}**Time for completing a task page in seconds**{% endif %}. Времени должно быть достаточно для чтения инструкции, загрузки задания, просмотра видео и ответа. Например, `1200` секунд.

    1. Включите опцию {% if locale == "ru-ru" %}**Сохранять порядок заданий**{% endif %}{% if locale == "en-com" %}**Keep task order**{% endif %}.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Сохранить**{% endif %}{% if locale == "en-com" %}**Save**{% endif %}.

## Загрузите задания {#upload-file}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. На странице пула нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне вы можете скачать шаблон файла с заданиями.

1. Настройте параметры загрузки файла:

    1. Выберите {% if locale == "ru-ru" %}**Умное смешивание**{% endif %}{% if locale == "en-com" %}**Smart mixing**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Основных заданий**{% endif %}{% if locale == "en-com" %}**Main tasks**{% endif %} укажите `9`.

    1. В поле {% if locale == "ru-ru" %}**Обучающих заданий**{% endif %}{% if locale == "en-com" %}**Training tasks**{% endif %} укажите `0`.

    1. В поле {% if locale == "ru-ru" %}**Контрольных заданий**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %} укажите `1`.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}.

    1. В открывшемся окне выберите файл с заданиями для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

    1. В открывшемся окне проверьте количество заданий и нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

1. Создайте [контрольное задание](goldenset.md):

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Разметить**{% endif %}{% if locale == "en-com" %}**Edit**{% endif %}.

        {% note info %}

        Если вместо **умного смешивания** было выбрано другое, необходимо нажать кнопку **Разметить**. Если такой кнопки нет, удалите файл и загрузите заново.

        {% endnote %}

    1. В открывшемся окне нажмите кнопку {% if locale == "ru-ru" %}**Создать контрольные**{% endif %}{% if locale == "en-com" %}**Create control tasks**{% endif %}.

    1. В открывшемся окне в разделе {% if locale == "ru-ru" %}**Создать контрольное задание**{% endif %}{% if locale == "en-com" %}**Create control task**{% endif %} слева отметьте пункт **result**.

    1. Выберите правильный ответ на вопрос.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Сохранить и перейти к следующему**{% endif %}{% if locale == "en-com" %}**Save and go to next**{% endif %}.

    1. Нажмите **Оцените качество видео**, чтобы выйти из режима разметки заданий.

        {% note info %}

        В небольших пулах контрольные задания должны составлять около 10% от всех заданий. Включайте разные варианты правильных ответов в равных количествах. Посмотрите распределение ответов на странице {% if locale == "ru-ru" %}**Разметить задания**{% endif %}{% if locale == "en-com" %}**Edit tasks**{% endif %} на вкладке {% if locale == "ru-ru" %}**Контрольные**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %}.

        {% endnote %}

1. Нажмите кнопку ![](../_images/other/b-start-pool.svg), чтобы запустить пул.

## Получите результаты {#get-results}

1. Рядом с кнопкой {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %} нажмите кнопку ![Выпадающее меню](../_images/other/drop-down.svg).

1. Выберите пункт списка {% if locale == "ru-ru" %}**Агрегация результатов по методу Дэвида — Скина**{% endif %}{% if locale == "en-com" %}**Dawid-Skene aggregation model**{% endif %}. Подробнее об [Агрегации результатов по методу Дэвида — Скина](result-aggregation.md#dawid-skene).

1. В открывшемся окне нажмите {% if locale == "ru-ru" %}**Да**{% endif %}{% if locale == "en-com" %}**Yes**{% endif %}.

1. Наверху страницы нажмите {% if locale == "ru-ru" %}**Перейти к списку операций**{% endif %}{% if locale == "en-com" %}**View the list of operations**{% endif %}.

1. Когда операция завершится, скачайте файл с результатами. Для этого в столбце {% if locale == "ru-ru" %}**Файлы**{% endif %}{% if locale == "en-com" %}**Files**{% endif %} нажмите {% if locale == "ru-ru" %}**Скачать**{% endif %}{% if locale == "en-com" %}**Download**{% endif %}.

{% note tip %}

Для того чтобы избежать нежелательных ошибок, сначала рекомендуем выполнить проект в [Песочнице]({{ sandbox }}).

{% endnote %}

## Решение проблем {#troubleshooting}

{% if locale == "ru-ru" %}

{% cut "Как сделать задание, в котором исполнитель должен просматривать видео с Яндекс Диска?" %}

Для создания задания возьмите за основу [шаблон для разметки видео]({{ templates-video-new }}).

Чтобы разместить ваши видеоролики на Яндекс Диске, его нужно подключить и настроить проект.

{% if locale == "ru-ru" %}Подробная видеоинструкция об этом [в нашем блоге]({{ toloka-blog-yadisk }}).{% endif %}

{% endcut %}

{% cut "Как в задание добавить видео, которое размещено на Яндекс Диске?" %}

Можно взять за основу шаблон [для разметки видео]({{ templates-video }}).

Чтобы разместить ваши видеоролики на Яндекс Диске, его нужно подключить и настроить проект.

{% if locale == "ru-ru" %}Подробная видеоинструкция есть в нашем [блоге]({{ toloka-blog-yadisk }}).{% endif %}

{% endcut %}

{% cut "Не загружаются файлы с Яндекс Диска" %}

Если картинки, аудио или видео с Яндекс Диска не отображаются в [инструкции](../../glossary.md#instructions) или на [странице задания](../../glossary.md#task-suite), убедитесь, что вы правильно подключили Диск и загрузили файлы.

- [Как подключить Яндекс Диск](prepare-data.md#prepare-data__connect)
- [Как загрузить файлы для инструкции](prepare-data.md#prepare-data__instruction)
- [Как загрузить файлы для задания](prepare-data.md#prepare-data__interface)

{% cut "Как сделать задание, в котором исполнитель должен просматривать видео с Яндекс Диска?" %}

Для создания задания возьмите за основу [шаблон для разметки видео]({{ templates-video-new }}).

Чтобы разместить ваши видеоролики на Яндекс Диске, его нужно подключить и настроить проект.

{% if locale == "ru-ru" %}Подробная видеоинструкция об этом [в нашем блоге]({{ toloka-blog-yadisk }}).{% endif %}

{% endcut %}

{% cut "Почему в задании по выделению объектов на изображении не отображаются изображения с Яндекс Диска?" %}

Проблема в шаблоне задания. Проверьте, что:

- Для поля входных данных, куда вы передаете ссылку на файл, в проекте указан тип «строка».

- В компоненте в шаблоне задания используется выражение proxy.

- Формат относительных ссылок в файле с заданиями указан верно: <уникальное имя>/<путь и имя файла>.

Подробная инструкцию и видео на странице [Использование файлов с Яндекс Диска](prepare-data.md).

{% endcut %}

{% if locale == "ru-ru" %}

{% cut "Частые ошибки при подключении Диска и загрузке файлов" %}

- В настройках проекта в поле **Входные данные** указан тип _ссылка_. Необходимо выбрать тип _строка_.

- В [файле с заданиями](../../glossary.md#tsv) указаны абсолютные ссылки на файлы для заданий. Необходимо вставить ссылку вида `<уникальное имя>/<путь и имя файла>`. Например: `yadisk/image1.jpg` или `yadisk/photos/image1.png`.

- Фото с Яндекс Диска используются в инструкции к заданию в мобильном приложении. Чтобы фото отобразилось в инструкции, используйте только прямые ссылки.

- Файлы удалены или находятся не в той папке на Диске, на которую ведет ссылка.

- OAuth-токен не активен. Обновите токен на странице [Интеграция]({{ integration }}).

Чтобы файлы, загруженные на Яндекс Диск (картинки, аудио, видео), отображались у исполнителя, нужно:

1. Подключить Яндекс Диск в профиле.

1. Установить тип строка для поля [входных данных](../../glossary.md#input-output-data).

1. Вставлять ссылку на файл при помощи компонента `proxy`.

[Подробная инструкция](prepare-data.md)

{% endcut %}

{% endif %}

{% endcut %}

{% endif %}

{% if locale == "ru-ru" %}

{% cut "Файлы на Яндекс Диск загружаются слишком медленно. Как ускорить загрузку?" %}

Попробуйте воспользоваться рекомендациями с [этой страницы]({{ yadisk-uploading }}) или написать в службу поддержки Яндекс Диска.

{% endcut %}

{% endif %}

{% include [contact-support](../_includes/contact-support-help.md) %}
