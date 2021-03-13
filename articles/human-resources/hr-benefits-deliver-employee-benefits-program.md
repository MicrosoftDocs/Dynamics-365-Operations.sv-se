---
title: Utveckla förmånsprogram för medarbetare
description: Den här artikeln visar hur du skapar förmånselement som ska användas när du skapar en ny förmån.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitElementSetup, HcmBenefit, HcmBenefitNewBenefit, HcmBenefitPlanLookup, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 8fe53b28d1e2ff539cf431a2a6a00b10d1adb06f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114264"
---
# <a name="deliver-employee-benefits-program"></a><span data-ttu-id="854e1-103">Utveckla förmånsprogram för medarbetare</span><span class="sxs-lookup"><span data-stu-id="854e1-103">Deliver employee benefits program</span></span>

<span data-ttu-id="854e1-104">Den här artikeln visar hur du skapar förmånselement som ska användas när du skapar en ny förmån.</span><span class="sxs-lookup"><span data-stu-id="854e1-104">This article shows you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="854e1-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="854e1-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="854e1-106">Denna uppgift är avsedd för kompensations- och förmånsansvariga.</span><span class="sxs-lookup"><span data-stu-id="854e1-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="854e1-107">Skapa förmånselement</span><span class="sxs-lookup"><span data-stu-id="854e1-107">Create benefit elements</span></span>
1. <span data-ttu-id="854e1-108">Denna uppgift börjar från förmånslistsidan.</span><span class="sxs-lookup"><span data-stu-id="854e1-108">This task starts from the Benefits list page.</span></span> <span data-ttu-id="854e1-109">Starta uppgiften genom att öppna sidan eller att söka efter förmånslistsidan.</span><span class="sxs-lookup"><span data-stu-id="854e1-109">Start the task by opening that page or searching the Benefits list page.</span></span>
2. <span data-ttu-id="854e1-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="854e1-110">Click New.</span></span>
3. <span data-ttu-id="854e1-111">Ange namnet typen av förmån som du skapar i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="854e1-111">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="854e1-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="854e1-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="854e1-113">Markera ett alternativ i fältet Samtidig anmälan.</span><span class="sxs-lookup"><span data-stu-id="854e1-113">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="854e1-114">Välj En anmälan per typ om du vill begränsa medarbetarnas möjlighet att anmäla sig till flera sjukförsäkringsplaner.</span><span class="sxs-lookup"><span data-stu-id="854e1-114">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="854e1-115">Välj ett alternativ i fältet Lönekategori.</span><span class="sxs-lookup"><span data-stu-id="854e1-115">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="854e1-116">Klicka på fliken Planer.</span><span class="sxs-lookup"><span data-stu-id="854e1-116">Click the Plans tab.</span></span>
8. <span data-ttu-id="854e1-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="854e1-117">Click New.</span></span>
9. <span data-ttu-id="854e1-118">Ange ett värde i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="854e1-118">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="854e1-119">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="854e1-119">In the Description field, type a value.</span></span>
11. <span data-ttu-id="854e1-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="854e1-120">In the Type field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="854e1-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="854e1-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="854e1-123">Välj ett alternativ i fältet Effekt på lön.</span><span class="sxs-lookup"><span data-stu-id="854e1-123">In the Payroll impact field, select an option.</span></span>
15. <span data-ttu-id="854e1-124">Klicka på fliken Alternativ.</span><span class="sxs-lookup"><span data-stu-id="854e1-124">Click the Options tab.</span></span>
16. <span data-ttu-id="854e1-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="854e1-125">Click New.</span></span>
17. <span data-ttu-id="854e1-126">Ange ett värde i fältet Alternativ.</span><span class="sxs-lookup"><span data-stu-id="854e1-126">In the Option field, type a value.</span></span>
18. <span data-ttu-id="854e1-127">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="854e1-127">In the Description field, type a value.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="854e1-128">Skapa en förmån</span><span class="sxs-lookup"><span data-stu-id="854e1-128">Create a benefit</span></span>
1. <span data-ttu-id="854e1-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="854e1-129">Close the page.</span></span>
2. <span data-ttu-id="854e1-130">Gå till Personal > Förmåner > Förmåner.</span><span class="sxs-lookup"><span data-stu-id="854e1-130">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="854e1-131">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="854e1-131">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="854e1-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="854e1-132">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="854e1-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-133">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="854e1-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="854e1-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Alternativ.</span><span class="sxs-lookup"><span data-stu-id="854e1-135">In the Option field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="854e1-136">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-136">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="854e1-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-137">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="854e1-138">Ange datum och tid i fältet Giltighet.</span><span class="sxs-lookup"><span data-stu-id="854e1-138">In the Effective field, enter a date and time.</span></span>
11. <span data-ttu-id="854e1-139">Klicka på Skapa förmån.</span><span class="sxs-lookup"><span data-stu-id="854e1-139">Click Create benefit.</span></span>
12. <span data-ttu-id="854e1-140">Växla utökningen av avsnittet Löneuppgifter.</span><span class="sxs-lookup"><span data-stu-id="854e1-140">Toggle the expansion of the Payroll details section.</span></span>
13. <span data-ttu-id="854e1-141">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frekvens.</span><span class="sxs-lookup"><span data-stu-id="854e1-141">In the Frequency field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="854e1-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-142">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="854e1-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="854e1-143">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="854e1-144">Markera ett alternativ i fältet Bas.</span><span class="sxs-lookup"><span data-stu-id="854e1-144">In the Basis field, select an option.</span></span>
17. <span data-ttu-id="854e1-145">Ange ett tal i fältet Belopp eller tariff.</span><span class="sxs-lookup"><span data-stu-id="854e1-145">In the Amount or rate field, enter a number.</span></span>

