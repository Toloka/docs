
#### Пул

Перейдите к редактированию пула (кнопка ![](../../../../_images/location-job/project/edit-project.svg) в верхнем правом углу страницы) и в блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} нажмите {% if locale == "ru-ru" %}**Добавить правило контроля качества**{% endif %}{% if locale == "en-com" %}**Add Quality Control Rule**{% endif %}.

Вы можете скопировать настройки контроля качества из другого пула. Для этого в разделе {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} нажмите ссылку {% if locale == "ru-ru" %}**Скопировать из другого пула**{% endif %}{% if locale == "en-com" %}**Copy audience filters and quality control settings**{% endif %}.

#### Проект

Откройте страницу проекта, перейдите на вкладку {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} и нажмите кнопку {% if locale == "ru-ru" %}**Настроить контроль качества**{% endif %}{% if locale == "en-com" %}**Set quality control**{% endif %}. Далее нажмите {% if locale == "ru-ru" %}**+ Добавить блок контроля качества**{% endif %}{% if locale == "en-com" %}**+ Add Quality Control Rule**{% endif %}.

Правила будут действовать во всех пулах проекта, и изменить их настройку в одном из пулов будет невозможно.

{% note alert %}

При [клонировании проекта](../../../../concepts/project.md) настройки контроля качества не переносятся.

{% endnote %}
