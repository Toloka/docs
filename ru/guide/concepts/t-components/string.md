# Поле для ввода строки

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать поле для ввода строки в {% if locale == "ru-ru" %}[Конструкторе шаблонов](../../../template-builder/reference/field.text.md){% endif %}{% if locale == "en-com" %}[Template Builder](../../../../en/docs/template-builder/reference/field.text.md){% endif %}.

{% endnote %}

Чтобы добавить в задание поле для ввода строки, используйте компонент `{{field type="input" name="<название [выходного поля](../incoming.md)>"}}`. Например:

{% if locale == "ru-ru" %}

```plaintext
{{field type="input" name="result" placeholder="Введите слово" validation-show="right-center"}}
```

{% endif %}{% if locale == "en-com" %}

```plaintext
{{field type="input" name="result" placeholder="Enter a word" validation-show="right-center"}}
```

{% endif %}

В описании [выходных данных](../incoming.md) добавьте поле с типом `string`. Например:

```plaintext
{
  "result": {
    "type": "string",
    "required": true
     }
}
```

#### Параметры

#|
||**Параметр**|**Описание**|**Обязательный**|**Значение по умолчанию**||
||`type` | Тип поля: `input` — поле для ввода строки. | да | нет||
||`name` | Атрибут для поля выходных данных. Содержит имя поля выходных данных. | да | нет||
||`value` | Строка, которая записывается в файл с выходными данными по умолчанию. | нет | нет||
||`width` | Ширина поля. Указывается в следующих единицах:

- Пиксели. Например: `width="100px"`.

- Доля от размера родительского элемента. Например: `width="100%"`.

Можно также задать ширину формулой. Например: `width="calc(100%-30px)"`. | нет | зависит от браузера и размера шрифта||
||`validation-show` | Расположение всплывающих подсказок (отображаются, если ответ не прошел валидацию). Расположение указывается относительно поля ввода.

Допустимые значения:

- Над полем ввода: `"top-left"` (слева), `"top-center"` (посередине), `"top-right"` (справа).

- Под полем ввода: `"bottom-left"` (слева), `"bottom-center"` (посередине), `"bottom-right"` (справа).

- Слева от поля ввода: `"left-top"` (сверху), `"left-center"` (посередине), `"left-bottom"` (внизу).

- Справа от поля ввода: `"right-top"` (сверху), `"right-center"` (посередине), `"right-bottom"` (внизу).

- Не показывать сообщение (`"false"`). | нет |` "top-left"`||
||`size` | Размер поля.

Допустимые значения: `"S"`, "`M"`, `"L"`, `"XL"`. | нет |`"L"`||
||`disabled` | Возможность редактирования:

- `disabled=true` — поле закрыто для редактирования.

- `disabled=false` — поле открыто для редактирования. | нет |`false`||
||`placeholder` | Текст-подсказка, отображаемый в пустом поле ввода. | нет | нет||
||`class` | CSS-класс для поля. Например: `class="annotation"`. | нет |`".field" ".field_type_input"`||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}