# Кнопка с проверкой перехода по ссылке

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать кнопку с проверкой перехода по ссылке в {% if locale == "ru-ru" %}[Конструкторе шаблонов](https://toloka.ai/ru/docs/template-builder/operations/internet-search#action.open-link){% endif %}{% if locale == "en-com" %}[Template Builder](https://toloka.ai/en/docs/template-builder/operations/internet-search#action.open-link){% endif %}.

{% endnote %}


Если в задании требуется перейти по ссылке (например, открыть веб-страницу), Толока может проверить, выполнил ли исполнитель этот переход. Ссылка для перехода отображается в задании в виде кнопки.

Варианты использования кнопки:

- Проверка перехода по ссылке. В [выходных данных](../../../glossary.md#input-output-data-ru) задания будет поле со значением `true` (переход выполнен) или `false` (переход не выполнен).

- Запрет на выполнение задания без перехода по ссылке. Для этого добавьте параметр `"allowed_values":[true]` в описание выходных данных.


Чтобы добавить кнопку со ссылкой в [интерфейс задания](../../../glossary.md#task-interface-ru), используйте компонент `{{field type="button-clicked" name="<название [выходного поля](../incoming.md)>"}}`. Например:
 {% if locale == "ru-ru" %}
```no-highlight
{{field type="button-clicked" name="ads" label="Нажми меня" href="https://yandex.ru" action=true}}
```
{% endif %}{% if locale == "en-com" %}
```no-highlight
{{field type="button-clicked" name="ads" label="Click me" href="https://yandex.ru" action=true}}
```
{% endif %}
Полный список параметров см. в [таблице](#table).

В описании выходных данных добавьте поле с типом `boolean`. Чтобы запретить отправку ответов без перехода по ссылке, добавьте параметр `"allowed_values":[true]`.

```no-highlight
{
  "ads": {
    "type": "boolean",
    "required": true,
    "allowed_values": [true]
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
``` type ``` | Тип поля: `button-clicked` — кнопка с проверкой перехода по ссылке. | да | нет
``` name ``` | Атрибут для поля выходных данных. Содержит имя поля выходных данных. | да | нет
``` label ``` | Надпись на кнопке. Например: `label="Нажми меня"` | нет | нет
``` href ``` | URL ресурса, на который должен перейти исполнитель для выполнения задания. | нет | нет
``` size ``` | Размер поля.<br/><br/>Допустимые значения: `"S"`, `"M"`, `"L"`, `"XL"`. | нет | ``` "L" ```
``` action ``` | Цвет кнопки:<br/><br/>- `action=true` — желтый.<br/>    <br/>- `action=false` — белый. | нет | ``` false ```

{% include [contact-support](../../_includes/contact-support-help.md) %}