# Классификация изображений

В Толоке есть пресет **Классификация изображений** ([посмотреть код в песочнице](https://clck.ru/TJ7W2)). В нем уже настроена валидация, горячие клавиши и внешний вид задания.

{% cut "Из каких компонентов состоит этот пример" %}

- [view.image](../reference/view.image.md) — картинка;
- [field.button-radio-group](../reference/field.button-radio-group.md) — кнопки вариантов ответа;
- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания;
- [plugin.hotkeys](../reference/plugin.hotkeys.md) — [горячие клавиши](../best-practices/hotkeys.md).

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Что еще можно настроить {#add-more}

- Чтобы добавить подробное описание к заданию, используйте компонент [view.text](../reference/view.text.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TeyZ9)

- Чтобы исполнитель мог оставить комментарий к заданию или своему ответу, добавьте поле для ввода текста [field.textarea](../reference/field.textarea.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TeyS2)

- Добавьте горячие клавиши на поворот и увеличение картинки в конфигурации [plugin.hotkeys](../reference/plugin.hotkeys.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Teyp8)

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.


## Другие варианты кнопок {#mult-ans-options}

Определите, может ли исполнитель выбрать несколько вариантов ответа или только один:

{% list tabs %}

- Несколько (чекбокс)

  Если ответов на вопрос может быть несколько — настройте чекбоксы [field.checkbox-group](../reference/field.checkbox-group.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tez2w)

- Один (радиокнопка)

  Компонент [field.button-radio-group](../reference/field.button-radio-group.md) отображается в виде цельных кнопок. Такие кнопки лучше подходят, когда в вопросе 2-4 варианта с короткими названиями.

  Если вариантов ответа много или названия длинные, то лучше использовать переключатель [field.radio-group](../reference/field.radio-group.md), как в примере.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TezMY)

{% endlist %}

## Добавить условия {#dependencies}

С помощью [helper.if](../reference/helper.if.md) можно показывать любой элемент интерфейса только при выборе определенного ответа. Например, отметить верные об изображении утверждения можно только если оно загрузилось.

[![](../_images/buttons/view-example.svg)](https://clck.ru/TiVTm)

## Сравнение картинки и поискового запроса {#search}

#### Подходит ли картинка под поисковый запрос

Добавьте кнопку, по которой исполнители будут открывать результаты поиска, и сформируйте ссылку поискового запроса с помощью компонента [helper.search-query](../reference/helper.search-query.md). Чтобы убедиться, что исполнитель перешел по ссылке и проверил ее содержимое, настройте валидацию, как в примере.

[![](../_images/buttons/view-example.svg)](https://clck.ru/TeKBs)

#### Попарное сравнение с веб-страницей

С помощью компонента [view.iframe](../reference/view.iframe.md) вы можете отобразить веб-страницу во встроенном окне. Расположите рядом картинку, используя [layout.side-by-side](../reference/layout.side-by-side.md).

[![](../_images/buttons/view-example.svg)](https://clck.ru/TeKQA)

#### Попарное сравнение с веб-страницей в рамке мобильного устройства

Это более сложный пример, который сравнивает картинку с результатами поискового запроса. В нем добавлены компоненты:

- [view.iframe](../reference/view.iframe.md) — отображает веб-страницу во встроенном окне;
- [view.device-frame](../reference/view.device-frame.md) — оборачивает окно в рамку смартфона;
- [layout.side-by-side](../reference/layout.side-by-side.md) — располагает картинку и окно с результатами запроса рядом друг с другом.

[![](../_images/buttons/view-example.svg)](https://clck.ru/TeKPK)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
