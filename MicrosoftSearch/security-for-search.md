---
title: Безопасность и конфиденциальность для службы поиска Майкрософт в Bing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Защита данных и конечных пользователей компании, а также предоставление сведений для авторизованных пользователей с помощью Microsoft Search в Bing
ms.openlocfilehash: 1cc00a3b14b1918903c9aa34a24f13b1761b64b6
ms.sourcegitcommit: 5946fe6aad2331c023bedda8faf826c0248651f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41711757"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Безопасность и конфиденциальность для службы поиска Майкрософт в Bing

Благодаря расширенным мерам конфиденциальности и безопасности служба поиска Microsoft Search в Bing помогает защитить данные пользователей и рабочих местах.

## <a name="secure-by-default"></a>Защита по умолчанию

Microsoft Search в запросах Bing выполняется по протоколу HTTPS. Для усиления безопасности соединение шифруется от конца к концу.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Проверка подлинности и авторизация с помощью Azure Active Directory

Проверка подлинности для поиска Майкрософт в Bing связана с Azure Active Directory. Когда пользователи Microsoft Search переходят в Bing, заголовок Bing будет отображать параметры входа для учетной записи Майкрософт, а также рабочую или учебную учетную запись. Если служба Bing не может определить, является ли пользователь подходящим участником, пользователи могут перейти на страницу " [изучение службы поиска Майкрософт](https://www.bing.com/business/explore) ", где она будет автоматически перенаправлены на страницу входа в организацию.

Пользователи могут получить доступ к Поиску (Майкрософт) только с помощью рабочей или учебной учетной записи. Они должны выполнить вход с помощью тех же учетных данных, которые они используют для доступа к службам Office 365, таким как SharePoint или Outlook. Для входа в Поиск (Майкрософт) нельзя использовать личную учетную запись Майкрософт.

## <a name="single-sign-on"></a>Единый вход

Если пользователь уже прошел проверку подлинности с помощью рабочей или учебной учетной записи в другой службе (например, Outlook или SharePoint), они будут автоматически входить в одну рабочую или учебную учетную запись при переходе на Bing в том же браузере. Кроме того, когда пользователь выходит из рабочей или учебной учетной записи, он автоматически выйдет из других служб Microsoft Office в том же браузере.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Обменивается данными с облаком Майкрософт из браузера

Когда пользователь входит с помощью рабочей или учебной учетной записи, служба Bing загрузит в браузер необходимые клиентские библиотеки, чтобы включить результаты поиска Microsoft. Затем, когда выполняется поиск, код в браузере вызывает облако Office 365 для получения результатов работы. Для этого Microsoft Search использует выделенный API, который управляется в соответствии с целями управления ССАЕ 18 SOC2 Type 1. Это означает, что результаты работы и рабочие данные не проходят через системы Bing, которые подвержены менее строгим целям контроля обработки данных, чем сами результаты работы, которые могут быть обработаны в Office 365 Core Online Services.
  
## <a name="permissions"></a>Разрешения

Рабочие результаты, полученные из рабочих нагрузок Office 365, таких как SharePoint и OneDrive для бизнеса, фильтруются на основе ролей безопасности в источнике. Пользователи не видят такие ресурсы, как документы Word или презентации PowerPoint, если они не могут их просматривать и получать к ним доступ через Office 365. Они могут просматривать только свои файлы и файлы, которыми с ними явно или неявно поделился автор (например, посредством участия в группе) в SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Служба поиска Microsoft Search в Bing обеспечивает защиту при поиске в рабочем месте

Когда пользователь вводит поисковый запрос в службу поиска Microsoft Search в Bing, происходит два одновременных запроса поиска:

- Поиск внутренних ресурсов Организации.
- Отдельный Поиск общедоступных результатов из Bing.com.

Так как поиск на рабочем месте может быть конфиденциальным, служба поиска Майкрософт реализовала набор мер доверия, описывающих, как будет обрабатываться отдельный Поиск общедоступных результатов из Bing.com.

### <a name="logging"></a>Ведение журнала

- Все журналы поиска Bing.com, которые относятся к Microsoft Search в трафике Bing, не связаны с удостоверением вашего рабочего места.
- Если достигнут набор ограничений или пороговых значений частоты, что дает нам уверенность, что запрос не зависит от конкретной организации, запрос будет рассматриваться, как описано в разделе "Поиск и искусственный анализ" в заявлении [о конфиденциальности](https://privacy.microsoft.com/privacystatement). Например, такие запросы будут использоваться для моделирования и обучения общедоступных функций, таких как Автоподбор или связанные поиски.
- Запросы, не соответствующие набору ограничений или пороговых значений частоты, будут храниться отдельно от общедоступного трафика, не относящегося к Поиску (Майкрософт).

### <a name="advertising"></a>Реклама

Реклама, показанная в Bing.com в связи с поиском на рабочем месте, исключительно связана с содержимым поисковых запросов. Реклама никогда не направляется пользователям на основе их рабочих удостоверений.

## <a name="gdpr"></a>GDPR

[21 мая 2018 г. запись блога](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) от корпорации Майкрософт отражает наши обязательства на соответствие требованиям GDPR, а также о том, как корпорация Майкрософт помогает предприятиям и организациям с собственными обязательствами по обеспечению соответствия требованиям GDPR. Дополнительные сведения можно найти в [разделе вопросы и ответы центра управления безопасностью](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)Майкрософт.

Запросы Microsoft Search, выполняемые с внутренними ресурсами и результатами клиента, считаются данными о клиентах и, таким образом, также удовлетворяют обязательствам процессора, приведенным в статье 28, как показано в разделе [вопросы и ответы центра управления безопасностью](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). По отношению к запросам от Microsoft Search, которые переходят на общедоступный Bing Bing, корпорация Майкрософт отвечает за соблюдение своих обязательств по GDPR в качестве контроллера данных.
