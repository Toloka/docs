# Копирайтинг

В Толоке есть пресет **Копирайтинг** ([посмотреть код в песочнице](https://clck.ru/TJ6on)). В нем уже настроена валидация и внешний вид задания.

{% cut "Из каких компонентов состоит этот пример" %}

- [view.image](../reference/view.image.md) — картинка;
- [layout.columns](../reference/layout.columns.md) — размещает картинку в отдельном столбце слева от других элементов интерфейса;
- [view.text](../reference/view.text.md) — показывает текст из входных данных задания;
- [field.textarea](../reference/field.textarea.md) — поле для ввода текста;
- [condition.required](../reference/condition.required.md) — проверяет, что поле для текста заполнено;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает ширину задания.

{% endcut %}

## Что еще можно настроить {#add-more}

- Чтобы задать необходимую длину текста, вместо [condition.required](../reference/condition.required.md) используйте компонент [condition.schema](../reference/condition.schema.md). Он не даст отправить ответ, если введенный текст будет короче или длиннее, чем вы указали.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2fm)

- Для ввода короткого текста в одну строку вместо [field.textarea](../reference/field.textarea.md) удобно использовать [field.text](../reference/field.text.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2gi)

- Если для выполнения задания нужно что-то найти в интернете, добавьте компонент [helper.search-query](../reference/helper.search-query.md). Поисковый запрос можно составить из слов, взятых из входных данных.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2h9)

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.


## Пример без картинки {#text-answer-only}

Упрощенный пример без картинки и без разделения компонентов по столбцам. Подойдет для заданий, в которых не нужно визуальное отображение, например, для переводов.

[![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2pc)

## Несколько столбцов {#several-columns}

Чтобы сравнить два текста, расположите их в соседних столбцах с помощью компонента [layout.columns](../reference/layout.columns.md). Он позволяет задавать ширину столбцов и выравнивание по вертикали.

Компонент [view.group](../reference/view.group.md) добавляет вокруг текстов рамки, чтобы визуально отделить их друг от друга и облегчить восприятие.

Третий столбец в примере содержит два поля для ввода, куда исполнитель может написать свой текст.

[![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2uX)

## Показать скрытое поле {#checkbox-showing-text}

Этот пример подойдет для поиска в тексте. Например, для поиска ошибок. Если ошибки есть, то при выборе соответствующей опции откроется поле для ввода текста.

Выберите, как вы хотите оформить опции: радиокнопками, обычными кнопками или чекбоксом.

{% list tabs %}

- Радиокнопки

  Используйте компонент [field.radio-group](../reference/field.radio-group.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2wD)

- Кнопки

  Используйте компонент [field.button-radio-group](../reference/field.button-radio-group.md).
  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2ws)

- Чекбокс

  Используйте компонент [field.checkbox](../reference/field.checkbox.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tf2vc)

{% endlist %}

## Исполнитель добавляет поля для ввода {#dynamic-field-add}

Это сложный пример, который состоит из четырех основных частей:
- [view.image](../reference/view.image.md) — картинка;
- [field.radio-group](../reference/field.radio-group.md) — опции выбора ответа;
- [field.text](../reference/field.text.md) — поле для ввода текста;
- [field.list](../reference/field.list.md)— кнопка, которая добавляет новые поля для ввода текста.

Особенность примера в том, что исполнитель может сам добавлять и удалять поля для ввода текста.

Дополнительно в примере действует проверка, чтобы в каждой строке было не менее трех символов: русских или английских букв и пробелов. Условие реализуется с помощью [condition.schema](../reference/condition.schema.md).

[![](../_images/buttons/view-example.svg)](https://clck.ru/TULJM)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
