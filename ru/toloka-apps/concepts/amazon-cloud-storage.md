# Amazon S3

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

Чтобы опробовать возможности [S3](https://aws.amazon.com/ru/s3/?nc1=h_ls), вы можете активировать [пробный период](https://aws.amazon.com/ru/free).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
------------ | ----------------- | ------------
12 месяцев | 5 ГБ | &mdash;

## Порядок действий {#workflow}

Чтобы получить ссылки:

1. Зарегистрируйтесь в [Amazon Web Services](https://aws.amazon.com/ru/getting-started/hands-on/backup-files-to-amazon-s3/?nc1=h_ls).
1. Войдите в [консоль управления](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin).
1. Войдите в сервис [Amazon S3](https://s3.console.aws.amazon.com/s3/home).
1. [Создайте бакет](#create-bucket).
1. [Загрузите файлы в бакет](#upload).
1. [Скопируйте ссылки](#get-files).

## Создайте бакет {#create-bucket}

1. В разделе **Buckets** нажмите **Create Bucket**.

    ![Create Bucket](../_images/tutorials/cloud-storage/amazon/create-bucket.png =600x118)

1. Введите имя бакета. Имя должно быть уникальным и не содержать пробелов и прописных букв.

    Подробнее о [Правилах наименования бакетов](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html).

1. Выберите наиболее близкий к исполнителям регион. Например, для исполнителей из Германии: **AWS Region → EU (Frankfurt) eu-central-1**.

1. Чтобы файлы в бакете были доступны по ссылке, в разделе **Block Public Access settings for this bucket** отключите опцию **Block all public access**.

    {% note info %}

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% endnote %}

1. Подтвердите изменения.

    ![Подтвердите изменения](../_images/tutorials/cloud-storage/amazon/accept-privacy.png =600x121)

1. Если хотите включить систему контроля версий, выберите **Bucket Versioning → Enable**.

    Чтобы упростить навигацию по файлам, добавьте [теги](https://docs.aws.amazon.com/AmazonS3/latest/userguide/CostAllocTagging.html).

1. Нажмите **Create bucket**.

    {% note info %}

    Вы можете настроить время жизни файлов в бакете, чтобы они автоматически удалялись через несколько дней. [Подробнее](https://aws.amazon.com/ru/blogs/aws/amazon-s3-object-expiration/).

    {% endnote %}

## Загрузите файлы в бакет {#upload}

1. В разделе **Buckets** выберите бакет.

1. На вкладке **Objects** нажмите **Upload**.

    ![Confirm changes](../_images/tutorials/cloud-storage/amazon/upload.png =600x182)

1. {% cut "Загрузить файлы" %}

    Выберите файлы на компьютере и нажмите **Add files**.

    {% endcut %}

    {% cut "Загрузить папку с файлами" %}

    Выберите папку с файлами на компьютере и нажмите **Add folder**.

    {% endcut %}

    {% cut "Создать папку и загрузить файлы" %}

    Чтобы создать папку в бакете, нажмите **Create folder** и загрузите файлы в нее.

    {% endcut %}

    {% note info %}

    Все символы, кроме латинских букв, будут заменены на коды символов, пробелы будуи заменены знаками плюс.

    {% endnote %}

1. Нажмите **Upload**.

1. По окончании загрузки нажмите **Close**.


## Скопируйте ссылки {#get-files}

1. Выберите загруженный файл, на вкладке **Object** нажмите **Copy URL**.

    ![Confirm changes](../_images/tutorials/cloud-storage/amazon/overview.png =600x345)

1. Все ссылки на файлы создаются по одному шаблону.

    Ссылка выглядит так:

    ```
    https://<имя-бакета>.s3.<код-региона>.amazonaws.com/<имя-файла>
    ```

    Ссылка в папке выглядит так:

    ```
    https://<имя-бакета>.s3.<код-региона>.amazonaws.com/<путь-к-файлу>/<имя-файла>
    ```

    {% note info %}

    Чтобы быстро получить ссылки на другие файлы, скопируйте ссылку на один из них и подставьте вместо `<имя-файла>` имена других загруженных файлов.

    {% endnote %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-amazon](_includes/cloud-storage/markup/markup-images-amazon.md) %}

{% include [contact-support](_includes/contact-support.md) %}