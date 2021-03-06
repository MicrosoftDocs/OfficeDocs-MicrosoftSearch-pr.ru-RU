---
title: Соединители SQL Azure и Microsoft SQL Graph для Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Настройка соединиттеля Azure SQL Microsoft SQL Graph для Microsoft Search.
ms.openlocfilehash: 499c0fad93f97e634086ff9025d947c4f70336fb
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508907"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Соединители SQL Azure и Microsoft SQL Graph

Соединители SQL Microsoft или Azure SQL Graph позволяют организации обнаруживть и индексировать данные из локальной SQL Server базы данных или базы данных, которая SQL экземпляре Azure в облаке.
Индексы соединиттеля Graph заданы контентом в Microsoft Search. Чтобы поддерживать индекс в курсе исходных данных, он поддерживает периодические полные и дополнительные обходы. С помощью SQL соединители можно также ограничить доступ к результатам поиска для определенных пользователей.

> [!NOTE]
> Ознакомьтесь [**со статьей Настройка соединиттеля Graph,**](configure-connector.md) чтобы понять общие инструкции по настройке соединитений Graph.

Эта статья для всех, кто настраивает, запускает и отслеживает соединители Azure SQL Microsoft SQL Graph. Он дополняет общий процесс установки и показывает инструкции, применимые только к соединители Azure SQL и Microsoft SQL Graph. В этой статье также [](#limitations) содержатся сведения об ограничениях для сервера Microsoft SQL и соединители Azure SQL.

## <a name="before-you-get-started"></a>Перед началом работы

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Установка агента соединителя Graph (требуется только для локального соединителя SQL microsoft)

Чтобы получить доступ к локальной сторонней информации, необходимо установить и настроить агент соединителя Graph. Дополнительные дополнительные данные см. в [дополнительных подробной](on-prem-agent.md) информации об установке агента соединителя Graph.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Шаг 1. Добавление соединителю Graph в центре администрирования Microsoft 365

Следуйте общим [инструкциям установки](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Шаг 2. Имя подключения

Следуйте общим [инструкциям установки](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Шаг 3. Настройка параметров подключения

### <a name="register-an-app-for-azure-sql-connector-only"></a>Регистрация приложения (только SQL Azure)

Для соедините SQL Azure необходимо зарегистрировать приложение в Azure Active Directory, чтобы позволить приложению Microsoft Search получать доступ к данным для индексации. Чтобы узнать больше о регистрации приложения, обратитесь к документации Microsoft Graph о том, как [зарегистрировать приложение.](https://docs.microsoft.com/graph/auth-register-app-v2)

После завершения регистрации приложения и с учетом имени приложения, имени приложения (клиента) и ИД клиента необходимо создать [новый секрет клиента.](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret) Секрет клиента будет отображаться только один раз. Помните, & хранить секрет клиента надежно. Используйте ID клиента и секрет клиента при настройке нового подключения в Microsoft Search.

Чтобы добавить зарегистрированное приложение в базу данных Azure SQL, необходимо:

- Войдите в DB SQL Azure
- Откройте новое окно запроса
- Создание нового пользователя с помощью команды 'CREATE USER [имя приложения] ОТ ВНЕШНЕГО ПОСТАВЩИКА'
- Добавление пользователя в роль, запуская команду "exec sp_addrolemember db_datareader", [имя приложения]" или "ALTER ROLE db_datareader ADD MEMBER [имя приложения]"

>[!NOTE]
>Чтобы отослать доступ к любому приложению, зарегистрированным в Azure Active Directory, перенапослать документацию Azure об удалении [зарегистрированного приложения.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Параметры подключения

Чтобы подключить соединители SQL Microsoft к источнику данных, необходимо настроить сервер базы данных, который необходимо пройти, и агент на преме. Затем вы можете подключиться к базе данных с помощью требуемого метода проверки подлинности.

> [!NOTE] 
> Ваша база данных должна работать SQL версии 2008 или более поздней версии для подключения SQL microsoft SQL сервера.

Для соединитетеля SQL Azure необходимо указать только имя сервера или IP-адрес, к который необходимо подключиться. Соедините SQL Azure поддерживает проверку подлинности Azure Active Directory Open ID connect (OIDC) для подключения к базе данных.

Для обеспечения безопасности можно настроить правила брандмауэра IP для SQL или базы данных Azure. Чтобы узнать больше о настройке правил брандмауэра IP, обратитесь к документации по [правилам брандмауэра IP.](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure) Добавьте следующие диапазоны IP-адресов клиента в параметры брандмауэра.

| Region | Диапазон IP |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Для поиска контента базы данных необходимо указать SQL запросы при настройке соединители. В SQL запросы необходимо назвать все столбцы баз данных, которые необходимо индексировать (то есть исходные свойства), включая все SQL, которые необходимо выполнить для получения всех столбцов. Чтобы ограничить доступ к результатам поиска, при настройке соединителя необходимо указать списки управления доступом (ACLs) SQL запросов.

## <a name="step-3a-full-crawl-required"></a>Шаг 3a. Полный обход (обязательно)

На этом шаге настраивается SQL запрос, который выполняет полный обход базы данных. Полный обход выбирает все столбцы или свойства, в которых необходимо выбрать **параметры Запрос,** **Поиск** или **Извлечение.** Также можно указать столбцы ACL, чтобы ограничить доступ к результатам поиска определенным пользователям или группам.

> [!Tip]
> Чтобы получить все необходимые столбцы, можно присоединиться к нескольким таблицам.

![Сценарий, показывающий свойства OrderTable и AclTable с примерами](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Выбор столбцов данных (обязательно) и столбцов ACL (необязательный)

В этом примере демонстрируется выбор пяти столбцов данных, которые удерживают данные для поиска: OrderId, OrderTitle, OrderDesc, CreatedDateTime и IsDeleted. Чтобы установить разрешения представления для каждого ряда данных, можно дополнительно выбрать эти столбцы ACL: AllowedUsers, AllowedGroups, DeniedUsers и DeniedGroups. Все эти столбцы данных также имеют параметры **Запрос,** **Поиск** или **Извлечение**.

Выберите столбцы данных, как показано в этом примере запроса: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Чтобы управлять доступом к результатам поиска, в запросе можно указать один или несколько столбцов ACL. Соединитель SQL позволяет управлять доступом на уровне записи. Вы можете выбрать один и тот же контроль доступа для всех записей в таблице. Если сведения ACL хранятся в отдельной таблице, может потребоваться присоединиться к этим таблицам в запросе.

Ниже описано использование каждого из столбцов ACL в приведенной выше области запроса. В следующем списке рассказывается о четырех **механизмах управления доступом.**

- **AllowedUsers.** В этом столбце указан список пользовательских ИД, которые могут получить доступ к результатам поиска. В следующем примере список пользователей: john@contoso.com, keith@contoso.com и lisa@contoso.com будут иметь доступ только к записи с orderId = 12.
- **AllowedGroups.** В этом столбце указывается группа пользователей, которые смогут получить доступ к результатам поиска. В следующем примере группа sales-team@contoso.com будет иметь доступ к записи только с OrderId = 12.
- **DeniedUsers.** В этом столбце указан  список пользователей, которые не имеют доступа к результатам поиска. В следующем примере пользователи john@contoso.com и keith@contoso.com не имеют доступа к записи с OrderId = 13, в то время как все остальные имеют доступ к этой записи.
- **DeniedGroups.** В этом столбце указывается  группа пользователей, у которых нет доступа к результатам поиска. В следующем примере группы engg-team@contoso.com и pm-team@contoso.com не имеют доступа к записи с OrderId = 15, в то время как все остальные имеют доступ к этой записи.  

![Пример данных, показывающих свойства OrderTable и AclTable с примерными свойствами](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Поддерживаемые типы данных

В приведенной ниже таблице SQL типы данных, поддерживаемые в соединитчиках MS SQL Azure SQL Azure. В таблице также кратко приводится тип индексации данных для поддерживаемого SQL типа данных. Дополнительные сведения о соединители Microsoft Graph, поддерживаемые типами данных для индексации, переслать документацию по [типам ресурсов свойств.](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)

| Category | Тип исходных данных | Тип индексации данных |
| ------------ | ------------ | ------------ |
| дата и время; | date <br> datetime <br> datetime2 <br> smalldatetime | datetime |
| Точные числимые | bigint <br> int <br> smallint <br> tinyint | int64 |
| Точные числимые | bit | boolean |
| Примерная числовая | float <br> real | double |
| Строка символов | char <br> varchar <br> text | string |
| Строки символов Юникод | nchar <br> nvarchar <br> ntext | string |
| Другие типы данных | uniqueidentifier | string |

Для любого другого типа данных, который в настоящее время не поддерживается напрямую, столбец должен быть явно отлит в поддерживаемый тип данных.

### <a name="watermark-required"></a>Водяной знак (обязательно)

Чтобы предотвратить перегрузку базы данных, соединители пакеты и возобновляют запросы полного обхода с помощью столбца водяного знака полного обхода. Используя значение столбца водяного знака, каждая последующая партия получается, и запрос возобновляется с последней контрольной точки. По сути, эти механизмы контролируют обновление данных для полного обхода.

Создание фрагментов запросов для водяных знаков, как показано в этих примерах:

- `WHERE (CreatedDateTime > @watermark)`. Приведи имя столбца водяного знака с зарезервированным ключевым словом `@watermark` . Если порядок сортировки столбца водяных знаков возрастает, `>` используйте; в противном случае используйте `<` .
- `ORDER BY CreatedDateTime ASC`. Сортировка на столбце водяного знака в порядке подъема или убывания.

В конфигурации, показанной на следующем изображении, `CreatedDateTime` находится выбранный столбец водяного знака. Чтобы получить первую партию строк, укажите тип данных столбца водяного знака. В этом случае тип данных `DateTime` .

![Конфигурация столбца водяного знака](media/MSSQL-watermark.png)

Первый запрос получает первое число строк **N** с помощью: "CreatedDateTime > 1 января 1753 г. 00:00:00" (min value of DateTime data type). После получения первой партии максимальное значение возвращается в пакете в качестве контрольной точки, если строки сортироваться в порядке `CreatedDateTime` восходящей. Пример: 1 марта 2019 г. 03:00:00. Затем следующая партия **строк N** извлекается с помощью "CreatedDateTime > 1 марта 2019 г. 03:00:00" в запросе.

### <a name="skipping-soft-deleted-rows-optional"></a>Пропуск строк с мягким удалением (необязательный)

Чтобы исключить из индексации мягкие удаленные строки в базе данных, укажите имя и значение столбца с мягким удалением, указывав на удаление строки.

![Мягкие параметры удаления: "Мягкий столбец удаления" и "Значение столбца мягкого удаления, которое указывает на удаленную строку"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Полный обход: управление разрешениями поиска

Выберите **управление разрешениями** для выбора столбцов управления доступом (ACL), которые указывают механизм управления доступом. Выберите имя столбца, указанное в полном запросе SQL обхода.

Ожидается, что каждый из столбцов ACL будет иметь несколько значений. Эти несколько значений ID могут быть разделены сепараторами, такими как ;), запятая и так далее. Этот сепаратор необходимо указать в поле **сепаратора** значений.

Следующие типы ID поддерживаются для использования в качестве acLs:

- **Имя основного пользователя (UPN).** Имя пользователя —имя пользователя в формате адресов электронной почты. UpN (например: john.doe@domain.com) состоит из имени пользователя (имя логотипа), сепаратора (символ @) и доменного имени (суффикс UPN).
- **Azure Active Directory (AAD) ID.** В Azure AD каждый пользователь или группа имеет объектный ИД, который выглядит как 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'.
- Идентификатор безопасности **Active Directory (AD).** В локальной установке AD каждый пользователь и группа имеют уникальный идентификатор безопасности, похожий на S-1-1-5-21-3878594291-2115959936-132693609-65242.'

![Параметры разрешений поиска для настройки списков управления доступом](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Шаг 3b. Дополнительный обход (необязательный)

На этом необязательный шаг SQL запрос для выполнения дополнительного обхода базы данных. С помощью этого запроса соединитель SQL определяет любые изменения в данных после последнего инкрементного обхода. Как и в полном обходе, выберите все столбцы, в которых необходимо выбрать **параметры Запрос,** **Поиск** или **Извлечение**. Укажите тот же набор столбцов ACL, который указан в полном запросе обхода.

Компоненты на следующем изображении напоминают компоненты полного обхода с одним исключением. В этом случае выбран столбец водяного знака "ModifiedDateTime". Просмотрите [все этапы обхода,](#step-3a-full-crawl-required) чтобы узнать, как написать дополнительный запрос обхода, и в качестве примера см. следующее изображение.

![Дополнительный сценарий обхода, показывающий свойства OrderTable, AclTable и примеры, которые можно использовать.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Шаг 4. Назначение меток свойств

Следуйте общим [инструкциям установки](https://docs.microsoft.com/microsoftsearch/configure-connector).

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Шаг 5. Управление схемой

Следуйте общим [инструкциям установки](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Шаг 6. Управление разрешениями на поиск

Вы можете использовать [acLs,](#full-crawl-manage-search-permissions) указанные на экране полного обхода, или переопределять их, чтобы сделать содержимое видимым для всех.

## <a name="step-7-choose-refresh-settings"></a>Шаг 7. Выбор параметров обновления

Следуйте общим [инструкциям установки](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Шаг 8. Просмотр подключения

Следуйте общим [инструкциям установки](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

<!---## Troubleshooting-->

<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Ограничения

Соединители SQL имеют эти ограничения в выпуске предварительного просмотра:

- Соедините SQL Microsoft: локальной базе данных необходимо запустить SQL версии сервера 2008 или более поздней версии.
- Подписка на M365 и подписка Azure (SQL база данных Azure) должны лежать в том же Azure Active Directory.
- AcLs поддерживаются только с помощью основного имени пользователя (UPN), Azure Active Directory (Azure AD) или active Directory Security.
- Индексация богатого контента внутри столбцов баз данных не поддерживается. Примерами такого контента являются HTML, JSON, XML, blobs и размыва документов, которые существуют в качестве ссылок внутри столбцов базы данных.
