# Обзор

{% include [deprecate](../../_includes/deprecate.md) %}

## Описание {#description}

Навык — это оценка какого-либо аспекта ответов исполнителя (число от 0 до 100). Вы можете настроить подсчет навыка в [блоке контроля качества](quality_control.md) или задать значение навыка у исполнителя вручную. Навык можно использовать для [отбора исполнителей](filter-skill.md), выполняющих задания в пуле.

## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание**||
||POST | [/skills](create-skill.md) |{% include [create-skill-create-skill-p](../_includes/concepts/create-skill/id-create-skill/create-skill-p.md) %}||
||PUT | [/skills/\<id\>](edit-skill.md) |{% include [edit-skill-edit-skill-p](../_includes/concepts/edit-skill/id-edit-skill/edit-skill-p.md) %}||
||PUT | [/user-skills](set-skill.md) |{% include [set-skill-set-skill-p](../_includes/concepts/set-skill/id-set-skill/set-skill-p.md) %}||
||GET | [/user-skills](get-user-skill-list.md) |{% include [get-user-skill-list-get-skill](../_includes/concepts/get-user-skill-list/id-get-user-skill-list/get-skill.md) %}||
||GET | [/user-skills/\<id\>](get-user-skill.md) |{% include [get-user-skill-get-skill](../_includes/concepts/get-user-skill/id-get-user-skill/get-skill.md) %}||
||GET | [/skills](get-skill-list.md) |{% include [get-skill-list-get-skill](../_includes/concepts/get-skill-list/id-get-skill-list/get-skill.md) %}||
||GET | [/skills/\<id\>](get-skill.md) |{% include [get-skill-get-skill-p](../_includes/concepts/get-skill/id-get-skill/get-skill-p.md) %}||
||DELETE | [/user-skills/\<id\>](delete-skill.md) |{% include [delete-skill-delete-skill-p](../_includes/concepts/delete-skill/id-delete-skill/delete-skill-p.md) %}||
|#

## Узнайте больше {#links}

- [Описание навыков в Руководстве заказчика](../../guide/concepts/nav.md)