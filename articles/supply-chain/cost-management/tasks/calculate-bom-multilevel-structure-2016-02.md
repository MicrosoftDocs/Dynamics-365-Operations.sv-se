---
title: Beräkna en strukturlista genom att använda en enda nivå (februari 2016)
description: Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda flera olika nedbrytningsnivåer baserade på arket för kostnadsredovisning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0834baf42ed6aa10acec6529513e44ff52ab754
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845652"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a><span data-ttu-id="e282f-103">Beräkna en strukturlista genom att använda en enda nivå (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="e282f-103">Calculate a BOM by using a multilevel structure (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e282f-104">Denna procedur beskriver hur du beräknar kostnaden för en färdig produkt genom att använda flera olika nedbrytningsnivåer baserade på arket för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="e282f-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="e282f-105">Detta är den sjunde uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="e282f-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="e282f-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="e282f-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="e282f-107">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="e282f-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="e282f-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e282f-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e282f-109">Välj produkten BOM_1.</span><span class="sxs-lookup"><span data-stu-id="e282f-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="e282f-110">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e282f-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="e282f-111">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="e282f-111">Click Item price.</span></span>
5. <span data-ttu-id="e282f-112">Klicka på Beräkna artikelkostnad.</span><span class="sxs-lookup"><span data-stu-id="e282f-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="e282f-113">Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="e282f-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="e282f-114">Ange eller välj ett värde i fältet Kostnadsredovisningsversion.</span><span class="sxs-lookup"><span data-stu-id="e282f-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="e282f-115">Välj kostnadsredovisningsversion 20, detta eftersom kostnadstypen är planerad och nedbrytningsläget är multinivå.</span><span class="sxs-lookup"><span data-stu-id="e282f-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="e282f-116">Nedbrytningsläget multinivå gäller för planerade kostnader och simuleringar.</span><span class="sxs-lookup"><span data-stu-id="e282f-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="e282f-117">Det används inte för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="e282f-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="e282f-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e282f-118">Click OK.</span></span>
8. <span data-ttu-id="e282f-119">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e282f-119">Click View calculation details.</span></span>
    * <span data-ttu-id="e282f-120">Du kan behöva klicka på ellipsen (...) om du vill se det här alternativet i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="e282f-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="e282f-121">I detta fall, notera hur BOM_2 har beräknats med hänsyn till råmaterial, bearbetning och omkostnader med totalt 29,40 i stället för standardkostnaden 10, som aktiverades i den inledande uppgiftsguiden i denna serie.</span><span class="sxs-lookup"><span data-stu-id="e282f-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="e282f-122">Klicka på fliken för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="e282f-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="e282f-123">I fliken för kostnadsredovisning varierar summorna per kostnadsgrupp jämfört med den beräkning som utförts i föregående uppgiftsguide.</span><span class="sxs-lookup"><span data-stu-id="e282f-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="e282f-124">Välj "Multi" i nivåfältet.</span><span class="sxs-lookup"><span data-stu-id="e282f-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="e282f-125">När du väljer multi klassificeras flera kostnader i enlighet med sammansättningen av BOM_2, där 10 härleds från kostnadsgruppen M1 (ITEM_C) och 15,60 härleds från tillverkningen, där kostnadsgruppen är L2.</span><span class="sxs-lookup"><span data-stu-id="e282f-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="e282f-126">Indirekta kostnader kan också variera.</span><span class="sxs-lookup"><span data-stu-id="e282f-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="e282f-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e282f-127">Close the page.</span></span>
12. <span data-ttu-id="e282f-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e282f-128">Close the page.</span></span>

