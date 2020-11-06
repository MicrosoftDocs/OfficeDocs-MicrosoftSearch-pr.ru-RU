---
title: Управление настраиваемыми фильтрами
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Управление настраиваемыми фильтрами
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927389"
---
# <a name="create-custom-filters"></a>Создание настраиваемых фильтров

Вы можете создать фильтры, чтобы настроить поисковый интерфейс, который пользователи видят при поиске в Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)и Microsoft Search в [Bing](https://bing.com). Фильтры позволяют пользователям быстро уточнять набор результатов из запроса поиска.

Настраиваемый фильтр можно создать в вертикальном направлении на основе свойства Connection. Например, вы можете создать **опубликованный** фильтр для подключения ServiceNow в настраиваемом вертикальном расположении.

## <a name="things-to-consider"></a>Важные факторы

1. Для создания настраиваемого фильтра для источника контента подключения предоставляются некоторые дополнительные возможности:
- Вы также можете создать фильтр для свойств источника для соединителя.
- Если вертикальная линия имеет несколько подключений, вы можете создать общий фильтр для этих подключений. Это можно сделать, создав фильтр на общем псевдониме, который будет псевдонимом свойств источника для разных подключений. Например, вы можете создать фильтр **авторов** в ServiceNow & подключения жира, создав псевдонимы следующим образом:

| Connection | Свойство | Alias |
| --- | --- | --- |
| Служба сейчас | Владелец | Автор |
| жира | Publisher | Автор |

2. Существуют фильтры в пределах области действия по вертикали. Силу  
- Если фильтр создается вертикально на уровне Организации, то фильтр будет виден только на уровне Организации.
- Если фильтр создается по вертикали на уровне сайта, то фильтр будет виден только на уровне сайта.

## <a name="steps-to-create-custom-filter"></a>Действия для создания настраиваемого фильтра

### <a name="create-filter-in-organizational-level-vertical"></a>Создать фильтр на вертикальном уровне Организации:

Чтобы создать фильтр для поиска Microsoft Search, выполните следующие действия:

1. В центре администрирования Microsoft 365 откройте страницу [вертикальные черты](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .
2. Создайте или измените вертикальный фильтр, на котором нужно создать фильтр.
3. Перейдите к шагу "фильтры" мастера.
4. Нажмите кнопку "добавить фильтр" и приступайте к работе после добавления фильтров вы можете просмотреть и сохранить вертикальную.

## <a name="known-limitations"></a>Известные ограничения

1. В настоящее время фильтры можно создавать только для строкового & тип данных управляемых свойств.
2. Невозможно создать иерархические фильтры

## <a name="resources"></a>Ресурсы

[Настройка страницы результатов поиска](customize-search-page.md)