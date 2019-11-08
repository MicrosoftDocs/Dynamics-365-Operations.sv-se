---
title: Underhållsschema
description: I det här avsnittet beskrivs underhållsschema i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fab21d6f3a1b7386d304ece6ebf3b93cdc0c504d
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570017"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="b1b1f-103">Underhållsschema</span><span class="sxs-lookup"><span data-stu-id="b1b1f-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b1b1f-104">Underhållsschemat innehåller en lista över alla förväntade förebyggande underhållsplaner, underhållsbegäranden och underhållsomgångar som ska utföras. Vissa schemarader kan ha konverterats till arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="b1b1f-105">De fyra vyerna för underhållsscheman skiljer sig något beroende på vilka underhållsschemarader du vill se.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="b1b1f-106">Menyalternativ</span><span class="sxs-lookup"><span data-stu-id="b1b1f-106">Menu item</span></span>                  | <span data-ttu-id="b1b1f-107">Beskrivning av innehåll</span><span class="sxs-lookup"><span data-stu-id="b1b1f-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b1b1f-108">Alla underhållsscheman</span><span class="sxs-lookup"><span data-stu-id="b1b1f-108">All maintenance schedule</span></span>       | <span data-ttu-id="b1b1f-109">Alla underhållsschemarader visas.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="b1b1f-110">Min tidsplan för tillgången</span><span class="sxs-lookup"><span data-stu-id="b1b1f-110">My asset schedule</span></span>        | <span data-ttu-id="b1b1f-111">Alla underhållsschemarader innehåller tillgångar som är installerade på funktionsplatser som du är relaterad till som arbetare (ställs in i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md)) som visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="b1b1f-112">Öppna rader för underhållsschema</span><span class="sxs-lookup"><span data-stu-id="b1b1f-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="b1b1f-113">Underhållsschemarader med status "Skapad" – innebär att de ännu inte har konverterats till en arbetsorder eller kasserats – visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="b1b1f-114">Öppna pooler för underhållsschema</span><span class="sxs-lookup"><span data-stu-id="b1b1f-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="b1b1f-115">Underhållsschemarader som hör till en arbetsorderpool visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="b1b1f-116">Om en underhållsschemarad ingår i flera arbetsorderpooler (se [Arbetsorderpooler](../work-orders/work-order-pools.md)) visas en post för varje pool i **Öppna pooler för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="b1b1f-117">Detta görs för att optimera filtreringsalternativen för arbetsorderpooler.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="b1b1f-118">Öppna ett underhållsschema:</span><span class="sxs-lookup"><span data-stu-id="b1b1f-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="b1b1f-119">Klicka på **Tillgångshantering** > **Allmänt** > **Underhållsschema** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="b1b1f-120">Om du vill uppdatera underhållsschemat klickar du på **Underhållsplan** eller **Underhållsomgång**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="b1b1f-121">Du kan redigera en underhållsschemarad genom att markera den och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="b1b1f-122">Du kan till exempel enkelt uppdatera servicenivån eller den arbetare som är ansvarig för jobbet.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="b1b1f-123">Du kan bara redigera underhållsschemarader som ännu inte har kopplats till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="b1b1f-124">Du kan ta bort en underhållsschemarad genom att markera den på listsidan och klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="b1b1f-125">Du kan ignorera en underhållsschemarad genom att markera den på listsidan och klicka på **Ignorera**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="b1b1f-126">Den här funktionen är användbar om till exempel en tillgång har en underhållsplan på 2 000 km och en underhållsplan på 10 000 km.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="b1b1f-127">Sedan vill du kanske ignorera den rad som har skapats från underhållsplanen för 2 000 km när den sammanfaller med 10 000 km, 20 000 km, 30 000 km och så vidare.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="b1b1f-128">Om du tar bort en underhållsschemarad som är relaterad till en underhållsplan kommer den raden aldrig att visas när underhållsplanen planeras.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="b1b1f-129">Du kan välja ett antal underhållsschemarader i **Alla underhållsplaner** och klicka på **Arbetsorderpool** om du vill att alla valda rader ska inkluderas i samma pool för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="b1b1f-130">Du kan välja ett antal underhållsschemarader i **Alla underhållsscheman** eller **Öppna underhållsschemarader** eller **Öppna pooler för underhållsschema** och klicka på **Justera schema** om du vill göra samma justeringar på flera rader.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="b1b1f-131">Du kan ändra förväntade start- och slutdatum, servicenivå och den ansvariga underhållsarbetargruppen eller ansvariga underhållsarbetaren relaterad till de valda underhållsschemaraderna.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="b1b1f-132">När en underhållsschemarad har relaterats till en arbetsorder visas arbetsorder-ID:t i fältet **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="b1b1f-133">I informationsvyn **Alla tillgångar** > snabbfliken **Underhållsplaner för tillgångar** kan du välja underhållsplaner för till gången.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="b1b1f-134">Om du senare tar bort en underhållsplanrad som är relaterad till en tillgång i **Alla tillgångar** tar du också automatiskt bort alla underhållsschemarader med status "Skapat" som har skapats baserat på den underhållsplanen.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="b1b1f-135">Se även [Skapa en tillgång](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="b1b1f-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="b1b1f-136">På bilden nedan visas listsidan **Alla underhållsscheman**.</span><span class="sxs-lookup"><span data-stu-id="b1b1f-136">The illustration below shows the **All maintenance schedule** list page.</span></span>

![Figur 1](media/16-preventive-maintenance.png)

