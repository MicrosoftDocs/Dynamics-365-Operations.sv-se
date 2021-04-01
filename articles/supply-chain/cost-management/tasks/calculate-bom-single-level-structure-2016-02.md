---
title: Beräkna en strukturlista med en enda nivå (februari 2016)
description: Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda en enda nedbrytningsnivå som baseras på arket för kostnadsredovisning.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c370c623c29f2b2f3b65ffbd65aabbc941be3cb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239480"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="475e3-103">Beräkna en strukturlista med en enda nivå (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="475e3-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="475e3-104">Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda en enda nedbrytningsnivå som baseras på arket för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="475e3-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="475e3-105">Detta är den fjärde uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="475e3-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="475e3-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="475e3-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="475e3-107">Gå till Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="475e3-107">Go to Released products.</span></span>
2. <span data-ttu-id="475e3-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="475e3-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="475e3-109">Välj produkten BOM_1.</span><span class="sxs-lookup"><span data-stu-id="475e3-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="475e3-110">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="475e3-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="475e3-111">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="475e3-111">Click Item price.</span></span>
5. <span data-ttu-id="475e3-112">Klicka på Beräkna artikelkostnad.</span><span class="sxs-lookup"><span data-stu-id="475e3-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="475e3-113">Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="475e3-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="475e3-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kostnadsredovisningsversion.</span><span class="sxs-lookup"><span data-stu-id="475e3-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="475e3-115">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="475e3-115">For this demo, select 10.</span></span> <span data-ttu-id="475e3-116">Detta är samma kostnadsversion som används för att lägga till självkostnaden för komponenter.</span><span class="sxs-lookup"><span data-stu-id="475e3-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="475e3-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="475e3-117">Click OK.</span></span>
8. <span data-ttu-id="475e3-118">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="475e3-118">Click View calculation details.</span></span>
    * <span data-ttu-id="475e3-119">Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="475e3-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="475e3-120">Här följer sammansättningen av kostnaden:  \*    10 härleds från  ITEM_A, 10 från ITEM_B, 10 from BOM_2.</span><span class="sxs-lookup"><span data-stu-id="475e3-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="475e3-121">I det här fallet finns ingen information för BOM_2 eftersom denna har registrerats som en standardkostnad på 10, men inte beräkningen.</span><span class="sxs-lookup"><span data-stu-id="475e3-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="475e3-122">\*    7 härleds från ställtiden, som är en konstant kostnad, och ytterligare 7 härleds från körningen (Process).</span><span class="sxs-lookup"><span data-stu-id="475e3-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="475e3-123">\*    Det finns också andra belopp som motsvarar indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="475e3-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="475e3-124">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="475e3-124">@SysTaskRecorder:_RequestClose</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]