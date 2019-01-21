---
title: Поисковая система набор по умолчанию
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Узнайте, как назначить Bing поисковая система вашей компании по умолчанию с помощью Microsoft Search.
ms.openlocfilehash: 1102c4c58b1e46e450276430a1e79b34964b4ad4
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379149"
---
# <a name="set-default-search-engine"></a>Поисковая система набор по умолчанию

Настройка браузера по умолчанию, поисковую систему по умолчанию и главной страницы по умолчанию поможет пользователям обнаружения возможностей поиска Microsoft, рекомендуем Дополнительные об использовании и предоставление облегчению интерфейса.
  
Чтобы установить средство поиска по умолчанию для вашей организации, выполните следующие действия.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Пользователи смогут изменять службу поиска после установки этой политики.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. Настройте локальный компьютер, который будет использоваться для установки объекта групповой Политики

Вставьте следующий текст в reg (\*реестра) файла.
  
Windows Registry Editor Version 5.00
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
Дважды щелкните файл, созданный и выполните действия, чтобы импортировать файл. В следующем диалоговом окне должно привести к успешного импорта:
  
![Сообщение успешного импорта редактор реестра](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. Откройте консоль управления групповой политикой (gpmc.msc) и перейдите в изменении существующей политики или создание нового

1. Перейдите к **Configuration\Policies\Preferences\Windows параметров пользователя**.
    
2. Щелкните правой кнопкой мыши на **Registry\New** и выберите **Мастер реестра**. В окне браузера реестра выберите **Локальный компьютер** и нажмите кнопку **Далее**.
    
3. Перейдите к **Explorer\SearchScopes того**.
    
4. Из данного раздела убедитесь в том выбрать DefaultScope.
    
    ![Браузер реестра с DefaultScope выбранные](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Проверьте все разделы sub, содержащая GUID для Microsoft поиска в Bing и каждое значение в раздел, за исключением любой путь к профилям пользователей. Прокрутите список вниз, чтобы выбрать другие элементы.
    
    ![Браузер реестра на дополнительные выбранные значения](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Нажмите кнопку Готово для завершения этой конфигурации.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. Настройка пользовательских параметров для предотвращения появления предупреждений, которые пользователь может получить при DefaultScope поиска

Это предупреждение — это предусмотрено при проектировании и оповещений пользователям программы для изменения их параметров.
  
1. В рамках одного объекта групповой Политики щелкните правой кнопкой мыши **Registry\New** и выберите **Мастер реестра**.
    
2. Перейдите к **того Explorer\User предпочтения**.
    
3. Выберите раздел **Настроек пользователя** .
    
4. Нажмите кнопку **Готово**.
    
5. Щелкните только что созданный объект. На правой панели дважды щелкните на объекте пользовательские настройки, **действия** для **удаления и сохранить**.
    
Обеспечение результирующий объект групповой Политики, путем связывания ее соответствующего домена.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>10 Windows, 1703 или более поздняя версия

Пользователи смогут изменять службу поиска после установки этой политики.
  
Для последних ADMX-файлы для различных версий Windows Узнайте, [как создавать и управлять ими центрального хранилища для административных шаблонов групповой политики в Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Если параметр, описанных в данном разделе не удается найти в консоли управления групповыми Политиками, загрузите соответствующий ADMX и копировать их в центральном хранилище. Для получения дополнительных сведений см [Editing Domain-Based объектов групповой политики с помощью ADMX-файлы](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Центральное хранилище на контроллере — это папка с следующее соглашение об именовании:
  
 **%systemroot%\Sysvol\\<domain\>\policies\PolicyDefinitions**
  
Каждого, обрабатывающего контроллере домена должны получить отдельную папку. Для копирования файлов ADMX из командной строки можно использовать следующую команду:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Откройте консоль управления групповой политикой (gpmc.msc) и перейдите в изменении существующей политики или создать новый.
    
2. Перейдите к ** &lt;Конфигурация компьютера/пользователя&gt;\Administrative Templates\Windows Components\Microsoft Edge**.
    
1. Дважды щелкните значок **Установка поисковой системы по умолчанию**, **включена**и введите`https://www.bing.com/sa/osd/bfb.xml`
    
3. Обеспечение результирующий объект групповой Политики, путем связывания ее соответствующего домена.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP с пакетом обновления 2 или более поздней версии

Пользователи не смогут изменять службу поиска после установки этой политики.
  
Chrome, поступающие собственный набор параметров групповой политики, которые можно загрузить в виде ADMX-файл справки [Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202). Если операционных системах Windows Vista/Server 2008 или более поздней версии используются для управления в объект групповой Политики для домена, файлов ADMX, представленные в этот пакет отвечает за параметры хрома на Windows XP с пакетом обновления 2 или более поздней версии.
  
Скопируйте файл шаблона центральное хранилище для ADMX-файлы на контроллере домена. Для получения дополнительных сведений см [Editing Domain-Based объектов групповой политики с помощью ADMX-файлы](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Центральное хранилище на контроллере — это папка с следующее соглашение об именовании:
  
 **%systemroot%\Sysvol\\<domain\>\policies\PolicyDefinitions**
  
Каждого, обрабатывающего контроллере домена должны получить отдельную папку. Для копирования файлов ADMX из командной строки можно использовать следующую команду:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Откройте консоль управления групповой политикой (gpmc.msc) и перейдите в редактирования любые существующие политики или создать новый.
    
2. Убедитесь, что в разделе Административные шаблоны обоих Конфигурация пользователя/компьютера отображаются следующие папки: Google Chrome и Google Chrome - параметры по умолчанию.
    
  - Предопределенные параметры первый раздел и локальных администраторов не сможет изменить их в браузере.
    
  - Можно изменить параметры последнем разделе политик пользователями в настройки браузера.
    
3. Перейдите к ** \<компьютера или пользователя\> Chrome\Default Templates\Google Конфигурация пользователя\Административные поставщика поиска**
    
4. Дважды щелкните **Включить службу поиска по умолчанию**и задайте для него значение **включено**.
    
5. Дважды щелкните **значок поставщика поиска по умолчанию**, задайте для него значение **Enabled**и введите`https://www.bing.com/sa/simg/bb.ico`
    
6. Дважды щелкните значок **мгновенного URL-адреса поиска поставщика по умолчанию**и введите`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Дважды щелкните **имя поставщика поиска по умолчанию**, задайте для него значение Enabled и введите «Microsoft поиска в Bing»
    
8. Дважды щелкните значок **по умолчанию URL-адреса поиска поставщика поиска**, задайте для него значение **Enabled**и введите`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Дважды щелкните значок **службы поиска по умолчанию предложить URL-адрес**, задайте для него значение **Enabled**и введите`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Обеспечение результирующий объект групповой Политики, путем связывания ее соответствующего домена.
    
Установка по умолчанию поисковая система добавит функции предложения поиска Microsoft Search в адресной строке браузера. На данный момент поддерживает только закладки. Пользователи будут видеть верхней предложений два закладку выше предложений общедоступных веб, как они введите в адресной строке.