# Выпадающий список

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать выпадающий список в {% if locale == "ru-ru" %}[Конструкторе шаблонов](https://toloka.ai/ru/docs/template-builder/reference/field.select){% endif %}{% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.select){% endif %}.

{% endnote %}


Чтобы добавить в задание выпадающий список, используйте компонент `{{#field type="select" name="<название [выходного поля](../incoming.md)>"}}... {{/field}}`. Элементы выпадающего списка создаются с помощью вложенного выражения ``{{select_item}}``. Например:
 {% if locale == "ru-ru" %}
```no-highlight
{{#field type="select" name="colour" placeholder="Выберите цвет" width="200px"}}
  {{select_item value="red" text="Красный"}}
  {{select_item value="green" text="Зелёный"}}
{{/field}}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{{#field type="select" name="colour" placeholder="Choose a color" width="200px"}}
  {{select_item value="red" text="Red"}}
  {{select_item value="green" text="Green"}} {{/field}}
```
{% endif %}
В описании [выходных данных](../../../glossary.md#input-output-data-ru) добавьте поле с типом `string`:

```no-highlight
{
  "colour": {
    "type": "string",
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
``` type ``` | Тип поля: `select` — выпадающий список. | да | нет
``` name ``` | Атрибут для поля выходных данных. Содержит имя поля выходных данных. | да | нет
``` placeholder ``` | Название выпадающего списка в интерфейсе. | нет | нет
``` width ``` | Ширина поля. Указывается в следующих единицах:<br/><br/>- Пиксели. Например: `width="100px"`.<br/>    <br/>- Доля от размера родительского элемента. Например: `width="100%"`.<br/>    <br/><br/>Можно также задать ширину формулой. Например: `width="calc(100%-30px)"`. | нет | зависит от длины подписи
``` validation-show ``` | Расположение всплывающих подсказок (отображаются, если ответ не прошел валидацию). Расположение указывается относительно поля ввода.<br/><br/>Допустимые значения:<br/><br/>- Над полем ввода: `"top-left"` (слева), `"top-center"` (посередине), `"top-right"` (справа).<br/>    <br/>- Под полем ввода: `"bottom-left"` (слева), `"bottom-center"` (посередине), `"bottom-right"` (справа).<br/>    <br/>- Слева от поля ввода: `"left-top"` (сверху), `"left-center"` (посередине), `"left-bottom"` (внизу).<br/>    <br/>- Справа от поля ввода: `"right-top"` (сверху), `"right-center"` (посередине), `"right-bottom"` (внизу).<br/>    <br/>- Не показывать сообщение (`"false"`). | нет | ``` "top-left" ```
``` size ``` | Размер поля.<br/><br/>Допустимые значения: `"S"`, `"M"`, `"L"`. | нет | ``` "L" ```
``` class ``` | CSS-класс для поля. Например: `class="annotation"`. | нет | ``` ".field" ".field_type_select" ```
``` disabled ``` | Возможность редактирования:<br/><br/>- `disabled=true` — поле закрыто для редактирования.<br/>    <br/>- `disabled=false` — поле открыто для редактирования. | нет | ``` false ```
``` mode ``` | Направление, в котором раскрывается список:<br/><br/>- `mode="dropdown"` — вниз.<br/>    <br/>- `mode="dropup"` — вверх. | нет | ``` "dropdown" ```
``` value ``` | Текст, который записывается в файл с выходными данными при выборе данного элемента. | нет | нет
``` text ``` | Название элемента списка. | нет | нет
``` selected ``` | Элемент списка, который выбран по умолчанию:<br/><br/>- `selected=true` — сделать элемент списка выбранным по умолчанию.<br/>    <br/>- `selected=false` — оставить элемент списка невыбранным по умолчанию. | нет | ``` false ```

{% include [contact-support](../../_includes/contact-support-help.md) %}