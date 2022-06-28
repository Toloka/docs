# Yandex Object Storage

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

Чтобы опробовать возможности [Yandex&#160;Cloud](https://cloud.yandex.ru/docs/storage/quickstart), вы можете активировать [Пробный период](https://cloud.yandex.ru/docs/free-trial/).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
------------ | ----------------- | ------------
60 дней | 5 ТБ | 50 $

## Порядок действий {#plan}

Чтобы использовать файлы из Yandex&#160;Cloud:

1. Создайте бакет в сервисе Object Storage. Для этого воспользуйтесь разделом [Начало работы](https://cloud.yandex.ru/docs/storage/quickstart).

    {% note tip %}

    Создавайте бакет с публичным доступом, чтобы не генерировать ссылку на каждый файл отдельно.

    {% endnote %}

1. Выберите бакет и загрузите в него ваши файлы.

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% note info %}

    Вы можете настроить время жизни файлов в бакете, чтобы они автоматически удалялись через несколько дней. [Подробнее](https://cloud.yandex.ru/docs/storage/operations/buckets/lifecycles).

    {% endnote %}

1. Если вы сделали бакет с ограниченным доступом, то для каждого файла надо будет получить свою ссылку по инструкции.

    Выберите файл и нажмите **Получить ссылку → Скопировать**.

    {% include [get-files-link-form](_includes/amazon-cloud-storage/id-get-files/link-form.md) %}

    {% include [get-files-link-without-folder](_includes/amazon-cloud-storage/id-get-files/link-without-folder.md) %}

    ```
    https://storage.yandexcloud.net/<имя-бакета>/<имя-файла>
    ```

    {% include [get-files-link-from-folder](_includes/amazon-cloud-storage/id-get-files/link-from-folder.md) %}

    ```
    https://storage.yandexcloud.net/<имя-бакета>/<путь-к-файлу>/<имя-файла>
    ```

    {% include [get-files-files-links-create](_includes/amazon-cloud-storage/id-get-files/files-links-create.md) %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-yandex](_includes/cloud-storage/markup/markup-images-yandex.md) %}

{% include [contact-support](_includes/contact-support.md) %}