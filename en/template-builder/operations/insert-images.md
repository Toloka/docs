# Inserting images

This section describes how to insert [one image](insert-images.md), [two images side-by-side](insert-images.md), or an [array of images](insert-images.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## One image {#single-picture}

To display an image, you need a direct link to the image and the [view.image](../reference/view.image.md) component. You can change the height, width, frame, and other parameters of the image. For more information, see the component description.

To insert an image passed in the input data, use the `data.input` component in the `url` property.

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9Q2MgsQBfUwdaAwAPAHU4NzoIlCwAVgAGQrisRNL7YPpmF1p4Im43TklUgKSq7n0AIwbI9LDPLH4sPjCIEmxoLByiIYMjAH5hUpx3T307FZonGsiPL04Ifz82rdWQUJzIy9yt+NL7sywAXUVH+JMo338UNEU8aJGSJhOh0Jh8ZAAekhDH0Ak8nCgRDokL4AGZIXQuqivHQ4GBIfBuEQALREVL6KRMYl8SGAoiogzcbicJhQBB4TAfeJAA).

## Two images side-by-side {#side-by-side}

To place two images side-by-side, use the [layout.side-by-side](../reference/layout.side-by-side.md) component.


[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IAOANgK4JxQDOeyWA2pjjhtozngAzVbOut4AuAT3wBTLngCGYfnGgA6CiP54ANA15sQAEwn8JXHhsYDhYlLm26JciMX747q9UYv5dAC3EgATiIrFCZRBnXgBfNRYNPDdBQggJLS8YCTgSXzwQnHDMiwBGAxzNIVEvKRl5RSCIlzwdPQLIoxMS81qrGzsHKsLjAg8vX39AjMbWbNHemLiE0pGNcaiQACYGmpBisxpJaVkoBSUnCc06-XNDNY2vE477RxBql1d+1p8-AKCehaa+2PjEl4ARnMwg8+OtTF4iKRyHJ3BB+ABrESCKjBRqhdQAXQeeAAbnARAB3Va9S4vQgSQS2fgKOBaEQAWgBggZFDpZlBFjg-BEAFtUTR6BNzrxmpsLPiiXI4LyJAgOT08MRvIQSRcIS9ruQuodHk9+J4XjK5SIAPqnT6csEwAKEAASIkQ7iCNH43mIYgmX1YIrBZK2IElhOlsvluu+ytVZx6RQ1Aa1UB19xj+sNAeN8tNQLRLm9opANsI9sdCGdXDdHpyGMa2JCeEgUDdEEIAu4OTFXiDckIcAo3QmeG5fNbQpcvvz-os8BEhC0cm8CVkDIQ3ls+HDawpAJnXgA6u44GB3Fh8HD+BAsFoL1TiFge0isNu+wB+DffCD4cqULijvVto7fFuO4vAAgm+ep4hIJDipIwJ6nmY4pmCQFRgGABC4GPJB0FeNmSFYAhRjjpuEjbqhFgAJKhn4l50lAADk-B3n8mFrLiUGVi8ySpMqZj4dWeq1gBxxWGqWHgi08btNSSZWt8bgGgMbzDDmjwCUYhFMCmHZcQSs5yDyAAeei+KccnIaRwEBgACoQIgSIoWAiIZRApNghLuLoWA3necAPqR1JYNycisb0JxieqkkWNcMl3OZ+YKWmFgeYIcEafFmjsT2dS7BF3yTvW0BaNyuzziIACOxBwL4-wZb0B6Nl4AAqB4UFgvLEH2j4iFg8BFiIWhBVAaXzJ8OSYiE6nVqE9wgNqdgoGg6iDtR5peM69gUMgAD020Zn4ciiIZM4UHIkC8ttp7whAFDbbkACsSy5AAzOwAAsl3OSdDJXeeDIPU9r1vXIABWogIOGK0mlm638JtO17dRp1HSdZ0QBdv03Xdj0vewABsn3HS2P1nhA-0469eOg+DIwzaEQA&locale=en). For a detailed analysis of the example, see [Quick start](../quickstart.md).


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

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).

### Components for displaying a group of images {#additional-components}

To display multiple images, you need a component that you can add your images to. To do this, you can use components that implement a list or table:
- [view.list](../reference/view.list.md): Lets you create a list of any elements, including images. It's good for making vertical lists.

    [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).

    In horizontal mode (to do this you need to add `"direction": true`), the images are small because they have a restricted height and width. You can increase the image width by setting the minimum width in the `minWidth` property .

    [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfap046pQ4B1ODdu8hv4xNPxsQAXTWtDccCsRDAdDg0EiYQgVjgAC9oF5NopxikTFEjnQUGhFHgrrJegpRngwnQ6Ew+MgAPR0sBuKCcAQQMAAaz4UH0TF0EDpegQAFpuhYpAAjPh0gCcADZ4iQ6XxrDAiFZhSR9PgiAB9ADMABEAEIAeQAmsaAArG-UADU4ACsmAgTo4QJTqbSGUyWWzOdzefzBVIRWLJdL5Yq6fA+GF1QYoMK+HBuPCLEQqXqAKoAQUN2YAMgAlYsACQAogBpJ0ut21D1Umn0xnM1l0dlcnl8mEhsNhcVS2UKpUQbhuYVMeEd3UAcQrAEUbgB2U2vABaADVN7XXSBFIDMFiUkA).

- [layout.columns](../reference/layout.columns.md): This component is good for displaying a small number of images in the horizontal mode. It lets you align the content vertically, like if you want to position images in the center.

    [View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6SO14BbKAGc8AGkw1acOkVFSUWANpz5lLdtqMWbPIVIC4ozglYhZ1PXl4Andmyp75eA9Yp4AJpzpOMygmfhlddzwmAIALIxBzSyIJAQAGPAj5AF9MrCzbPTdI+mZvWhMSMwsrcLttB2dXXI8SwzU-AKC4ELCbZpoo2PjEqxSARgy67Nz83KL7VrLjYkqR6wLipxc1eeKveP9A4NC6WvcBkGi6OPaE6uSBACZJ85ypvIiAXQ2cPBhedjsAASREQMVOajojl4RB+5SIjjocDAnHYAEF2IgoPFRHBfL52NYtG8sjYEj06Cg0Fo8GtVBRNHU8OC6EwJMgAPQcsC+KACCR0CBgADWEignCYZggHPMCAAtNcxAAjCQcgCcADZUiQORInDAEXKSJx8EQAPoAZgAIgAhADyAE0bQAFG0WgAaAgAVkwEGcLiy2Zzubz+YKRWKJVKZaJ5YrRCr1VqdfAJDEERYoHKJHB2DE+EQ6EozQBVNFWksAGQAStWgQBRADS3t9-t+IED7K5PL5AqFovFkrg0tlCpiytVmu1HIg7F8cqY+cFZoA4vWAIqPADsdoA6gAtABqh5bfpAWk+mFJWSAA).

{% note info %}

This is relevant for creating an interface in Toloka for one task that uses multiple images. Consider whether you need multiple images in the same task. If not, the [view.image](../reference/view.image.md) component is enough for your task.

{% endnote %}


### Many images or unknown number of images {#unknown-size}

If you don't know the size of your array with images in advance or you have so many images that the code is too large, use one of the components described above and add the [helper.transform](../reference/helper.transform.md) component into the `items` property. This component lets you convert an array of links to an array of [view.image](../reference/view.image.md) components to display them in the interface.

[View example in the sandbox](https://tb.yandex.net/editor?locale=en&config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNlTE48jFmzwALItxYAnTnW0BDKHxgRtU4aIV4J02SkpWFtZawd4AJgboHOcKEwAroIgItTOeEzeaqogcFIGCET2TjQAvmERcVB0EHKpYkrMbhR4HCR+CUmW4dYggdrc+bVZrrFePjwQYAZNoQV1UXQx7nGSFiADOGkDM7Vz05hpodlBdChoVjZVyWwA2qnqdHRMfMgA9OdgHlCcAt0A1nxQBkx+EOfxCAC0w4FSACM+OcAJwANgADCRznwGjAiNpviQDPgiAB9ADMABEAEIAeQAmjiAAo4jEADU4ACsmAgaoUQGpjqcLlcbndcmAni83nAPl9fmp-kDQZDofA+BpzEZvnw4Nw1BBAkRjuiAKoAQSxaoAMgAlPUACQAogBpam0+k0I4nM6Xa63e5c56vd6fKQ-P6A4HgqHnCDcDzfJiK3JogDixoAigAmADseIA6gAtABqqYtdMm1AAuksQGkgA).

## Zooming in on an image {#zoom-image}

To zoom in on an image by pressing a shortcut key, use the [plugin.hotkeys](../reference/plugin.hotkeys.md) component. Specify which key triggers [action.open-close](../reference/action.open-close.md). The image is specified in the `view` property using the [$ref](../best-practices/reuse.md) structure. The action is performed when the performer presses the selected key.

[View example in the sandbox](https://clck.ru/U3RyK).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
