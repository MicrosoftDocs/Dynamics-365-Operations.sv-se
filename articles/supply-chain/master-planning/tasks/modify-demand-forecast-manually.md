--- 
title: "Ändra en efterfrågeprognos manuellt"
description: "I den här proceduren visas hur du ändrar prognosen för en artikel."
author: ShylaThompson
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 72080dc7782320e82a3eabf7498c816495721b2d
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="7a75a-103">Ändra en efterfrågeprognos manuellt</span><span class="sxs-lookup"><span data-stu-id="7a75a-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a75a-104">I den här proceduren visas hur du ändrar prognosen för en artikel.</span><span class="sxs-lookup"><span data-stu-id="7a75a-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="7a75a-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="7a75a-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7a75a-106">Registreringen är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="7a75a-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="7a75a-107">Ändra en prognos för en artikel</span><span class="sxs-lookup"><span data-stu-id="7a75a-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="7a75a-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="7a75a-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="7a75a-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7a75a-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7a75a-110">Välj den artikel om du vill ändra prognosen för.</span><span class="sxs-lookup"><span data-stu-id="7a75a-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="7a75a-111">Du kan till exempel välja artikel D0001.</span><span class="sxs-lookup"><span data-stu-id="7a75a-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="7a75a-112">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7a75a-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="7a75a-113">Klicka på Efterfrågeprognos.</span><span class="sxs-lookup"><span data-stu-id="7a75a-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="7a75a-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="7a75a-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7a75a-115">Om det inte finns några rader för inköpsprognoser, skapa en ny rad genom att</span><span class="sxs-lookup"><span data-stu-id="7a75a-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="7a75a-116">klicka på Ny i appfältet.</span><span class="sxs-lookup"><span data-stu-id="7a75a-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="7a75a-117">Ange ett nummer i fältet Försäljningskvantitet.</span><span class="sxs-lookup"><span data-stu-id="7a75a-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="7a75a-118">Det här numret representerar den prognosticerade kvantiteten för artikeln.</span><span class="sxs-lookup"><span data-stu-id="7a75a-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="7a75a-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7a75a-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="7a75a-120">Ändra prognosen i Excel</span><span class="sxs-lookup"><span data-stu-id="7a75a-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="7a75a-121">Klicka på Öppna i Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7a75a-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="7a75a-122">Klicka på Redigera en efterfrågeprognos i Excel.</span><span class="sxs-lookup"><span data-stu-id="7a75a-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="7a75a-123">I Excel kan du lägga till, ta bort och redigera efterfrågeprognosrader.</span><span class="sxs-lookup"><span data-stu-id="7a75a-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="7a75a-124">Om du inte kan se data i Excel måste du logga in i Microsoft Dynamics 365 for Finance and Operations med alternativet "Håll mig inloggad" aktiverat och du måste lita på dataanslutningsappen.</span><span class="sxs-lookup"><span data-stu-id="7a75a-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  


