---
title: Классические страницы в SharePoint Online и Поиске (Майкрософт)
ms.author: keremy
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
description: Использование Поиска (Майкрософт) на классических страницах SharePoint
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863177"
---
# <a name="classic-pages-and-microsoft-search"></a>Классические страницы и Поиск (Майкрософт)

Сайты SharePoint, созданные до современных сайтов, используют классическое поле поиска и классический опыт результатов поиска. Мы развявем функцию, которая будет использовать классические страницы по умолчанию, чтобы начать использовать современный поиск, использующий Поиск (Майкрософт), который обеспечивает персонализированные результаты с более высокой релевантностью.

Поиск (Майкрософт) рекомендуется использовать для всех сайтов, в том числе классических, но если на классических сайтах используются настраиваемые этаководные страницы и/или вы настроили классический режим результатов поиска, мы автоматически обнавим эти настройки и не переключимся на Поиск (Майкрософт).

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Классические сайты, которые автоматически переключаются на Поиск (Майкрософт)

Классические сайты начнут использовать Поиск (Майкрософт), если все следующие узлы являются истинными:

* Сайт основан на шаблоне сайта группы (например, STS#0 и STS#1).
* На сайте не включена функция публикации.
* На сайте не используется настраиваемая этакое страница (этакое, чем oslo.master или seattle.master).
* В источнике результатов по умолчанию нет активных правил запроса, кроме правил добавления продвигаемого результата для сайта, веб-сайта или клиента.
* В источнике результатов по умолчанию нет пользовательских типов результатов для сайта или коллекции веб-сайтов.
* Сайт или коллекция веб-сайтов не отключаются от переключения с помощью параметра *SearchBoxInNavBar,* описанного ниже.

После перехода на Поиск (Майкрософт) классические страницы на сайте начнут показывать поле поиска на панели навигации набора и удалять классическое поле поиска со страницы. Затем, когда пользователь ищет термин, результаты будут отображаться с использованием современного интерфейса поиска Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Оставаясь в классическом поиске

Если сайт соответствует перечисленным выше критериям, но вы не хотите, чтобы он переключился на поиск (Майкрософт), вы можете отказаться от использования следующих команд в качестве владельца сайта или веб-сайта.

Эту команду можно использовать в любое время, до или после переключения, чтобы можно было легко вернуться к ранее имевшийся опыт поиска.

Чтобы выполнить команды ниже, используйте PowerShell с расширениями SharePoint PnP PowerShell. Вы можете установить и узнать больше о том, как при этом начать [работу.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Чтобы войти на сайт или в его коллекцию, с помощью этой команды:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Чтобы остаться с классическим опытом поиска для сайта, запустите следующую команду:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Кроме того, если вы хотите настроить его для всех сайтов в коллекции сайтов, можно использовать команду:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Отказ от поиска (Майкрософт)

Для тех сайтов, которые не соответствуют перечисленным выше критериям, или для определенных сайтов в коллекции сайтов, которые решили использовать классический режим, можно вручную включить поиск (Майкрософт).

Чтобы изменить этот параметр для определенного сайта, можно воспользоваться этой командой:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Если вы хотите установить его для всех сайтов в коллекции сайтов, можно использовать команду:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Поиск (Майкрософт) можно включить вручную только для сайта группы или сайта публикации (коды шаблонов, содержащие "STS", "CMSPUBLISHING", "BLANKINTERNET" и "GROUP").
