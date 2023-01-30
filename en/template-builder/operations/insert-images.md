# Inserting images

This section describes how to insert [one image](insert-images.md), [two images side-by-side](insert-images.md), or an [array of images](insert-images.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## One image {#single-picture}

To display an image, you need a direct link to the image and the [view.image](../reference/view.image.md) component. You can change the height, width, frame, and other parameters of the image. For more information, see the component description.

To insert an image passed in the input data, use the `data.input` component in the `url` property.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/zDwELDM23ttBiT)

## Two images side-by-side {#side-by-side}

To place two images side-by-side, use the [layout.side-by-side](../reference/layout.side-by-side.md) component.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ZdGClef13ttEz8)

 For a detailed analysis of the example, see [Quick start](../quickstart.md).

## Array of images {#array}

To get a value from a specific element in an array, use the path to specify its sequence number, starting from zero.

Let's say the input data contains of an array of links to images:
```json
{
  "images": [
    "https://cdn.stocksnap.io/img-thumbs/960w/surfer-wave_3DBOYBPB3X.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/fisherman-silhouette_UADULRRHEK.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/old-photo_GEQ27OWZVV.jpg"
  ]
}
```
You can reference a specific array element like this:
```json
"url": {
  "type": "data.input",
  "path": "images.<Element number, starting from zero>"
}
```

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/V44snIfa3ttBb2)

### Components for displaying a group of images {#additional-components}

To display multiple images, you need a component that you can add your images to. To do this, you can use components that implement a list or table:
- [view.list](../reference/view.list.md): Lets you create a list of any elements, including images. It's good for making vertical lists.

    [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/V44snIfa3ttBb2)

    In horizontal mode (to do this you need to add `"direction": true`), the images are small because they have a restricted height and width. You can increase the image width by setting the minimum width in the `minWidth` property .

    [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/VBzpJKCp3ttBpt)

- [layout.columns](../reference/layout.columns.md): This component is good for displaying a small number of images in the horizontal mode. It lets you align the content vertically, like if you want to position images in the center.

    [![image](../_images/buttons/view-example.svg)](https://ya.cc/t/zZHgwLrX3ttBrK)

{% note info %}

This is relevant for creating an interface in Toloka for one task that uses multiple images. Consider whether you need multiple images in the same task. If not, the [view.image](../reference/view.image.md) component is enough for your task.

{% endnote %}

### Many images or unknown number of images {#unknown-size}

If you don't know the size of your array with images in advance or you have so many images that the code is too large, use one of the components described above and add the [helper.transform](../reference/helper.transform.md) component into the `items` property. This component lets you convert an array of links to an array of [view.image](../reference/view.image.md) components to display them in the interface.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/IqTqGpfg3ttBtA)

## Zooming in on an image {#zoom-image}

To zoom in on an image by pressing a shortcut key, use the [plugin.hotkeys](../reference/plugin.hotkeys.md) component. Specify which key triggers [action.open-close](../reference/action.open-close.md). The image is specified in the `view` property using the [$ref](../best-practices/reuse.md) structure. The action is performed when a Toloker presses the selected key.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/xdavUyAN3ttEzb)

{% include [contact-support](../_includes/contact-support.md) %}