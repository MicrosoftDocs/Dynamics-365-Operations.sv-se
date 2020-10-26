---
title: Konfigurera en arbetare med den mobila jobbenheten
description: I det här avsnittet visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att göra arbetsregistreringar.
author: ShylaThompson
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ada42a98a8a87e377f939d063b17f9904f6b3408
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978244"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="456be-103">Konfigurera en arbetare med den mobila jobbenheten</span><span class="sxs-lookup"><span data-stu-id="456be-103">Configure a worker using the mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="456be-104">I det här avsnittet visas hur du tilldelar de korrekta rollerna till användarkontot för en arbetare och sedan aktiverar arbetaren för att göra arbetsregistreringar.</span><span class="sxs-lookup"><span data-stu-id="456be-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="456be-105">Kontrollera att en arbetstagare har tilldelats en viss roll</span><span class="sxs-lookup"><span data-stu-id="456be-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="456be-106">I det här exemplet kontrollerar du att användaren "SHANNON" har tilldelats rollen maskinoperatör innan du konfigurerar arbetarkontot.</span><span class="sxs-lookup"><span data-stu-id="456be-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="456be-107">Gå till **Navigeringsfönster > Moduler > Systemadministration > Användare > Användare**.</span><span class="sxs-lookup"><span data-stu-id="456be-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="456be-108">Sök efter en användare i snabbfiltret.</span><span class="sxs-lookup"><span data-stu-id="456be-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="456be-109">Ange `shannon` i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="456be-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="456be-110">Markera länken i kolumnen **användar-ID** för det användarkonto som visas.</span><span class="sxs-lookup"><span data-stu-id="456be-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="456be-111">I trädet **Användares roller** väljer du **Roller > Maskinoperatör**.</span><span class="sxs-lookup"><span data-stu-id="456be-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="456be-112">Stäng sidorna **användarinformation** och **användare** för att gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="456be-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="456be-113">Konfigurera arbetarkonto.</span><span class="sxs-lookup"><span data-stu-id="456be-113">Configure worker account</span></span>
1. <span data-ttu-id="456be-114">Gå till **navigeringsfönstret > moduler > personal > arbetare > arbetare**.</span><span class="sxs-lookup"><span data-stu-id="456be-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="456be-115">Sök efter en användare i snabbfiltret.</span><span class="sxs-lookup"><span data-stu-id="456be-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="456be-116">Ange `shannon` i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="456be-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="456be-117">Markera länken i kolumnen **Namn** för det användarkonto som visas.</span><span class="sxs-lookup"><span data-stu-id="456be-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="456be-118">Välj fliken **tidsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="456be-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="456be-119">Välj **Aktivera på registreringsterminaler**</span><span class="sxs-lookup"><span data-stu-id="456be-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="456be-120">Ange eller välj värden i följande fält:</span><span class="sxs-lookup"><span data-stu-id="456be-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="456be-121">**Beräkningsgrupp**</span><span class="sxs-lookup"><span data-stu-id="456be-121">**Calculation group**</span></span>  
    - <span data-ttu-id="456be-122">**Standardberäkningsgrupp**</span><span class="sxs-lookup"><span data-stu-id="456be-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="456be-123">**Godkännandegrupp**</span><span class="sxs-lookup"><span data-stu-id="456be-123">**Approval group**</span></span>  
    - <span data-ttu-id="456be-124">**Standardprofil**</span><span class="sxs-lookup"><span data-stu-id="456be-124">**Standard profile**</span></span>  
    - <span data-ttu-id="456be-125">**Profilgrupp**</span><span class="sxs-lookup"><span data-stu-id="456be-125">**Profile group**</span></span>  

7. <span data-ttu-id="456be-126">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="456be-126">Select **OK**.</span></span>
8. <span data-ttu-id="456be-127">Klicka på **Redigera** för att ange ett bricknummer för den nya tidsregistreringsarbetaren.</span><span class="sxs-lookup"><span data-stu-id="456be-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="456be-128">Ange ett värde i fältet **ID-bricka**.</span><span class="sxs-lookup"><span data-stu-id="456be-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="456be-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="456be-129">Select **Save**.</span></span>
10. <span data-ttu-id="456be-130">Stäng sidorna **arbetardetaljer** och **arbetare**.</span><span class="sxs-lookup"><span data-stu-id="456be-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="456be-131">Tilldela arbetare till enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="456be-131">Assign worker to device group</span></span>
1. <span data-ttu-id="456be-132">Gå till **Produktionskontroll > Inställningar > Tillverkningskörning > Konfigurera jobbkort för enheter**.</span><span class="sxs-lookup"><span data-stu-id="456be-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="456be-133">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="456be-133">Select **Add**.</span></span>
3. <span data-ttu-id="456be-134">Välj önskad arbetare i listan.</span><span class="sxs-lookup"><span data-stu-id="456be-134">In the list, select the desired worker.</span></span> <span data-ttu-id="456be-135">Välj **SHANNON** i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="456be-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="456be-136">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="456be-136">Select **OK**.</span></span>
5. <span data-ttu-id="456be-137">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="456be-137">Select **Edit**.</span></span>
6. <span data-ttu-id="456be-138">I fältet **Produktionsenhet** kan du ställa in standardfiltret för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="456be-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="456be-139">Då säkerställs att endast produktionsjobb för den valda produktionsenheten visas när arbetaren loggar in på enheten.</span><span class="sxs-lookup"><span data-stu-id="456be-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="456be-140">Ange önskat värde.</span><span class="sxs-lookup"><span data-stu-id="456be-140">Enter the desired value.</span></span>
7. <span data-ttu-id="456be-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="456be-141">Close the page.</span></span>

