---
title: Ställ in befattningar
description: Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmWorkforceWorkspace, HcmWorkerActivityChart, HcmAllWorkersListPart, HcmPosition, HcmPositionNewPosition, HcmJobLookup, HcmPositionReportsToDialog, HcmPositionLookup, FinancialDimensionDefaultTemplatesLookup, DimensionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cefab1101ff2dc9800342831443f1a7994701e8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051795"
---
# <a name="set-up-positions"></a><span data-ttu-id="1120f-103">Ställ in befattningar</span><span class="sxs-lookup"><span data-stu-id="1120f-103">Set up positions</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="1120f-104">Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1120f-104">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="1120f-105">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="1120f-105">A position is an individual instance of a job.</span></span> <span data-ttu-id="1120f-106">Befattningen "Försäljningschef (öst)" är exempelvis bara en de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="1120f-106">For example, the position, “Sales manager (East),” is one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="1120f-107">En befattning finns på en avdelning och kan ha endast har en arbetare associerad med den.</span><span class="sxs-lookup"><span data-stu-id="1120f-107">A position exists in a department and may have only one worker associated with it.</span></span> <span data-ttu-id="1120f-108">I den här uppgiften ska du gå igenom de steg som behövs för att skapa en befattning.</span><span class="sxs-lookup"><span data-stu-id="1120f-108">In this task we will walk through the steps required to create a position.</span></span> <span data-ttu-id="1120f-109">Uppgiften är avsedd för en personalresursspecialist.</span><span class="sxs-lookup"><span data-stu-id="1120f-109">This procedure is intended for Human Resources Specialists.</span></span>

1. <span data-ttu-id="1120f-110">Klicka på Personalhantering.</span><span class="sxs-lookup"><span data-stu-id="1120f-110">Click Workforce management.</span></span>
2. <span data-ttu-id="1120f-111">Klicka på Lediga befattningar.</span><span class="sxs-lookup"><span data-stu-id="1120f-111">Click Open positions.</span></span>
3. <span data-ttu-id="1120f-112">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1120f-112">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="1120f-113">Ange eller välj ett värde i fältet Jobb.</span><span class="sxs-lookup"><span data-stu-id="1120f-113">In the Job field, enter or select a value.</span></span>
    * <span data-ttu-id="1120f-114">Jobbeskrivningen, titeln och heltidsanställningsfaktorn kopieras automatiskt från det valda jobbet till befattningen.</span><span class="sxs-lookup"><span data-stu-id="1120f-114">The Job description, title, and full-time equivalent employment factor are automatically copied from the selected job into the position.</span></span>  
5. <span data-ttu-id="1120f-115">ResolveChanges jobbet.</span><span class="sxs-lookup"><span data-stu-id="1120f-115">ResolveChanges the Job.</span></span>
6. <span data-ttu-id="1120f-116">Klicka på Skapa befattning.</span><span class="sxs-lookup"><span data-stu-id="1120f-116">Click Create position.</span></span>
7. <span data-ttu-id="1120f-117">Ange eller välj ett värde i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="1120f-117">In the Department field, enter or select a value.</span></span>
8. <span data-ttu-id="1120f-118">Ange eller välj ett värde i fältet Befattningstyp.</span><span class="sxs-lookup"><span data-stu-id="1120f-118">In the Position type field, enter or select a value.</span></span>
9. <span data-ttu-id="1120f-119">Ange eller välj ett värde i fältet Kompensationsregion.</span><span class="sxs-lookup"><span data-stu-id="1120f-119">In the Compensation region field, enter or select a value.</span></span>
    * <span data-ttu-id="1120f-120">Fältet Kompensationsregion bestämmer reglerna för kompensationberättigande och de fasta ökningsbudgeterna som gäller för en medarbetare i den befattningen.</span><span class="sxs-lookup"><span data-stu-id="1120f-120">The Compensation region field determines the compensation eligibility rules and fixed increase budgets that apply to an employee in that position.</span></span>  
10. <span data-ttu-id="1120f-121">Ange datum och tid i fältet Tillgänglig för tilldelning.</span><span class="sxs-lookup"><span data-stu-id="1120f-121">In the Available for assignment field, enter a date and time.</span></span>
11. <span data-ttu-id="1120f-122">Visa avsnittet Befattningstidslängd.</span><span class="sxs-lookup"><span data-stu-id="1120f-122">Expand the Position duration section.</span></span>
    * <span data-ttu-id="1120f-123">Befattningvaraktighet anges som standard utifrån aktivering och avyttringsdatum som har angetts tidigare</span><span class="sxs-lookup"><span data-stu-id="1120f-123">Position duration is entered by default based on activation and retirement dates entered earlier</span></span>  
12. <span data-ttu-id="1120f-124">Expandera avsnittet Rapporter till befattning.</span><span class="sxs-lookup"><span data-stu-id="1120f-124">Expand the Reports to position section.</span></span>
    * <span data-ttu-id="1120f-125">När du tilldelar en anställd till en befattning som rapporterar till en annan befattning, skapar du en direktrapporteringsrelation mellan arbetarna som tilldelas de två befattningarna.</span><span class="sxs-lookup"><span data-stu-id="1120f-125">When you assign a worker to a position that reports to another position, you create a direct reporting relationship between the workers who are assigned to the two positions.</span></span>  
13. <span data-ttu-id="1120f-126">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1120f-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="1120f-127">I fältet Rapporter till fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="1120f-127">In the Reports to field, enter or select a value.</span></span>
15. <span data-ttu-id="1120f-128">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="1120f-128">Click Create.</span></span>
16. <span data-ttu-id="1120f-129">Visa avsnittet Arbetartilldelning.</span><span class="sxs-lookup"><span data-stu-id="1120f-129">Expand the Worker assignment section.</span></span>
17. <span data-ttu-id="1120f-130">Utöka avsnittet Relationer.</span><span class="sxs-lookup"><span data-stu-id="1120f-130">Expand the Relationships section.</span></span>
    * <span data-ttu-id="1120f-131">Om din organisation använder en matrishierarki eller en annan anpassad hierarki, kan du ställa in befattninghierarkityper, och sedan lägga till rapporteringrelationer till befattningar för varje hierarkityp som du ställer in.</span><span class="sxs-lookup"><span data-stu-id="1120f-131">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span>  
18. <span data-ttu-id="1120f-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="1120f-132">Click Add.</span></span>
19. <span data-ttu-id="1120f-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="1120f-133">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="1120f-134">I fältet Hierarkinamn, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="1120f-134">In the Hierarchy name field, enter or select a value.</span></span>
21. <span data-ttu-id="1120f-135">I fältet Rapporter till befattning, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="1120f-135">In the Reports to position field, enter or select a value.</span></span>
22. <span data-ttu-id="1120f-136">Visa avsnittet Lön.</span><span class="sxs-lookup"><span data-stu-id="1120f-136">Expand the Payroll section.</span></span>
23. <span data-ttu-id="1120f-137">Ange eller välj ett värde i fältet Lönecykel.</span><span class="sxs-lookup"><span data-stu-id="1120f-137">In the Pay cycle field, enter or select a value.</span></span>
24. <span data-ttu-id="1120f-138">Ange eller välj ett värde i fältet Betald av.</span><span class="sxs-lookup"><span data-stu-id="1120f-138">In the Paid by field, enter or select a value.</span></span>
25. <span data-ttu-id="1120f-139">Ange en siffra i fältet Ordinarie timmar per år.</span><span class="sxs-lookup"><span data-stu-id="1120f-139">In the Annual regular hours field, enter a number.</span></span>
    * <span data-ttu-id="1120f-140">Detta är antalet regelbundet betalda timmar som arbetare med den här befattningen förväntas att arbeta varje år.</span><span class="sxs-lookup"><span data-stu-id="1120f-140">This is the number of regularly paid hours that the worker in this position is expected to work each year.</span></span>  
26. <span data-ttu-id="1120f-141">Visa avsnittet Fackförening.</span><span class="sxs-lookup"><span data-stu-id="1120f-141">Expand the Labor union section.</span></span>
27. <span data-ttu-id="1120f-142">Dölj avsnittet Fackförening.</span><span class="sxs-lookup"><span data-stu-id="1120f-142">Collapse the Labor union section.</span></span>
28. <span data-ttu-id="1120f-143">Expandera avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="1120f-143">Expand the Financial dimensions section.</span></span>
29. <span data-ttu-id="1120f-144">Ange eller välj ett värde i fältet Fördelningsmall.</span><span class="sxs-lookup"><span data-stu-id="1120f-144">In the Distribution template field, enter or select a value.</span></span>
30. <span data-ttu-id="1120f-145">Ange eller välj ett värde i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="1120f-145">In the Department field, enter or select a value.</span></span>
31. <span data-ttu-id="1120f-146">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1120f-146">Click Save.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]