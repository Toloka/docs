# Поиск характеристик товара

{% include [deprecate](../../_includes/deprecate.md) %}

{% note tip %}

Сначала запустите проект в [Песочнице]({{ sandbox }}). Так вы сможете избежать ошибок и потраченных средств, если окажется, что ваше задание не работает.

{% endnote %}

В проектах этого типа исполнители ищут в сети объект или информацию о нем. Вы можете использовать их для:

- поиска объекта по описанию, например товара или услуги;
- поиска информации на определенном сайте, например городов доставки на сайте магазина;
- поиска информации об объекте в интернете, например контактных данных организации.

В этой инструкции вы создадите задание, в котором исполнители будут искать данные об организациях. Допустим, у вас есть список организаций и нужно найти их телефоны и адреса электронных почт. В этом задании исполнители увидят названия и ссылки на сайты организаций и найдут необходимую информацию о них.

## Создайте проект {#create-project}

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. {% include [toloka-requester-source-template-data-search](../_includes/toloka-requester-source/id-toloka-requester-source/template-data-search.md) %}

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. {% include [toloka-requester-source-interface-def](../_includes/toloka-requester-source/id-toloka-requester-source/interface-def.md) %}

          Воспользуйтесь {% if locale == "ru-ru" %}[готовым кодом](https://clck.ru/U8ksm){% endif %}{% if locale == "en-com" %}[ready-made code](https://clck.ru/VC555){% endif %} для этого проекта, где уже настроена валидация и внешний вид задания.

          [Подробнее о настройке условий](../../template-builder/best-practices/conditions.md) в конструкторе шаблонов.

      1. {% include [toloka-requester-source-tb-input-output](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output.md) %}

          - Поля входных данных:

            - `title` — строка c названием организации;
            - `url` — адрес сайт организации, тип `url`.

          - Поля выходных данных:

            - `phone` — строка, в которую будет записан номер телефона организации;
            - `email` — строка, в которую будет записан адрес электронной почты организации;
            - `not_found` — флажок, обозначающий отсутствие контактов организации.

      1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

    - Редактор HTML/CSS/JS

      В разделе **Спецификация данных** можно настроить поля входных и выходных данных.

      {% cut "Что такое входные и выходные данные?" %}

      {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

      {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

      [Подробнее](incoming.md) о полях входных и выходных данных.

      {% endcut %}

      {% note info %}

      Вы можете настроить валидацию выходных данных с помощью [регулярных выражений](incoming.md#section_y2v_qqq_tlb). Это позволит формализовать ответы исполнителей. В примере ниже использованы регулярные выражения, позволяющие задать необходимый формат электронных почт и телефонных номеров.

      Если вы используете регулярные выражения, то проект можно запустить с перекрытием больше единицы — чтобы каждое задание выполнило несколько человек. Тогда можно будет не использовать отложенную приемку и не проверять каждое задание, а довериться усредненным данным.

      {% endnote %}

      1. Нажмите кнопку ![](../_images/other/code.svg), чтобы переключить графический режим на формат JSON.

      1. В поле {% if locale == "ru-ru" %}**Входные данные**{% endif %}{% if locale == "en-com" %}**Input data**{% endif %} введите следующий код:

          ```json
          {
          "url": {
          "type": "url",
          "hidden": false,
          "required": true
          },
          "title": {
          "type": "string",
          "hidden": false,
          "required": false
          }
          }
          ```

      1. В поле {% if locale == "ru-ru" %}**Выходные данные**{% endif %}{% if locale == "en-com" %}**Output data**{% endif %} введите следующий код:

          ```json
          {
          "email": {
          "type": "string",
          "hidden": false,
          "pattern": "^[a-zA-Zа-яА-ЯёЁ0-9\\._-]+@[a-zA-Zа-яА-ЯёЁ0-9\\._-]+\\.[a-zA-Zа-яА-ЯёЁ]{2,}$",
          "required": false
          },
          "phone": {
          "type": "string",
          "hidden": false,
          "pattern": "^\\+?[0-9()\\s-]{4,}$",
          "required": false
          },
          "not_found": {
          "type": "boolean",
          "hidden": false,
          "required": false
          }
          }
          ```

      1. В разделе {% if locale == "ru-ru" %}**Интерфейс задания**{% endif %}{% if locale == "en-com" %}**Task interface**{% endif %} вы можете настроить внешний вид заданий для исполнителей.

          [Подробнее](spec.md) об интерфейсе заданий.

          Заполните блоки **HTML**, **JS** и **CSS**.

          {% cut "Код для блока **HTML**" %}

          {% if locale == "ru-ru" %}

          ```html
          <!-- Кнопки для перехода на сайт организации и поиска по ее названию в Яндексе-->
          <div class="left">
          <div class="title">not_var{{title}}
          </div>
          <div class="site-buttons">
          {{button label="Перейти на сайт" action=false href=url}}
          <a href="https://yandex.ru/search/?text=not_var{{title}}" target="_blank" class="btn_ya">Найти в Яндексе</a>
          </div>
          <!-- Поля для ввода телефона и электронной почты. Формат данных проверяется с помощью регулярных выражений. Выражение записано в параметр "Паттерн" выходных полей "phone" и "email". -->
          <div class="output-fields">
          <label><span>Телефон</span>{{field type="input" name="phone" placeholder="8 800 800 88 88"}}</label>
          <!-- Можно ввести только цифры, дефисы, знак +, пробелы и скобки. Символ "+" допустим только в первой позиции. Общий формат: +7(459)123-45-67, 8 800 123 45 67 -->
          <label><span>Почта</span>{{field type="input" name="email" placeholder="example@example.com"}}</label>
          <!-- Можно ввести только латинские буквы, точки, символы минус, плюс и нижнее подчеркивание. Общий формат: test.example@example.com -->
          </div>
          <!-- Чекбокс -->
          {{field class="site-buttons"type="checkbox" name="not_found" label="Нет контактов"}}
          </div>
          ```

          {% endif %}{% if locale == "en-com" %}

          ```html
          <!-- Buttons to go to the company's website and search for the company's name in Yandex -->
          <div class="left">
          <div class="title">not_var{{title}}
          </div>
          <div class="site-buttons">
          {{button label="Go to site" action=false href=url}}
          <a href="https://yandex.ru/search/?text=not_var{{title}}" target="_blank" class="btn_ya">Search Yandex</a>
          </div>
          <!-- Fields for phone numbers and email addresses. The data format is checked using regular expressions. The expression is written in the "Pattern" parameter of the "phone" and "email" output fields. -->
          <div class="output-fields">
          <label><span>Phone</span>{{field type="input" name="phone" placeholder="8 800 800 88 88"}}</label>
          <!-- The performer can only enter numbers, hyphens, plus sign (+), spaces, and brackets. The "+" symbol is only allowed in the first position. General format: +7(459)123-45-67, 8 800 123 45 67 -->
          <label><span>Email</span>{{field type="input" name="email" placeholder="example@example.com"}}</label>
          <!-- The performer can only enter Latin letters, dots, plus and minus signs, and underscores. General format: test.example@example.com -->
          </div>
          <Checkbox>
          {{field class="site-buttons"type="checkbox" name="not_found" label="No contacts"}}
          </div>
          ```

          {% endif %}

          {% endcut %}

          {% cut "Код для блока **JS**" %}

          {% if locale == "ru-ru" %}

          ```javascript
          exports.Task = extend(TolokaHandlebarsTask, function (options) {
          TolokaHandlebarsTask.call(this, options);
          }, {
          // Показываем сообщение об ошибке, если данные введены неверно или поля не заполнены.
          _addError: function (message, field, errors) {
          errors || (errors = {
          task_id: this.getOptions().task.id,
          errors: {}
          });

          errors.errors[field] = {
          message: message
          };

          return errors;
          },

          // Дописываем `https://` в начало ссылки, если его нет.
          _prepareURL: function (url) {
          if (!/^\s*https?:\/\//i.test(url)) {
          url = 'http://' + url.trim();
          }

          return url;
          },

          // Устанавливаем состояния полей.
          _renderField: function(values) {
          if (this.getWorkspaceOptions().isReadOnly) return;

          for (const field of ['email', 'phone']) {
          if (this.getField(field)) {
          const impl = this.getField(field).getImplementation();
          if (impl.options.disabled !== values.not_found) {
          impl.options.disabled = values.not_found;
          impl.render();
          }

          $('[name="' + field + '"]', this.getDOMElement())
          .parents('.field')
          .toggleClass('field_readonly', values.not_found);
          }
          }
          $('.popup_type_error', this.getDOMElement()).removeClass('popup_visible');
          },

          setSolutionOutputValues: function (values) {
          this._renderField(values);

          TolokaHandlebarsTask.prototype.setSolutionOutputValues.call(this, values);
          },

          onRender: function() {
          this._renderField(this.getSolution().output_values);
          },

          // Эти данные будут переданы в Handlebars-часть шаблона.
          getTemplateData: function () {
          const data = TolokaHandlebarsTask.prototype.getTemplateData.call(this);

          // Дописываем `http://` в начало ссылки, если нужно.
          data.url = this._prepareURL(data.url);

          return data;
          },

          // Проверяем ответы при отправке задания.
          validate: function (solution) {
          let errors;
          const output = solution.output_values;

          if (output.not_found) {
          delete output.email;
          delete output.phone;

          } else {
          const fields = ['email', 'phone'];

          // Показываем ошибку, если ни одно из полей не заполнено.
          if (!Object.entries(solution.output_values).find(e => fields.includes(e[0]) && e[1])) {
          for (const field of fields) {
          errors = this._addError(this.getWorkspaceOptions().translations['field:error:REQUIRED'], field, errors);
          }
          }

          delete output.not_found;
          }

          solution.output_values = output;
          return errors || TolokaHandlebarsTask.prototype.validate.call(this, solution);
          }
          });

          function extend(ParentClass, constructorFunction, prototypeHash) {
          constructorFunction = constructorFunction || function () { };
          prototypeHash = prototypeHash || {};

          if (ParentClass) {
          constructorFunction.prototype = Object.create(ParentClass.prototype);
          }

          for (var i in prototypeHash) {
          constructorFunction.prototype[i] = prototypeHash[i];
          }

          return constructorFunction;
          }
          ```

          {% endif %}{% if locale == "en-com" %}

          ```javascript
          exports.Task = extend(TolokaHandlebarsTask, function (options) {
          TolokaHandlebarsTask.call(this, options);
          }, {
          // Show an error message if the data is entered incorrectly or fields are empty.
          _addError: function (message, field, errors) {
          errors || (errors = {
          task_id: this.getOptions().task.id,
          errors: {}
          });

          errors.errors[field] = {
          message: message
          };

          return errors;
          },

          // Add `https://` at the beginning of the link, if none.
          _prepareURL: function (url) {
          if (!/^\s*https?:\/\//i.test(url)) {
          url = 'http://' + url.trim();
          }

          return url;
          },

          // Set the field status.
          _renderField: function(values) {
          if (this.getWorkspaceOptions().isReadOnly) return;

          for (const field of ['email', 'phone']) {
          if (this.getField(field)) {
          const impl = this.getField(field).getImplementation();
          if (impl.options.disabled !== values.not_found) {
          impl.options.disabled = values.not_found;
          impl.render();
          }

          $('[name="' + field + '"]', this.getDOMElement())
          .parents('.field')
          .toggleClass('field_readonly', values.not_found);
          }
          }
          $('.popup_type_error', this.getDOMElement()).removeClass('popup_visible');
          },

          setSolutionOutputValues: function (values) {
          this._renderField(values);

          TolokaHandlebarsTask.prototype.setSolutionOutputValues.call(this, values);
          },

          onRender: function() {
          this._renderField(this.getSolution().output_values);
          },

          // This data will be passed to the Handlebars part of the template.
          getTemplateData: function () {
          const data = TolokaHandlebarsTask.prototype.getTemplateData.call(this);

          // Add `http://` to the beginning of the link, if necessary.
          data.url = this._prepareURL(data.url);

          return data;
          },

          // We check the responses when the task is submitted.
          validate: function (solution) {
          let errors;
          const output = solution.output_values;

          if (output.not_found) {
          delete output.email;
          delete output.phone;

          } else {
          const fields = ['email', 'phone'];

          // We show an error if none of the fields are filled in.
          if (!Object.entries(solution.output_values).find(e => fields.includes(e[0]) && e[1])) {
          for (const field of fields) {
          errors = this._addError(this.getWorkspaceOptions().translations['field:error:REQUIRED'], field, errors);
          }
          }

          delete output.not_found;
          }

          solution.output_values = output;
          return errors || TolokaHandlebarsTask.prototype.validate.call(this, solution);
          }
          });

          function extend(ParentClass, constructorFunction, prototypeHash) {
          constructorFunction = constructorFunction || function () { };
          prototypeHash = prototypeHash || {};

          if (ParentClass) {
          constructorFunction.prototype = Object.create(ParentClass.prototype);
          }

          for (var i in prototypeHash) {
          constructorFunction.prototype[i] = prototypeHash[i];
          }

          return constructorFunction;
          }
          ```

          {% endif %}

          {% endcut %}

          {% cut "Код для блока **CSS**" %}

          {% if locale == "ru-ru" %}

          ```css
          /* Задание на странице */
          .task {
          width: 450px;
          }

          /* Кнопка "Найти в Яндексе" */
          .btn_ya {
          font-size: 13px;
          margin-left: 10px;
          color: #0065D9;
          }

          /* Заголовок с названием организации */
          .title {
          padding: 10px;
          border-radius: 5px;
          font-size: 18px;
          line-height: 24px;
          }

          /* Поля для ввода телефона и электронной почты */
          .output-fields {
          display: table;
          font-size: 13px;
          border-spacing: 0 5px;
          }

          .output-fields > label {
          display: table-row;
          margin-bottom: 5px;
          }

          .output-fields > label > span {
          display: table-cell;
          text-align: left;
          padding-right: 10px;
          padding-left: 10px;
          }

          .output-fields > label > .field {
          margin: 0;
          display: table-cell;
          width: 100%;
          }

          /* Кнопка для перехода на сайт организации */
          .site-buttons {
          margin: 10px;
          margin-left: 5;
          }

          /* Отображение задания на мобильных устройствах. */

          @media (pointer: coarse) {
          .field__hotkey {
          display:none;
          }
          }

          @media (max-width: 980px) {
          .task {
          width: initial;
          }
          .popup__text {
          width: auto;
          }
          }
          ```

          {% endif %}{% if locale == "en-com" %}

          ```css
          /* Task on the page */
          .task {
          width: 450px;
          }

          /* The "Find in Yandex" button */
          .btn_ya {
          font-size: 13px;
          margin-left: 10px;
          color: #0065D9;
          }

          /* Title with the organization name */
          .title {
          padding: 10px;
          border-radius: 5px;
          font-size: 18px;
          line-height: 24px;
          }

          /* Phone and email input fields*/
          . output-fields {
          display: table;
          font-size: 13px;
          border-spacing: 0 5px;
          }

          .output-fields > label {
          display: table-row;
          margin-bottom: 5px;
          }

          .output-fields > label > span {
          display: table-cell;
          text-align: left;
          padding-right: 10px;
          padding-left: 10px;
          }

          .output-fields > label > .field {
          margin: 0;
          display: table-cell;
          width: 100%;
          }

          /* Button to go to the organization's website*/
          . site-buttons {
          margin: 10px;
          margin-left: 5;
          }

          /* Task display on mobile devices. */

          @media (pointer: coarse) {
          .field__hotkey {
          display:none;
          }
          }

          @media (max-width: 980px) {
          .task {
          width: initial;
          }
          .popup__text {
          width: auto;
          }
          }
          ```

          {% endif %}

          {% endcut %}

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

          {% note info %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. В открывшемся окне проверьте работу опций задания:

          1. Ответьте на вопрос.

          1. В правом нижнем углу нажмите кнопку {% if locale == "ru-ru" %}**Отправить**{% endif %}{% if locale == "en-com" %}**Submit**{% endif %}.

          1. Выйдите из режима предпросмотра.

      1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

    {% endlist %}

1. 1. Напишите краткую и ясную инструкцию. Опишите в ней, что надо сделать, и приведите примеры.

    Вы можете подготовить инструкцию в формате HTML и вставить ее в редактор. Чтобы переключиться в режим HTML, нажмите **<>**.

   1. Нажмите **Завершить**.

Подробнее о работе с проектом читайте в разделе [Проект](project.md).

## Создайте пул {#create-pool}

Пул — это набор оплачиваемых заданий, которые одновременно выдаются исполнителям.

1. Откройте страницу проекта по поиску информации в интернете.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Добавить пул**{% endif %}{% if locale == "en-com" %}**Add a pool**{% endif %}.

1. Укажите {% if locale == "ru-ru" %}**Название пула**{% endif %}{% if locale == "en-com" %}**Pool name**{% endif %}.

1. В блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} отфильтруйте исполнителей.

    Чтобы задание было доступно только исполнителям, владеющим русским языком:

    1. Нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Готовые наборы аудиторий**{% endif %}{% if locale == "en-com" %}**Audience presets**{% endif %} и выберите набор фильтров {% if locale == "ru-ru" %}**Русскоязычные исполнители**{% endif %}{% if locale == "en-com" %}**Russian speaking perfomers**{% endif %}.

    1. Присвойте [навык](../../glossary.md#skill) исполнителям, которые участвуют в проекте по поиску информации в интернете. В дальнейшем это позволит поручить проверку выполненных заданий только исполнителям без навыка — то есть тем, кто не выполнял задания этого проекта.

    Нажмите кнопку {% if locale == "en-com" %}**+ Add skill**{% endif %}{% if locale == "ru-ru" %}**+Добавить навык**{% endif %} и укажите название навыка, например `Поиск информации`.

    {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. {% include [contain_item-pool-speed-quality](../_includes/concepts/contain_item/id-contain_item/pool-speed-quality.md) %}

1. В блоке {% if locale == "ru-ru" %}**Цена**{% endif %}{% if locale == "en-com" %}**Price **{% endif %} в поле {% if locale == "ru-ru" %}**Цена за страницу заданий**{% endif %}{% if locale == "en-com" %}**Price per task suite**{% endif %} укажите цену. Например, `0.01`.

    {% cut "Что такое страница заданий?" %}

    На одной странице может отображаться одно или несколько заданий. Если задания простые, то можно добавлять 10–20 заданий на одну страницу. Не рекомендуем создавать длинные страницы, поскольку это снизит скорость загрузки данных у исполнителя.

    Исполнитель получит оплату, только если выполнил все задания на странице.

    Количество заданий на странице вы определите при [загрузке заданий](#smart-mixing).

    {% endcut %}

    Подробнее о том, как установить [справедливую цену](dynamic-pricing.md#section_wb1_lhl_vlb).

1. [Правила контроля качества](../../glossary.md#quality-control) позволяют отсеивать невнимательных исполнителей.

    {% list tabs %}

    - Для проекта с перекрытием больше единицы

      В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} задайте {% if locale == "ru-ru" %}**Частоту показа капчи**{% endif %}{% if locale == "en-com" %}**Captcha frequency**{% endif %}, например {% if locale == "ru-ru" %}**Среднюю**{% endif %}{% if locale == "en-com" %}**Middle**{% endif %}.

      Добавьте следующие правила контроля качества:

      1. {% if locale == "ru-ru" %}**Контрольные задания**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %} — отсеивает исполнителей, которые часто ошибаются в контрольных заданиях.

          1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

          1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Контрольные задания**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %}.

          1. Задайте правило для контрольного задания: если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %} на контрольные вопросы **≥ 3** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%)**{% endif %} на контрольные вопросы **< 60**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %} исполнителя {% if locale == "ru-ru" %}**на проекте на 10 дней**{% endif %}{% if locale == "en-com" %}**on project**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В качестве причины укажите **Контрольное задание**.

            {% if locale == "ru-ru" %}![](../_images/tutorials/image-segmentation/wsdm-tutorial-part1-2.png){% endif %}

            Это означает, что если исполнитель выполнил более трех контрольных заданий и дал неправильные ответы более чем в 60% из них, он будет заблокирован и не сможет выполнять задания на этом проекте в течение 10 дней.

      1. {% if locale == "ru-ru" %}**Быстрые ответы**{% endif %}{% if locale == "en-com" %}**Fast responses**{% endif %} — отсеивает исполнителей, которые отвечают слишком быстро.

          1. В поле {% if locale == "ru-ru" %}**Учитывать последних страниц заданий**{% endif %}{% if locale == "en-com" %}**Recent task suites to use**{% endif %} введите количество последних страниц заданий, выполненных исполнителем. Например, `10`.

          1. В поле {% if locale == "ru-ru" %}**Минимальное время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Minimum time per task suite**{% endif %} укажите время в секундах. Например, `20`.

          1. Задайте правило для быстрого ответа: если {% if locale == "ru-ru" %}**количество быстрых ответов**{% endif %}{% if locale == "en-com" %}**number of fast responses**{% endif %}** ≥ 1**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**у меня**{% endif %}{% if locale == "en-com" %}**on requester**{% endif %} на {% if locale == "ru-ru" %}**10 дней**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В поле {% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} введите **Быстрые ответы**.

            {% if locale == "ru-ru" %}![](../_images/other/fast-answers2.png){% endif %}

            Это означает, что если исполнитель выполнит хотя бы одну страницу заданий быстрее, чем за 20 секунд, он не сможет выполнять ваши задания 10 дней.

      1. {% if locale == "ru-ru" %}**Капча**{% endif %}{% if locale == "en-com" %}**Captcha**{% endif %} — предотвращает выполнение заданий роботами.

          1. В поле {% if locale == "ru-ru" %}**Учитывать последних вводов капчи**{% endif %}{% if locale == "en-com" %}**Recent captchas to use**{% endif %} введите количество последних страниц заданий, выполненных исполнителем. Например, `10`.

          1. Задайте правило для капчи: если {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %}** ≥ 5** и {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%) **{% endif %}**< 65**, то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**на проекте**{% endif %}{% if locale == "en-com" %}**on project**{% endif %} на {% if locale == "ru-ru" %}**10 дней**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В поле {% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} введите **Капча**.

            {% if locale == "ru-ru" %}![](../_images/control-rules/captcha/qcr-captcha_example1.png){% endif %}

            Это означает, что если исполнитель верно вводит капчу менее чем в 65% случаев, он не сможет выполнять задания на проекте в течение 10 дней.

      1. {% if locale == "ru-ru" %}**Пропуск заданий**{% endif %}{% if locale == "en-com" %}**Skipped assignments**{% endif %} — отсеивает исполнителей, которые пропускают несколько страниц заданий подряд.

          Задайте правило для [пропущенных заданий](pool_statistic-pool.md#skipped-tasks): если {% if locale == "ru-ru" %}**пропущенных подряд страниц заданий**{% endif %}{% if locale == "en-com" %}**task pages skipped in a row**{% endif %}** ≥ 4**, то {% if locale == "ru-ru" %}**приостановить**{% endif %}{% if locale == "en-com" %}**suspend**{% endif %}{% if locale == "ru-ru" %}**в пуле**{% endif %}{% if locale == "en-com" %}**in pull**{% endif %} на {% if locale == "ru-ru" %}**10 дней**{% endif %}{% if locale == "en-com" %}**10 days**{% endif %}. В поле {% if locale == "ru-ru" %}**Причина**{% endif %}{% if locale == "en-com" %}**Reason**{% endif %} введите **Пропуск заданий**.

          {% if locale == "ru-ru" %}![](../_images/other/skipped.png){% endif %}

          Это означает, что если исполнитель пропустит 4 и более страниц заданий, он потеряет доступ к пулу на 10 дней.

      1. Установите перекрытие — количество исполнителей, которые должны выполнить задание. В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} в разделе {% if locale == "ru-ru" %}**Перекрытие задания**{% endif %}{% if locale == "en-com" %}**Task overlap**{% endif %} укажите значение поля {% if locale == "ru-ru" %}**Количество исполнителей, которые должны выполнить каждое задание**{% endif %}{% if locale == "en-com" %}**The number of performers to complete every task**{% endif %}. Для заданий этого типа, как правило, `3-5`.

    - Для проекта с отложенной приемкой

      В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} включите опцию {% if locale == "ru-ru" %}**Отложенная приёмка заданий**{% endif %}{% if locale == "en-com" %}**Non-automatic acceptance**{% endif %}.

      {% cut "Что такое отложенная приемка?" %}

      [Отложенная приемка](offline-accept.md) позволяет вам просматривать [выполненные страницы заданий](../../glossary.md#completed-tasks) перед тем, как принять их и заплатить исполнителю. Задания, выполненные в несоответствии с инструкцией, можно отклонять. Максимальный срок проверки устанавливается в поле **Срок проверки**.

      {% endcut %}

      В поле {% if locale == "ru-ru" %}**Срок проверки в днях**{% endif %}{% if locale == "en-com" %}**Review period in days**{% endif %} укажите количество дней на проверку задания.

      Добавьте следующие блоки контроля качества:

      - {% if locale == "ru-ru" %}**Обработка отклоненных и принятых заданий**{% endif %}{% if locale == "en-com" %}**Recompletion of rejected assignments**{% endif %} — отправляет отклоненные вами задания другим исполнителям по заданным правилам.

        1. Нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add а quality control rule**{% endif %}.

        1. Найдите в списке блок {% if locale == "ru-ru" %}**Правила**{% endif %}{% if locale == "en-com" %}**Rules**{% endif %} и выберите пункт {% if locale == "ru-ru" %}**Обработка отклоненных и принятых заданий**{% endif %}{% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %}.

        1. Задайте правило для отклоненного задания: если {% if locale == "ru-ru" %}**задание становится отклоненным**{% endif %}{% if locale == "en-com" %}**assignment becomes rejected**{% endif %}, то {% if locale == "ru-ru" %}**увеличить перекрытие на**{% endif %}{% if locale == "en-com" %}**extend overlap by**{% endif %} **1**. А также включите опцию {% if locale == "ru-ru" %}**Открыть пул, если закрыт**{% endif %}{% if locale == "en-com" %}**Open pool if closed**{% endif %}.

            {% if locale == "ru-ru" %}![](../_images/other/rejected-accepted-tasks.png){% endif %}

            Это означает, что отклоненное задание будет возвращено в пул и показано еще одному исполнителю.

      - {% if locale == "ru-ru" %}**Результаты проверки**{% endif %}{% if locale == "en-com" %}**Results of assignment review**{% endif %} — ограничивает доступ к пулу исполнителей, которые часто ошибаются.

          Задайте правило для отклоненного задания: если {% if locale == "ru-ru" %}**количество проверенных ответов**{% endif %}{% if locale == "en-com" %}**total reviewed responses**{% endif %} **≥ 3** и {% if locale == "ru-ru" %}**процент отклоненных ответов**{% endif %}{% if locale == "en-com" %}**rejected responses (%)**{% endif %} **> 35** то {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %}{% if locale == "ru-ru" %}**у меня**{% endif %}{% if locale == "en-com" %}**on requester**{% endif %} на {% if locale == "ru-ru" %}**15 дней**{% endif %}{% if locale == "en-com" %}**15 days**{% endif %}.

          {% if locale == "ru-ru" %}![](../_images/other/offline-accept.png){% endif %}

          Это означает, что если 35% и более ответов исполнителя будут отклонены, он будет заблокирован и не сможет больше выполнять ваши задания 15 дней. Правило начинает действовать после проверки 3 ответов исполнителя.

          {% note info %}

          Вы можете скопировать настройки контроля качества из другого пула. Для этого в блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} в разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} нажмите {% if locale == "ru-ru" %}**перенесите их из другого пула**{% endif %}{% if locale == "en-com" %}**copy them from another pool**{% endif %}.

          {% endnote %}

    {% endlist %}

1. Настройте {% if locale == "ru-ru" %}**Параметры**{% endif %}{% if locale == "en-com" %}**Parameters**{% endif %} пула.

    В блоке **Дополнительные настройки** укажите значение поля {% if locale == "ru-ru" %}**Время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Time per task suite**{% endif %}. Времени должно быть достаточно для чтения инструкции, загрузки задания, поиска информации и ответа. Например, `1200` секунд.

1. Нажмите кнопку {% if locale == "ru-ru" %}**Создать пул**{% endif %}{% if locale == "en-com" %}**Create a pool**{% endif %}.

## Загрузите задания {#upload-file}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. На странице пула нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне вы можете скачать шаблон файла.

1. В открывшемся окне настройте параметры загрузки файла.

    {% list tabs %}

    - Для проекта с перекрытием больше единицы

        1.  1. Выберите {% if locale == "ru-ru" %}**Умное смешивание**{% endif %}{% if locale == "en-com" %}**Smart mixing**{% endif %}.

            1. В поле {% if locale == "ru-ru" %}**Основных заданий**{% endif %}{% if locale == "en-com" %}**Main tasks**{% endif %} укажите `9`.

            1. В поле {% if locale == "ru-ru" %}**Обучающих заданий**{% endif %}{% if locale == "en-com" %}**Training tasks**{% endif %} укажите `0`.

            1. В поле {% if locale == "ru-ru" %}**Контрольных заданий**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %} укажите `1`.

            1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}.

            1. В открывшемся окне выберите файл с заданиями для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

            1. В открывшемся окне проверьте количество заданий и нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

        1. Создайте [контрольное задание](../../glossary.md#control-task):

            1. Нажмите кнопку {% if locale == "ru-ru" %}**Разметить**{% endif %}{% if locale == "en-com" %}**Edit**{% endif %}.

                {% note info %}

                Если вместо **умного смешивания** было выбрано другое, необходимо нажать кнопку **Разметить**. Если такой кнопки нет, удалите файл и загрузите заново.

                {% endnote %}

            1. В открывшемся окне нажмите кнопку {% if locale == "ru-ru" %}**Создать контрольные**{% endif %}{% if locale == "en-com" %}**Create control tasks**{% endif %}.

            1. В открывшемся окне в разделе {% if locale == "ru-ru" %}**Создать контрольное задание**{% endif %}{% if locale == "en-com" %}**Create control task**{% endif %} слева отметьте пункт **result**.

            1. Выберите правильный ответ на вопрос.

            1. Нажмите кнопку {% if locale == "ru-ru" %}**Сохранить и перейти к следующему**{% endif %}{% if locale == "en-com" %}**Save and go to next**{% endif %}.

            1. Выйдите из режима разметки заданий.

                {% note info %}

                В небольших пулах контрольные задания должны составлять около 10% от всех заданий. Включайте разные варианты правильных ответов в равных количествах. Посмотрите распределение ответов на странице {% if locale == "ru-ru" %}**Разметить задания**{% endif %}{% if locale == "en-com" %}**Edit tasks**{% endif %} на вкладке {% if locale == "ru-ru" %}**Контрольные**{% endif %}{% if locale == "en-com" %}**Control tasks**{% endif %}.

                {% endnote %}

    - Для проекта с отложенной приемкой

      1. Выберите {% if locale == "ru-ru" %}**Указать вручную**{% endif %}{% if locale == "en-com" %}**Set manually**{% endif %}.

      1. В поле {% if locale == "ru-ru" %}**Заданий на странице**{% endif %}{% if locale == "en-com" %}**Tasks per page**{% endif %} укажите `1`.

      1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}.

      1. В открывшемся окне выберите файл с заданиями для загрузки и нажмите кнопку {% if locale == "ru-ru" %}**Открыть**{% endif %}{% if locale == "en-com" %}**Open**{% endif %}.

      1. В открывшемся окне проверьте количество заданий и нажмите кнопку {% if locale == "ru-ru" %}**Добавить**{% endif %}{% if locale == "en-com" %}**Add**{% endif %}.

    Нажмите кнопку ![](../_images/other/b-start-pool.svg), чтобы запустить пул.

  {% endlist %}

## Получите результаты {#get-results}

Когда исполнители выполнили ваши задания, получите результаты.

{% list tabs %}

- Для проекта с перекрытием больше единицы

  На странице пула нажмите кнопку {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %}. В открывшемся окне нажмите кнопку {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %}.

- Для проекта с отложенной приемкой

  1. На странице пула нажмите кнопку {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %}. В открывшемся окне:

      1. В блоке {% if locale == "ru-ru" %}**Статус**{% endif %}{% if locale == "en-com" %}**Status**{% endif %} оставьте включенной только опцию {% if locale == "ru-ru" %}**Не проверенные**{% endif %}{% if locale == "en-com" %}**Submitted**{% endif %}.

      1. В блоке {% if locale == "ru-ru" %}**Поля**{% endif %}{% if locale == "en-com" %}**Columns**{% endif %} оставьте включенной только опцию {% if locale == "ru-ru" %}**id ответа**{% endif %}{% if locale == "en-com" %}**assignment ID**{% endif %}.

      1. Отключите опцию {% if locale == "ru-ru" %}**Разделять ответы пустой строкой**{% endif %}{% if locale == "en-com" %}**Separate assignments with empty row**{% endif %}.{% if locale == "ru-ru" %}

          ![](../_images/tutorials/image-segmentation/wsdm-tutorial-part3-2.png)

          {% endif %}

      1. Нажмите кнопку {% if locale == "ru-ru" %}**Скачать результаты**{% endif %}{% if locale == "en-com" %}**Download results**{% endif %}.

{% endlist %}

## Поручите проверку исполнителям {#check-up-project}

Если в проекте по поиску информации в интернете вы использовали {% if locale == "ru-ru" %}**Отложенную приемку**{% endif %}{% if locale == "en-com" %}**Non-automatic acceptance**{% endif %}, отдайте результаты на проверку исполнителям в качестве задания. [Подробнее](offline-accept.md) об отложенной приемке.

1. Создайте еще один проект с помощью [Пустого]({{ blank }}) шаблона. О том, какие настройки нужно задать для этого проекта, написано ниже.

1. Создайте интерфейс задания, чтобы исполнитель увидел:

    - название организации;
    - электронную почту и номер телефона организации;
    - переключатель с вариантами ответов:

        `Электронная почта и номер телефона указаны верно.`

        `Электронная почта указана неверно.`

        `Номер телефона указан неверно.`

        `Электронная почта и номер телефона указаны неверно.`

1. Добавьте пул и укажите в нем {% if locale == "ru-ru" %}**Перекрытие**{% endif %}{% if locale == "en-com" %}**Overlap**{% endif %} — 3.
1. Чтобы это задание было доступно исполнителям, которые не искали информацию в сети на вашем проекте, установите {% if locale == "ru-ru" %}**фильтр**{% endif %}{% if locale == "en-com" %}**filter**{% endif %}.

    1. В разделе {% if locale == "ru-ru" %}**Исполнители**{% endif %}{% if locale == "en-com" %}**Performers**{% endif %} нажмите {% if locale == "ru-ru" %}**Добавить фильтр**{% endif %}{% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Найдите в списке блок {% if locale == "ru-ru" %}**Навыки**{% endif %}{% if locale == "en-com" %}**Skills**{% endif %} и выберите навык {% if locale == "ru-ru" %}**Выбрать навык**{% endif %}{% if locale == "en-com" %}**Choose skill**{% endif %}.

    1. В поле {% if locale == "ru-ru" %}**Выберите навык**{% endif %}{% if locale == "en-com" %}**Choose a skill**{% endif %} выберите **Поиск информации**.

    1. В поле **?** укажите `=`. Поле {% if locale == "ru-ru" %}**Отсутствует**{% endif %}{% if locale == "en-com" %}**Missing**{% endif %} оставьте пустым.

1. Загрузите в пул задания и запустите его.

1. Когда пул будет полностью выполнен, запустите [агрегацию результатов](result-aggregation.md).

1. Примите задания по поиску информации, в которых нет ошибок. Остальные отклоните, указав причину. Как только вы отклоните задания, они будут отправлены на повторное выполнение.

## Решение проблем {#troubleshooting}

{% cut "Как сделать так, чтобы для разных вопросов было различное количество вариантов ответов?" %}

Используйте [конкатенацию](t-components/helpers.md#concat), например:

```html
{{field type="checkbox" name=(concat "result." @index ) label=(concat "checkbox –
          " @index) size="L"}}
```

{% endcut %}

{% cut "Как в JS сделать так, чтобы если чекбокс отмечен, то ссылку не запрашивать, а если ссылка вставлена, то галочка стоять не должна?" %}

1. Посмотрите как это реализовано в шаблоне «[Поиск данных в сети](#internet-search__create-project)».

1. Для решения второй задачи вы можете добавить ещё одну валидацию по аналогии с этой:

{% if locale == "ru-ru" %}

    ```javascript
    if (solution.output_values.url && solution.output_values.check) {return {task_id:
    this.getTask().id,errors: {'url': {code: 'Вставьте ссылку или отметьте галочкой,что сайта нет'}}}}
    ```

    {% endif %}{% if locale == "en-com" %}

    ```javascript
    if (solution.output_values.url && solution.output_values.check) {return {task_id:
    this.getTask().id,errors: {'url': {code: ''Insert a link or check the box if the site doesn't exist'}}}}
    ```

    {% endif %}

{% endcut %}

{% cut "Как в режиме предпросмотра включить загрузку аудиофайлов?" %}

В режиме предпросмотра проверить загрузку файлов нельзя, но это можно сделать в песочнице, выполнив своё задание. Для этого нужно зарегистрироваться в сендбоксе в качестве исполнителя и добавить логин в доверенные на странице **Пользователи**. Подробнее можете прочитать в этой [статье](sandbox.md) .

{% endcut %}

{% cut "Исполнитель не может загрузить файл в задание?" %}

Если никто из исполнителей не смог отправить задание, скорее всего проблема в валидации в JS. Проверьте её ещё раз.

Перенесите проект в сендбокс и попробуйте выполнить задание самостоятельно в песочнице.

{% endcut %}

{% cut "Как снять выбор с радиокнопки?" %}

Снять выбор нельзя. Только изменить на другую радиокнопку с ответом.

{% endcut %}

{% cut "Что делать, если атрибуты радио-кнопки в предпросмотре отображаются правильно, а после сохранения — нет?" %}

Если после сохранения инструкции пропадают теги или атрибуты (например, `checked="true"`), значит они не поддерживаются. Полный список допустимых в инструкции тегов можно найти в [руководстве](instruction.md#html-yes).

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}