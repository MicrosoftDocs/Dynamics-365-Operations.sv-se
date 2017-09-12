--- 
title: "Ställ in momskvittningsperioder"
description: "Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4d65dee3bd059966458cb9603807de85b704fc49
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="5db46-103">Ställ in momskvittningsperioder</span><span class="sxs-lookup"><span data-stu-id="5db46-103">Set up sales tax settlement periods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5db46-104">Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms.</span><span class="sxs-lookup"><span data-stu-id="5db46-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="5db46-105">En kvittningprocess kan köras för en kvittningsperiod för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="5db46-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="5db46-106">Alla momskoder som är kopplade till kvittningsperioden kvittas.</span><span class="sxs-lookup"><span data-stu-id="5db46-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="5db46-107">Beroende på inställningen av den relaterade skattemyndigheten bokförs skatteskulden antingen till en leverantör eller ett redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="5db46-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="5db46-108">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5db46-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="5db46-109">Gå till Moms > Indirekt moms > Moms > Momskvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="5db46-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="5db46-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5db46-110">Click New.</span></span>
3. <span data-ttu-id="5db46-111">I fältet Kvittningsperiod, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="5db46-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="5db46-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5db46-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5db46-113">I fältet Myndighet väljer du skattekontoret som tar emot rapporter och betalningar som skapats för kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="5db46-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="5db46-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5db46-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5db46-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5db46-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5db46-116">I fältet Betalningsvillkor, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="5db46-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5db46-117">Den relaterade skattemyndigheten kan ställas in som en leverantör och vid momskvittningen skapas en öppen leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="5db46-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="5db46-118">Förfallodatumet för den öppna leverantörsfakturan definieras i betalningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="5db46-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="5db46-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5db46-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="5db46-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5db46-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="5db46-121">Välj en typ av kvittningsperiodintervall.</span><span class="sxs-lookup"><span data-stu-id="5db46-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="5db46-122">Ange antalet periodintervallenheter per period.</span><span class="sxs-lookup"><span data-stu-id="5db46-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="5db46-123">Till exempel har ett kvartal 3 månader.</span><span class="sxs-lookup"><span data-stu-id="5db46-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="5db46-124">Markera eller avmarkera kryssrutan Använd batchbearbetning för momskvittning.</span><span class="sxs-lookup"><span data-stu-id="5db46-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="5db46-125">Kvittningprocessen för kvittningsperioden kan behandlas som batchjobb i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="5db46-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="5db46-126">Detta rekommenderas för ett stort antal momstransaktioner inom ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="5db46-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="5db46-127">Expandera periodintervallfliken.</span><span class="sxs-lookup"><span data-stu-id="5db46-127">Expand the Period intervals tab.</span></span>
15. <span data-ttu-id="5db46-128">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5db46-128">Click Add.</span></span>
16. <span data-ttu-id="5db46-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5db46-129">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="5db46-130">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="5db46-130">In the From date field, enter a date.</span></span>
18. <span data-ttu-id="5db46-131">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="5db46-131">In the To date field, enter a date.</span></span>
19. <span data-ttu-id="5db46-132">Klicka på Nytt periodintervall.</span><span class="sxs-lookup"><span data-stu-id="5db46-132">Click New period interval.</span></span>
    * <span data-ttu-id="5db46-133">När det första periodintervallet har angetts, kan nya perioder skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5db46-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="5db46-134">Du kan komma tillbaka och lägga till nya periodintervall som krävs.</span><span class="sxs-lookup"><span data-stu-id="5db46-134">You can come back and add new period intervals as required.</span></span>  
20. <span data-ttu-id="5db46-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5db46-135">Close the page.</span></span>


