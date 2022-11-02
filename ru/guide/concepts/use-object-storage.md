# Yandex Object Storage

{% include [deprecate](../../_includes/deprecate.md) %}

{% include [amazon-cloud-storage-alternatives-note](../_includes/concepts/amazon-cloud-storage/id-amazon-cloud-storage/alternatives-note.md) %}

Чтобы опробовать возможности [Yandex Cloud]({{ object-storage }}), вы можете активировать [Пробный период]({{ yandex-cloud-free-trial }}).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
----- | ----- | -----
60 дней | 5 ТБ | 50 $

## Порядок действий {#concept_ebz_yz4_nlb}

Чтобы использовать файлы с Yandex Cloud:

1. Создайте бакет в сервисе Object Storage. Для этого воспользуйтесь разделом [Начало работы]({{ object-storage }}).

    {% note info %}

    Создавайте бакет с публичным доступом, чтобы не генерировать ссылку на каждый файл отдельно.

    {% endnote %}

1. Выберите бакет и загрузите в него ваши файлы. Файлы по ссылке будут доступны всем. В целях безопасности рекомендуем использовать хешированные имена файлов. Для хеширования вы можете использовать онлайн генератор (например, [Online MD5 Hash Generator]({{ hash-function-wiki }})). Подробнее о [хеш-функции]({{ hash-function-wiki }}).

    {% note info %}

    Вы можете настроить время жизни файлов в бакете, чтобы они автоматически удалялись через несколько дней. [Подробнее]({{ yandex-tts }}).

    {% endnote %}

1. Если вы сделали бакет с ограниченным доступом, то для каждого файла надо будет получить свою ссылку по [инструкции]({{ link-for-download }}).

    Выберите файл и нажмите {% if locale == "ru-ru" %}**Получить ссылку** → **Скопировать**{% endif %}{% if locale == "en-com" %}**Get a link → Copy**{% endif %}.

    {% include [get-files-link-form](../_includes/concepts/amazon-cloud-storage/id-get-files/link-form.md) %}

    {% include [get-files-link-without-folder](../_includes/concepts/amazon-cloud-storage/id-get-files/link-without-folder.md) %}

    {% if locale == "ru-ru" %}

    ```http
    https://storage.yandexcloud.net/<имя-бакета>/<имя-файла>
    ```

    {% endif %}{% if locale == "en-com" %}

    ```http
    https://<bucket-name>.s3.<region-code>.amazonaws.com/<filename>
    ```

    {% endif %}

    {% include [get-files-link-from-folder](../_includes/concepts/amazon-cloud-storage/id-get-files/link-from-folder.md) %}

    {% if locale == "ru-ru" %}

    ```http
    https://storage.yandexcloud.net/<имя-бакета>/<путь-к-файлу>/<имя-файла>
    ```

    {% endif %}{% if locale == "en-com" %}

    ```http
    https://<bucket-name>.s3.<region-code>>.amazonaws.com/<path-to-file>/<filename>
    ```

    {% endif %}

    {% include [get-files-files-links-create](../_includes/concepts/amazon-cloud-storage/id-get-files/files-links-create.md) %}

1. {% include [tsv-create-create-tsv](../_includes/concepts/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [tsv-create-use-links](../_includes/concepts/cloud-storage/id-tsv-create/use-links.md) %}

    ```plaintext
    INPUT:image
    https://storage.yandexcloud.net/my-bucket/1.jpg
    https://storage.yandexcloud.net/my-bucket/2.jpg
    ```

{% include [contact-support](../_includes/contact-support-new.md) %}