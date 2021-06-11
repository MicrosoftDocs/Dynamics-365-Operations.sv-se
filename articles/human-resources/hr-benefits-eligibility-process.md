---
title: Bearbeta förmånsberättigande
description: Den här proceduren visar hur förmånsberättigandeprocessen fungerar.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 9d5ea8e1255c91c930685f84b9f9f76b03da192d
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053091"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="7d2c5-103">Bearbeta förmånsberättigande</span><span class="sxs-lookup"><span data-stu-id="7d2c5-103">Benefit eligibility process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7d2c5-104">Den här proceduren visar hur förmånsberättigandeprocessen fungerar.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="7d2c5-105">När processen är klar kan du visa resultaten.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="7d2c5-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7d2c5-107">Gå till Personal > Förmåner > Förmåner.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="7d2c5-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7d2c5-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7d2c5-110">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-110">Click Edit.</span></span>
5. <span data-ttu-id="7d2c5-111">Välj Regelbaserad i fältet Berättigande.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="7d2c5-112">I fältet Regeltyp, välj förmånpolicyregeln du vill tillämpa för förmånen.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="7d2c5-113">Klicka på Förmån i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="7d2c5-114">Klicka på Skapa berättigandehändelse om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="7d2c5-115">I fältet Händelse, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="7d2c5-116">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="7d2c5-117">I fältet Händelsetyp, välj Öppna anmälan.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="7d2c5-118">Ange datum och tid i fältet Giltighetsstartdatum.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="7d2c5-119">I fältet Startdatum för anmälningsperiod, ange datum och tid.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="7d2c5-120">I fältet Dagar till anmälan, ange ett nummer.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="7d2c5-121">Klicka på Skapa händelse.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-121">Click Create event.</span></span>
16. <span data-ttu-id="7d2c5-122">Klicka på Lägg till på snabbfliken Arbetare.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="7d2c5-123">I fältet Visa per typ, välj Medarbetare.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="7d2c5-124">I fältet Visa per juridisk person, välj Aktuell juridisk person.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="7d2c5-125">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="7d2c5-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-126">Click OK.</span></span>
21. <span data-ttu-id="7d2c5-127">Klicka på Process.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-127">Click Process.</span></span>
22. <span data-ttu-id="7d2c5-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-128">Click OK.</span></span>
23. <span data-ttu-id="7d2c5-129">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-129">Refresh the page.</span></span>
24. <span data-ttu-id="7d2c5-130">Klicka på Visa resultat.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-130">Click Show results.</span></span>
25. <span data-ttu-id="7d2c5-131">Öppna kolumnfiltret Status.</span><span class="sxs-lookup"><span data-stu-id="7d2c5-131">Open Status column filter.</span></span>
26. <span data-ttu-id="7d2c5-132">Sortera A till Z</span><span class="sxs-lookup"><span data-stu-id="7d2c5-132">Sort A to Z</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]