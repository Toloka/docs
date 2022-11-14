# Вставка картинок

{% include [deprecate](../../_includes/deprecate.md) %}

В этом разделе описано, как вставить [одну картинку](insert-images.md), [две картинки рядом](insert-images.md) или [массив картинок](insert-images.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}



## Одна картинка {#single-picture}

Чтобы отобразить картинку, вам необходима прямая ссылка на нее и компонент [view.image](../reference/view.image.md). Вы можете менять высоту, ширину, рамку и другие параметры картинки. Подробнее об этом в описании компонента.

Чтобы вставить картинку, переданную во входных данных, в свойстве `url` используйте компонент `data.input`.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/sHqi-bKY3YF9Dz)


## Две картинки рядом (side-by-side) {#side-by-side}

Чтобы разместить рядом две картинки, используйте компонент [layout.side-by-side](../reference/layout.side-by-side.md).

[![](../_images/buttons/view-example.svg)](https://clck.ru/rcRVK)

Подробный разбор примера в разделе [Быстрый старт](../quickstart.md).


## Массив картинок {#array}

Чтобы получить значение из конкретного элемента массива, укажите в пути его порядковый номер, начиная с нуля.

Например, во входных данных указан массив ссылок на изображения:
```json
{
  "images": [
    "https://cdn.stocksnap.io/img-thumbs/960w/surfer-wave_3DBOYBPB3X.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/fisherman-silhouette_UADULRRHEK.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/old-photo_GEQ27OWZVV.jpg"
  ]
}
```
Сослаться на конкретный элемент массива можно так:
```json
"url": {
  "type": "data.input",
  "path": "images.<Номер элемента, начиная с нуля>"
}
```

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ER1ZQcx63YEySx)

### Компоненты для отображения группы картинок {#additional-components}

Чтобы отобразить несколько картинок, вам необходим компонент, в который можно добавить свои изображения. Для этого могут подойти компоненты, реализующие список или таблицу:
- [view.list](../reference/view.list.md) — позволяет сделать список любых элементов, в том числе картинок. Подходит, если надо сделать вертикальный список.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/ER1ZQcx63YEySx)

  При горизонтальном режиме (надо добавить `"direction": true`) картинки будут маленькие, т.к. они будут ограничены по высоте и ширине. Увеличить ширину картинки можно, задав минимальную ширину в свойстве `minWidth`.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/VvbEoAFU3YFAUh)

- [layout.columns](../reference/layout.columns.md) — этот компонент подходит для отображения небольшого количества картинок в горизонтальном режиме. В нем можно выровнять содержимое по вертикали, например, расположить картинки по центру.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/85sWA9Uj3YFAov)

{% note info %}

Если вы создаете интерфейс заданий в Толоке, то здесь речь идет про одно задание и отображение в нем больше одной картинки. Подумайте, надо ли вам отображать несколько картинок в одном задании? Если нет, то для вставки картинки вам достаточно компонента [view.image](../reference/view.image.md).

{% endnote %}


### Если количество картинок неизвестно или их много {#unknown-size}

Если величина массива с картинками заранее неизвестна или картинок так много, что код слишком объемный, используйте один из компонентов, описанных выше, а в свойство `items` добавьте компонент [helper.transform](../reference/helper.transform.md). Этот компонент позволит вам преобразовать массив ссылок в массив компонентов [view.image](../reference/view.image.md), чтобы отобразить их в интерфейсе.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/sjyWXYxE3YEtWG)

## Увеличение картинки {#zoom-image}

Чтобы увеличить картинку по нажатию горячей клавиши, используйте компонент [plugin.hotkeys](../reference/plugin.hotkeys.md). Укажите в нем, какая клавиша вызывает действие [action.open-close](../reference/action.open-close.md). Картинка указывается в свойстве `view` с помощью конструкции [$ref](../best-practices/reuse.md). Действие вызовется при нажатии на выбранную клавишу.

[![](../_images/buttons/view-example.svg)](https://clck.ru/U3RyK)


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
