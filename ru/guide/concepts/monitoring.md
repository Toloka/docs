# Мониторинг объектов в полях

{% include [deprecate](../../_includes/deprecate.md) %}

{% note tip %}

Сначала запустите проект в [Песочнице](https://sandbox.toloka.yandex.com/ru/). Так вы сможете избежать ошибок и потраченных средств, если окажется, что ваше задание не работает.

{% endnote %}

{% include [walk-walk-abstract](../_includes/concepts/walk/id-walk/walk-abstract.md) %}

{% include [walk-walk-abstract-decomposing](../_includes/concepts/walk/id-walk/walk-abstract-decomposing.md) %}

Возможно, для вашего проекта нужны дополнительные настройки, например, добавление новой кнопки со сценарием выполнения или добавление блока с прикреплением файлов. Подробнее об этом читайте в разделе [Примеры кастомизации](advanced-features.md).

Примеры задач, которые поможет решить пресет **Мониторинг объектов в полях**:

- визуальный контроль качества и состояния оборудования;

- проверка наличия оборудования по заданному адресу.

Предположим, вам нужно проверить наличие оборудования на улице.

Для этого создадим такое задание: исполнителю нужно будет прийти на точку, сфотографировать оборудование со всех сторон, найти и сфотографировать табличку с адресом. Если оборудования нет, предоставить фотографии в качестве доказательств. Если к оборудованию нет доступа, сфотографировать окружение и показать причину.

Чтобы запустить задания и получить ответы:

1. [Создайте проект](#create)

1. [Создайте пул заданий](#create-task-pull)

1. [Загрузите задания](#download-task)

1. [Запустите пул и получите результаты](#get-the-results)

## Создайте проект {#create}

{% include [toloka-requester-source-project-def](../_includes/toloka-requester-source/id-toloka-requester-source/project-def.md) %}

#### В интерфейсе:

1. Выберите пресет:

    1. {% include [toloka-requester-source-create-project](../_includes/toloka-requester-source/id-toloka-requester-source/create-project.md) %}

    1. Выберите пресет **Мониторинг объектов в полях** в блоке **Пешеходные задания**.

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. {% include [toloka-requester-source-edit-interface](../_includes/toloka-requester-source/id-toloka-requester-source/edit-interface.md) %}

    {% list tabs %}

    - Конструктор шаблонов

      1. Интерфейс задания описывает, как будут расположены элементы задания.

          Для этого проекта воспользуйтесь [готовым кодом](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4gDgggHwggLwggBwggEIg4YACINGRgMwgWOGAjCCAUiCArCCAXCDxgEwgWMWA-CDhgNwggPIggKIgeCpKAL6+Dk4AFtIuISBwsBD15jTNDTj2rfTMXW5cXj4j-iDcugBGRNyaIIC4IIAMIIDsIIXbMTnIwvM4AdZEtq5jfk6TGwAmunS6nL1MAK5zgxYgTC82hsoLopC4zlhGvNhr9lLDzhMNK4tO5OI84IRHkYBqoYapbkp7kjutpOLNTvDaEtVutkSBAAgggBYQBI5QCCICdTBCLkE7BCEc4ni83h9vhS-AiAXQgXTdI9HoYiHxZCAIVDYXilATHIipiiuOjMdiVeqWmItQsBXTSeTOZS8NS1htAHggpWirMO0Ry6Wy+Vi2w5psJ4ECV2CcPFagedOer3eUC+PwjeEl0u6TEMEEenzAJlV0MDoy5Oo2pINcCxhhxTQL4fGlpJqN4UAA1mLxp9DLTum06HQmHxkAB6QcMXQCF5wMCcKBEOiDvgAZkHdAg3Agzd0g6Yg4VAEdPorJIZB7oAGyngAsAE4AEwABgAjAAOXQPhd3x4AdgXC8-jwArJ+uifk+n5Xp+d4wL+p6cAAVkwCBtn8Vg8nSgCEIKygDSIBUeTbFgkR4dEuyZAk2yAGwgORHN6uQFNsVZiBqZpFvW0w6LoOZwNAAC0yzfCuUBIUGDpdrQgD4IDkLKMtssSADIgWCsoU4TRFgeThIkjLJNJmGCdq7F0JxAk3HykbErQekGZwfCzjpQYAgwa6yrylLaixeAAAKjlAWKeFxK5rhug4xm8a5gBO0D0Q4jHjEFTkRvyUbdEFnAQN8CY2X8KYbCQECGM2RgAPqQDl6IgpIyrGWqfhRdq+D6OWYWGRQ5ouQltBWOi+nQHo3C0jW2rtRIBnKhQCjOTQzV1q1FwdRZe6fHACqPOl4xtL0YZ4DsZGADwgcRegRKmROEpR5IAwiBCFggDiIPEGSYVgpQSTkUmyfJinKap6mabE2m2nFCwxUZY1-K5IBJSlfaij9v0LJldLZblBVFYYJUvIqEURpVcXVQ4E1A1NIAeboXlED5fnrpuA2dVAaL8K8UBgC4fUrWtGyFLdBE1OEGmxGyclSRU+ThOksTUb62ycMtfwwBmUixVD8Wme5nneb5q5k4FQo8BAoWU2j4pY3c9D9ADcvy7qIMayKiYm8mgIbIjyNlbrVWM38Ui6J4bD-nexk4BjfgALp5ia8wTUSZulhi5ZGvmIfMXjpL6EYVvISG1xNcZYcbPAayPJwvG9txhiypxXEIBmnxMBLVIrI6dKAEggmEZBJu0lNsSSHMLrPlBUkSUdEVRYLs2xSTEVQBhnIAQEwlPDVgo2-TjQk1yJeCAPQg+HbIAEiA5BUIsFFXNX6AeGzrk71Y+7Wv32svGzr-tW1stz52HXvfr4TksQHwstXcMfdJQBAfKEBliwTPgxF240L4ImEs6WIrITpwNiIUT0WBGThFZLEE6pQ8J5FfidL+CIf5-26AA-K7F6ZKjAUMYy-sIFaDqjGAysskzFjpBTWaRB9wLSIEtSGLDVpp1oA3JuSRubpEZJEE6WAiLpFKIAMRBoiAE4QCgcjKIxFwQRRRjJKLnVUZEdReFe6xHOkUNuhiP7SIqMpLa2wUh7GSIPbYeQEiYViOLY06M6Hm1eMw8UmdowazBmlPhfj-i2ytEYdEOYqF+3PnaegHQwQbF6DAI2MdYSh1Yd2NYLBDCWRIBIMA0pGaWDHKjVw89xSLwROw8Kxsob+O6LUqmnDPj6GVBAlyRtuinxCSw-66dAZBmBqDVKENOm2XCSSSJk5cxDN9hffWQYFR8E+NwMM1SLTx0bDTAh4hJAyHkFAyB8zhnbK4G7XKjwIAkEMhMlOlxBF4AAFTPMACQg4R4iv22K8qhuJ7knJNlshWBBUSXObNc25ez+qp3WiAZ5aFtEVG2IosRO0YhbROltLAF4sCABEQT5gtMg0TfqyLApFdiREwjUeS8QEhRCwH6PI50rqZFujdXe3dDoYJkoAORASjRG0ZEV+50cgpEFtJJIGQEGYWftsLlfcvQAAo2RWKwI-GSABKaRWAH4YKOpUcIFEqKfO5btCoMkX7hGcSdY1-dODPL+XEoFmzcYgtJE2VsfSGkgA7CvEAPY+wDmHFIOgXEUKhi4l8ZYvApyLk4ErYm05ZyDl6AIQw2YZ7LlVhufK2duCPHygcpgSwyqDmAbBPNxAC35QfFxKQvROBMCgIhb1V9gyPLhaJJID8EhOvAccwspyWogvzbnME6JdBcXgAYaF38GENV8UCxpbVoAzS6nNbhvCAV-AEXCzYORMgcw0ltQWpQkgVCNXEOSBKvnEtFu4wdQwd0LHIUQaeS7rb-DaBAFcbA6AZtYMO59T6EQDMvkCkyZtRng2TpBm2UpklSAQHwIBID+3OvgyAKQaz9IlqmAB4+wGll+FdWc91YLdBXJuXc0Dq7O0bFeYAFBADU93NZa7YA9kgEoSDYhRVRfkeJNiR7GdGV16h0OCyFtHgM1NhYxwA6CDaNZHJUirJu5Gsooy-IGDzqqTpZhRRd0ki7EwgcCxbouXmoHkdN00k5L3oKJY5SYrBYKXCIojBBxzqFEKI9AerI1JII-l5k6vLACSIGF6RkQeN8eiPy4oMQKLnuiH5oVh0vTdxyA6jDvsX1kZHWbMdZJiavAVLoOdYGhSfrluJ7xbwgnjLoxKKZtApA5SIPlFJEBOCQCkGCa4dGRMGx-vVHW9TINQbtmuwaG7WlbsqwsPdGwD1Hs5tEU9G9XTumeqpLaD9Ih+iSIox9snIRPuG5qMTWTaDFaLuiCApdy6VzbXFa+NINhKZ5uS7Y6nDXGpKEdelZKyWKV2Kesi3LZIJcbqRZ663hUHHbodoWfm-TjzO3gKeM8jlnaHZN7UMD65t2iB3LAD5FuH1-mbdrCout9FrRToTk3LukeawsIn3Q64k7JzeSn87qcbFp517rta+fM8g6z0TeOOc32J8j4WC5+eEKPjTjr9PUm1qVxLoFsS5a0Ou+Bgr5HoOBLGXB5dYTEN0mFxrnrWI+BgEMHAaeBla25ZA5jggC7xuDIJ1NthM3KacE3YtfneBlt0lWxkY9G3BaswyHDuSSPSco8+WjsWHuFnEfy9d4GxWilEDAM2ZYEAfJlxSi9l90C5fdC+ypn7f3L0A8Uue9B8lAfg6NVDvlJRYf2ffqyVSFrVKtwV+EYo6eP7+kW1j130BZ6VMm8bv4nOhE85R0z6vQYiFq7p6Lm8TP2dS-xOzmvH35ep+FuL7fVPiFtfVwf8Xx-b8Qcm+92uXON+K+V+wVXQvH8Gcbxtdj86MDcvcjd2c6sYNglX8ENUwH998+g0RFQncXdKZ8pn8zsT8BcxsmEJssNgZmkQ95sw9Xt21I9uho9Y9NsE8k8x8r9Udp9TsWcLtc8vdgZSQpMaNZ8O1UJuhXkPkvlh4WRWRDojM-QMgrELo8hohBM2Cn0V8A8GwLkqMIUeDyDQkI0nl4U0Jb1wgUhSI8VogEgTpUUvRuNEg4sohJF+VJDpDToO8RC2RwhsVog1VWQkUUUxF9CsBnD3R5J0FHpe5xVUFXC8IlUTorE5E8I0EKhIc8JAtChsEno5IyU3Q9sPNNUcsddMZ2D38bsJMeBegvVt88A-UNhA1+whxBxQ1w1YUo1PgY1JxLIFwE1CZvJk05w01CMOIF9s1-JdAq0c4i1pAS0UY+By0QFhia0bx8oFx8oLx61G1m1W0yi+DQwNhu0NsJIPccClC6tisJ04Ap0Z0GZrtRtGE6k-cCc6tiDQ8eFw8A1mYo9D0Y91tNsUtm9r18VCU-DmQ2RxDGVtgpDogZDogWDJd1i30P0CDLcmAf0-1XBCMgMWd1jICZdoCzdYMniYZug4BkNUNZR5RFRypsD1icN1kXdZ1kTAMFDgMDjCjQVVDqMoVNCDZtC4VXlAAsEFcIOyOyUXkJz0ULz3OUkzUOk14M5MY0AFQQVkNVA4bFXuLAE6PmdBOSe6SSAfQoVkflSw3jbYBRBLX4+IQw7YYw2oc6coMibYCoMwjBbYHzV0TeFuHIL0XUqSHI+kl1UU0datXOWYKjIgCrdk6KarOEr9EZbE2AqAq3BAgIfrTY3I36PXTGY5QOIZVMgdMaTZaaWbRqN-UJIgoPCyVpdpPZJwbpWgUhCtCs+rGrIsvGGAprYDeAksGZaJZMyKRZCZPAFZXDBst1cOHZAQOsiQaQRfEUjgsUzgbgtk9Y6UukBFfQs04w0w8wwIkoVkHIGlfVelYVPVL5dw5Sa1Uwu1HIc6FIbRMI+IrTdmdbWSVkGzH0AoExJxFla6W6CHF+DlQWE6JuLmGSJ8koIWeBRBZBZSSRSHAwolF8v0L04Uhk30orf02cnhE46dOAGk9Yy4xdCM2rJk+40gx40Mg2Sg2gagj4s9C9K9Z6Xw0821PuKoSE3XaEsAemWEm4gohE39KslEobdE8Mriwgps6Mls-3NsukAklDMhcuLyNDUBLszxa7SkvDGkigfixCn06cijFk9Q+c67RcgQvQwlVckwswsRfU6w-RKLewsExwslfw1w5zeSLwjc3w-wxIoIiRVzMImxLASI6I2IyoBIwI5I4eAfdIofVwrIhC1iqcgozgnZFsXgioukKo4NWosNTkxo5ouNNoxNTwLo1NKAdNTNIaAYsmGYwtYtUtRUKYytMdTA+YxY5YqmVYqU+TOkbY3tPY-IkSv0nONCydTC7Ci4n3fA4Sy3YsryfMkgrhMguA54nQyik9ai9w2im9P4-woEuy8Eli4TNijijZWMnipEjSuk8kw3ISwsgiqM2MRrC3L9PE8QQkshOUFZMktElS3DakgjS6+KpCnS4cvSyU0ioMIy2gHkvkyiAUxRIUwG7SxKmcucmTAoyGvAUSIHTICyr0E6SlAfFLC6ZIKRT5MCrzfub5HVE6XCMiFuYoPbfkknCEvqhKgalCoawM8rXgjEiSpk5sp6gil6hMgbOZVg4jdMxZCqCBXMjtddAssjO4ksrqMs7gDpY5Ss4EQBN9ShcGvAXmyM0Sh683OdSS6ZJGWZDDLMzDFhfs9ZQck3EsEcwW8Yccw5CpNm6alGiUjQhcrqgQ7Y5xHIV0HwwlOVFSQlelbFZBCRIlG1G0iLN04zdBWIUiSILzcIc6PCJlCiYzMEzSUChBCmgeNBDBLBHBPBOKw6z2w23SnQT1VKzsSo3saokNbKho6NWNVo9oomIqmcbo0q3orNUmXNJq2qiYhq6q-Kf8NqptFtTqhjbqntXYpSyKfqr2wagtYajCs43g3C33W6n1Ga+W+a+aRa2M8ijaN4mg9a74uiv4tvDBNOrzTPVe52a7GEk6zE79Xi-9AGqE66nxfCo+o2hrE28GjKVrPAaSokuSwtUhHWr6gBr3VSv6v+ojRGk2RkpK0G32wy-2qGky00ow8yjcqyw06IGw2ykEhwqRRygEwLNwjwty0O4Qhhry7cny0ItBfywK6IGIm80KpIlIyK6RaK09RRbIx1N+m2qGbBmchuiBhYNK7sFuzKuonKzulo+NQq4qnojNPo0qyq0e-00YqQcYstCtKeuYhYpYhtdq+epRuTRe7oHqle70rB5CrOVC4404rC84r3feyaw+9tY+uah47dC+l4qg6+qivOu+rath0Q3amh+ylmmR-5D+9i99L+vms6vi-+zBy3A25GkFAW3EqBnoN64kz6rPSECk36-DdB1E6uoG0pkG8U1ktGrDDG+FZ5J0DIKoIebmC1KlIzRm2GkneG6RjxuWeRuu2cn2gyr3Xp55HYZ0luImkmq08IC6HITFPvd+eSU9FINVcobBHlFSSumZrSzx4G7xzm0rIMkMwSoBqa2u03Y2nEpx6GSpvrUWupnAlXXgK4hW2MsJ4PCJp4y+rYWJtarbOzXbGGw7KZg6uWa2qqSWzMiqCEDM3EBoPF+pxQZMX+BANNXHJiWEOrEtT4MlqmEel5+Ya+BgMGBsvAZsXoXhboR3DMHqZaJwMcZsAAdXLGtwoCfDvG9nVAaAxgzMaFMB6HjG+BQDQHQErEGDwBBCSTpEACIQHTYWGRbuAedAE1kALV1gU104dV7UAk3QBAM2DKmo0cccfSKcfu+cJcBlrcHcVpQ8IwE8c8a8e8Z8V8d8L8H8P8QCYCUCcCSCaCOCBCK1hoPAGp0kjYPVvIDBaRXYO6SoY1011NyhS1zka16GDMLMTs7oDNrNw1vN3AU19MTMTNE1+oEt5N4MYqXoCYjYf8f8TgT8G8f8cCJ8L2BcU8b8XtoQX8TgU8O8J8G8G8J8cCH8J8J8U8J8eodV+VxoIAA), где уже настроена валидация и внешний вид задания.

          Исполнитель не сможет отправить задание, если:

          - его геолокация будет отличаться от заданной более, чем на 50 метров;

          - не выберет вариант выполнения задания с помощью одной из трех кнопок;

          - не загрузит фотографии объекта или фотографии, подтверждающие его отсутствие;

          - не напишет комментарий в том случае, если отсутствует доступ к объекту.

      1. {% include [toloka-requester-source-tb-input-output_1](../_includes/toloka-requester-source/id-toloka-requester-source/tb-input-output_1.md) %}

          В данном проекте:

          - Поля входных данных:

            - `name` — строка с названием организации;
            - `image` — ссылка на изображение объекта;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием объекта;
            - `coordinates` — координаты точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который может написать исполнитель;
            - `verdict` — строка со статусом выполнения задания;
            - `imgs_obj` — массив файлов, фотографии объекта, которые будет загружать исполнитель;
            - `more_info` — JSON-объект с дополнительной информацией об объекте;
            - `coordinates` — строка с координатами задания;
            - `imgs_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель;
            - `imgs_around_obj` — массив файлов, фотографии окружения на месте объекта, которые загрузит исполнитель;
            - `worker_coordinates` — координаты исполнителя в момент исполнения задания, со включенной опцией **Текущее положение**;
            - `imgs_around_no_access` — массив файлов, фотографии окружения если нет доступа к объекту, которые загрузит исполнитель.

      1. {% include [toloka-requester-source-new-name-description](../_includes/toloka-requester-source/id-toloka-requester-source/new-name-description.md) %}

      1. Нажмите **Сохранить**.

    - Редактор HTML/CSS/JS

      1. {% include [toloka-requester-source-interface-html-block](../_includes/toloka-requester-source/id-toloka-requester-source/interface-html-block.md) %}

          Блок **JS** используется для описания логики задания. Крооме того, основной контент данного задания заложен в **JS** для простоты редактирования.

          В логике шаблона заложено минимальное количество фотографий объекта, окружения на месте объекта, окружения если нет доступа к объекту. Когда нет доступа к объекту, то фотографий таблички с адресом. Если вы хотите поменять эти значения, то найдите все строчки и измените для каждого варианта выполнения задания минимальное количество фото:

          ```javascript
          if (solution.output_values.imgs_obj.length < 4)
          if (solution.output_values.imgs_around_obj.lrngth < 4)
          if (solution.output_values.imgs_around_no_access.length < 4)
          ```

          В этом проекте в переменной `texts` хранятся тексты для блока с информацией и тексты для трех вариантов выполнения задания: **Я нашел объект**; **Я на месте, но объекта нет**; **Отсутствует доступ к объекту**.

          В переменной `MAX_DISTANCE` указана максимальная удаленность от назначенной точки (по умолчанию в километрах), на которую может отойти исполнитель во время выполнения задания, в км. Вы можете указать подходящее для вас значение.

          Количество радиокнопок можно менять. Достаточно добавить или удалить в соответствующем месте объект вида:

          ```plaintext
          {
          'name': 'more_info.radio',
          'value': 'radio_1',
          'label': 'Вариант 1'
          }
          ```

          где `name` — путь в выходных данных, `value` — значение отдельной радиокнопки в выходных данных, `label` — отображаемое название в шаблоне.

          Количество чекбоксов можно менять. Достаточно добавить или удалить в соответствующем месте объект вида:

          ```plaintext
          {
          'name': 'more_info.checkboxes.checkboxe_1',
          'label': 'Вариант 1'
          }
          ```

          где `name` — путь в выходных данных, `label` — отображаемое название в шаблоне. Значения у чекбоксов `true/false`.

      1. В блоке **Спецификация данных** задаются поля входных и выходных данных.

          {% cut "Что такое входные и выходные данные?" %}

          {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

          {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

          {% endcut %}

          В данном проекте:

          - Поля входных данных:

            - `name` — строка с названием организации;
            - `image` — ссылка на изображение объекта;
            - `address` — строка с адресом задания;
            - `product` — строка с описанием объекта;
            - `coordinates` — строка с координатами точки, куда должен прийти исполнитель.

          - Поля выходных данных:

            - `address` — строка с адресом задания;
            - `comment` — строка с комментарием, который может написать исполнитель;
            - `verdict` — строка со статусом выполнения задания;
            - `imgs_obj` — массив файлов, фотографии объекта, которые будет загружать исполнитель;
            - `more_info` — дополнительная информацией об объекте, тип JSON;
            - `coordinates` — строка с координатами задания;
            - `imgs_address` — массив файлов, фотографии таблички с адресом, которые загрузит исполнитель;
            - `imgs_around_obj` — массив файлов, фотографии окружения на месте объекта, которые загрузит исполнитель;
            - `worker_coordinates` — координаты исполнителя в момент исполнения задания, со включенной опцией **Текущее положение**;
            - `imgs_around_no_access` — массив файлов, фотографии окружения если нет доступа к объекту, которые загрузит исполнитель.

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

## Загрузите задания {#download-task}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}

1. Нажмите кнопку **Загрузить**. В открывшемся окне вы можете скачать шаблон файла.

    #### Использовать пример данных

    Если вы хотите посмотреть, как ваш проект будет выглядеть после запуска, но у вас еще нет заданий для разметки, вы можете загрузить в пул готовый пример данных.

    Нажмите **Использовать пример данных** справа от надписи **Прикрепите подготовленный файл с данными**. Это позволит избежать дополнительных действий с файлами.

    После того, как вы поработали с примером данных и вас все устроило, подготовьте свои данные и загрузите их в пул.

1. Добавьте в него входные данные. Заголовок столбца с входными данными содержит слово `INPUT`. Для пешеходных заданий также нужно указать широту `AI:latitude` и долготу `AI:longitude` каждой точки. Координаты можно уточнить, например, в [Яндекс Картах]({{ ya-maps-object-search }}).![](../_images/tutorials/monitoring/download-task.png)

1. Загрузите задания, выбрав **Указать вручную** и установив 1 задание на странице.

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