# Кнопка

{% note info %}

Справочник по настройке интерфейса описывает работу редактора HTML/JS/CSS. Вы также можете попробовать создать кнопку в {% if locale == "ru-ru" %}[Конструкторе шаблонов](../../../template-builder/reference/field.button-radio.md){% endif %}{% if locale == "en-com" %}[Template Builder](../../../../en/docs/template-builder/reference/field.button-radio.md){% endif %}.

{% endnote %}

Чтобы вставить в задание кнопку, используйте компонент `not_var{{button}}`. Например:

{% if locale == "ru-ru" %}

```plaintext
{{button label="Нажми меня" href="https://yandex.ru" action=true}}
```

{% endif %}{% if locale == "en-com" %}

```plaintext
{{button label="Click me" href="https://yandex.ru" action=true}}
```

{% endif %}

#### Параметры

#|
||**Параметр**|**Описание**|**Обязательный**|**Значение по умолчанию**||
||`label` | Надпись на кнопке | нет | пустая строка||
||`href` | Ссылка, которая откроется при нажатии на кнопку. Ссылка открывается в новой вкладке браузера. | нет | —||
||`action` | Цвет кнопки:

- `action=true` — желтый.

- `action=false` — белый. | нет | `false`||
||`size` | Размер кнопки (с сохранением соотношения высоты и ширины):

- `"S"` — высота 24 px.

- `"M"` — высота 28 px.

- "`L"` — высота 32 px.

- "`XL"` — высота 38 px. | нет | `"M"`||
||`class` | CSS-класс. | нет | `".button"`||
|#

{% include [contact-support](../../_includes/contact-support-help.md) %}