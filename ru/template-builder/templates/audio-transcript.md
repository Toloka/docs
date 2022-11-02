# Транскрипция аудио

{% include [deprecate](../../_includes/deprecate.md) %}

В Толоке есть пресет **Расшифровка аудиозаписей** . В нем уже настроена валидация, внешний вид задания и горячие клавиши.

[![](../_images/buttons/view-example.svg)](https://clck.ru/SsYtF)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.audio](../reference/view.audio.md) — аудиоплеер;
- [condition.played-fully](../reference/condition.played.md) — проверяет, что исполнитель дослушал аудио до конца;
- [field.button-radio-group](../reference/field.button-radio-group.md) — кнопки вариантов ответа;
- [field.textarea](../reference/field.textarea.md) — поле для ввода текста;
- [condition.required](../reference/condition.required.md) — проверяет, что поле для текста заполнено;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания;
- [plugin.hotkeys](../reference/plugin.hotkeys.md) — [горячие клавиши](../best-practices/hotkeys.md).

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}



## Что еще можно настроить {#add-more}

- Если вам важно [проверить](../best-practices/conditions.md), что аудио запускалось — замените компонент [condition.played-fully](../reference/condition.played-fully.md) на [condition.played](../reference/condition.played.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/T324W)

- Пригодится для коротких аудио — поставьте их на повтор, добавив в свойства компонента [view.audio](../reference/view.audio.md) `loop: true`.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/T3279)


Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.


## Другие варианты кнопок {#options}

Выберите, может ли исполнитель выбрать несколько вариантов ответа или только один:

{% list tabs %}

- Несколько (чекбокс)

  Используйте компонент [field.checkbox-group](../reference/field.checkbox-group.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/SWicE)

- Один (радиокнопка)

  Используйте компонент [field.radio-group](../reference/field.radio-group.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/T2zwe)

{% endlist %}

## Добавить предварительно распознанный текст {#text}

В заданиях на расшифровку аудио можно добавлять текст из входных данных. Например, если аудиозапись была распознана автоматически, а сейчас вам нужно, чтобы исполнители исправили в тексте ошибки. Для этого используйте компонент [view.text](../reference/view.text.md) и в свойстве `content` сошлитесь на номер элемента массива входных данных.

[![](../_images/buttons/view-example.svg)](https://clck.ru/T2zvs)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
