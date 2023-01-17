# Сравнить видеоклипы

{% include [deprecate](../../_includes/deprecate.md) %}

В этом разделе описано, как [сравнить два видео](#video-side-by-side), как сделать, чтобы они [запускались и останавливались одновременно](#same-time-video) и как разместить [больше двух видео на странице](#compare-more-video).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}



## Два видео рядом (side-by-side) {#video-side-by-side}

Чтобы расположить рядом два видео, можно использовать компонент [layout.side-by-side](../reference/layout.side-by-side.md). Компоненты с видео ([view.video](../reference/view.video.md)) добавьте в свойство `items`, а поля для ответов в свойство `controls`.

{% note info %}

В отличие от других компонентов, у [layout.side-by-side](../reference/layout.side-by-side.md) есть переключатели, которые позволяют скрыть или отобразить любой из элементов в `items`.

{% endnote %}


[![](../_images/buttons/view-example.svg)](https://ya.cc/t/KNi834ma3tvNBu)

Вместо [layout.side-by-side](../reference/layout.side-by-side.md) вы можете использовать другие компоненты, например:
- [view.list](../reference/view.list.md) — список любых элементов, вертикальный или горизонтальный.
- [layout.columns](../reference/layout.columns.md) — набор горизонтальных колонок, в которые можно поместить видео. В отличие от [view.list](../reference/view.list.md), этот компонент дает больше опций для настройки ширины колонок.


## Одновременное воспроизведение двух видео {#same-time-video}

Вы можете сделать, чтобы оба видео воспроизводились и останавливались одновременно.

Для этого добавьте кнопку ([view.action-button](../reference/view.action-button.md)), которая будет вызывать действие [action.play-pause](../reference/action.play-pause.md) для обоих видео. Чтобы по кнопке вызвать сразу два действия (для каждого видео), используйте компонент [action.bulk](../reference/action.bulk.md).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/e65F9wVL3tvNwv)

Вы также можете сделать воспроизведение по горячей клавише. Используемая горячая клавиша будет написана на кнопке.

Для этого используйте плагин [plugin.hotkeys](../reference/plugin.hotkeys.md). Чтобы привязать горячую клавишу к кнопке, необходимо выполнить по горячей клавише то же самое действие.

{% note tip %}

Чтобы вызвать одно и то же действие из разных частей кода, вынесите его в отдельную переменную в `vars`, а затем ссылайтесь на него с помощью конструкции `$ref`. Подробнее об этом в разделе [Переиспользуйте код](../best-practices/reuse.md).

{% endnote %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/8MU78BrT3tvNR7)

## Сравнить несколько видео {#compare-more-video}

В примерах выше в свойстве `items` вы можете добавить сколько угодно компонентов с видео.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/LezaXWtv3tvNjd)

Если вы хотите добавить много разных видео, которые не надо смотреть одновременно, лучше расположить их вертикально с помощью компонента [view.list](../reference/view.list.md). А чтобы кнопки для выбора ответа не потерялись, можно использовать компонент [layout.sidebar](../reference/layout.sidebar.md).

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/7-xr01b63tvPRY)


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
