# Кнопка с проверкой перехода по ссылке

{% include [deprecate](../../../_includes/deprecate.md) %}

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать кнопку с проверкой перехода по ссылке в {% if locale == "ru-ru" %}[Конструкторе шаблонов](../../../template-builder/operations/internet-search.md#action.open-link){% endif %}{% if locale == "en-com" %}[Template Builder](../../../../en/template-builder/operations/internet-search.md#action.open-link){% endif %}.

{% endnote %}

Если в задании требуется перейти по ссылке (например, открыть веб-страницу), Толока может проверить, выполнил ли исполнитель этот переход. Ссылка для перехода отображается в задании в виде кнопки.

Варианты использования кнопки:

- Проверка перехода по ссылке. В [выходных данных](../../../glossary.md#input-output-data) задания будет поле со значением `true` (переход выполнен) или `false` (переход не выполнен).

- Запрет на выполнение задания без перехода по ссылке. Для этого добавьте параметр `"allowed_values":[true]` в описание выходных данных.

Чтобы добавить кнопку со ссылкой в [интерфейс задания](../../../glossary.md#task-interface), используйте компонент `{{field type="button-clicked" name="<название выходного поля>"}}`. Например:

{% if locale == "ru-ru" %}

```plaintext
{{field type="button-clicked" name="ads" label="Нажми меня" href="https://yandex.ru" action=true}}
```

{% endif %}{% if locale == "en-com" %}

```plaintext
{{field type="button-clicked" name="ads" label="Click me" href="https://yandex.ru" action=true}}
```

{% endif %}

Полный список параметров см. в [таблице](#parametry).

В описании выходных данных добавьте поле с типом `boolean`. Чтобы запретить отправку ответов без перехода по ссылке, добавьте параметр `"allowed_values":[true]`.

```json
{
  "ads": {
    "type": "boolean",
    "required": true,
    "allowed_values": [true]
  }
}
```

#### Параметры

#|
||**Параметр**|**Описание**|**Обязательный**|**Значение по умолчанию**||
||`type` | Тип поля: `button-clicked` — кнопка с проверкой перехода по ссылке. | да | нет||
||`name` | Атрибут для поля выходных данных. Содержит имя поля выходных данных. | да | нет||
||`label` | Надпись на кнопке. Например: `label="Нажми меня"` | нет | нет||
||`href` | URL ресурса, на который должен перейти исполнитель для выполнения задания. | нет | нет||
||`size` | Размер поля.

Допустимые значения: `"S"`, `"M"`, `"L"`, `"XL"`. | нет | `"L"`||
||`action` | Цвет кнопки:

- `action=true` — желтый.

- `action=false` — белый. | нет | `false`||
|#

{% include [contact-support](../../_includes/contact-support.md) %}