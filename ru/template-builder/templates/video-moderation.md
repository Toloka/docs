# Оценка видео

{% include [deprecate](../../_includes/deprecate.md) %}

В Толоке есть пресет **Классификация жестов рук**. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/APRf3OVx3twCRi)

{% cut "Из каких компонентов состоит этот пример" %}

- [view.video](../reference/view.video.md) — видеоплеер;
- [condition.played](../reference/condition.played.md) — проверяет, что исполнитель начал смотреть видео;
- [field.button-radio-group](../reference/field.button-radio-group.md) — кнопки вариантов ответа;
- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания;
- [plugin.hotkeys](../reference/plugin.hotkeys.md) — [горячие клавиши](../best-practices/hotkeys.md).

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## Что еще можно настроить {#add-more}

- Добавьте [проверку](../best-practices/conditions.md), что видео просмотрели до конца — замените компонент [condition.played](../reference/condition.played.md) на [condition.played-fully](../reference/condition.played-fully.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/GxkXPo9H3twCaq)

Если вам не подходит этот пресет, посмотрите другие примеры в этом разделе.

## Другие варианты кнопок {#add-variants}

Определите, может ли исполнитель выбрать несколько вариантов ответа или только один:

{% list tabs %}

- Несколько (чекбокс)

  Добавьте группу переключателей с помощью компонента [field.checkbox-group](../reference/field.checkbox-group.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/7SA9XQ7a3twCxf)

- Один (радиокнопка)

  Компонент [field.button-radio-group](../reference/field.button-radio-group.md) отображается в виде цельных кнопок. Такие кнопки лучше подходят, когда в вопросе 2–4 варианта с короткими названиями.

  Если вариантов ответа много или названия длинные, то лучше использовать переключатель [field.radio-group](../reference/field.radio-group.md), как в примере.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/VuUsN-9Y3twDJm)

{% endlist %}

## Сравнить видео с другим типом данных {#compare-video-and-other}

Добавьте картинку с помощью компонента [view.image](../reference/view.image.md). Расположите видео рядом с картинкой через компонент [layout.columns](../reference/layout.columns.md).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/-GfV_wyG3x5JPc)

Расположите видео рядом с текстом или аудио с помощью компонента [view.list](../reference/view.list.md).

{% list tabs %}

- Сравнить с текстом

  Добавьте компонент [view.text](../reference/view.text.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/FOjqcYqP3twE9m)

- Сравнить аудиодорожки

  Добавьте компонент [view.audio](../reference/view.audio.md).

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/CVwoidzj3tvbVH)

{% endlist %}

## Сравнить видео и поисковую выдачу {#compare-results}

С помощью компонента [view.iframe](../reference/view.iframe.md) вы можете отобразить веб-страницу во встроенном окне. Расположите рядом видео через [layout.side-by-side](../reference/layout.side-by-side.md).

В примере видео нужно сравнить с результатами запроса, который формируется компонентом [helper.search-query](../reference/helper.search-query.md).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/jlyFOc-s3vuWKU)

## Добавить уточняющие вопросы к одному из вариантов {#add-addition}

С помощью [helper.switch](../reference/helper.switch.md) можно показывать любой элемент интерфейса только при выборе определенного ответа. В этом примере отметить верные утверждения о видео можно только если исполнитель подтверждает, что оно загрузилось.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/MkbZzOht3twEqU)

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)