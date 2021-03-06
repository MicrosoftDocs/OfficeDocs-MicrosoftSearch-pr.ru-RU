---
title: Управление ответами Power BI
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Управление тем, как отчеты и данные Power BI отображаются в результатах поиска
ms.openlocfilehash: e78b8b5d22f7a91d80832fb4f5b536afc277fb6c
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773048"
---
# <a name="manage-power-bi-answers"></a>Управление ответами Power BI

Чтобы упростить пользователям поиск данных и аналитики, необходимых для принятия обоснованных решений, Поиск (Майкрософт) добавил поддержку панелей мониторинга и отчетов Power BI. Вот несколько преимуществ поиска Power BI:

* **Простой в использовании:** Этот доступный способ поиска помогает пользователям легко и быстро находить панели мониторинга и отчеты Power BI в организации.
* **Более емкий контент:** Чтобы сделать результаты поиска Power BI более полезными, они включают ключевую информацию, например тип контента (панель мониторинга или отчет), а также команду или человека, который им владеет.
* **Встроенная защита данных:** Результаты Power BI будут отображаться только для пользователей, у которых есть доступ к панели мониторинга или отчету.
* **Единый поиск:** Чтобы обеспечить единообразие, результаты Power BI согласованы во всех точках входа поиска. При поиске вы получите одинаковые результаты с одинаковым внешний вид.

## <a name="what-users-experience"></a>Впечатления от работы пользователей

Пользователи Поиска (Майкрософт) могут находить результаты Power BI, выступая в поле поиска Windows, SharePoint, Office 365 и Bing. Пользователи могут искать отчеты и панели мониторинга с такими запросами:

* Power BI о `<topic>`
* Power BI для `<topic>`
* `<topic>` Панель мониторинга Power BI или панель мониторинга Power BI `<topic>`
* `<topic>` Отчет Power BI или отчет Power BI `<topic>`
* `<topic>` Метрики Power BI или метрики Power BI `<topic>`
* `<topic>` Система показателей Power BI или система показателей Power BI `<topic>`

Замените в примерах выше сведениями, которые вы ищете, например сведения о `<topic>` продажах, использовании, емкости, 2021, Q1 и других, чтобы увидеть релевантные результаты из Power BI.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Снимок экрана: SERP с ответами и вертикалью Power BI" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Включить или отключить поиск Power BI

Результаты Power BI включены для вашей организации по умолчанию. Администратор Power BI может отключить их в любое время. На портале администрирования Power BI перейдите к настройкам клиента и отключив параметр "Использовать **глобальный** поиск для Power BI". Дополнительные узнать см. [в администрировании Power BI на портале администрирования.](https://docs.microsoft.com/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview)

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Screenshot of setting to turn Power BI answers on or off" border="true":::

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Вопрос. Включен ли поиск Power BI по умолчанию?**

**О.** Да. Поиск Power BI включен по умолчанию для Поиска (Майкрософт). Администратор клиента не должен в первый раз настроить эту функцию.

**Вопрос. Можно ли включить или отключить поиск Power BI для определенных групп или пользователей?**

**О.** В настоящее время его можно включить или отключить только для всей организации.

**Вопрос. Если поиск Power BI отключен, скрыта ли страница результатов поиска Power BI?**

**О.** Нет. Появится страница результатов поиска Power BI с сообщением о том, что в настоящее время она недоступна для их организации.

**Вопрос: будет ли страница результатов поиска Power BI, если у меня нет лицензии На Power BI?**

**О.** Нет. Если у пользователя поиска нет лицензии Power BI, страница результатов поиска Power BI не будет отображаться в результатах Поиска (Майкрософт).

**Вопрос. Будут ли я видеть результаты поиска Power BI, к которые не могу получить доступ?**

**О.** Нет. Поиск (Майкрософт) возвращает только результаты Power BI, к которые у вас есть доступ.

**Вопрос. Можно ли настроить результаты поиска Power BI (например, тип отчета или владелец отчета)?**

**О.** В настоящее время мы не поддерживаем настройку полей, включенных в результаты поиска Power BI.
