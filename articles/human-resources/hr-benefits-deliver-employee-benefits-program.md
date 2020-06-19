---
title: Utveckla förmånsprogram för medarbetare
description: Den här artikeln visar hur du skapar förmånselement som ska användas när du skapar en ny förmån.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitElementSetup, HcmBenefit, HcmBenefitNewBenefit, HcmBenefitPlanLookup, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: cc02346ebccd04f2b4f6fc7029717a8793d75e0d
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430864"
---
# <a name="deliver-employee-benefits-program"></a><span data-ttu-id="a0580-103">Utveckla förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="a0580-103">Deliver employee benefits program</span></span>

<span data-ttu-id="a0580-104">Den här artikeln visar hur du skapar förmånselement som ska användas när du skapar en ny förmån.</span><span class="sxs-lookup"><span data-stu-id="a0580-104">This article shows you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="a0580-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="a0580-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="a0580-106">Denna uppgift är avsedd för kompensations- och förmånsansvariga.</span><span class="sxs-lookup"><span data-stu-id="a0580-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="a0580-107">Skapa förmånselement</span><span class="sxs-lookup"><span data-stu-id="a0580-107">Create benefit elements</span></span>
1. <span data-ttu-id="a0580-108">Denna uppgift börjar från förmånslistsidan.</span><span class="sxs-lookup"><span data-stu-id="a0580-108">This task starts from the Benefits list page.</span></span> <span data-ttu-id="a0580-109">Starta uppgiften genom att öppna sidan eller att söka efter förmånslistsidan.</span><span class="sxs-lookup"><span data-stu-id="a0580-109">Start the task by opening that page or searching the Benefits list page.</span></span>
2. <span data-ttu-id="a0580-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0580-110">Click New.</span></span>
3. <span data-ttu-id="a0580-111">Ange namnet typen av förmån som du skapar i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="a0580-111">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="a0580-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a0580-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a0580-113">Markera ett alternativ i fältet Samtidig anmälan.</span><span class="sxs-lookup"><span data-stu-id="a0580-113">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="a0580-114">Välj En anmälan per typ om du vill begränsa medarbetarnas möjlighet att anmäla sig till flera sjukförsäkringsplaner.</span><span class="sxs-lookup"><span data-stu-id="a0580-114">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="a0580-115">Välj ett alternativ i fältet Lönekategori.</span><span class="sxs-lookup"><span data-stu-id="a0580-115">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="a0580-116">Klicka på fliken Planer.</span><span class="sxs-lookup"><span data-stu-id="a0580-116">Click the Plans tab.</span></span>
8. <span data-ttu-id="a0580-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0580-117">Click New.</span></span>
9. <span data-ttu-id="a0580-118">Ange ett värde i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="a0580-118">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="a0580-119">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a0580-119">In the Description field, type a value.</span></span>
11. <span data-ttu-id="a0580-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="a0580-120">In the Type field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="a0580-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="a0580-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a0580-123">Välj ett alternativ i fältet Effekt på lön.</span><span class="sxs-lookup"><span data-stu-id="a0580-123">In the Payroll impact field, select an option.</span></span>
15. <span data-ttu-id="a0580-124">Klicka på fliken Alternativ.</span><span class="sxs-lookup"><span data-stu-id="a0580-124">Click the Options tab.</span></span>
16. <span data-ttu-id="a0580-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0580-125">Click New.</span></span>
17. <span data-ttu-id="a0580-126">Ange ett värde i fältet Alternativ.</span><span class="sxs-lookup"><span data-stu-id="a0580-126">In the Option field, type a value.</span></span>
18. <span data-ttu-id="a0580-127">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a0580-127">In the Description field, type a value.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="a0580-128">Skapa en förmån</span><span class="sxs-lookup"><span data-stu-id="a0580-128">Create a benefit</span></span>
1. <span data-ttu-id="a0580-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a0580-129">Close the page.</span></span>
2. <span data-ttu-id="a0580-130">Gå till Personal > Förmåner > Förmåner.</span><span class="sxs-lookup"><span data-stu-id="a0580-130">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="a0580-131">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a0580-131">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="a0580-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="a0580-132">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a0580-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-133">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="a0580-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a0580-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Alternativ.</span><span class="sxs-lookup"><span data-stu-id="a0580-135">In the Option field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a0580-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-136">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="a0580-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-137">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="a0580-138">Ange datum och tid i fältet Giltighet.</span><span class="sxs-lookup"><span data-stu-id="a0580-138">In the Effective field, enter a date and time.</span></span>
11. <span data-ttu-id="a0580-139">Klicka på Skapa förmån.</span><span class="sxs-lookup"><span data-stu-id="a0580-139">Click Create benefit.</span></span>
12. <span data-ttu-id="a0580-140">Växla utökningen av avsnittet Löneuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a0580-140">Toggle the expansion of the Payroll details section.</span></span>
13. <span data-ttu-id="a0580-141">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frekvens.</span><span class="sxs-lookup"><span data-stu-id="a0580-141">In the Frequency field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="a0580-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-142">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="a0580-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a0580-143">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="a0580-144">Markera ett alternativ i fältet Bas.</span><span class="sxs-lookup"><span data-stu-id="a0580-144">In the Basis field, select an option.</span></span>
17. <span data-ttu-id="a0580-145">Ange ett tal i fältet Belopp eller tariff.</span><span class="sxs-lookup"><span data-stu-id="a0580-145">In the Amount or rate field, enter a number.</span></span>

