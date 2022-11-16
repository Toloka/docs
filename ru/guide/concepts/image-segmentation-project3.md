# Проект 3. Верно ли выделены объекты на изображении

{% include [deprecate](../../_includes/deprecate.md) %}

В этом [проекте](../../glossary.md#project) исполнители будут определять, верно ли на изображениях из [первого проекта](image-segmentation-project1.md) были выделены дорожные знаки во [втором проекте](image-segmentation-project2.md).

## Создайте проект {#create-project}

#### В интерфейсе:

1. Выберите шаблон:

    1. Нажмите кнопку **Создать проект**.
    1. Выберите шаблон **Распознавание объектов и выделение областей**.
    1. Нажмите **Использовать решение**.

1. Заполните общую информацию:

    1. В поле **Название для исполнителей** проекта введите `Верно ли выделены дорожные знаки`.
    1. В поле **Описание для исполнителей** введите `Посмотрите на изображение и решите, верно ли выделены дорожные знаки`.
    1. По желанию добавьте **Приватный комментарий**.

1. Отредактируйте интерфейс задания. От редактора интерфейса зависит формат выходных данных, поэтому выберите тот же редактор, что и в [Проекте 2](image-segmentation-project2.md#interface-tb-html).

    {% list tabs %}

    - Конструктор шаблонов

      1. Создайте шаблон на основе примера [Проверка выделенной области](https://clck.ru/sFyNY), в котором используется Компонент для разметки изображений.

      1. Чтобы увидеть поля входных и выходных данных, в разделе {% if locale == "ru-ru" %}**Спецификация данных**{% endif %}{% if locale == "en-com" %}**Data specification**{% endif %} нажмите {% if locale == "ru-ru" %}**Показать спецификации**{% endif %}{% if locale == "en-com" %}**Show specifications**{% endif %}.

          Поля входных данных, которые используются в проекте:

          - `image` — адрес картинки;
          - `result` — массив с координатами выделенной области;
          - `assignment_id` — идентификатор задания.

          В поле выходных данных `verdict` будет записан ответ исполнителя.

      1. Включите опцию **Настроить спецификацию вручную**.

      1. Нажмите кнопку ![](../_images/other/code.svg), чтобы переключить графический режим на формат JSON.

      1. {% include [image-segmentation-project3-del-input-temp](../_includes/concepts/image-segmentation-project3/id-image-segmentation-project3/del-input-temp.md) %}

          ```json
          {
          "image": {
          "type": "url",
          "hidden": false,
          "required": true
          },
          "result": {
          "type": "array_json",
          "hidden": false,
          "required": false
          },
          "assignment_id": {
          "type": "string",
          "hidden": true,
          "required": true
          }
          }
          ```

      1. {% include [image-segmentation-project3-del-output-temp](../_includes/concepts/image-segmentation-project3/id-image-segmentation-project3/del-output-temp.md) %}

          ```json
          {
          "verdict": {
          "type": "string",
          "hidden": false,
          "required": true,
          "allowed_values": [
          "OK",
          "BAD"
          ]
          }
          }
          ```

    - Редактор HTML/CSS/JS

      1. Подготовьте {% if locale == "ru-ru" %}**Интерфейс задания**{% endif %}{% if locale == "en-com" %}**Task interface**{% endif %}:

      1. {% include [image-annotation-p_tgf_nsv_wlb](../_includes/concepts/t-components/image-annotation/id-image-annotation/p_tgf_nsv_wlb.md) %}

      1. В блоке **HTML** замените текущий код на следующий:

          {% if locale == "ru-ru" %}

          ```html
          <!-- редактор для выделения областей с возможностью заранее добавить область -->
          {{field type="image-annotation" name="object" src=image annotations=selection}}

          <!-- кнопки для ответов -->
          {{field type="radio" name="result" value="OK" label="Верно" hotkey="1"}}
          {{field type="radio" name="result" value="BAD" label="Неверно" hotkey="2"}}
          ```

          {% endif %}{% if locale == "en-com" %}

          ```html
          <!-- editor for selecting objects that lets you add an area in advance -->
          {{field type="image-annotation" name="object" src=image annotations=selection}}

          <!-- buttons for responses -->
          {{field type="radio" name="result" value="OK" label="Correct" hotkey="1"}}
          {{field type="radio" name="result" value="BAD" label="Incorrect" hotkey="2"}}
          ```

        {% endif %}

      1. В блоке **CSS** замените текущий код на следующий:

          {% if locale == "ru-ru" %}

          ```css
          /* скрыть кнопку для выделения полигоном */
          .image-annotation-editor__shape-polygon {
          display: none;
          }

          /* настроить высоту интерфейса */
          .image-annotation-editor__annotation-layer {
          height: max-content;
          }
          ```

          {% endif %}{% if locale == "en-com" %}

          ```css
          /* hide the button for polygon selection */
          .image-annotation-editor__shape-polygon {
          display: none;
          }

          /* adjust the interface height */
          .image-annotation-editor__annotation-layer {
          height: max-content;
          }
          ```

        {% endif %}

      1. Настройте раздел **Спецификация данных**:

      1. Нажмите кнопку ![](../_images/other/code.svg), чтобы переключить графический режим на формат JSON.

      1. Удалите шаблонный код из поля {% if locale == "ru-ru" %}**Входные данные**{% endif %}{% if locale == "en-com" %}**Input data**{% endif %} и введите следующий код:

          ```json
          {
          "image": {
          "type": "url",
          "hidden": false,
          "required": true
          },
          "selection": {
          "type": "array_json",
          "hidden": false,
          "required": false
          },
          "assignment_id": {
          "type": "string",
          "hidden": true,
          "required": true
          }
          }
          ```

      1. Удалите шаблонный код из поля {% if locale == "ru-ru" %}**Выходные данные**{% endif %}{% if locale == "en-com" %}**Output data**{% endif %} и введите следующий код:

          ```json
          {
          "result": {
          "type": "string",
          "hidden": false,
          "required": true,
          "allowed_values": [
          "OK",
          "BAD"
          ]
          }
          }
          ```

          Подробнее о параметрах {% if locale == "ru-ru" %}**Спецификации**{% endif %}{% if locale == "en-com" %}**Specifications**{% endif %} читайте в разделе [Входные и выходные данные](incoming.md).

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

          {% note tip %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. Нажмите **Изменить входные данные**.

      1. В поле **selection** добавьте пример входных данных:

          ```json
          [{"data":{"p1":{"x":0.472,"y":0.413},"p2":{"x":0.932,"y":0.877}},"type":"rectangle"},
          {"data":[{"x":0.143,"y":0.807},{"x":0.317,"y":0.87},{"x":0.511,"y":0.145},{"x":0.328,"y":0.096},{"x":0.096,"y":0.554}], "type":"polygon"}]
          ```

      1. Если все в порядке, закройте вкладку с предпросмотром. Если нет — проверьте данные, которые вы вставляли в блоки кода.

    {% endlist %}

1. Напишите инструкцию для исполнителей:

    **Текст инструкции:**

    {% if locale == "ru-ru" %}

    ```plaintext
    Посмотрите на изображение и ответьте на вопрос: **Все ли дорожные знаки выделены верно?**
    Если да, нажмите **Да**.
    Если нет, нажмите **Нет**.
    Например, дорожные знаки выделены верно, поэтому правильный ответ **Да**.
    ```

    {% endif %}{% if locale == "en-com" %}

    ```plaintext
    Look at the image and answer the question: **Are all traffic signs outlined correctly?**
    If there are, click **Yes**.
    If there isn't, click **No**.
    For example, road signs are outlined correctly, so the correct answer is **Yes**.
    ```

    {% endif %}

    {% note tip %}

    Если вы хотите добавить в инструкцию примеры выполнения задания, выполните его самостоятельно в режиме предпросмотра. Сделайте скриншоты, загрузите их на фотохостинг{% if locale == "ru-ru" %}, ваш Яндекс Диск{% endif %} или в облачное хранилище и вставьте ссылки на изображения в инструкцию, нажав кнопку ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.svg) на панели инструментов.

    {% endnote %}

1. Нажмите кнопку **Создать проект**.

## Создайте пул {#create_pool}

1. Откройте страницу проекта с именем **Верно ли выделены дорожные знаки?**.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить пул**{% endif %}{% if locale == "en-com" %}**Add a pool**{% endif %}.

1. Укажите {% if locale == "ru-ru" %}**Название пула**{% endif %}{% if locale == "en-com" %}**Pool name**{% endif %}.

1. (опционально) Укажите **Приватный комментарий**{% if locale == "en-com" %}**Private comment**{% endif %}. Эта информация доступна только вам.

1. В блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} отфильтруйте исполнителей:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Добавьте фильтры {% if locale == "ru-ru" %}**Регион по номеру телефона**{% endif %}{% if locale == "en-com" %}**Region by phone number**{% endif %} и {% if locale == "ru-ru" %}**Языки**{% endif %}{% if locale == "en-com" %}**Languages**{% endif %}: выберите исполнителей из России, Украины, Казахстана и Беларуси, которые в своем профиле отметили знание русского языка.

    1. Добавьте еще один фильтр. Нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Навыки**{% endif %}{% if locale == "en-com" %}**Skills**{% endif %} и выберите навык {% if locale == "ru-ru" %}**Выбрать свой навык**{% endif %}{% if locale == "en-com" %}**My skills**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Навыки**{% endif %}{% if locale == "en-com" %}**Skills**{% endif %} выберите **Выделение областей**.

    1. В поле **?** укажите `=`.

    1. Поле {% if locale == "ru-ru" %}**Отсутствует**{% endif %}{% if locale == "en-com" %}**Missing**{% endif %} оставьте пустым.

    {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. {% include [contain_item-pool-speed-quality](../_includes/concepts/contain_item/id-contain_item/pool-speed-quality.md) %}

1. В блоке {% if locale == "ru-ru" %}**Цена**{% endif %}{% if locale == "en-com" %}**Price**{% endif %} в поле {% if locale == "ru-ru" %}**Цена за страницу заданий**{% endif %}{% if locale == "en-com" %}**Price per task suite**{% endif %} укажите цену. Например, `0.01`.

1. В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} задайте [настройки контроля качества](control.md) для пула:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Мнение большинства**{% endif %}{% if locale == "en-com" %}**Majority vote**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Считать большинством**{% endif %}{% if locale == "en-com" %}**Accept as majority**{% endif %} укажите `2`.

    1. Задайте правило: если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %} **≥ 10** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%)**{% endif %} **< 50**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %} исполнителя {% if locale == "ru-ru" %}**на проекте на 10 дней**{% endif %}{% if locale == "en-com" %}**on project**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В качестве причины укажите **Не совпадает с большинством**.

    ![](../_images/tutorials/image-segmentation/majority-vote.png)

    {% note info %}

    Правило начинает действовать, когда количество ответов на задание равно [перекрытию](../../glossary.md#overlap).

    {% endnote %}

    Подробнее о контроле качества читайте в разделе [Контроль качества](control.md).

1. В разделе {% if locale == "ru-ru" %}**Перекрытие задания**{% endif %}{% if locale == "en-com" %}**Task overlap**{% endif %} в поле {% if locale == "ru-ru" %}**Количество исполнителей, которые должны выполнить каждое задание **{% endif %}{% if locale == "en-com" %}**The number of performers to complete every task**{% endif %} укажите `3`.

1. В блоке {% if locale == "ru-ru" %}**Дополнительные настройки**{% endif %}{% if locale == "en-com" %}**Additional settings**{% endif %}:

    1. В поле {% if locale == "ru-ru" %}**Время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Time per task suite**{% endif %} укажите `600`.

    1. Включите опцию {% if locale == "ru-ru" %}**Сохранять порядок заданий**{% endif %}{% if locale == "en-com" %}**Keep task order**{% endif %}.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Создать пул**{% endif %}{% if locale == "en-com" %}**Create a pool**{% endif %}.

## Подготовьте и загрузите файл с результатами {#upload_file}

1. Подготовьте [файл](../../glossary.md#tsv) с заданиями:

    1. Откройте в редакторе текста или электронных таблиц файл, полученный после агрегации результатов во [втором проекте](image-segmentation-project2.md).

    1. Столбец `INPUT:image` оставьте без изменений.

    1. Измените имя столбца `OUTPUT:result` на `INPUT:selection`.

    1. Измените имя столбца `ASSIGNMENT:assignment_id` на `INPUT:assignment_id`.

    1. Удалите столбцы `ACCEPT:verdict` и `ACCEPT:comment`.

    1. Добавьте входные данные, например:

        ```json
        [{""type"":""rectangle"",""data"":{""p1"":{""x"":0.2421,""y"":0.98871},""p2"":{""x"":0.93663,""y"":0.8776}}}]
        ```

    и сохраните файл в формате `tsv`.

    {% note tip %}

    Вы можете подготовить файл в программе {% if locale == "ru-ru" %}**Блокнот**{% endif %}{% if locale == "en-com" %}**Notepad**{% endif %}. Чтобы перенести данные в **Microsoft Excel**, используйте {% if locale == "ru-ru" %}**Мастер импорта текста**{% endif %}{% if locale == "en-com" %}**Text Import Wizard**{% endif %}, отключив опцию {% if locale == "ru-ru" %}**Ограничитель текста**{% endif %}{% if locale == "en-com" %}**Text qualifier**{% endif %}.

    {% endnote %}

1. Загрузите получившийся файл в пул **Верно ли выделены дорожные знаки?** :

    1. Откройте пул **Верно ли выделены дорожные знаки?**

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне настройте параметры загрузки файла.

    1. Выберите {% if locale == "ru-ru" %}**Указать вручную**{% endif %}{% if locale == "en-com" %}**Set manually**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Заданий на странице**{% endif %}{% if locale == "en-com" %}**Tasks per page**{% endif %} укажите `10`.

    1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}.

    1. В открывшемся окне выберите файл с заданиями для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

    1. В открывшемся окне проверьте количество заданий и нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

    1. На странице пула нажмите кнопку {% if locale == "ru-ru" %}**Предпросмотр**{% endif %}{% if locale == "en-com" %}**Preview**{% endif %}. Убедитесь, что в задании отображаются изображения с выделенными объектами.

    {% note tip %}

    Если выделенных объектов нет, проверьте, правильно ли выставлены кавычки в файле в столбце **INPUT:selection**. Убедитесь, что [параметры интерфейса](#task-interface) заданы верно.

    {% endnote %}

1. Нажмите кнопку ![](../_images/other/b-start-pool.svg), чтобы запустить пул.

    {% note alert %}

    Поставленные задачи выполнят настоящие исполнители Толоки. Перепроверьте конфигурацию вашего проекта перед запуском пула.

    {% endnote %}

## Скачайте проверенные результаты  {#get_results}

1. Рядом с кнопкой {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %} нажмите кнопку ![](../_images/other/drop-down.svg).

1. Выберите из списка пункт {% if locale == "ru-ru" %}**Агрегация результатов по методу Дэвида — Скина**{% endif %}{% if locale == "en-com" %}**Dawid-Skene aggregation model**{% endif %}. Подробнее об [Агрегации результатов по методу Дэвида — Скина](result-aggregation.md#dawid-skene).

1. В открывшемся окне нажмите {% if locale == "ru-ru" %}**Да**{% endif %}{% if locale == "en-com" %}**Yes**{% endif %}.

1. Наверху страницы нажмите {% if locale == "ru-ru" %}**Перейти к списку операций**{% endif %}{% if locale == "en-com" %}**View the list of operations**{% endif %}.

    {% note info %}

    Отслеживайте прогресс операции, периодически обновляя страницу. Агрегация занимает от 5 до 20 минут, в это время вы можете приступить к оформлению другого проекта.

    {% endnote %}

1. Когда операция завершится, скачайте файл с результатами. Для этого в столбце {% if locale == "ru-ru" %}**Файлы**{% endif %}{% if locale == "en-com" %}**Files**{% endif %} нажмите {% if locale == "ru-ru" %}**Скачать**{% endif %}{% if locale == "en-com" %}**Download**{% endif %}.

1. Используйте файл с результатами во [втором проекте](image-segmentation-project2.md).

## Проверьте выполненные задания {#check_results}

Так как в настройках пула во [втором проекте](image-segmentation-project2.md) включена опция {% if locale == "ru-ru" %}**Отложенная приёмка**{% endif %}{% if locale == "en-com" %}**Non-automatic acceptance**{% endif %}, вы должны проверить ответы исполнителей в течение срока, установленного в поле {% if locale == "ru-ru" %}**Срок проверки**{% endif %}{% if locale == "en-com" %}**Review period**{% endif %}.

Вы можете проверить результаты двумя способами:

- В файле с результатами.
- В интерфейсе пула.

{% list tabs %}

- Проверить задания в файле с результатами

  1. Откройте в редакторе текста или электронных таблиц файл, полученный после агрегации результатов.

      {% note tip %}

      Вы можете воспользоваться онлайн-редактором электронных таблиц. Перейдите на [Яндекс Диск]({{ yadisk-client }}), подключенный к вашему аккаунту заказчика. Нажмите {% if locale == "ru-ru" %}**Создать → Таблицу**{% endif %}{% if locale == "en-com" %}**Create → Spreadsheet**{% endif %}. Скопируйте в таблицу агрегированные данные из файла.

      {% endnote %}

  1. Подготовьте файл:

      1. Добавьте столбец `ACCEPT:verdict` — результат проверки.

      1. Добавьте столбец `ACCEPT:comment` — комментарий для исполнителя, если ответ был отклонен. Например, какая часть инструкций не была выполнена.

      1. Измените имя столбца `INPUT:assignment_id` на `ASSIGNMENT:assignment_id`.

  1. Заполните столбцы `ACCEPT:verdict:` и `ACCEPT:comment:`:

      - Если агрегированный результат задания правильный, поставьте `+`, и задание будет принято.
      - Если агрегированный результат задания неправильный или не открывается, поставьте `-`, и задание будет отклонено. Введите причину отклонения задания в поле `ACCEPT:comment:`, например, `Объект не выделен или выделен неверно.`

      {% note tip %}

      Для отбора изображений на устройствах с Linux и MacOS вы можете воспользоваться командами awk:

      {% if locale == "ru-ru" %}

      ```shell
      awk 'BEGIN {FS=OFS="\t";} NR>1 {if($4~"OK"){ print $1, "+", ""; }else{ print $1, "-", "Объект не выделен или выделен неверно.";}}' <post_accept_res>.tsv > <review_res>.tsv
      ```

      {% endif %}{% if locale == "en-com" %}

      ```shell
      awk 'BEGIN {FS=OFS="\t";} NR>1 {if($4~"OK"){ print $1, "+", ""; }else{ print $1, "-", "The object isn't selected or is selected incorrectly.";}}' <post_accept_res>.tsv > <review_res>.tsv
      ```

      {% endif %}

      {% endnote %}

  1. Удалите все остальные столбцы.

  1. Сохраните файл в формате `tsv`.

  1. Откройте страницу пула во [втором проекте](image-segmentation-project2.md).

  1. Нажмите кнопку {% if locale == "ru-ru" %}**Проверить задания**{% endif %}{% if locale == "en-com" %}**Review assignments**{% endif %}.

  1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить результаты**{% endif %}{% if locale == "en-com" %}**Upload results**{% endif %}.

  1. В открывшемся окне выберите файл с результатами для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

  1. В открывшемся окне сравните количество заданий в поле {% if locale == "ru-ru" %}**Успешно обработано**{% endif %}{% if locale == "en-com" %}**Processed successfully**{% endif %} с полем {% if locale == "ru-ru" %}**Всего выполненных заданий**{% endif %}{% if locale == "en-com" %}**Total submitted**{% endif %} на странице пула.

  1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

  1. В открывшемся окне нажмите кнопку {% if locale == "ru-ru" %}**Закрыть**{% endif %}{% if locale == "en-com" %}**Close**{% endif %}.

  1. При настройке пула во [втором проекте](image-segmentation-project2.md) вы включили опцию {% if locale == "ru-ru" %}**Повторное выполнение отклонённых заданий**{% endif %}{% if locale == "en-com" %}**Recompletion of the rejected tasks**{% endif %}.

    При повторном выполнении задания пул автоматически открывается снова, и задания передаются другим исполнителям. Когда задания будут выполнены, отправьте результаты на проверку. Затем скачайте результаты, проверьте их и загрузите проверенные результаты. Вы можете отклонять задания столько раз, сколько захотите, чтобы получить более точные результаты.

- Проверить задания в интерфейсе пула

  1. Откройте страницу пула во [втором проекте](image-segmentation-project2.md).

  1. Нажмите кнопку {% if locale == "ru-ru" %}**Просмотреть задания**{% endif %}{% if locale == "en-com" %}**View assignments**{% endif %}.

  1. Наведите курсор на строку с заданием, которое хотите проверить.

  1. В столбце {% if locale == "ru-ru" %}**Статус**{% endif %}{% if locale == "en-com" %}**Status**{% endif %} появятся кнопки, чтобы принять (кнопка ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button-yes.svg)) или отклонить (кнопка ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button-no.svg)) выполненное задание. Если вы отклоняете задание, в открывшемся окне введите комментарий и нажмите кнопку {% if locale == "ru-ru" %}**Готово**{% endif %}{% if locale == "en-com" %}**Done**{% endif %}.

{% endlist %}

## Что дальше {#what-next}

- Почитайте подробнее [про декомпозицию заданий](solution-architecture.md).

{% include [contact-support](../_includes/contact-support-help.md) %}