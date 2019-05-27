---
title: Skapa omallokering av artiklar för kort plockning
description: I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf56a0811c4793ee2e3eaf78c8696c3c29e984c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560847"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="977d2-103">Skapa omallokering av artiklar för kort plockning</span><span class="sxs-lookup"><span data-stu-id="977d2-103">Set up short picking item reallocation</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="977d2-104">I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.</span><span class="sxs-lookup"><span data-stu-id="977d2-104">This procedure shows you how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> <span data-ttu-id="977d2-105">Det går att använda en automatisk omallokeringsprocess som använder platsdirektiv för att hämta varorna, om dessa är tillgängliga på en annan plats.</span><span class="sxs-lookup"><span data-stu-id="977d2-105">It’s possible to use an automatic re-allocation process, which uses location directives to retrieve the goods if they’re available at another location.</span></span> <span data-ttu-id="977d2-106">Alternativt visas, när den manuella omallokeringen används, en lista över platserna med den tillgängliga kvantiteten på den mobila enheten, vilket gör det möjligt för lagerställearbetaren att välja vilken plats lagret ska användas från.</span><span class="sxs-lookup"><span data-stu-id="977d2-106">Alternatively, when manual re-allocation is used, a list of the locations with the available quantity is shown on the mobile device, allowing the warehouse worker to choose which location to use inventory from.</span></span> <span data-ttu-id="977d2-107">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="977d2-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="977d2-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="977d2-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-work-exceptions"></a><span data-ttu-id="977d2-109">Konfigurera arbetsavvikelser</span><span class="sxs-lookup"><span data-stu-id="977d2-109">Set up work exceptions</span></span>
1. <span data-ttu-id="977d2-110">Gå till Lagerstyrning > Inställningar > Arbete > Arbetsavvikelser.</span><span class="sxs-lookup"><span data-stu-id="977d2-110">Go to Warehouse management > Setup > Work > Work exceptions.</span></span>
2. <span data-ttu-id="977d2-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="977d2-111">Click New.</span></span>
    * <span data-ttu-id="977d2-112">Det går att definiera flera arbetsundantag med olika artikelomallokeringspolicyer om du vill göra det möjligt för lagerarbetare att välja en baserat på behoven hos den försändelse som de bearbetar.</span><span class="sxs-lookup"><span data-stu-id="977d2-112">It’s possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>  
3. <span data-ttu-id="977d2-113">Ange ett värde i fältet Work exception code.</span><span class="sxs-lookup"><span data-stu-id="977d2-113">In the Work exception code field, type a value.</span></span>
    * <span data-ttu-id="977d2-114">Ge arbetsundantaget en rubrik för att ange vad den används för.</span><span class="sxs-lookup"><span data-stu-id="977d2-114">Give the work exception a title to indicate what it’s used for.</span></span> <span data-ttu-id="977d2-115">Till exempel "Kortplockning manuellt".</span><span class="sxs-lookup"><span data-stu-id="977d2-115">For example, Short picking manual.</span></span>  
4. <span data-ttu-id="977d2-116">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="977d2-116">In the Description field, type a value.</span></span>
5. <span data-ttu-id="977d2-117">Välj "Short pick" i fältet Exception type.</span><span class="sxs-lookup"><span data-stu-id="977d2-117">In the Exception type field, select 'Short pick'.</span></span>
6. <span data-ttu-id="977d2-118">Välj kryssrutan Adjust inventory.</span><span class="sxs-lookup"><span data-stu-id="977d2-118">Select the Adjust inventory check box.</span></span>
    * <span data-ttu-id="977d2-119">Detta alternativ innebär att lagret justeras automatiskt till 0 på en kort plockad plats.</span><span class="sxs-lookup"><span data-stu-id="977d2-119">This option means that inventory will automatically be adjusted to 0 at the short picked location.</span></span>  
7. <span data-ttu-id="977d2-120">Ange eller välj ett värde i fältet Default adjustment type code.</span><span class="sxs-lookup"><span data-stu-id="977d2-120">In the Default adjustment type code field, enter or select a value.</span></span>
    * <span data-ttu-id="977d2-121">I USMF kan du till exempel välja "Remove Res Adj Out".</span><span class="sxs-lookup"><span data-stu-id="977d2-121">For example, in USMF you can select 'Remove Res Adj Out'.</span></span>  
8. <span data-ttu-id="977d2-122">Välj "Manual" i fältet Item reallocation.</span><span class="sxs-lookup"><span data-stu-id="977d2-122">In the Item reallocation field, select 'Manual'.</span></span>
    * <span data-ttu-id="977d2-123">Om du väljer manuellt, eller automatiskt och manuellt, måste lagerställearbetaren auktoriseras för att använda manuell omallokering.</span><span class="sxs-lookup"><span data-stu-id="977d2-123">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="977d2-124">Ställ in en arbetare som ska använda manuell artikelomallokering</span><span class="sxs-lookup"><span data-stu-id="977d2-124">Set up a worker to use manual item reallocation</span></span>
1. <span data-ttu-id="977d2-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="977d2-125">Close the page.</span></span>
2. <span data-ttu-id="977d2-126">Gå till Lagerstyrning > Inställningar > Arbetare.</span><span class="sxs-lookup"><span data-stu-id="977d2-126">Go to Warehouse management > Setup > Worker.</span></span>
3. <span data-ttu-id="977d2-127">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="977d2-127">Click Edit.</span></span>
4. <span data-ttu-id="977d2-128">I listan väljer du worker 24.</span><span class="sxs-lookup"><span data-stu-id="977d2-128">In the list, select worker 24.</span></span>
5. <span data-ttu-id="977d2-129">Expandera avsnittet Work.</span><span class="sxs-lookup"><span data-stu-id="977d2-129">Expand the Work section.</span></span>
6. <span data-ttu-id="977d2-130">Välj Yes i fältet Allow manual item reallocation.</span><span class="sxs-lookup"><span data-stu-id="977d2-130">Select Yes in the Allow manual item reallocation field.</span></span>

