---
title: Ställ in momskvittningsperioder
description: Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms.
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "326203"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="95e17-103">Ställ in momskvittningsperioder</span><span class="sxs-lookup"><span data-stu-id="95e17-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="95e17-104">Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms.</span><span class="sxs-lookup"><span data-stu-id="95e17-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="95e17-105">En kvittningprocess kan köras för en kvittningsperiod för ett specifikt datumintervall.</span><span class="sxs-lookup"><span data-stu-id="95e17-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="95e17-106">Alla momskoder som är kopplade till kvittningsperioden kvittas.</span><span class="sxs-lookup"><span data-stu-id="95e17-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="95e17-107">Beroende på inställningen av den relaterade skattemyndigheten bokförs skatteskulden antingen till en leverantör eller ett redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="95e17-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="95e17-108">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="95e17-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="95e17-109">Gå till Moms > Indirekt moms > Moms > Momskvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="95e17-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="95e17-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="95e17-110">Click New.</span></span>
3. <span data-ttu-id="95e17-111">I fältet Kvittningsperiod, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="95e17-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="95e17-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="95e17-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="95e17-113">I fältet Myndighet väljer du skattekontoret som tar emot rapporter och betalningar som skapats för kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="95e17-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="95e17-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="95e17-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="95e17-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="95e17-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="95e17-116">I fältet Betalningsvillkor, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="95e17-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="95e17-117">Den relaterade skattemyndigheten kan ställas in som en leverantör och vid momskvittningen skapas en öppen leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="95e17-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="95e17-118">Förfallodatumet för den öppna leverantörsfakturan definieras i betalningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="95e17-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="95e17-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="95e17-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="95e17-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="95e17-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="95e17-121">Välj en typ av kvittningsperiodintervall.</span><span class="sxs-lookup"><span data-stu-id="95e17-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="95e17-122">Ange antalet periodintervallenheter per period.</span><span class="sxs-lookup"><span data-stu-id="95e17-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="95e17-123">Till exempel har ett kvartal 3 månader.</span><span class="sxs-lookup"><span data-stu-id="95e17-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="95e17-124">Markera eller avmarkera kryssrutan Använd batchbearbetning för momskvittning.</span><span class="sxs-lookup"><span data-stu-id="95e17-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="95e17-125">Kvittningprocessen för kvittningsperioden kan behandlas som batchjobb i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="95e17-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="95e17-126">Detta rekommenderas för ett stort antal momstransaktioner inom ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="95e17-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="95e17-127">Markera eller avmarkera kryssrutan Förhindra att motbokade momstransaktioner genereras.</span><span class="sxs-lookup"><span data-stu-id="95e17-127">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="95e17-128">Som standard genereras motbokade momstransaktioner under kvittningsprocessen som kan orsaka prestandaproblem om det finns ett stort antal momstransaktioner inom ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="95e17-128">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="95e17-129">Markera denna kryssruta för att förhindra att motbokade momstransaktioner genereras.</span><span class="sxs-lookup"><span data-stu-id="95e17-129">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="95e17-130">Expandera periodintervallfliken.</span><span class="sxs-lookup"><span data-stu-id="95e17-130">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="95e17-131">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="95e17-131">Click Add.</span></span>
17. <span data-ttu-id="95e17-132">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="95e17-132">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="95e17-133">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="95e17-133">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="95e17-134">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="95e17-134">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="95e17-135">Klicka på Nytt periodintervall.</span><span class="sxs-lookup"><span data-stu-id="95e17-135">Click New period interval.</span></span>
    * <span data-ttu-id="95e17-136">När det första periodintervallet har angetts, kan nya perioder skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="95e17-136">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="95e17-137">Du kan komma tillbaka och lägga till nya periodintervall som krävs.</span><span class="sxs-lookup"><span data-stu-id="95e17-137">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="95e17-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="95e17-138">Close the page.</span></span>

