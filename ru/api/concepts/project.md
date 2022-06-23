# Обзор

## Описание {#description}

Задайте в проекте свойства заданий и ответов:

- Параметры входных данных. Описывают объекты, которые необходимо отобразить в задании. Например, картинка или текст.
    
- Параметры выходных данных. Описывают ответы исполнителей. Используются для валидации введенных значений: тип данных (число, строка и т. д.), диапазон значений, длина строки и т. д.
    
- Интерфейс задания. Определяет внешний вид задания для исполнителя и логику обработки ответов
    

## Методы {#methods}

#|
||Метод | Эндпоинт | Описание||
||POST | [/projects](create-prj.md) | 
{% include [create-prj-create](../_includes/concepts/create-prj/id-create-prj/create.md) %}
||
||PUT | [/projects/<project_id>](edit-prj.md) | 
{% include [edit-prj-edit](../_includes/concepts/edit-prj/id-edit-prj/edit.md) %}
||
||GET | [/projects](get-prj-list.md) | 
{% include [get-prj-list-get-list](../_includes/concepts/get-prj-list/id-get-prj-list/get-list.md) %}
||
||GET | [/projects/<project_id>](get-prj.md) | 
{% include [get-prj-prj](../_includes/concepts/get-prj/id-get-prj/prj.md) %}
||
||POST | [/projects/<project_id>/archive](archive-prj.md) | 
{% include [archive-prj-archive](../_includes/concepts/archive-prj/id-archive-prj/archive.md) %}
||
|#


## Узнайте больше {#links}

- [Подробнее о проекте в Руководстве заказчика]({{ requester-prj }})

