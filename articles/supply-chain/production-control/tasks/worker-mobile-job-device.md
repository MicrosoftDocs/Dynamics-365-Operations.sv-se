--- 
title: Konfigurera en arbetare med den mobila jobbenheten
description: "I den här proceduren visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att göra arbetsregistreringar."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 449c8411b06303a470aba279f85fb904ca1ad3c2
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="70738-103">Konfigurera en arbetare med den mobila jobbenheten</span><span class="sxs-lookup"><span data-stu-id="70738-103">Configure a worker using the mobile job device</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="70738-104">I den här proceduren visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att göra arbetsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="70738-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="70738-105">Tilldela roller till användarkontot</span><span class="sxs-lookup"><span data-stu-id="70738-105">Assign roles to user account</span></span>
1. <span data-ttu-id="70738-106">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="70738-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="70738-107">Använd snabbfiltret för att filtrera på namnet på en arbetare där användarkontot associeras med rollen maskinoperatör.</span><span class="sxs-lookup"><span data-stu-id="70738-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="70738-108">I exempeldata skulle namnet vara Shannon.</span><span class="sxs-lookup"><span data-stu-id="70738-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="70738-109">Markera användarkontoposten.</span><span class="sxs-lookup"><span data-stu-id="70738-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="70738-110">I listan, klicka på den ”Namn” länken i den valda raden för att visa information om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="70738-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="70738-111">I trädet, välj Roller\Maskinoperatör.</span><span class="sxs-lookup"><span data-stu-id="70738-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="70738-112">Stäng sidan för användarkontodetaljer.</span><span class="sxs-lookup"><span data-stu-id="70738-112">Close the user account details page.</span></span>
7. <span data-ttu-id="70738-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="70738-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="70738-114">Konfigurera arbetarkonto.</span><span class="sxs-lookup"><span data-stu-id="70738-114">Configure worker account.</span></span>
1. <span data-ttu-id="70738-115">Gå till Personal > Arbetare > Arbetare.</span><span class="sxs-lookup"><span data-stu-id="70738-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="70738-116">Använd snabbfiltret för att filtrera på namnet på en arbetare där användarkontot associeras med rollen maskinoperatör.</span><span class="sxs-lookup"><span data-stu-id="70738-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="70738-117">I exempeldata skulle namnet vara Shannon.</span><span class="sxs-lookup"><span data-stu-id="70738-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="70738-118">Markera användarkontoposten.</span><span class="sxs-lookup"><span data-stu-id="70738-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="70738-119">I listan, klicka på den ”Namn” länken i den valda raden för att visa information om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="70738-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="70738-120">Klicka på fliken Anställning.</span><span class="sxs-lookup"><span data-stu-id="70738-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="70738-121">Expandera snabbfliken Tidsregistrering och klicka på Aktivera på registreringsterminaler.</span><span class="sxs-lookup"><span data-stu-id="70738-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="70738-122">Klicka på Aktivera på registreringsterminaler.</span><span class="sxs-lookup"><span data-stu-id="70738-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="70738-123">I fältet Beräkningsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="70738-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="70738-124">I fältet Standardberäkningsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="70738-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="70738-125">I fältet Godkännandegrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="70738-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="70738-126">I fältet Standardprofil, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="70738-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="70738-127">I fältet Profilgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="70738-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="70738-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70738-128">Click OK.</span></span>
14. <span data-ttu-id="70738-129">Klicka på Redigera för att ange ett bricknummer för den nya tidsregistreringsarbetaren.</span><span class="sxs-lookup"><span data-stu-id="70738-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="70738-130">I fältet ID-bricka, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="70738-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="70738-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="70738-131">Click Save.</span></span>
17. <span data-ttu-id="70738-132">Använd genvägen SaveRecord.</span><span class="sxs-lookup"><span data-stu-id="70738-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="70738-133">Stäng sidan med arbetardetaljer.</span><span class="sxs-lookup"><span data-stu-id="70738-133">Close the worker details page.</span></span>
19. <span data-ttu-id="70738-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="70738-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="70738-135">Tilldela arbetare till enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="70738-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="70738-136">Gå till Produktionskontroll > Inställningar > Tillverkningskörning > Konfigurera jobbkort för enheter.</span><span class="sxs-lookup"><span data-stu-id="70738-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="70738-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="70738-137">Click Add.</span></span>
3. <span data-ttu-id="70738-138">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="70738-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="70738-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70738-139">Click OK.</span></span>
5. <span data-ttu-id="70738-140">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="70738-140">Click Edit.</span></span>
6. <span data-ttu-id="70738-141">I fältet Produktionsenhet kan du ställa in standardfiltret för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="70738-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="70738-142">Då säkerställs att endast produktionsjobb för den valda produktionsenheten visas när arbetaren loggar in på enheten.</span><span class="sxs-lookup"><span data-stu-id="70738-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="70738-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="70738-143">Close the page.</span></span>

