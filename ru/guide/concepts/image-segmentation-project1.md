# Проект 1. Содержит ли изображение определенный объект

В этом [проекте](../../glossary.md#project) вы опросите исполнителей на наличие дорожных знаков на фотографии.

## Создайте проект {#create-project}

#### В интерфейсе:

1. Выберите пресет:

    1. Откройте [Толоку для заказчика]({{ yandex-toloka }}).

    1. Нажмите кнопку {% if locale == "ru-ru" %}**+ Создать проект**{% endif %}{% if locale == "en-com" %}**+ Create project**{% endif %}.

    1. В открывшемся окне найдите пресет {% if locale == "ru-ru" %}**Классификация изображений**{% endif %}{% if locale == "en-com" %}**Image classification**{% endif %} и нажмите кнопку {% if locale == "ru-ru" %}**Выбрать**{% endif %}{% if locale == "en-com" %}**Select**{% endif %}.

1. Заполните общую информацию:

    1. В поле {% if locale == "ru-ru" %}**Название для исполнителей**{% endif %}{% if locale == "en-com" %}**Name to show performers**{% endif %} введите `Есть ли на фотографии дорожные знаки?`.

    1. В поле {% if locale == "ru-ru" %}**Описание для исполнителей**{% endif %}{% if locale == "en-com" %}**Description for performers**{% endif %} введите `Посмотрите на картинку и скажите, есть ли на ней дорожные знаки.`

    1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. {% include [toloka-requester-source-interface-def](../_includes/toloka-requester-source/id-toloka-requester-source/interface-def.md) %}

          В  шаблоне уже настроена проверка. Исполнитель не сможет отправить задание, если не выберет вариант ответа.

          Подробнее в Справке конструктора:

          - [настройка условий](../../template-builder/best-practices/conditions.md);
          - шаблон [Классификация изображений](../../template-builder/templates/image-classification.md).

      1. На панели **Конфигурация** замените строки кода с 19 по 28:

          {% if locale == "ru-ru" %}

          ```json
          "label": "Какое у кота настроение?",
          "options": [
          {
          "label": "Хорошее",
          "value": "ok"
          },
          {
          "label": "Плохое",
          "value": "bad"
          },
          ```

          {% endif %}{% if locale == "en-com" %}

          ```json
          "label": "What is the cat's mood?",
          "options": [
          {
          "label": "Good",
          "value": "ok"
          },
          {
          "label": "Bad",
          "value": "bad"
          },
          ```

          {% endif %}

          на:

          {% if locale == "ru-ru" %}

          ```json
          "label": "Есть ли на картинке дорожные знаки?",
          "options": [
          {
          "label": "Да",
          "value": "ok"
          },
          {
          "label": "Нет",
          "value": "bad"
          },
          ```

          {% endif %}{% if locale == "en-com" %}

          ```json
          "label": "Are there traffic signs in the picture?",
          "options": [
          {
          "label": "Yes",
          "value": "ok"
          },
          {
          "label": "No",
          "value": "bad"
          },
          ```

          {% endif %}

      1. Чтобы увидеть поля входных и выходных данных, нажмите **Показать спецификации**.

          Поля входных данных создаются из кода на вкладке **Пример входных данных**.

          Поля выходных данных создаются на основе того, в каких компонентах используются `data.output`, а также какие значения в нем разрешены.

          Подробнее о [полях входных и выходных данных](../../template-builder/operations/create-specs.md) в Справке конструктора шаблона.

          - Поле входных данных: `image` — ссылка для загрузки картинки.

          Измените тип данных на строку, чтобы использовать ссылки на свои файлы{% if locale == "ru-ru" %} или [загружать картинки](prepare-data.md#interface), хранящиеся на Яндекс Диске{% endif %}.

          - Поле выходных данных: `result` — строка, в которую будет записан ответ исполнителя.

              {% cut "Что такое входные и выходные данные?" %}

              {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

              {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

              {% include [toloka-requester-source-tb-spec](../_includes/toloka-requester-source/id-toloka-requester-source/tb-spec.md) %}

              {% endcut %}

    - Редактор HTML/CSS/JS

      1. В блоке {% if locale == "ru-ru" %}**Интерфейс задания**{% endif %}{% if locale == "en-com" %}**Task interface**{% endif %} отредактируйте блок **HTML**:

      1. После строки с изображением введите вопрос:

      1. Измените надписи на вариантах ответа: **Хорошее** → **Да**, **Плохое** → **Нет**:

          {% if locale == "ru-ru" %}

          ```html
          {{img src=image width="100%" height="400px"}}
          <div>Есть ли на картинке <b>дорожные знаки</b>?<div>

          {{field type="radio" name="result" value="OK" label="Да" hotkey="1"}}
          {{field type="radio" name="result" value="BAD" label="Нет" hotkey="2"}}
          {{field type="radio" name="result" value="404" label="Ошибка загрузки" hotkey="3"}}
          ```

          {% endif %}{% if locale == "en-com" %}

          ```html
          {{img src=image width="100%" height="400px"}}
          <div>Are there <b>traffic signs</b> in the picture?<div>

          {{field type="radio" name="result" value="OK" label="Yes" hotkey="1"}}
          {{field type="radio" name="result" value="BAD" label="No" hotkey="2"}}
          {{field type="radio" name="result" value="404" label="Loading error" hotkey="3"}}
          ```

          {% endif %}

      1. Блоки **JS**, **CSS** и {% if locale == "ru-ru" %}**Спецификация данных**{% endif %}{% if locale == "en-com" %}**Data specification**{% endif %} оставьте без изменений.

          Подробнее о параметрах {% if locale == "ru-ru" %}**Спецификации**{% endif %}{% if locale == "en-com" %}**Specifications**{% endif %} читайте в разделе [Входные и выходные данные](incoming.md).

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

          {% note info %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. В открывшемся окне проверьте работу опций задания. И в правом нижнем углу нажмите кнопку {% if locale == "ru-ru" %}**Отправить**{% endif %}{% if locale == "en-com" %}**Submit**{% endif %}.

      1. Выйдите из режима предпросмотра. В нижнем левом углу нажмите кнопку {% if locale == "ru-ru" %}**Выйти**{% endif %}{% if locale == "en-com" %}**Exit**{% endif %}{% if locale == "ru-ru" %}** → Выйти**{% endif %}{% if locale == "en-com" %}**Exit**{% endif %} . Если при тестировании задания были ошибки — проверьте блоки кода, которые вы вводили.

    {% endlist %}

1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. В блоке {% if locale == "ru-ru" %}**Инструкция для исполнителей**{% endif %}{% if locale == "en-com" %}**Instructions for performers**{% endif %} введите [инструкцию](../../glossary.md#instructions) и добавьте изображение.

    1. **Текст инструкции:**{% if locale == "ru-ru" %}

        ```plaintext
        Посмотрите на изображение и определите, есть ли на нем **дорожные знаки**?
        Если да, нажмите **Да**.
        Если нет, нажмите **Нет**.
        Например, на изображении есть дорожные знаки, поэтому правильный ответ **Да**.
        ```

        {% endif %}{% if locale == "en-com" %}

        ```plaintext
        Look at the image and answer whether there are any **traffic signs** in it.
        If there are, click **Yes**.
        If there aren't, click **No**.
        For example, there are traffic signs in the image, so the correct answer is **Yes**.
        ```

        {% endif %}

    1. Чтобы добавить изображение, нажмите кнопку ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.svg) и укажите ссылку на изображение, которое вы хотите использовать в качестве примера.

    1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. В правом верхнем углу нажмите кнопку {% if locale == "ru-ru" %}**Завершить**{% endif %}{% if locale == "en-com" %}**Finish**{% endif %}

    Подробнее о работе с проектом читайте в разделе [Проект](project.md).

## Создайте пул {#create-pool}

1. Откройте страницу проекта с именем **Есть ли на фотографии дорожные знаки?**.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить пул**{% endif %}{% if locale == "en-com" %}**Add a pool**{% endif %}.

1. Укажите {% if locale == "ru-ru" %}**Название пула**{% endif %}{% if locale == "en-com" %}**Pool name**{% endif %}.

1. (опционально) Добавьте {% if locale == "ru-ru" %}**Приватный комментарий**{% endif %}{% if locale == "en-com" %}**Private comment**{% endif %}. Эта информация доступна только вам.

1. В блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} отфильтруйте исполнителей по языку:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Добавьте фильтры {% if locale == "ru-ru" %}**Регион по номеру телефона**{% endif %}{% if locale == "en-com" %}**Region by phone number**{% endif %} и {% if locale == "ru-ru" %}**Языки**{% endif %}{% if locale == "en-com" %}**Languages**{% endif %}: выберите исполнителей из России, Украины, Казахстана и Беларуси, которые в своем профиле отметили знание русского языка.

    {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. {% include [contain_item-pool-speed-quality](../_includes/concepts/contain_item/id-contain_item/pool-speed-quality.md) %}

1. В блоке {% if locale == "ru-ru" %}**Цена**{% endif %}{% if locale == "en-com" %}**Price**{% endif %} в поле {% if locale == "ru-ru" %}**Цена за страницу заданий**{% endif %}{% if locale == "en-com" %}**Price per task suite, **{% endif %} укажите цену. Например, `0.01`.

1. В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} задайте [настройки контроля качества](control.md) для пула:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Контрольные задания**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %}.

    1. Задайте правило для [контрольного задания](../../glossary.md#control-task): если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %} на контрольные вопросы **≥ 3** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%)**{% endif %} на контрольные вопросы **< 60**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %} исполнителя {% if locale == "ru-ru" %}**на проекте на 10 дней**{% endif %}{% if locale == "en-com" %}**on project**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В качестве причины укажите **Контрольное задание**.

    {% if locale == "ru-ru" %}![](../_images/tutorials/image-segmentation/wsdm-tutorial-part1-2.png){% endif %}

    Подробнее о контроле качества читайте в разделе [Контроль качества](control.md).

1. В разделе {% if locale == "ru-ru" %}**Перекрытие задания**{% endif %}{% if locale == "en-com" %}**Task overlap**{% endif %} в поле {% if locale == "ru-ru" %}**Количество исполнителей, которые должны выполнить каждое задание **{% endif %}{% if locale == "en-com" %}**The number of performers to complete every task**{% endif %} укажите `3`.

1. В блоке {% if locale == "ru-ru" %}**Дополнительные настройки**{% endif %}{% if locale == "en-com" %}**Additional settings**{% endif %} в поле {% if locale == "ru-ru" %}**Время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Time per task suite**{% endif %} укажите `600`.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Создать пул**{% endif %}{% if locale == "en-com" %}**Create a pool**{% endif %}.

## Загрузите задания {#upload-file}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне вы можете скачать шаблон файла.

    #### Использовать пример данных

    Если вы хотите посмотреть, как ваш проект будет выглядеть после запуска, но у вас еще нет заданий для разметки, вы можете загрузить в пул готовый пример данных.

    Нажмите {% if locale == "ru-ru" %}**Использовать пример данных**{% endif %}{% if locale == "en-com" %}**Use sample data**{% endif %} справа от надписи {% if locale == "ru-ru" %}**Прикрепите подготовленный файл с данными**{% endif %}{% if locale == "en-com" %}**Attach the prepared file with data**{% endif %}. Это позволит избежать дополнительных действий с файлами.

    После того, как вы поработали с примером данных и вас все устроило, подготовьте свои данные и загрузите их в пул.

    {% cut "Использовать пример данных" %}

    Если вы хотите посмотреть, как ваш проект будет выглядеть после запуска, но у вас еще нет заданий для разметки, вы можете загрузить в пул готовый пример данных.

    Нажмите **Использовать пример данных** справа от надписи **Прикрепите подготовленный файл с данными**. Это позволит избежать дополнительных действий с файлами.

    {% endcut %}

После того, как вы поработали с примером данных и вас все устроило, подготовьте свои данные и загрузите их в пул.

1. В открывшемся окне настройте параметры загрузки файла:

    1. Выберите {% if locale == "ru-ru" %}**Умное смешивание**{% endif %}{% if locale == "en-com" %}**Smart mixing**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Основных заданий**{% endif %}{% if locale == "en-com" %}**Main tasks**{% endif %} укажите `9`.

    1. В поле {% if locale == "ru-ru" %}**Обучающих заданий**{% endif %}{% if locale == "en-com" %}**Training tasks**{% endif %} укажите `0`.

    1. В поле {% if locale == "ru-ru" %}**Контрольных заданий**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %} укажите `1`.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}.

    1. В открывшемся окне выберите [файл](../../glossary.md#tsv) с заданиями для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

    1. В открывшемся окне проверьте количество заданий и нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

1. Создайте [контрольное задание](goldenset.md):

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Разметить**{% endif %}{% if locale == "en-com" %}**Edit**{% endif %}.

    {% note info %}

    Если вместо **умного смешивания** было выбрано другое, необходимо нажать кнопку **Разметить**. Если этой кнопки нет, удалите файл и загрузите заново.

    {% endnote %}

    1. В открывшемся окне нажмите кнопку {% if locale == "ru-ru" %}**Создать контрольные**{% endif %}{% if locale == "en-com" %}**Create control tasks**{% endif %}.

    1. В открывшемся окне в разделе {% if locale == "ru-ru" %}**Создать контрольное задание**{% endif %}{% if locale == "en-com" %}**Create control task**{% endif %} слева включите опцию **result**.

    1. Выберите правильный ответ на вопрос.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Сохранить и перейти к следующему**{% endif %}{% if locale == "en-com" %}**Save and go to next**{% endif %}.

    1. Нажмите **Есть ли на фотографии дорожные знаки?**, чтобы выйти из режима [разметки заданий](../../glossary.md#task-markup).

    {% note alert %}

    В небольших пулах контрольные задания должны составлять 10–20% от всех заданий. Включайте разные варианты правильных ответов в равных количествах. Посмотрите распределение ответов на странице {% if locale == "ru-ru" %}**Разметить задания**{% endif %}{% if locale == "en-com" %}**Edit tasks**{% endif %} на вкладке {% if locale == "ru-ru" %}**Контрольные**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %}.

    {% endnote %}

1. Нажмите кнопку ![](../_images/other/b-start-pool.svg), чтобы запустить пул.

    {% note alert %}

    Поставленные задачи выполнят настоящие исполнители Толоки. Перепроверьте конфигурацию вашего проекта перед запуском пула.

    {% endnote %}

## Получите результаты {#get-results}

1. Рядом с кнопкой {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %} нажмите кнопку ![](../_images/other/drop-down.svg).

1. Выберите пункт списка {% if locale == "ru-ru" %}**Агрегация результатов по методу Дэвида — Скина**{% endif %}{% if locale == "en-com" %}**Dawid-Skene aggregation model**{% endif %}. Подробнее об [Агрегации результатов по методу Дэвида — Скина](result-aggregation.md#dawid-skene).

1. В открывшемся окне нажмите {% if locale == "ru-ru" %}**Да**{% endif %}{% if locale == "en-com" %}**Yes**{% endif %}.

1. Наверху страницы нажмите {% if locale == "ru-ru" %}**Перейти к списку операций**{% endif %}{% if locale == "en-com" %}**View the list of operations**{% endif %}.

    {% note info %}

    Отслеживайте прогресс операции, периодически обновляя страницу. Агрегация занимает от 5 до 20 минут, в это время вы можете приступить к оформлению другого проекта.

    {% endnote %}

1. Когда операция завершится, скачайте файл с результатами. Для этого в столбце {% if locale == "ru-ru" %}**Файлы**{% endif %}{% if locale == "en-com" %}**Files**{% endif %} нажмите {% if locale == "ru-ru" %}**Скачать**{% endif %}{% if locale == "en-com" %}**Download**{% endif %}.

1. Используйте файл с результатами во [втором проекте](image-segmentation-project2.md).

## Что дальше {#what-next}

- Создайте [Проект 2](image-segmentation-project2.md) для выделения объектов.

{% include [contact-support](../_includes/contact-support-help.md) %}