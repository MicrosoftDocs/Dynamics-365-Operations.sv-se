---
title: Registrera och ta bort förmåner för arbetare
description: I den här proceduren visas hur en enskild anställd kan omfattas av en eller flera förmåner, samt flera anställd kan omfattas av en förmån.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmWorkerEnrollment, HcmBenefitByEligibilityLookup, HcmMassBenefitEnrollment, HcmBenefitLookup, HcmMassBenefitEnrollmentResults
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32f0e641f5e6824df89112aa5ea21dc3a708efa0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "341866"
---
# <a name="enroll-and-remove-benefits-from-workers"></a><span data-ttu-id="240b9-103">Registrera och ta bort förmåner för arbetare</span><span class="sxs-lookup"><span data-stu-id="240b9-103">Enroll and remove benefits from workers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="240b9-104">I den här proceduren visas hur en enskild anställd kan omfattas av en eller flera förmåner, samt flera anställd kan omfattas av en förmån.</span><span class="sxs-lookup"><span data-stu-id="240b9-104">This procedure demonstrates how a single worker can be enrolled in one or more benefits, as well as multiple workers can be enrolled in a benefit.</span></span> <span data-ttu-id="240b9-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="240b9-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="enroll-a-single-worker-in-benefits"></a><span data-ttu-id="240b9-106">Anmäl en enstaka medarbetare till förmåner</span><span class="sxs-lookup"><span data-stu-id="240b9-106">Enroll a single worker in benefits</span></span>
1. <span data-ttu-id="240b9-107">Gå till Personal > Arbetare > Medarbetare</span><span class="sxs-lookup"><span data-stu-id="240b9-107">Go to Human resources > Workers > Employees</span></span>
2. <span data-ttu-id="240b9-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="240b9-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="240b9-109">Klicka på Förmåner.</span><span class="sxs-lookup"><span data-stu-id="240b9-109">Click Benefits.</span></span>
4. <span data-ttu-id="240b9-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="240b9-110">Click New.</span></span>
5. <span data-ttu-id="240b9-111">Ange eller välj ett värde i fältet Förmån.</span><span class="sxs-lookup"><span data-stu-id="240b9-111">In the Benefit field, enter or select a value.</span></span>
6. <span data-ttu-id="240b9-112">Ange datum och tid i fältet Giltighetsstartdatum.</span><span class="sxs-lookup"><span data-stu-id="240b9-112">In the Coverage start date field, enter a date and time.</span></span>
7. <span data-ttu-id="240b9-113">Ange datum och tid i fältet Giltighetsslutdatum.</span><span class="sxs-lookup"><span data-stu-id="240b9-113">In the Coverage end date field, enter a date and time.</span></span>
8. <span data-ttu-id="240b9-114">Expandera avsnittet Mottagare om mottagare ska läggas till i förmånen.</span><span class="sxs-lookup"><span data-stu-id="240b9-114">Expand the Beneficiaries section if beneficiaries need to be added to the benefit.</span></span> <span data-ttu-id="240b9-115">Du kan också lägga till beroenden från den här sidan, om det behövs för förmånen.</span><span class="sxs-lookup"><span data-stu-id="240b9-115">You can also add dependents from this page if applicable to the benefit.</span></span>
9. <span data-ttu-id="240b9-116">Du kan också redigera informationen om en förmånsregistrering och ta bort en registrering på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="240b9-116">You can also edit the details of a benefit enrollment or delete an enrollment on this page.</span></span> <span data-ttu-id="240b9-117">När du är klar med ändringarna av förmånregistreringen, stängs sidan.</span><span class="sxs-lookup"><span data-stu-id="240b9-117">When you have finished making changes to the benefit enrollment, close the page.</span></span>

## <a name="enroll-multiple-workers-in-a-benefit"></a><span data-ttu-id="240b9-118">Anmäl flera arbetare till en förmån</span><span class="sxs-lookup"><span data-stu-id="240b9-118">Enroll multiple workers in a benefit</span></span>
1. <span data-ttu-id="240b9-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="240b9-119">Close the page.</span></span>
2. <span data-ttu-id="240b9-120">Gå till Personal > Arbetare > Medarbetare</span><span class="sxs-lookup"><span data-stu-id="240b9-120">Go to Human resources > Workers > Employees</span></span>
3. <span data-ttu-id="240b9-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="240b9-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="240b9-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="240b9-122">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="240b9-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="240b9-123">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="240b9-124">Klicka på Anmälan för förmån.</span><span class="sxs-lookup"><span data-stu-id="240b9-124">Click Enroll in benefits.</span></span>
7. <span data-ttu-id="240b9-125">Ange eller välj ett värde i fältet Förmån.</span><span class="sxs-lookup"><span data-stu-id="240b9-125">In the Benefit field, enter or select a value.</span></span>
8. <span data-ttu-id="240b9-126">Ange datum och tid i fältet Giltighetsstartdatum.</span><span class="sxs-lookup"><span data-stu-id="240b9-126">In the Coverage start date field, enter a date and time.</span></span>
9. <span data-ttu-id="240b9-127">Ange datum och tid i fältet Giltighetsslutdatum.</span><span class="sxs-lookup"><span data-stu-id="240b9-127">In the Coverage end date field, enter a date and time.</span></span>
10. <span data-ttu-id="240b9-128">Klicka på Anmäl.</span><span class="sxs-lookup"><span data-stu-id="240b9-128">Click Enroll.</span></span>
11. <span data-ttu-id="240b9-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="240b9-129">Close the page.</span></span>
12. <span data-ttu-id="240b9-130">Gå till Personal > Förmåner > Anmälning > Resultat från förmånsanmälan</span><span class="sxs-lookup"><span data-stu-id="240b9-130">Go to Human Resources > Benefits > Enrollment > Benefit enrollment results</span></span>
13. <span data-ttu-id="240b9-131">Hitta förmånresultatsposten du söker efter.</span><span class="sxs-lookup"><span data-stu-id="240b9-131">Find the benefit results record that you are looking for.</span></span>
14. <span data-ttu-id="240b9-132">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="240b9-132">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="240b9-133">På den här sidan kan du visa vilka medarbetare som har anmälts till förmånen, samt vilka medarbetare som inte har anmälts.</span><span class="sxs-lookup"><span data-stu-id="240b9-133">This page allows you to view which employees have been enrolled in the benefit, as well as any employees who were not enrolled.</span></span>

