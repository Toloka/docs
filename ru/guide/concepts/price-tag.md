# Мониторинг цен

{% include [deprecate](../../_includes/deprecate.md) %}

{% note tip %}

Сначала запустите проект в [Песочнице](https://sandbox.toloka.yandex.com/ru/). Так вы сможете избежать ошибок и потраченных средств, если окажется, что ваше задание не работает.

{% endnote %}

{% include [walk-walk-abstract](../_includes/concepts/walk/id-walk/walk-abstract.md) %}

{% include [walk-walk-abstract-decomposing](../_includes/concepts/walk/id-walk/walk-abstract-decomposing.md) %}

Возможно, для вашего проекта нужны дополнительные настройки, например, добавление новой кнопки со сценарием выполнения или добавление блока с прикреплением файлов. Подробнее об этом читайте в разделе [Примеры кастомизации](advanced-features.md).

Примеры задач, которые поможет решить пресет **Фото товара и ценника**:

- проверка актуальности цен в конкретных торговых точках;
- оценка ценовой и товарной политики конкурентов;
- мониторинг акций и специальных предложений;
- контроль OOS (out-of-stock).

Предположим, вам нужно узнать цену товара в определенном магазине.

Для этого создадим такое задание: исполнителю нужно будет прийти на точку, сфотографировать фасад магазина, сфотографировать товар и ценник на него. Если нет товара или ценника, предоставить фотографии в качестве доказательств. Если по адресу нет магазина, сфотографировать здание, где он должен находиться.

Чтобы запустить задания и получить ответы:

1. [Создайте проект](#project)
1. [Добавьте пул заданий](#pool)
1. [Загрузите задания](#tasks-upload)
1. [Загрузите пул и получите результаты](#launch)

## Создайте проект {#project}

{% include [toloka-requester-source-project-def](../_includes/toloka-requester-source/id-toloka-requester-source/project-def.md) %}

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. {% include [toloka-requester-source-template-price-tag](../_includes/toloka-requester-source/id-toloka-requester-source/template-price-tag.md) %}

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. {% include [toloka-requester-source-interface-def](../_includes/toloka-requester-source/id-toloka-requester-source/interface-def.md) %}

          Для этого проекта воспользуйтесь [готовым кодом](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4gCQggHwggEIg4VjRgEwggAwggAIgCViAHCBYgGIggKwggLwguWmAXCAJeCpKAL6+Dk4AFtIuISBwsBCl5jSVZTj21fTMDW5cXj5d-iDcugBGRNyaIIC4IAmA7CCJBdnIwqM4AdZEtq49fk79cwAmunS6nM1MAK4j7RYgTBc1c1C6Ui5bWOWjnY9lIDtn0NK4tO5OKc4IRTkY2qoAapDkpjmDGtpOMNNsDaBNprNwSBAAgggBYQJLZQCCIBtTD8dkE7D8Qc4zhcrjd7ji-CCXnQ3kTdKdToYiHxZCAfn9AUilCjHKCBhCuNDYfCJdKqmI5WMWUTMdjabi8PiZnNAHgggH4QNKUhJrLDhQCMIIApEGyhUiCRpmtR4ECe2CQO5ahORPOl2uUDuD0DeF5-MaTEMEFOtzAJkl-y93TpCrmmJVcDhhgRFUzAd6uoxkN4UAA1lzerdDITGjU6HQmHxkAB6LsMXQCC5wMCcKBEOhdvgAZi7dAg3AgNd0XaYXZFAEdbqLJIYu7oAGx7gAsAE4AEwABgAjAAOXSXyfn04Adknk6fpwArE-dE-r0-j0+54wG+e6cAAVkwCD1k8VgMkSgCEIJSgDSIIA3CDFFguSpGkSyOikgBsIHkaTZLE4SJCkxZiDKWrZhWgw6LoqZwNAAC0kz3LOUDQd6JrNrQgD4INkFKkgkkSADIgWCUnE4QZIU4ThEkpJpJhkRIVx8oMXQTGcQcTJBuitAaVpnB8GOanei8DDzoKjK4vKtF4AAAn2UBwp4zGzvOi5dqGVzzmAg7QBRDhUb0Pk2YGzLBo0PmcBA9yRmZTyxnMJAQIYNZGAA+pAaXQh8kjirpUp+CF8r4PoBYBdpFDanZUW0FY0KadAejcISpbyo1EhaeKFAKLZNC1eW9U7E1RnrrccAiqciW9DUzT+nggBIIAkgA8IBhgDCIHhuQxBagnZMJYkSVJMlyQpSkiUhWCAOIg+1LFghQ7RahQbbNTxhTpA1PPZIAxRyUYRfKyVEql6VZTlhh5RcopBYGxURaVDhDd9I0gE5uguUQbkeQuS5dc1UBQvwlxQGALgdXNC1zHEV2YYAoiDhIpkRUuJwkoa6MRRPazquu6nBvd6MCJlI4WAzqqPo5j2Nzrj3lsjwED+QTsPcojRz0K0n1i+L+l4H9Eacoa2s8q8cwQ1DBUqyVFNPFIuieGwH7nrpODw34AC66YaqMQ1ooqBCQvmhYq4jvs5nqkL6EYAMwb6+w1bpftzPAMynJwbFtixhiCkxzEIImtxMALxpTKaRJLUhDqCWkzNYGRaS2pEddIRa4QobkhGAPIgWBLAkwkFJ3nqJyAEBMATvVYP1gPI9xpe8XggD0IBhCSABIg2QoVkeQFIUy+bdtSGAJwgJFkQLZX6JucwLlbJYu2WgMlwScyAEQgpHJFgVJiUIGExFX905PkRQShGzFloc+-soAQEygmIcRBMqXCguqQGatZS3xBDxZ+r8UgYWyE3TCWBW5oWyKfMY5VuAXyJBAzKEhpDX0ojbQaqC8RzzmIAHBAEiAGYQZYSke4JEKEkJCTc0goQyFESkG1IiUkiHEDaODiEglIeQxolC0oINvm7Bw7t6GgN4KGLSotozh0aPjcaRANxTSIDNYBBj5rx1oBXKuSQa7EUZrkDa6R7rhAtJkNIB8KD-23svA+pI8hf38YA7BkQv7xGSKkDugjhFYFWhwrhuQeF8IEfzRBqstG-TZPo7kScQzyziu2Q29CTZ8lzEYaEqZaG-ElBTWo9Q5jNBgJrDMPsaKozqNwFghhjIkAkGAfkjTwD9hhq4Ke3IZ4gmMYFLWIDDENWgGNFqpjbj6HFOUnUmtGhXysRFPWeSFna0KdFYp8UymMIqXGdg1Shxpi+h0NR2y8Aij4Lcbg-oZk639piXgAg5HiEkDIeQ1y77GzOXRTgdt0qnAgCQbS2zY67FsXgAAVOiiI0QsCABEQBINphKJOSUsC6mK6mImRQwp5KNdYBy4LCms8LEVAs6nHRaIB0XwWCShBIB9a6njxVEGI+LCWpCSZw0leDKRYBSEsXISE6YSWiEkcIqT3SFC-tdaIDpaapFxcKrAureV1zSKSPBNM4hUnQhkTCKxbRESwAzVVK8YjXRrgkFC4RKSiU4OiilN8aXUuNr83MVZmh1gOackAjZ54gFbO2TsPYpB0GYrBP0zE7iTF4MOKcnBnKuRHGOLszQBCGBTOPGcMtFyZRTtwU4cDpBMAmAVZchgYGZRUZlS8mVDyZT3MxKQzROBMCgAgqlbLUUcr4o41agkA10PBT82l-s61py+NCXQzF4AGFZSQiquj5kJyDSus2KzuotQmuYyxE7vQ2I5fMbIjoGaKVWrtRxXq8I13EganFEqUkJEyeC12t6QQMTJmPfJIaYw1AgLONgdBy2sBPR0UDtAPrHpDXVOlMUSkJSjZC54psiRwCkAgPgtaGKCm+ChkDwHaBSE+ZpZtAxEMXxQ8gvwy7vQ-UxIy5lSL6P0j9HMTF2KYjRJSOSrJ2tONIyE0spUOh+MIsE7R5ZU7RPcvXny2uHdKSyRQqJWSQrohap1VdY1qQ4hmrwcInIiRu6SPkmq1IMq7WrCIutDIIlHEOnEWtDIknAP+pk2LOTyIFO8fDbWPdIJY1zATR2bsXYU1pvZZm242ahzGUnPmjGhbRzjlLWxxi0A+BVs8roWtxB62NqkM26GFXoFk07YYBAmVTyDuHaO8dCn01opADOtIc6kgLtQ0uqLqM10wosXALdO7yYKdIZVZWJysNQtGhewmV7ppxbGPeuYj7n2MxG++oR4Qv1HV-RJzBgHxuLvU3gcDRBIPreg88WD8HXBseQ1h34aGjmXCg4Rn6uHLkxw20RypJGyMUeoSLMLsnAcgEY18uALGENIfBRFlBT3FP0uU7oOFqn9vCcG2Jw1YTijSZx7e7j2G-mQhUyygj98fSaaJFynluniJ8I2haVxgA5EFM+EdhKRcVpBF9T2JqRIgUn89kVah9j7JE4FgQAZCBbyKFgUkbcCKpN7gUJJR0HRt1EivDaIvroEqOsUckgGsDad5fy4iN3Yi8PM46K6aqYgdyNahGIcrlcqW83XSkxFMKkitJSDI7N2Emfde6YRPq-UPYB5N-H0WuDVkjSjhLRIktJtS6mgbqas05ty-lqWRbitQDLRWnqlXcY1dTvVxrraWuwK7ZObrhNetk453BRow3Rvp9x9RLP03avrrmwtuAu62eHIIAeqqIPo0-TmTt9Z179sgkO0SY7DoX1nfwR+y737RebwAcUID6mJ-ehe29zD-3aBMC+7srAv36MP-lBhiFH2YOFypSkOH2wMjQpG5GUC7aZM6edG+OaOzGi+FA3+HGjCnsTy6ilKukPyW2a2L+7Om+56BMnA6ymyQKTgn+eAlCXecCugfWQaQOug6+BSBO4OIBe6MYxGGI9ytSSOqsLyt8byooTGLBp6EcOexMFBTQIKE8Uy2sDOoaEhROJOrOKOZeomWKhqoqfc4qJKZKoWdOme-2m2hOMKxOTKpOS+BiGhXOzuvOWAgq7uOhRK-6UqbmsqywCqSqzmqq6qnuN0Fmu87uVmpq5q1mSEVqBmWEy89qdozq4QrqN0HqXqqehhHG9OU2dK-yEag+BeLYbYyWyapeGWFeOWeaBaWMteJa9epWlaOMNaa67eLaoobaHaXaPafaA6Q6-eY6g+thI+s686-BcMmRU+dKM2G68226C+S2+OK2h61UABoOqMW+nAu2Fie+tAB+jQR+J+b6Z+F2V2P6hqbhF0d+-2v+YwT+3y9GPIH+WO7GlxKO-+ihjOrIYYeGVy6mNyLScOlG-kcIcBGeCBTGGOyBX+2OGRxhUO2eKhlhah-W7Kmh4mquUm6RIaVxbxekTODKFhAm-RyJdhPOru2CBm5uJmN24uCQkuR8GqXuuqAeG8NmwSqSwSSQeEIk68rMKE3cMu6QWA9m2QjmyqLm0qsRnmSuApvmaQ-m7oq0QWd26uexp2BxlIVJEuaQqqiQR0cQlIIujovKkiokX8VICSkmopNcdcZJhmxmQenceucQaeIx2SMJgBqMORsW1hrB+R2xhRxeaWZemW2WuaeWlRng1RJW5aZW9ezejRM+zRTWbRrWXaXWPRI6fR3p6sAx-EQxY2Lp1sbpKxExM+s2m6Mxi+KOCxa+72xZ-saxGxN6dx2xVMh+T6x+qp52n6l+7uwWFxWGVxYGYAEGtxPxb+DxP2UJzxCmrxzZph7B+GaGvxsOUBCOwJg5DGYJmOk5TxxsWB3IGBSCRU9CuBHOqySx3GphaxZB3AWyjClB7wkCa5WZYws5KG85wBi54KXBMOPBkMDy42+52BTywhHyXyYhPGHp4agKL5IICOchRZG+UFeJqhamJhQ+ImXOWhOKLhehkqBh4+Yx6FcJ5hqFhJnOjQ3OOmpJTh2hBKuhxK+F4pcq3hopfhHumqgR3uwRhqoRLJFqkR1qMRHmDqxECRSRSenq3qvqGJe5RFsJyFOgueeRTYiW-pKWgZpRWWleFRBWVRRWNRDeMZFWDR1WTRIKHerRtBHRva-afeGZDB6FOZeAo+wxRhKG2Jphkxc+FZcx6F1Z+ByxSFdKDZO+e2sFlMg2Kpr6XZF+12px+hmE-ZmJKONxEFBi7+cGn+qB05+Ob5r+OJHxVwXxoBhG4B4g-xMAVGQJBZrpoJ6O25KBU5cliFiyJFLOaFUOzlnK2Fu0bc4QO8QiGQki68vKnJtO0JHlWRuJ8JBJEVk6w+tAXKGpNJWpG0pJepxEBChQGQw1zMKEY1w1aJgWJER8BED0XJ7C8kaQaQ6ugAKCD647QB66m2Z+7LCSlomkTq6ADoIAkHTDqU4jxdENSZLsNd6gdHaNtRkIACgEHFRqG0wSTcrcuQnckQO0Xue8O0V1x1uu2QB8kiNm+1okT1cSzp7lIanlBOnpeeCmvpeAReGlJRU6wZOlYZelEZBlUZje5WcZZlCZFlLRzWMB3e7WmUT49lA+81Yw3Vrl+Z5NxslNP03l5Zi2g+AVeitZwV9ZxBJiZi4VS5LZUV7Z+xsVxxV+BCA1XYI1Y1eNyVLV+OaVmtiymV32TVu5KVM5xyBBClOGn53xBVP5tyeAkBFGfAPSMA65KOiB4JrGzVyOrVhBilpFCJnVH23VmKgAWCDhCrRzq5DuiOJpATUe1TXjEzXJ1zXqFEmUV8SeKqr+akkbTyoiTiRuKUhRBJAI3bykSMUAaHHuquL2gSLiIE1pDdzBa7zbXEQZAbTFBXbERxAPTZ253503VYAAAUmEFoeZFAFpvcskuQ7qKElIncUSmCRq5ua82CZ+jMCQOCx9X8-uxqfVkiCQcQO1ApkQnAFonAAAlLJfHSXcRdPqnFiFjJcCKMwVLSCPla-h+Z8RDlsYHWelIF8PsD-jjugWoseTgUIWedtulUoUYjrWshuOQRFQ+RQpAiotITA1rUVbFAg1LUg3qLwY8rJoISBSAO8qIU7eIZWJITBVSsHbIWCoAz7WXR1eRYtRivBCtZLh3aSW3eHtkD4Sqmqj3P3I6kNYkh-OEF-OwsErrvrnkMvCfmJMfT3VKlEgEdqtxW+ttD-IHlgBtFXEzKJPfVxZjeEEfPJJwgUL3N4rajgmTZNRTdNcnKWVMfPpWctqvoFdiZFCFcQ9vnrZsVAwdq2bscbZ2Ycd2fFcDZqSIvzgbqPXbQA+hY7d7WAROW7X9gOS8V7UFW1ajAuf7bA9DkHU0P8cTnFC5JHQptHY1ZCe7eFvJe6dkczviVYZXRRUtbI8KiDWtaSX3BSJSMLh7g6MItdC9OkAkkpAakkEkt4mqgqkfCnk3DKis1SNnZYxdLvHEC+tkCE8XWE6XWGpIV6fnqpYXupcUelszWUaGdXoVsWlzcZbza3nVgLUmdZaLdeBLZmTM9I0NnmYRQncvkrZEz5arek9oqthrVU3WWei5NtusWFWkwbfTZk7QNFaflvUcT2Yalc2s94xs1sztWU6MwppU00+zi7dlXHfbehbQ+I-QyVYgx038VAYKMKKKIVPflHVuRCTlUKwreE8oeXdM0ibMxiuimaA6J3L3ETac4vTnXkCvQfEXaqwoeq-w7NVq-junYsFaCvIDfS-3W4qIsPVIqPbsxkHvfwpEL62cXghvQkPS6NhQHghSG+nndkF-AGwIg-cRAjVJT6oEkGwKVvb-c89a2LIrcA-WqA94MTkQJAw08Drwxiy037aVdGuVQECg5hT-lWXEwS7y9W0kySyQY2RKzsTS9kzFcvDHs3aa8vckD4py0eWgUGoeQjEVD8HO5RGUHOzKDGGQggKWqI5Pnw2-hu8OqZWZCXAwCUiwXgDWM0JYo0HwGAImG1LNE4P2DWAAOoFi-lYDXjnjOzShlDwwYHlCmBNAGx0AoBoDoBFjtDUGfD+xPyuiSLuL4JtzdzoAocgAfBfAoelC0gQfyikb0H+wM09h9gDiaTDgGVTi83LirjrJbhGC7gHgngXg3h3gPjPivjvhfg-h-gARAQgTgSQSbA4fXFCjvITx4CweFDwfYSIe8m4CocyuieYcSjYdlAxiJjJh8GNASdSf3QELIeocJhJgVpKeCeqc+i5TNBNZzAfgficBPingfgATXhOyTh7gvg2dCBvicB7jnjXininjXgASvjXjXh7jXilAQcAflBAA), где уже настроена валидация и внешний вид задания.

          Исполнитель не сможет отправить задание, если:

          - его геолокация будет отличаться от заданной более, чем на 50 метров;
          - не выберет вариант выполнения задания с помощью одной из четырех кнопок;
          - не загрузит необходимые фотографии товара, ценника и магазина;
          - не напишет комментарий в том случае, если магазин закрыт или отсутствует.

          Подробнее о [настройке условий](../../template-builder/best-practices/conditions.md) в Справке конструктора шаблонов.

      1. {% include [toloka-requester-source-tb-input-output_1](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output_1.md) %}

          В данном проекте:

          - Поля входных данных:

            - `name` — строка с названием магазина;
            - `image` — строка со ссылкой на фото товара;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием магазина;
            - `position` — координаты точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который напишет исполнитель;
            - `verdict` — статус выполнения задания;
            - `imgs_item` — массив файлов, фотографии товара, которые загрузит исполнитель;
            - `imgs_price` — массив файлов, фотографии ценника, которые загрузит исполнитель;
            - `imgs_shelf` — массив файлов, фотографии полки с товаром, которые загрузит исполнитель;
            - `coordinates` — координаты задания;
            - `imgs_around` — массив файлов, фотографии окружения, которые загрузит исполнитель;
            - `imgs_facade` — массив файлов, фотографии магазина, которые загрузит исполнитель;
            - `imgs_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель;
            - `woker_coordinates` — координаты исполнителя в момент исполнения задания, с включенной опцией **Текущее положение**.

      1. Блок **Настройки отображения пешеходных заданий** используется, чтобы помочь исполнителю отличить одно задание от другого, когда он выберет задание на карте. В данном проекте поля **Формат заголовка** и **Формат короткого описания** содержат ссылки на поля входных данных, чтобы показать адрес точки и ее название. Вы можете оставить эти поля без изменений или написать какое-нибудь другое пояснение.

      1. Нажмите **Сохранить**.

    - Редактор HTML/CSS/JS

      1. {% include [toloka-requester-source-interface-html-block](../_includes/toloka-requester-source/id-toloka-requester-source/interface-html-block.md) %}

          Блок **JS** используется для описания логики задания. Кроме того, основной контент данного задания заложен в **JS** для простоты редактирования.

          В логике шаблона заложено минимальное количество фотографий товара, полки с товаром, фасада магазина, таблички с адресом. Когда нет объекта, то фотографий окружения на месте объекта. Если вы хотите поменять эти значения, то найдите все строчки и измените для каждого варианта выполнения задания минимальное количество фото:

            ```javascript
            if (solution.output_values.imgs_item.length < 1)
            if (solution.output_values.imgs_shelf.length < 2)
            if (solution.output_values.imgs_facade.length < 2)
            if (solution.output_values.imgs_around.length < 4)
            ```

          В этом проекте в переменной `texts` хранятся тексты для блока с информацией и тексты для четырех вариантов вариантов выполнения задания: **Я нашел ценник на нужный товар**; **Товар есть, но без ценника**; **Товара нет на полке**; **Магазин закрыт или отсутствует**.

          В переменной `MAX_DISTANCE` указана максимальная удаленность от назначенной точки (по умолчанию в километрах), на которую может отойти исполнитель во время выполнения задания. Вы можете указать подходящее для вас значение.

      1. Определите, какие объекты будете передавать исполнителю и получать от него в ответ. Для этого необходимо создать поля входных и выходных данных в блоке **Спецификация данных**.

          {% cut "Что такое входные и выходные данные?" %}

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          Подробнее о [полях входных и выходных данных](incoming.md).

          {% endcut %}

          {% include [price-tag-input-output-data](../_includes/concepts/price-tag/id-price-tag/input-output-data.md) %}

      1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.svg) **Предпросмотр задания**, чтобы увидеть получившееся задание.

          {% note info %}

          В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

          {% endnote %}

      1. {% include [toloka-requester-source-exit-preview](../_includes/toloka-requester-source/id-toloka-requester-source/exit-preview.md) %}

      1. Нажмите **Сохранить**.

    {% endlist %}

1. Напишите краткую и ясную инструкцию. Опишите в ней, что надо сделать, и приведите примеры.

    Вы можете подготовить инструкцию в формате HTML и вставить ее в редактор. Чтобы переключиться в режим HTML, нажмите **<>**.

    Инструкция для пешеходных заданий должна хорошо читаться на экране мобильного телефона.

1. {% include [toloka-requester-source-end-edit](../_includes/toloka-requester-source/id-toloka-requester-source/end-edit.md) %}

## Добавьте пул заданий {#pool}

Пул — это набор оплачиваемых заданий, которые одновременно выдаются исполнителям.

1. Откройте проект и нажмите **Добавить пул**.

1. Дайте пулу любое удобное название и описание. Они доступны только вам, исполнитель будет видеть только название и описание проекта.

1. В блоке **Аудитория** добавьте **Фильтры** для отбора исполнителей. Чтобы ваши задания были доступны в мобильных приложениях Толоки исполнителям, владеющих русским языком и находящихся в Москве, установите язык и регион.

    ![](../_images/tutorials/walk/region-by-ip.png)

1. В блоке **Цена** установите цену за задание, например 0,2 $. Для пешеходных заданий всегда добавляйте одно задание на страницу.

    {% cut "Что такое страница заданий?" %}

    На одной странице может отображаться одно или несколько заданий. Если задания простые, то можно добавлять 10–20 заданий на одну страницу. Не рекомендуем создавать длинные страницы, поскольку это снизит скорость загрузки данных у исполнителя.

    Исполнитель получит оплату, только если выполнил все задания на странице.

    Количество заданий на странице вы определите при [загрузке заданий](#smart-mixing).

    {% endcut %}

    {% cut "Как определить справедливую цену?" %}

    Общее правило формирования цены — чем больше времени исполнитель тратит на выполнение, тем выше цена.

    Вы можете зарегистрироваться в Толоке как исполнитель и узнать, сколько платят другие заказчики за задания.

    {% endcut %}

1. В блоке **Контроль качества** установите **Перекрытие** — количество исполнителей, которые должны выполнить задание. Для пешеходных заданий, как правило, 1.

1. В блоке **Контроль качества** включите опцию **Отложенная приемка** и укажите количество дней на проверку для параметра **Срок проверки**. Например, 7.

    {% cut "Что такое отложенная приемка?" %}

    [Отложенная приемка](offline-accept.md) позволяет вам просматривать [выполненные страницы заданий](../../glossary.md#completed-tasks) перед тем, как принять их и заплатить исполнителю. Задания, выполненные в несоответствии с инструкцией, можно отклонять. Максимальный срок проверки устанавливается в поле **Срок проверки**.

    {% endcut %}

1. В блоке **Дополнительные настройки** укажите **Время** на выполнение страницы заданий. Его должно быть достаточно для того, чтобы добраться до места, найти указанную точку и загрузить фотографии. Для пешеходных заданий рекомендуем устанавливать сутки — 86 400 секунд.

1. Сохраните пул.

## Загрузите задания {#tasks-upload}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. Нажмите кнопку **Загрузить**. В открывшемся окне вы можете скачать шаблон файла.

    #### Использовать пример данных

    Если вы хотите посмотреть, как ваш проект будет выглядеть после запуска, но у вас еще нет заданий для разметки, вы можете загрузить в пул готовый пример данных.

    Нажмите **Использовать пример данных** справа от надписи **Прикрепите подготовленный файл с данными**. Это позволит избежать дополнительных действий с файлами.

    После того, как вы поработали с примером данных и вас все устроило, подготовьте свои данные и загрузите их в пул.

1. Добавьте в него входные данные. Заголовок столбца с входными данными содержит слово `INPUT`. Для пешеходных заданий также нужно указать широту `AI:latitude` и долготу `AI:longitude` каждой точки. Координаты можно уточнить, например, в [Яндекс Картах]({{ ya-maps-object-search }}).

    ![](../_images/tutorials/price-tag/price-tag-input-spreadsheet.png)

1. Загрузите задания.

1. Выберите **Указать вручную** и установите значение 1 в поле **Кол-во заданий на странице**.

1. Нажмите кнопку **Разделить задания на страницы**.

## Запустите пул и получите результаты {#launch}

1. Запустите пул, нажав кнопку ![](../_images/other/b-start-pool.svg).

1. Следите за выполнением в блоке **Статистика пула**.

1. Как только получены первые результаты, вы можете начинать проверку.

    Чтобы проверить задания, откройте пул и нажмите **Скачать результаты**. Чтобы скачать вложения, нажмите кнопку рядом ![Выпадающее меню](../_images/drop-down.svg) и выберите **Скачать вложения**.

    {% note info %}

    По истечении установленного срока проверки все ответы будут автоматически приняты вне зависимости от качества ответа.

    {% endnote %}

{% include [contact-support](../_includes/contact-support.md) %}