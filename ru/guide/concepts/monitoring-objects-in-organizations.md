# Сбор данных: Организации

{% include [deprecate](../../_includes/deprecate.md) %}

{% note tip %}

Сначала запустите проект в [Песочнице](https://platform.sandbox.toloka.ai/). Так вы сможете избежать ошибок и потраченных средств, если окажется, что ваше задание не работает.

{% endnote %}

{% include [walk-walk-abstract](../_includes/concepts/walk/id-walk/walk-abstract.md) %}

{% include [walk-walk-abstract-decomposing](../_includes/concepts/walk/id-walk/walk-abstract-decomposing.md) %}

Возможно, для вашего проекта нужны дополнительные настройки, например, добавление новой кнопки со сценарием выполнения или добавление блока с прикреплением файлов. Подробнее об этом читайте в разделе [Примеры кастомизации](advanced-features.md).

Предположим, вам нужно проверить наличие оборудования в организации.

Для этого создадим такое задание: исполнителю нужно будет прийти на точку, сфотографировать фасад организации, внутри сфотографировать оборудование с разных сторон. Если оборудования нет, предоставить фотографии в качестве доказательств. Если по адресу нет необходимой организации, сфотографировать здание, где она должна находиться.

Чтобы запустить задания и получить ответы:

1. [Создайте проект](#project)
1. [Создайте пул заданий](#pool)
1. [Загрузите задания](#tasks_upload)
1. [Запустите пул и получите результаты](#launch)

## Создайте проект {#project}

{% include [toloka-requester-source-project-def](../_includes/toloka-requester-source/id-toloka-requester-source/project-def.md) %}

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. Выберите пресет **Мониторинг объектов в организациях** в блоке **Пешеходные задания**.

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. Интерфейс задания описывает, как будут расположены элементы задания.

          Для этого проекта воспользуйтесь [готовым кодом](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4gDgggHwggLwggBwggEIg4YACINGRgMwgWOGAjCCAUiCArCCAXCDxgEwgWMWJKYAMIDGA7CDlgGIg0YDyIICiIHgqSgC+vg5OABbSLiEgcLAQreY0nW049t30zANuXF4+U-4g3LoARkTcmiCAuCDlVYWV0TnpCRXVddHRyMKrOAHWRLauM35O83sAJrp0uk4wyYAFcVuMLCAmP8ensoLopC5Hlh2qtJhDlBinnMNK4tO5OD84IQfkYxqp0aoPkovrjBtpOMsHljaBttrs8SBAAgggBYQBI5QCCIPdTMjnkE7Mjsc5fv9AcCwcy-NjoXRYZzdD8foYiHxZCBkaiMZSlNTHDiFviuESSWT9UaumJTWtpZyGUyRSy8GydntAHgggH4QaIC07nTK5ArlYUOmngQKvYKYpVqb6cv4AoFQUHgpN4FVqwZMQwQH4gsAmA1o6PTUXmvYM61wUmGckdKuJ2Yu+kE3hQADWitmIMMHMGPTodCYfGQAHppwxdAJ-nAwJwoEQ6NO+ABmad0CDcCC93TTpjT7UARxBOskhmnugAbPeACwATgATAAGACMAA5dF+tw-H4AHYty3YCfgAVmA3RgJ-YCX2Aj8YHA+9OAAKyYBAB0hKxxU5QBCEAFQBpEEAbhA8nKLBIko6IqkyBJykANhAchic4inKBiWzEY1HRrTtFh0XQyzgaAAFpNjBPcoBwmNvRHWhAHwQHJ+R5cpYkAGRAsAFQpwmiLA8nCRIeWSNTiJks0hLoETpPeSVkzpWhLOszg+HXcyY2hBgDw1CUWTNfi8AAAXnKBSU8US9wPI9pzTQEDzAJdoC4hweNmWLfKTKUU0GWLOAgMEs3cyE8z2EgIEMXsjAAfUgcqiXhSQ9Tsw0-FSs18H0RtEpsignX87LaCsIkrOgPRuA5NszSGiRrL1CgFD8mg+o7AbnmG5yLxBOBtR+IrZh6YYEzwQ5GMAHhA4nOaj9MicJ-TyQBhECELBAHEQeIMmIrB-WUnJVI0rSdL0gyjJM2IzI9TK1nS2zFshAKQFy-KJwVcGIbWErOTKirqtqwx6v+HVkqTFrMrahxlth1aQGC3RQqIcLIsPY9ppGqBCX4AEoDAFxJv2w69kKD7qKacJjNiQVNNU0j8nCdJYnSbJ8licpOD2yEYCLKQMtRrKHKCkKwoi-dGZi2UeAgBKWcJpVSc+ehRmh7WdYteHTflbNHdzGE9hxvHGqt1qechKRdE8NhII-OycGJvwAF0K3tVZltpZ362JRtbUrRO+Mphl9CMd3cLjN5ers5O9ngHYfk4CTxzEwwNRE0SECLEEmFV1kth9TlACQQYiMmUi6Sg46JKjlgX-XCUjIhYxosBqVSYgaKNS5ACAmBZuasAWiHydkzv5LwQB6ECo8pAAkQHJSPl8NYnb9r9CvPZD391tI-bCGvX3vZj9KS5ThqepohPRulfRWlFp43xRu-Ag99nZQAgFVCAmx0LP24oHJar9sRyT9L-a49QGhz3KHkBIxElZYGiKRPS4RYgCnutQ2IhR7o5AgWgu+3AH6cjgQgww2E7QQ2jg4GOaCtCdTTNZLWOZaycmZhtIgl5tpEF2pApUeADrF1oL3fuSQxbpB5JEe6ZCqjpH9PUQAnCAUFqCxGIeQT4mJ5CxJ6FjIhWLAUwp67EGJUSYWQihWBTrlAqFUZIBCiEkJVrw62QiXYAnEcoyROVTaI0Kko226N6RGCJGWFBKIDQ816P0PYwwYD20zhiJOcTaB9G4CwQwLkSASDAGqXJ4AFwE1cNvJUu9sTSKSg7VGZcpHQHWqNWRIJ9B6hYc6e2gwn7JNiVDEuMMYxwwRgVZGEyzSpPYOk5c5ZFlR1fjbGM2o+Agm4AmTpzoc7dnZrfNYEhpCb3adrC5FNdYEAJMHCqPwIAkBsusmMeF4x7AAFTAsACQgVCZaABEQcowZVIXCuLRG40RQVZIpP86seyllXK4J83s3zfm3MLi8NReBgUETsaRcoJjtFviwFCyF9LYXlHhWUP+yKtJYAYlUSIxEmhaXiAkKIWAlZ5Ceq9TIgtKIMviFgd6VKSjRF0ZRAWhRBQUTISfY4IYsDCyFafGWz04jlFIuEAU6lODArRS-LFmLHaXLeQyHs-ZZlQKHAfEAY4JxTlnFIOgolAXWFEqCTYvAVzbk4PrOmq51zTmGAIQwpYN67iNkeKqFduA-CqpIKQTANiNWnIg9CXCEBVS-FVLcokpDDE4EwKAPCMVrEDUdEACkkinWUta1BGD0G2odc7DNVdEREl0KJeABgiUxg6rwURPSFn2v6m87prNNryMUY2s0qiW37ByJkYWxlToy39EkU1jE4iaRlTLNluDbhhJ7d2vt2IhJc3XjE+1uYegQD3GwOgibWCPpRBu2g8y34Lv6fE9MiS1n3o8l7TkcApAID4OmoSGokQAcORIqQpyrJ5oWL+h+fbMNkxg07OsHzdBfJ+X80jg0i4ttBRC2VYZQGovCdrYjVJaPgYEpwPFBKaMAbFECzk5LKXUu0edGIp17qnSwHSy9ICIycu5by-lApBXCtFeKt6H15WfUnjdDT6lAByIIquxkQlOxCejkFIMs1JJAyLQ4iQDygTynjPc4AAKQUPjBQaQAJSao7Rp26k9wjMVYiUPRsQkgIvZQAy1XaJiNpedix11y+yTrNO6vYXrJwzmnH6gN9Hg0glDcuFyW5I00zCjGjc8aCPCWgHwFNUVdDpuIJm7N0g8341a0WktVU3xVprXWht3HYwkpbW26IHaEjJajqlybcNB18YUXAUd47uaTenV1S2vSF32Wdsuzgq6drZZjFuvYO690izm0ek9EXz30sZSxiMd6MNAbwM+ogr7DtgahJ+79rgCP-qO5xtKso30e3KXgFZSMC6A82XgBDSGEFIMWylyb2GzlwDwz+v9MH+FJjjosknNqkwXLWjNOdoGJFw1OyMsZk6nBTNoJwotrOom6BhwzymCOkmNs9qqOs2zMnsZJgciZeBjk4b5ytDLXBeACG5-cmQ8gYNpcXSnCjVHCWusysJ0lIBGOMphXCyi16kUALY8T5bQm4fvNxZR-F1HLtdPoyCilF8JPnAU+b5lrKcE29uCpo4amBWJC04QnTkqT6vdlfKlVSqrqqvVTRLVJwot6vCAal6xrTXmqS5LvhDujs8ctDoZ1HvaC5c5Pln1RX-XNrKxV8N1Wo2eHq3GqACak2zTa4zTrlceu5vzTqQtSChvlsrdW1m43a-G5m+2ztpeSbl8B6trrQ6NtbbgBOw3Ei9uzp6vT2HjPBm05XSMtdtfsTXc5LdjI+6HufSe2ev6im-EBJMp9iH32IAv2-286R2tATAwO7OYOtGkOkIIG2u6Wzsgu0GAGyocGgwaOyGMAqGpIWOS2OOOG+Oh+FA0BRGm+76TuDI-G7uR+sSzaIK4KjKSsGQFCz0eQlCIe-8twduZBWuK2OKOg1BBugB9BomBEl6KQDEUK0QCQ90NKbE5QLB0QbB+iQYBkh6dmWALK-IwY3iekyQDKCQfi9QUQvKJiWAFCGmnK2hgo4Qcm1uXBekae+6OQJe9ufBjucMTqwwLqgB9eo444BWvqLepWIaYaVWNWtM3ea4DWfeTWyaDMaag6Y+fWBag25UpaT4VUkEo2C+9aS+U2+Egws282WOsBvaFeTua2w6m2Y6B+O2juJ+3UCuUCl+oU1+Z2t+F2tBEij+gwz+r+h67+5Cz2X+TBihrB7B8WN60Q-+C65RFkYAL65ytGyokBhOhGABk28Bqxx2MokGqySOFBKOQwiGyGqRRAXCVUGoWoOoTUX2BBeOBOoOROvBfaCBZGroeubuwhk2ohgwZuzGRC90kWjQPB9qCx5+rRAhfGruAmBR-xtA4hkKkh5Q0hsh8hvi-m4QT0KQdiWAPIk8kWJ8r+GkAo+C721mWkMshQAoOQ6mmmlm2mL0umviEWwC8qMsAo4mf0IsN0PK5Qz0ZhJQxEOkPI8sssNCdChQYelJysZR5BF+lM1Re+dRh+gBTRB2oBlRbRQyN+ci3RQGD+fMT+u6L+92Qxx6Ixn+F6b2wJoJDQcxEJgBwBKxqB4B6xLxmx8xgBOx7plePOeUhx9+4B6B4gZx1xLcoUGOyC6+ZejxuGxBWApBzpHhOpMJQhgmlRiJZKwKgAWCB2EdqRBKxJAmLgmOyQkfF7FfEu765ZmA45mm4KS3RCpOaYn3QCl-RWlGp6KSm0IaYykUkKzKY-yIqOGar3QUSf7nDFDqFFkllh5ebURWnzYUDTwikablAykUJALnBWlqpVA7lR5xAJ4Ch5BUr4l6SxCcD+icABZuFvH2pVkBlrbLCUZEC849FQ7RIA4UHLIJLBlfkpJhkBBSCIhvAwHE49pk58LNRoLU5TZ6ktGIHexX4sycDM7cDjI9ps5wjwIZHc5+l-kC4AWI6XYi75hbK4w7LJYU7oqvyy46jy6-mxJeHXKq5AXiA5qPJplb4Zlwk0EiFe5iESFSEyFyHaICg0l0kMnR6WZVALxnB6FYmha4n4mEmkSMRXRCz3ZkkUmcE3ANBuKx4snx6HpaUyyclYD3T9yizqTklx5UQgk3TmEOEcrgIPmpnvH8FvIqkjpqkNGVGaliIsXawBmnbnYKIhkqImn9FmmDGPbWkvaiVomyn2kzyOl4GAaTaunIUSIQFfpQGvFbGO5EVgEBnIFHGw4nGYGRn5TRkEVxkb4JlEH4bFUVmKlhWUHfHwmcVTTCUAnInxConokSUKFKEqFkJnl2HhCaE2G6HkL6GRCGHGHRCmHETmGWFywChaF8i2H2EGUAIJ6FAuGeUdW8XEVK7V4+EFH+EVKBFN7Fat5hGVYRpd496NaJrNZ95D5JE74pET4DbT4ZFVRZE5Hz61r5F9VNoDWKSr4LZNUBwXVKm+U77rb+XbYFHBV05VmfGDARVdFRXQ2bqxW0ADEWmJWnrJXjETVTFuWJZZWQlPpLF-ZulgEemFUbHg4+nbHQ6hV9JO6VXRVQggWnHo4XFXE3HHL3ElWVG46JltXekcadUC1sW1k-H1kUGNmgq+gZANA1BiykTqTClzksQLlllWqI0pQq3QlXWwl1kImw1kqHCBinyDzdnJD6JUJSkDmzyLXBLEKxCzz02LnLnw1rmUT8iHrFk5BPQ1AhJUnrn3SSxmqaTUQ0r6Hv53lnXK3I1dXb6VyMh0wAjaifm+l83al8VvJC3E1oyi2QBgUiYwEakiLNH8220nZoUyIGlE1GkVKk3HTxUU0nyBjBh-Sm3FnDwmJOkVlQVYowVS6LR0VYAL3cRtAL3Gi5hsIIDxqa7jBOgBl5ogg72syJFl2rAfwMCIwK54C9jDCKKDB8BgBFjjR7ROALi9gADqjYourgP4H4EcRobQxMZO7QpgQwmYYIKAaA6AzY4weA8IiIewgARCD5BWG0QGakT4LoA4MgCIOsC4MPBwNmgIa6AIDOyN6FbziLhWQrgxGbg7hn0nhngjLXhGB3iPivifi-j-iAQgRgQQTQSwTwSITISoQYRYRENtA-aajS0oNoNywYPubYO4NS13E4OtAijENoxFglgS6DCoN5DoOGLKO4C4OFjFhJoaP6haPSOxh1TDD9Z7CQSQScDARviQSIQ-jhxbj3igQuNCDgScD3gfg-hvhvg-iIRgQ-g-j3g-itBwNgPtBAA), где уже настроена валидация и внешний вид задания.

          Исполнитель не сможет отправить задание, если:

          - его геолокация будет отличаться от заданной более, чем на 50 метров;

          - не выберет вариант выполнения задания с помощью одной из трех кнопок;

          - не загрузит необходимые фотографии;

          - не напишет комментарий в том случае, если организация закрыта или отсутствует.

      1. {% include [toloka-requester-source-tb-input-output_1](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output_1.md) %}

          В данном проекте:

          - Поля входных данных:

            - `name` — строка с названием организации;
            - `image` — ссылка на фото объекта;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием объекта;
            - `coordinates` — координаты точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который может написать исполнитель;
            - `verdict` — строка со статусом выполнения задания;
            - `imgs_obj` — массив файлов, фотографии объекта, которые загрузит исполнитель;
            - `coordinates` — строка с координатами задания;
            - `imgs_facade` — массив файлов, фотографии здания, которые загрузит исполнитель;
            - `imgs_around_obj` — массив файлов, фотографии окружения на месте объекта, которые загрузит исполнитель;
            - `imgs_around_org` — массив файлов, фотографии окружения здания, которые загрузит исполнитель;
            - `worker_coordinates` — координаты исполнителя в момент исполнения задания, с включенной опцией **Текущее положение**;
            - `imgs_plate_or_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель.

      1. {% include [toloka-requester-source-new-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/new-name-description.md) %}

      1. Нажмите **Сохранить**.

    - Редактор HTML/CSS/JS

      1. {% include [toloka-requester-source-interface-html-block](../_includes/toloka-requester-source/id-toloka-requester-source/interface-html-block.md) %}

          Блок **JS** используется для описания логики задания. Кроме того, основной контент данного задания заложен в **JS**, для простоты редактирования.

          В логике шаблона заложено минимальное количество фотографий фасада, объекта, окружения, таблички с объектом. Когда нет объекта, то фотографий окружения возле здания. Если вы хотите поменять эти значения, то найдите все строчки и измените для каждого варианта выполнения задания минимальное количество фото:

          ```javascript
          if (solution.output_values.imgs_facade.length < 2)
          if (solution.output_values.imgs_obj.length < 2)
          if (solution.output_values.imgs_around_obj.length < 4)
          ```

          В этом проекте в переменной `texts` хранятся тексты для блока с информацией и тексты для трех вариантов выполнения задания:** Я нашел объект**; **Я в организации, но объекта нет**; **Организация закрыта или отсутствует**.

          В переменной `MAX_DISTANCE` указана максимальная удаленность от назначенной точки (по умолчанию в километрах), на которую может отойти исполнитель во время выполнения задания. Вы можете указать подходящее для вас значение.

      1. В блоке **Спецификация данных** задаются поля входных и выходных данных.

          {% cut "Что такое входные и выходные данные?" %}

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

          {% endcut %}

          В данном проекте:

          - Поля входных данных:

            - `name` — строка с названием организации;
            - `image` — ссылка на фото объекта;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием объекта;
            - `coordinates` — строка с координатами точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который может написать исполнитель;
            - `verdict` — строка со статусом выполнения задания;
            - `imgs_obj` — массив файлов, фотографии объекта, которые загрузит исполнитель;
            - `coordinates` — строка с координатами задания;
            - `imgs_facade` — массив файлов, фотографии здания, которые загрузит исполнитель;
            - `imgs_around_obj` — массив файлов, фотографии окружения на месте объекта, которые загрузит исполнитель;
            - `imgs_around_org` — массив файлов, фотографии окружения здания, которые загрузит исполнитель;
            - `worker_coordinates` — координаты исполнителя в момент исполнения задания, с включенной опцией **Текущее положение**;
            - `imgs_plate_or_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель.

      1. {% include [toloka-requester-source-new-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/new-name-description.md) %}

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

1. {% include [toloka-requester-source-end-edit-new-interface](../_includes/toloka-requester-source/id-toloka-requester-source/end-edit-new-interface.md) %}

{% include [toloka-requester-source-about-project](../_includes/toloka-requester-source/id-toloka-requester-source/about-project.md) %}

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

## Загрузите задания {#tasks_upload}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. Нажмите кнопку **Загрузить**. В открывшемся окне вы можете скачать шаблон файла.

1. Добавьте в него входные данные. Заголовок столбца с входными данными содержит слово `INPUT`. Для пешеходных заданий также нужно указать широту `AI:latitude` и долготу `AI:longitude` каждой точки. Координаты можно уточнить, например, в [Яндекс Картах]({{ ya-maps-object-search }}).

    ![](../_images/tutorials/walk/squirrel_tsv.png)

1. Загрузите задания.

1. Выберите **Указать вручную** и установите значение 1 в поле **Кол-во заданий на странице**.

1. Нажмите кнопку **Разделить задания на страницы**.

## Запустите пул и получите результаты {#launch}

1. Запустите пул, нажав кнопку ![](../_images/other/b-start-pool.svg).

1. Следите за выполнением в блоке **Статистика пула**.

1. Как только получены первые результаты, вы можете начинать проверку.

    Чтобы проверить задания, откройте пул и нажмите **Скачать результаты**. Чтобы скачать вложения, нажмите кнопку рядом ![Выпадающее меню](../_images/other/drop-down.svg) и выберите **Скачать вложения**.

    {% note info %}

    По истечении установленного срока проверки все ответы будут автоматически приняты вне зависимости от качества ответа.

    {% endnote %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}