# Azure Blob Storage

[Порядок действий](#workflow)

[Создайте учетную запись хранения](#create-account)

[Создайте контейнер](#container)

[Загрузите файлы в контейнер](#upload)

[Скопируйте ссылки](#get-files)

{% note info %}

{% include [photo-hosting](_includes/cloud-storage/photo-hosting.md) %}

{% endnote %}

Чтобы опробовать возможности [Microsoft Azure](https://docs.microsoft.com/ru-ru/azure/storage/blobs/storage-blobs-introduction), создайте [бесплатную учетную запись](https://azure.microsoft.com/ru-ru/free/).

#### Условия пробного периода

Длительность | Размер бесплатного хранилища | Сумма гранта
------------ | ----------------- | ------------
12 месяцев | 5 ГБ | 200 $ в течение 30 дней

## Порядок действий {#workflow}

Чтобы получить ссылки:

1. Зарегистрируйтесь в [Azure](https://signup.azure.com/signup).
1. [Создайте учетную запись хранения](#create-account).
1. [Создайте контейнер](#container).
1. [Загрузите файлы в контейнер](#upload).
1. [Скопируйте ссылки](#get-files).

## Создайте учетную запись хранения {#create-account}

1. Откройте меню портала Azure на [главной странице](https://portal.azure.com/?quickstart=true#home) и слева вверху нажмите ![Hamburger menu](../_images/tutorials/cloud-storage/azure/more-icon.png).

1. Выберите **Учетные записи хранения**.

1. На верхней панели нажмите ![Создать](../_images/tutorials/cloud-storage/azure/plus-icon.png) **Создать**.

1. На вкладке **Основные** выберите подписку, в которой будет создана учетная запись хранения.

1. Введите имя группы ресурсов и учетной записи.

1. Выберите наиболее близкий к исполнителям регион. Например, для исполнителей из Германии: **Регион → (Europe) Центрально-Западная Германия**.

    {% cut "Как это выглядит в интерфейсе" %}

    ![Создайте учетную запись хранения](../_images/tutorials/cloud-storage/azure/create-storage-account.png =600x240)

    {% endcut %}

1. Остальные поля оставьте без изменений. Нажмите **Проверка и создание**.

1. Дождитесь окончания развертывания. Нажмите **Перейти к ресурсу.**

    ![Развертывание выполнено](../_images/tutorials/cloud-storage/azure/deployment-complete.png =450x269)

## Создайте контейнер {#container}

1. Слева в меню в разделе **Хранилище данных** выберите **Контейнеры**.

1. На верхней панели нажмите ![Контейнер](../_images/tutorials/cloud-storage/azure/plus-icon.png) **Контейнер**.

1. Введите имя контейнера.

1. В поле **Общедоступный уровень доступа** выберите **Контейнер**.

    {% note info %}

    {% include [storage-hash](_includes/cloud-storage/hash.md) %}

    {% endnote %}

1. Нажмите **Создать**.

{% note info %}

Вы можете настроить время жизни файлов в контейнере, чтобы они автоматически удалялись через несколько дней. [Подробнее](https://docs.microsoft.com/ru-ru/azure/cdn/cdn-manage-expiration-of-blob-content).

{% endnote %}

## Загрузите файлы в контейнер {#upload}

1. Чтобы войти в контейнер, нажмите на его имя.

1. На верхней панели нажмите ![Отправка](../_images/tutorials/cloud-storage/azure/send-icon.png) **Отправка**.

1. {% cut "Загрузить файлы" %}

    Выберите файлы на компьютере.

    {% endcut %}

    {% cut "Загрузить файлы в папку" %}

    В разделе **Дополнительно** в поле **Отправить в папку** введите имя папки. Если папки не было, она будет создана.

    {% endcut %}

    {% note alert %}

    В имени файлов не должно быть пробелов. Файлы будут недоступны по ссылке.

    {% endnote %}

1. Нажмите **Отправка**.

## Скопируйте ссылки {#get-files}

1. Выберите загруженный файл и в разделе **Обзор** скопируйте **URL-адрес**.

    ![URL-адрес](../_images/tutorials/cloud-storage/azure/url.png =600x120)

1. {% include [get-files-link-form](_includes/amazon-cloud-storage/id-get-files/link-form.md) %}

    {% include [get-files-link-without-folder](_includes/amazon-cloud-storage/id-get-files/link-without-folder.md) %}

    ```
    https://<учетная-запись-хранения>.blob.core.windows.net/<контейнер>/<имя-файла>
    ```

    {% include [get-files-link-from-folder](_includes/amazon-cloud-storage/id-get-files/link-from-folder.md) %}

    ```
    https://<учетная-запись-хранения>.blob.core.windows.net/<контейнер>/<путь-к-файлу>/<имя-файла>
    ```

    {% include [get-files-files-links-create](_includes/amazon-cloud-storage/id-get-files/files-links-create.md) %}

1. {% include [tsv-create-create-tsv](_includes/cloud-storage/id-tsv-create/create-tsv.md) %}

    {% include [markup-images-azure](_includes/cloud-storage/markup/markup-images-azure.md) %}

{% include [contact-support](_includes/contact-support.md) %}