# Вставка картинок

В этом разделе описано, как вставить [одну картинку](insert-images.md), [две картинки рядом](insert-images.md) или [массив картинок](insert-images.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}



## Одна картинка {#single-picture}

Чтобы отобразить картинку, вам необходима прямая ссылка на нее и компонент [view.image](../reference/view.image.md). Вы можете менять высоту, ширину, рамку и другие параметры картинки. Подробнее об этом в описании компонента.

Чтобы вставить картинку, переданную во входных данных, в свойстве `url` используйте компонент `data.input`.

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9Q2MgsQBfUwdaAwAPAHU4NzoIlCwAVgAGQrisRNL7YPpmF1p4Im43TklUgKSq7n0AIwbIwHIQQCEQQD4QLEBeEEAGEEB+EEAOEEBBEHHRkYmsacB2ECHARhBAARBxwDYQQFYQUenpgH5hUpx3T307C5onGsiPL04Ifz82u8uQUJzI39yd3ipWBZiwAF1FKD4iYor5-Cg0Io8NEjJEwnQ6Ew+MgAPS4hj6ASeOBgThQIh0XEkGm4gD6uNSuIAioyANYADgAmlk2WEAOIAKwAkvyAPJWABiUjpbgAMvkAOwcgCMXIAgpw+PgEHhMDD4kA).


## Две картинки рядом (side-by-side) {#side-by-side}

Чтобы разместить рядом две картинки, используйте компонент [layout.side-by-side](../reference/layout.side-by-side.md).

[Посмотреть пример в песочнице](https://clck.ru/rcRVK). Подробный разбор примера в разделе [Быстрый старт](../quickstart.md).


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

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).

### Компоненты для отображения группы картинок {#additional-components}

Чтобы отобразить несколько картинок, вам необходим компонент, в который можно добавить свои изображения. Для этого могут подойти компоненты, реализующие список или таблицу:
- [view.list](../reference/view.list.md) — позволяет сделать список любых элементов, в том числе картинок. Подходит, если надо сделать вертикальный список.

  [Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).

  При горизонтальном режиме (надо добавить `"direction": true`) картинки будут маленькие, т.к. они будут ограничены по высоте и ширине. Увеличить ширину картинки можно, задав минимальную ширину в свойстве `minWidth`.

  [Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfap046pQ4B1ODdu8hv4xNPxsQAXTWtDccCsRDAdDg0EiYQgVjgAC9oF5NopxikTFEjnQUGhFHgrrJegpRngwnQ6Ew+MgAPR0sBuKCcAQQMAAaz4UH0TF0EDpegQAFpuhYpAAjPh0gCcADZ4iQ6XxrDAiFZhSR9PgiAB9ADMABEAEIAeQAmsaAArG-UADU4ACsmAgTo4QJTqbSGUyWWzOdzefzBVIRWLJdL5Yq6fA+GF1QYoMK+HBuPCLEQqXqAKoAQUN2YAMgAlYsACQAogBpJ0ut21D1Umn0xnM1l0dlcnl8mEhsNhcVS2UKpUQbhuYVMeEd3UAcQrAEUbgB2U2vABaADVN7XXSBFIDMFiUkA).

- [layout.columns](../reference/layout.columns.md) — этот компонент подходит для отображения небольшого количества картинок в горизонтальном режиме. В нем можно выровнять содержимое по вертикали, например, расположить картинки по центру.

  [Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm0A2AhgxAK50A6SO14BbKAGc8AGkw1acOkVFSUWANpz5lLdtqMWbPIVIC4ozglYhZ1PXl4Andmyp75eA9Yp4AJpzpOMygmfhlddzwmAIALIxBzSyIJAQAGPAj5AF9MrCzbPTdI+mZvWhMSMwsrcLttB2dXXI8SwzU-AKC4ELCbZpoo2PjEqxSARgy67Nz83KL7VrLjYkqR6wLipxc1eeKveP9A4NC6WvcBkGi6OPaE6uSBACZJ85ypvIiAXQ2cPBhedjsAASREQMVOajojl4RB+5SIjjocDAnHYAEF2IgoPFRHBfL52NYtG8sjYEj06Cg0Fo8GtVBRNHU8OC6EwJMgAPQcsC+KACCR0CBgADWEignCYZggHPMCAAtNcxAAjCQcgCcADZUiQORInDAEXKSJx8EQAPoAZgAIgAhADyAE0bQAFG0WgAaAgAVkwEGcLiy2Zzubz+YKRWKJVKZaJ5YrRCr1VqdfAJDEERYoHKJHB2DE+EQ6EozQBVNFWksAGQAStWgQBRADS3t9-t+IED7K5PL5AqFovFkrg0tlCpiytVmu1HIg7F8cqY+cFZoA4vWAIqPADsdoA6gAtABqh5bfpAWk+mFJWSAA).

{% note info %}

Если вы создаете интерфейс заданий в Толоке, то здесь речь идет про одно задание и отображение в нем больше одной картинки. Подумайте, надо ли вам отображать несколько картинок в одном задании? Если нет, то для вставки картинки вам достаточно компонента [view.image](../reference/view.image.md).

{% endnote %}


### Если количество картинок неизвестно или их много {#unknown-size}

Если величина массива с картинками заранее неизвестна или картинок так много, что код слишком объемный, используйте один из компонентов, описанных выше, а в свойство `items` добавьте компонент [helper.transform](../reference/helper.transform.md). Этот компонент позволит вам преобразовать массив ссылок в массив компонентов [view.image](../reference/view.image.md), чтобы отобразить их в интерфейсе.

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNlTE48jFmzwALItxYAnTnW0BDKHxgRtU4aIV4J02SkpWFtZawd4AJgboHOcKEwAroIgItTOeEzeaqogcFIGCET2TjQAvmERcVB0EHKpYkrMbhR4HCR+CUmW4dYggdrc+bVZrrFePjwQYAZNoQV1UXQx7nGSFiADOGkDM7Vz05hpodlBdChoVjZVyWwA2qnqdHRMfMgA9OdgHlCcAt0A1nxQBkx+EOfxCAC0w4FSACM+OcAJwANgADCRznwGjAiNpviQDPgiAB9ADMABEAEIAeQAmjiAAo4jEADU4ACsmAgaoUQGpjqcLlcbndcmAni83nAPl9fmp-kDQZDofA+BpzEZvnw4Nw1BBAkRjuiAKoAQSxaoAMgAlPUACQAogBpam0+k0I4nM6Xa63e5c56vd6fKQ-P6A4HgqHnCDcDzfJiK3JogDixoAigAmADseIA6gAtABqqYtdMm1AAuksQGkgA).

## Увеличение картинки {#zoom-image}

Чтобы увеличить картинку по нажатию горячей клавиши, используйте компонент [plugin.hotkeys](../reference/plugin.hotkeys.md). Укажите в нем, какая клавиша вызывает действие [action.open-close](../reference/action.open-close.md). Картинка указывается в свойстве `view` с помощью конструкции [$ref](../best-practices/reuse.md). Действие вызовется при нажатии на выбранную клавишу.

[Посмотреть пример в песочнице](https://clck.ru/U3RyK).


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
