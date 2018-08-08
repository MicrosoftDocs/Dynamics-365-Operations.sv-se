--- 
title: "Beräkna en strukturlista genom att använda en enda nivå (enbart februari 2016)"
description: "Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda en enda nedbrytningsnivå som baseras på arket för kostnadsredovisning."
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1def2baf6a42ae4f8d117b4c06f402397b83bf88
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a><span data-ttu-id="25105-103">Beräkna en strukturlista genom att använda en enda nivå (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="25105-103">Calculate a BOM by using a single level structure (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25105-104">Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda en enda nedbrytningsnivå som baseras på arket för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="25105-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="25105-105">Detta är den fjärde uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="25105-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="25105-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="25105-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="25105-107">Gå till Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="25105-107">Go to Released products.</span></span>
2. <span data-ttu-id="25105-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="25105-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25105-109">Välj produkten BOM_1.</span><span class="sxs-lookup"><span data-stu-id="25105-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="25105-110">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="25105-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="25105-111">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="25105-111">Click Item price.</span></span>
5. <span data-ttu-id="25105-112">Klicka på Beräkna artikelkostnad.</span><span class="sxs-lookup"><span data-stu-id="25105-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="25105-113">Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="25105-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="25105-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kostnadsredovisningsversion.</span><span class="sxs-lookup"><span data-stu-id="25105-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="25105-115">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="25105-115">For this demo, select 10.</span></span> <span data-ttu-id="25105-116">Detta är samma kostnadsversion som används för att lägga till självkostnaden för komponenter.</span><span class="sxs-lookup"><span data-stu-id="25105-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="25105-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="25105-117">Click OK.</span></span>
8. <span data-ttu-id="25105-118">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="25105-118">Click View calculation details.</span></span>
    * <span data-ttu-id="25105-119">Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="25105-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="25105-120">Här följer sammansättningen av kostnaden: • 10 härleds från  ITEM_A, 10 från ITEM_B, 10 from BOM_2.</span><span class="sxs-lookup"><span data-stu-id="25105-120">Here's the composition of the cost:  •    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="25105-121">I det här fallet finns ingen information för BOM_2 eftersom denna har registrerats som en standardkostnad på 10, men inte beräkningen.</span><span class="sxs-lookup"><span data-stu-id="25105-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="25105-122">•  7 härleds från ställtiden, som är en konstant kostnad, och ytterligare 7 härleds från körningen (Process).</span><span class="sxs-lookup"><span data-stu-id="25105-122">•  7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="25105-123">•  Det finns också andra belopp som motsvarar indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="25105-123">•   There are also other amounts that correspond to indirect costs.</span></span>  
9. @SysTaskRecorder:_RequestClose


