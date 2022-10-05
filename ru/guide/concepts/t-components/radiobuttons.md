# Переключатель

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать переключатель в {% if locale == "ru-ru" %}[Конструкторе шаблонов](https://toloka.ai/ru/docs/template-builder/reference/field.radio-group){% endif %}{% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/reference/field.radio-group){% endif %}.

{% endnote %}


Чтобы вставить в задание переключатель, используйте компонент `{{field type="radio" name="<название [выходного поля](../incoming.md)>"}}`. Например (переключатель из двух элементов):
 {% if locale == "ru-ru" %}
```no-highlight
{{field type="radio" name="result" label="Да" value="Yes" hotkey="1"}}
{{field type="radio" name="result" label="Нет" value="No" hotkey="2"}}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{{field type="radio" name="result" label="Yes" value="Yes" hotkey="1"}}
{{field type="radio" name="result" label="No" value="No" hotkey="2"}}
```
{% endif %}
В описании [выходных данных](../incoming.md) добавьте поле с типом `string`. Например:

```no-highlight
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
||``` type ``` | Тип поля: `radio` — переключатель. | да | нет||
||``` name ``` | Атрибут для поля выходных данных. Содержит имя поля выходных данных. | да | нет||
||``` label ``` | Подпись. Например: `label="Да"`. | нет | нет||
||``` value ``` | Передаваемое значение (записывается в файл с выходными данными). | нет | нет||
||``` hotkey ``` | Горячая клавиша для выбора значения. | нет | нет||
||``` validation-show ``` | Расположение всплывающих подсказок (отображаются, если ответ не прошел валидацию). Расположение указывается относительно поля ввода.
Допустимые значения:
- Над полем ввода: `"top-left"` (слева), `"top-center"` (посередине), `"top-right"` (справа).
- Под полем ввода: `"bottom-left"` (слева), `"bottom-center"` (посередине), `"bottom-right"` (справа).
- Слева от поля ввода: `"left-top"` (сверху), `"left-center"` (посередине), `"left-bottom"` (внизу).
- Справа от поля ввода: `"right-top"` (сверху), `"right-center"` (посередине), `"right-bottom"` (внизу).
- Не показывать сообщение (`"false"`). | нет | ``` "top-left" ```||
||``` checked ``` | Состояние переключателя при отображении страницы:
- `checked=true` — включен.
- `checked=false` — выключен. | нет | ``` false ```||
||``` size ``` | Размер поля.
Допустимые значения: `"M"`, `"L"`. | нет | ``` "L" ```||
||``` width ``` | Ширина поля. Указывается в следующих единицах:
- Пиксели. Например: `width="100px"`.
- Доля от размера родительского элемента. Например: `width="100%"`.
Можно также задать ширину формулой. Например: `width="calc(100%-30px)"`. | нет | зависит от длины подписи||
||``` class ``` | CSS-класс для поля. Например: `class="annotation"`. | нет | ``` ".field" ".field_type_radio" ```||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}