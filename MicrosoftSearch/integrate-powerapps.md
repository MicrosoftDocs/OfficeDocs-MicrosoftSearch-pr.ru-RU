---
title: Интеграция PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Включение приложений на основе браузера в закладки результатов для поиска Microsoft
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379139"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="c1cf9-103">Интеграция PowerApps</span><span class="sxs-lookup"><span data-stu-id="c1cf9-103">Integrate PowerApps</span></span>

<span data-ttu-id="c1cf9-p101">Помочь пользователям выполнения задач, таких как ввод времени отпуска или отчетности расходы благодаря интеграции существующих PowerApps закладок. Встроенная PowerApps отобразиться в течение результатов закладку, устраняя необходимость перехода на другой сайт или для открытия отдельное средство, какие сохраняет время и силы.</span><span class="sxs-lookup"><span data-stu-id="c1cf9-p101">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks. Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="c1cf9-106">Что такое PowerApps?</span><span class="sxs-lookup"><span data-stu-id="c1cf9-106">What are PowerApps?</span></span>

<span data-ttu-id="c1cf9-p102">PowerApps — это служба, которая позволяет создавать бизнес-приложений, на которых выполняется в браузере или на телефоне или планшетном ПК с без написания кода взаимодействия требуется. Подробнее:</span><span class="sxs-lookup"><span data-stu-id="c1cf9-p102">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required. Learn more:</span></span>
  
- [<span data-ttu-id="c1cf9-109">Обучение под руководством инструктора</span><span class="sxs-lookup"><span data-stu-id="c1cf9-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="c1cf9-110">Документы</span><span class="sxs-lookup"><span data-stu-id="c1cf9-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="c1cf9-111">Добавление PowerApp закладку</span><span class="sxs-lookup"><span data-stu-id="c1cf9-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="c1cf9-112">PowerApps работать в любом браузере и на любом устройстве и выполните менее минуты для добавления.</span><span class="sxs-lookup"><span data-stu-id="c1cf9-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="c1cf9-113">[Найдите идентификатор приложения для PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) , который требуется интегрировать</span><span class="sxs-lookup"><span data-stu-id="c1cf9-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="c1cf9-114">На портале Microsoft SearchAdmin перейдите к **закладки**</span><span class="sxs-lookup"><span data-stu-id="c1cf9-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="c1cf9-115">Добавление закладку и найдите существующую закладку, который вы хотите добавить PowerApp для</span><span class="sxs-lookup"><span data-stu-id="c1cf9-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="c1cf9-116">В диалоговом окне закладку настройки нажмите кнопку **Power приложения**и нажмите кнопку **Добавить приложение Power**</span><span class="sxs-lookup"><span data-stu-id="c1cf9-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="c1cf9-117">Введите или вставьте код приложения</span><span class="sxs-lookup"><span data-stu-id="c1cf9-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="c1cf9-p103">Высота и ширина, автоматически добавляются. Закладки может поддерживать книжная или альбомная ориентации, но в настоящее время не может изменить размер.</span><span class="sxs-lookup"><span data-stu-id="c1cf9-p103">The height and width are automatically added. Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="c1cf9-120">Просмотр закладку показывает, как будет выглядеть PowerApp в результате закладку</span><span class="sxs-lookup"><span data-stu-id="c1cf9-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="c1cf9-121">Для упрощения их тестирования и использовать функционирует PowerApp в области предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="c1cf9-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="c1cf9-122">Нажмите кнопку **Опубликовать**</span><span class="sxs-lookup"><span data-stu-id="c1cf9-122">Click **Publish**</span></span>
    
<span data-ttu-id="c1cf9-123">При авторизованного пользователя Microsoft Search поиска в Bing для каких-либо закладки ключевые слова или зарезервированные ключевые слова, PowerApp будут отображаться в результате закладка.</span><span class="sxs-lookup"><span data-stu-id="c1cf9-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

