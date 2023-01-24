# Проект 1. Содержит ли фотография определенный объект?

{% include [deprecate](../../_includes/deprecate.md) %}

В этом [проекте](../../glossary.md#project) вы опросите исполнителей на наличие обуви на фотографии.

## Создайте проект {#create_project}

Чтобы создать проект, откройте [Толоку для заказчика]({{ yandex-toloka }}).

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. {% include [toloka-requester-source-template-image-specification](../_includes/toloka-requester-source/id-toloka-requester-source/template-image-specification.md) %}

1. Заполните общую информацию:

    1. В поле **Название для исполнителей** введите `Есть ли на фотографии обувь?`.

    1. В поле **Описание для исполнителей** введите `Посмотрите на картинку и скажите, есть ли на ней обувь.`.

    1. {% include [toloka-requester-source-private-comment](../_includes/toloka-requester-source/id-toloka-requester-source/private-comment.md) %}

    1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. {% include [toloka-requester-source-interface-def](../_includes/toloka-requester-source/id-toloka-requester-source/interface-def.md) %}

          В шаблоне уже настроена проверка. Исполнитель не сможет отправить задание, если не выберет варианта ответа.

          Подробнее в Справке конструктора шаблонов:

          - [настройка условий](../../template-builder/best-practices/conditions.md);

          - шаблон [Классификация изображений](../../template-builder/templates/image-classification.md).

      1. На панели **Конфигурация** замените строки кода с 19 по 28:

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

          на следующие:

          ```json
          "label": "Есть ли обувь на картинке?",
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

      1. {% include [toloka-requester-source-tb-input-output](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output.md) %}

          - Поле входных данных: `image` — ссылка для загрузки картинки.

            Измените тип данных на строку, чтобы использовать ссылки на свои файлы или [загружать картинки](prepare-data.md#interface), хранящиеся на Яндекс Диске.

          - Поле выходных данных: `result — строка`, в которую будет записан ответ исполнителя.

          #### Что такое входные и выходные данные?

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

          {% include [toloka-requester-source-tb-spec](../_includes/toloka-requester-source/id-toloka-requester-source/tb-spec.md) %}

    - Редактор HTML/CSS/JS

      1. {% include [toloka-requester-source-html-editor](../_includes/toloka-requester-source/id-toloka-requester-source/html-editor.md) %}

          - После строки с изображением добавьте вопрос:

              `<div>Есть ли <b>обувь</b> на картинке?<div>`

          - Измените надписи на вариантах ответа: **Хорошее** → **Да**, **Плохое** → **Нет**:

          ```html
          {{img src=image width="100%" height="400px"}}
          <div>Есть ли <b>обувь</b> на картинке?<div>

          {{field type="radio" name="result" value="OK" label="Да" hotkey="1"}}
          {{field type="radio" name="result" value="BAD" label="Нет" hotkey="2"}}
          {{field type="radio" name="result" value="404" label="Ошибка загрузки" hotkey="3"}}
          ```

      1. Блоки **JS**, **CSS** и **Спецификация данных** оставьте без изменений.

          Подробнее о параметрах **Спецификации** читайте в разделе [Входные и выходные данные](incoming.md).

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) **Предпросмотр задания**, чтобы увидеть получившееся задание.

          {% note info %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. {% include [toloka-requester-source-test](../_includes/toloka-requester-source/id-toloka-requester-source/test.md) %}

    {% endlist %}

1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. В поле **Инструкция для исполнителей** введите [инструкцию](../../glossary.md#instructions) и добавьте изображение.

    1. **Текст инструкции:**

    ```plaintext
    Посмотрите на картинку и определите, есть ли на фотографии **обувь**.
    Если есть, нажмите **Да**.
    Если нет, нажмите **Нет**.
    Например, на фотографии есть обувь, поэтому правильный ответ **Да**.
    ```

    1. Чтобы добавить изображение, нажмите кнопку ![](../_images/tutorials/image-segmentation/wsdm-tutorial-button.svg) и укажите ссылку на изображение, которое вы хотите использовать в качестве примера.

    1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. {% include [toloka-requester-source-end-edit](../_includes/toloka-requester-source/id-toloka-requester-source/end-edit.md) %}

Подробнее о работе с проектом читайте в разделе [проект](project.md).

## Создайте пул {#create_pool}

Чтобы создать [пул](../../glossary.md#pool):

1. Откройте страницу проекта с именем **Есть ли на фотографии обувь?**.

1. Нажмите кнопку **Добавить пул**.

1. Укажите **Название пула**.

1. (опционально) Укажите **Приватный комментарий**. Эта информация доступна только вам.

1. В блоке **Аудитория** в разделе **Исполнители** отфильтруйте исполнителей по языку:

    1. Нажмите **Добавить фильтр**.

    1. Найдите в списке блок **Профиль исполнителя** и выберите навык **Языки**.

    1. В поле **?** укажите `=`.

    1. В поле **Значение** укажите **Русский**.

    {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. (опционально) В разделе **Соотношение скорости и качества** укажите желаемый уровень качества. Повышение уровня качества может снизить скорость выполнения заданий, так как пул будет доступен меньшему числу исполнителей. Подробнее об этом читайте в разделе [Соотношение скорости и качества](adjust.md).

1. В блоке **Цена** в поле **Цена за страницу заданий** укажите `0.01`.

1. В блоке **Контроль качества** задайте настройки [контроля качества](../../glossary.md#quality-control) для пула:

    1. Нажмите **Добавить правило контроля качества**.

    1. Найдите в списке блок **Правила** и выберите пункт **Контрольные задания**.

    1. Задайте правило для контрольного задания: если **количество ответов** на контрольные вопросы **больше или равно 3** и **процент правильных ответов** на контрольные вопросы **меньше 60**, то **заблокировать** исполнителя **на проекте на 10 дней**. В качестве причины указать **Контрольное задание**.

    ![](../_images/tutorials/image-segmentation/wsdm-tutorial-part1-2.png)

    Подробнее о контроле качества читайте в разделе [Контроль качества](control.md).

1. В разделе **Перекрытие задания** в поле **Количество исполнителей, которые должны выполнить каждое задание** укажите `3`.

1. В блоке **Дополнительные настройки** в поле **Время на страницу заданий** укажите `600`.

1. Нажмите кнопку **Создать пул**.

## Загрузите задания {#upload_file}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

Чтобы загрузить задания:

1. Нажмите кнопку **Загрузить**. В открывшемся окне вы можете скачать шаблон файла.

1. В открывшемся окне настройте параметры загрузки файла:

    1. Выберите **Умное смешивание**.

    1. В поле **Основных заданий** укажите `9`.

    1. В поле **Обучающих заданий** укажите `0`.

    1. В поле **Контрольных заданий** укажите `1`.

    1. Нажмите кнопку **Загрузить**.

    1. В открывшемся окне выберите [файл](../../glossary.md#tsv) с заданиями для загрузки и нажмите кнопку **Открыть**.

    1. В открывшемся окне проверьте количество заданий и нажмите кнопку **Добавить**.

1. Создайте [контрольное задание](goldenset.md).

    1. Нажмите кнопку **Разметить**.

    {% note info %}

    Если вместо **умного смешивания** было выбрано другое, необходимо нажать кнопку **Разметить**. Если этой кнопки нет, удалите файл и загрузите заново.

    {% endnote %}

    1. В открывшемся окне нажмите кнопку **Создать контрольные**.

    1. В открывшемся окне в колонке слева включите опцию **result**.

    1. Выберите правильный ответ на вопрос.

    1. Нажмите кнопку **Сохранить и перейти к следующему**.

    1. Нажмите **Есть ли на фотографии обувь?**, чтобы выйти из режима [разметки заданий](../../glossary.md#task-markup).

    {% note info %}

    В небольших пулах [контрольные задания](../../glossary.md#control-task) должны составлять 10–20% от всех заданий. Включайте разные варианты правильных ответов в равных количествах. Посмотрите распределение ответов на странице **Разметить задания** на вкладке **Контрольные**.

    {% endnote %}

1. Нажмите кнопку ![](../_images/other/b-start-pool.svg), чтобы запустить пул.

    {% note alert %}

    Поставленные задачи выполнят настоящие исполнители Толоки. Перепроверьте конфигурацию вашего проекта перед запуском пула.

    {% endnote %}

## Получите результаты {#get_results}

Чтобы получить результаты:

1. Рядом с кнопкой **Скачать результаты** нажмите кнопку ![](../_images/other/drop-down.svg).

1. Выберите пункт списка **Агрегация результатов по методу Дэвида — Скина**. Подробнее об [Агрегации результатов по методу Дэвида — Скина](result-aggregation.md).

1. В открывшемся окне нажмите **Да**.

1. Наверху страницы нажмите **Перейти к списку операций**.

    {% note info %}

    Отслеживайте прогресс операции, периодически обновляя страницу. Агрегация занимает от 5 до 20 минут, в это время вы можете приступить к оформлению другого проекта.

    {% endnote %}

1. Когда операция завершится, скачайте файл с результатами. Для этого в столбце **Файлы** нажмите **Скачать**.

1. Используйте файл с результатами во [втором проекте](find_an_item_in_store.md).

## Что дальше {#what-next}

- Создайте [Проект 2](find_an_item_in_store.md) для поиска похожих объектов в интернет магазине.

{% include [contact-support](../_includes/contact-support.md) %}