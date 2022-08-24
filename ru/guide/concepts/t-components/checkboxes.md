# Флажок

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать флажок в {% if locale == "ru-ru" %}[Конструкторе шаблонов](https://toloka.ai/ru/docs/template-builder/reference/field.checkbox){% endif %}{% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.checkbox){% endif %}.

{% endnote %}


Чтобы вставить в задание флажок, используйте компонент `{{field type="checkbox" name="<название [выходного поля](../incoming.md)>"}}`. Например (набор из трех флажков):
 {% if locale == "ru-ru" %}
```no-highlight
{{field type="checkbox" name="red" label="красный" hotkey="1"}}
{{field type="checkbox" name="green" label="зелёный" hotkey="2"}}
{{field type="checkbox" name="yellow" label="жёлтый" hotkey="3"}}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{{field type="checkbox" name="red" label="red" hotkey="1"}}
{{field type="checkbox" name="green" label="green" hotkey="2"}}
{{field type="checkbox" name="yellow" label="yellow" hotkey="3"}}
```
{% endif %}
В описании [выходных данных](../incoming.md) добавьте поле с типом `boolean`. Например:
```no-highlight
{
  "red": {
    "type": "boolean",
    "required": true
  }
}
```

#### Параметры


Параметр
 |
Описание
 |
Обязательный
 |
Значение по умолчанию

----- | ----- | ----- | -----
``` type ``` | Тип поля: `checkbox` — флажок. | да | нет
``` name ``` | Атрибут для поля выходных данных. Содержит имя поля выходных данных. | да | нет
``` label ``` | Подпись. Например: `label="Да"`. | нет | нет
``` hotkey ``` | Горячая клавиша для выбора значения. | нет | нет
``` value ``` | Передаваемое значение (записывается в файл с выходными данными).<br/><br/>Допустимые значения: `true`, `false`. | нет | ``` false ```
``` validation-show ``` | Расположение всплывающих подсказок (отображаются, если ответ не прошел валидацию). Расположение указывается относительно поля ввода.<br/><br/>Допустимые значения:<br/><br/>- Над полем ввода: `"top-left"` (слева), `"top-center"` (посередине), `"top-right"` (справа).<br/>    <br/>- Под полем ввода: `"bottom-left"` (слева), `"bottom-center"` (посередине), `"bottom-right"` (справа).<br/>    <br/>- Слева от поля ввода: `"left-top"` (сверху), `"left-center"` (посередине), `"left-bottom"` (внизу).<br/>    <br/>- Справа от поля ввода: `"right-top"` (сверху), `"right-center"` (посередине), `"right-bottom"` (внизу).<br/>    <br/>- Не показывать сообщение (`"false"`). | нет | ``` "top-left" ```
``` checked ``` | Состояние флажка при отображении страницы:<br/><br/>- `checked=true` — установлен.<br/>    <br/>- `checked=false` — снят. | нет | ``` false ```
``` size ``` | Размер поля.<br/><br/>Допустимые значения: `"M"`, `"L"`. | нет | ``` "L" ```
``` width ``` | Ширина поля. Указывается в следующих единицах:<br/><br/>- Пиксели. Например: `width="100px"`.<br/>    <br/>- Доля от размера родительского элемента. Например: `width="100%"`.<br/>    <br/><br/>Можно также задать ширину формулой. Например: `width="calc(100%-30px)"`. | нет | зависит от длины подписи
``` disabled ``` | Возможность редактирования:<br/><br/>- `disabled=true` — поле закрыто для редактирования.<br/>    <br/>- `disabled=false` — поле открыто для редактирования. | нет | ``` false ```
``` class ``` | CSS-класс для поля. Например: `class="annotation"`. | нет | ``` ".field" ".field_type_checkbox" ```

{% include [contact-support](../../_includes/contact-support-help.md) %}