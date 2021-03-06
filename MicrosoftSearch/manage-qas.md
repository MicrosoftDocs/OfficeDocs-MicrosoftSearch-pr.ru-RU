---
title: Управление вопросами и ответами
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Поиск и обновление ответов по отдельности или использование доступных средств поиска Microsoft для одновременного редактирования&Q.
ms.openlocfilehash: 2a8b0727ef3540a35d617cf6c8bae7b0d99767a8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47423003"
---
# <a name="manage-qas"></a>Управление вопросами и ответами

Создание вопросов и ответов похоже на создание закладок. Q&, что позволяет отвечать на вопросы пользователя, а не только для ссылки на веб-страницу. Вы также можете отформатировать ответ в формате форматированного текста. Если закладка и Q&A используют одно и то же ключевое слово, сначала отображается результат закладки. Как и закладки,&Q обновляется сразу после добавления или изменения Q&A.

## <a name="add-or-edit-a-single-qa"></a>Добавление и изменение одного вопроса с ответом

1. В [центре администрирования Microsoft 365](https://admin.microsoft.com)откройте раздел [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Чтобы добавить Q&а, нажмите кнопку **Добавить**.
Чтобы изменить вопрос и ответ, выберите вопрос и ответ в соответствующем списке. При добавлении или изменении сведений предварительное изображение автоматически обновляется.
1. Сохраните изменения.

### <a name="supported-html-tags"></a>Поддерживаемые теги HTML

В ответе (описании) можно использовать существующее HTML-содержимое или добавлять теги HTML. Неподдерживаемые теги игнорируются.

Поддерживаются следующие HTML-теги:

- blockquote
- div
- em
- h1, h2, h3 и h4
- ol, ul и li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th и td
- u
- a
- code
- br
- hr
- img

## <a name="add-or-edit-qas-using-browser-extensions"></a>Добавление и редактирование&Q с использованием расширений браузера

Администраторы поиска могут легко создавать контент поиска, используя расширения браузеров. Установите расширение браузера, а затем перейдите на сайт, с которого нужно создать Q&A. Затем можно создать Q&A и включить ссылку на исходный сайт.

В настоящее время расширения браузера доступны для Microsoft EDGE и Chrome.

- Чтобы скачать расширения для пограничной (устаревшей версии), перейдите в [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Чтобы скачать расширения Chrome или EDGE (Чромиум), перейдите в [веб-магазин Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Массовое добавление и изменение вопросов и ответов

Администраторы могут использовать функции импорта и экспорта для массового создания или редактирования Q&как.

С помощью функции импорта и экспорта можно:

- Выполните массовое добавление&Q с добавлением сведений в файл Q&шаблона, а затем импортируйте его.
- Массовое изменение Q&AS-Export Q&как в CSV-файл, измените Q&сведения в экспортированном файле, а затем импортируйте файл.
- Выполните резервное копирование Q&AS-Export Q&как CSV-файл.

Чтобы импортировать или экспортировать Q&как:

1. В правом верхнем углу вкладки вопросов и ответов выберите пункт **Импорт**.
Выберите пункт **Экспорт** , чтобы скачать все существующие&Q как в CSV-файле.
1. В правой области выберите параметр для импорта с помощью CSV-файла. Скачайте файл шаблона, чтобы получить список обязательных полей и сведений.
1. Добавьте или измените Q&сведения в файле шаблона и сохраните его на своем компьютере.
1. В области **Импорт Q&A** нажмите кнопку **Обзор**, а затем выберите CSV-файл, который требуется импортировать.
1. Нажмите кнопку **Импорт**.

Важные советы по файлам шаблонов:

- Никогда не изменяйте данные в следующих полях: **Id**, **Last Modified** и **Last Modified By**.
- Если добавить **идентификатор** существующей закладки, он будет заменен сведениями из файла импорта.
- Если у вас есть закладка с таким же названием или URL-адресом, закладка будет обновлена данными из файла импорта.
- Не все поля в файле шаблона являются обязательными, а обязательные поля зависят от состояния закладки.
- В зависимости от поля **состояние** закладки сохраняются как *Черновики*, *предложенные*или *запланированные*или автоматически публикуются.
- Для партнеров, которые управляют несколькими организациями: вы можете экспортировать свои закладки из одной организации и импортировать их в другую. Но перед импортом нужно удалить данные в столбце **Id**.

> [!NOTE]
> Вы не можете импортировать Q&так, как если бы в файле шаблона возникли ошибки. Чтобы избежать ошибок, убедитесь, что файл импорта правильно отформатирован, и включите все необходимые сведения.

Для получения дополнительных сведений об устранении ошибок обратитесь к разделу [предотвращение ошибок импорта](manage-bookmarks.md#prevent-import-errors).
