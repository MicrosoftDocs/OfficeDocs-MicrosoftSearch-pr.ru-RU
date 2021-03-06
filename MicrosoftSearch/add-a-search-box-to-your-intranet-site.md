---
title: Добавление поля поиска на сайте интрасети
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Быстрее получайте релевантные варианты поиска и находите результаты, связанные с работой, добавив поле Поиска (Майкрософт) на сайт или страницу интрасети.
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798228"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Добавление поля поиска на сайте интрасети

Чтобы предоставить пользователям доступ к результатам из вашей организации, добавьте Microsoft Search в поле поиска Bing на любой сайт или страницу интрасети. Ниже приведены некоторые преимущества.

- Поле поиска на портале SharePoint или интрасети предоставляет известную надежную точку входа для начала поиска
- Поддержка всех основных веб-браузеров, в том числе Google Chrome и Microsoft Edge.
- Отображаются только предложения поиска из вашей организации, веб-предложения никогда не включаются
- Переводит пользователей на страницу результатов тестирования Microsoft Search, которая исключает рекламу и веб-результаты.
- Управление внешним видом и поведением поля поиска
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Добавление поля поиска на странице интрасети

Нужно добавить на страницу два элемента: контейнер для поля поиска и скрипт, который его запустит.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

На классическом сайте SharePoint добавьте веб-часть редактора скриптов и вставьте в нее этот скрипт.
  
## <a name="enable-the-search-box-for-mobile"></a>Включение поля поиска для мобильных устройств

Для сайтов и страниц интрасети, которые доступны пользователям мобильных устройств, добавьте в объект параметров строку "isMobile: true":
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a>Установка фокуса в поле поиска по умолчанию

Чтобы пользователи быстрее находили нужную информацию, установите курсор в поле поиска, когда страница или сайт загружается. Для этого добавьте в объект параметров строку "focus: true":
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a>Настройка внешнего вида поля поиска 

Чтобы поле поиска лучше подходило стилю вашей интрасети, можно использовать различные параметры настройки. Комбинируйте параметры в соответствии со своими потребностями.

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a>Внедрение поля поиска с помощью iFrame

Если внедрить скрипт на сайт невозможно, добавьте поле поиска с помощью iFrame. Вы не сможете настроить внешний вид поля поиска.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
