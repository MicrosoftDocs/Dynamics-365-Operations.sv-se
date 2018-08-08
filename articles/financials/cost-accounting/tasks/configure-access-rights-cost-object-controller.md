--- 
title: "Konfigurera åtkomsträttigheter för en kostnadsobjektcontroller"
description: "Använd den är proceduren för att konfigurera åtkomsträttigheter för en kostnadsobjektcontroller."
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6b7018f9d4926321341af94efd13911e2c69f5f5
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="8159a-103">Konfigurera åtkomsträttigheter för en kostnadsobjektcontroller</span><span class="sxs-lookup"><span data-stu-id="8159a-103">Configure access rights for a cost object controller</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8159a-104">Använd den är proceduren för att konfigurera åtkomsträttigheter för en kostnadsobjektcontroller.</span><span class="sxs-lookup"><span data-stu-id="8159a-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="8159a-105">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="8159a-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="8159a-106">Tilldela rollen kostnadsobjektcontroller</span><span class="sxs-lookup"><span data-stu-id="8159a-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="8159a-107">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="8159a-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="8159a-108">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="8159a-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8159a-109">Filtrera till exempel fältet Användarnamn med värdet "alicia".</span><span class="sxs-lookup"><span data-stu-id="8159a-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="8159a-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8159a-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8159a-111">Klicka på Tilldela roller.</span><span class="sxs-lookup"><span data-stu-id="8159a-111">Click Assign roles.</span></span>
5. <span data-ttu-id="8159a-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8159a-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="8159a-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8159a-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="8159a-114">Aktivera listan åtkomstsäkerhet</span><span class="sxs-lookup"><span data-stu-id="8159a-114">Enable access list security</span></span>
1. <span data-ttu-id="8159a-115">Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.</span><span class="sxs-lookup"><span data-stu-id="8159a-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="8159a-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8159a-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8159a-117">Välj Organisation.</span><span class="sxs-lookup"><span data-stu-id="8159a-117">Select Organization.</span></span>  
3. <span data-ttu-id="8159a-118">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8159a-118">Click Edit.</span></span>
4. <span data-ttu-id="8159a-119">Välj Ja i fältet Hierarki för åtkomstlista.</span><span class="sxs-lookup"><span data-stu-id="8159a-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="8159a-120">Klicka p Visa hierarki</span><span class="sxs-lookup"><span data-stu-id="8159a-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="8159a-121">Tilldela åtkomsträttigheter till användare</span><span class="sxs-lookup"><span data-stu-id="8159a-121">Assign access rights to user</span></span>
1. <span data-ttu-id="8159a-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8159a-122">Click New.</span></span>
2. <span data-ttu-id="8159a-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8159a-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="8159a-124">Ange eller välj ett värde i fältet Användar-ID.</span><span class="sxs-lookup"><span data-stu-id="8159a-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="8159a-125">Välj Administratör.</span><span class="sxs-lookup"><span data-stu-id="8159a-125">Select Admin.</span></span>  
4. <span data-ttu-id="8159a-126">Välj Organization\CEO\CFO\FIM i trädet.</span><span class="sxs-lookup"><span data-stu-id="8159a-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="8159a-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8159a-127">Click New.</span></span>
6. <span data-ttu-id="8159a-128">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8159a-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="8159a-129">Ange eller välj ett värde i fältet Användar-ID.</span><span class="sxs-lookup"><span data-stu-id="8159a-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="8159a-130">Välj Alicia.</span><span class="sxs-lookup"><span data-stu-id="8159a-130">Select Alicia.</span></span>  
8. <span data-ttu-id="8159a-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8159a-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="8159a-132">Aktivera åtkomsträttigheter i Kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="8159a-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="8159a-133">Gå till Kostnadsredovisning > Inställningar > Parametrar.</span><span class="sxs-lookup"><span data-stu-id="8159a-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="8159a-134">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8159a-134">Click the General tab.</span></span>
3. <span data-ttu-id="8159a-135">Välj Ja i fältet Aktivera visningsåtkomst för kostnadsobjektets dimensionsmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="8159a-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="8159a-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8159a-136">Click Save.</span></span>
5. <span data-ttu-id="8159a-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8159a-137">Close the page.</span></span>
6. <span data-ttu-id="8159a-138">Gå till Kostnadsredovisning > Inställningar > Konfiguration av arbetsytan för kostnadsstyrning.</span><span class="sxs-lookup"><span data-stu-id="8159a-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="8159a-139">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8159a-139">Click Edit.</span></span>
8. <span data-ttu-id="8159a-140">Välj Ja i fältet Publicerad.</span><span class="sxs-lookup"><span data-stu-id="8159a-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="8159a-141">Om du väljer Ja kan en användare med någon av följande fyra roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor, ansvarig kostnadsredovisare och kostnadsobjektcontroller.</span><span class="sxs-lookup"><span data-stu-id="8159a-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="8159a-142">Om du väljer Nej kan bara en användare med någon av följande fyra roller se rapporter: kostnadsredovisningschef, kostnadsrevisor och kostnadsredovisare.</span><span class="sxs-lookup"><span data-stu-id="8159a-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="8159a-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8159a-143">Click Save.</span></span>


