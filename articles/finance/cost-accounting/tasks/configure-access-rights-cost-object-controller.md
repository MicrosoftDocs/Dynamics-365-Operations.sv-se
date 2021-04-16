---
title: Konfigurera åtkomsträttigheter för en kostnadsobjektcontroller
description: Använd den är proceduren för att konfigurera åtkomsträttigheter för en kostnadsobjektcontroller.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eef755dd9a44ce24d3bfb2953cf9a52e6a8ac849
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822889"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="bedbe-103">Konfigurera åtkomsträttigheter för en kostnadsobjektcontroller</span><span class="sxs-lookup"><span data-stu-id="bedbe-103">Configure access rights for a cost object controller</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bedbe-104">Använd den är proceduren för att konfigurera åtkomsträttigheter för en kostnadsobjektcontroller.</span><span class="sxs-lookup"><span data-stu-id="bedbe-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="bedbe-105">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="bedbe-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="bedbe-106">Tilldela rollen kostnadsobjektcontroller</span><span class="sxs-lookup"><span data-stu-id="bedbe-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="bedbe-107">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="bedbe-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="bedbe-108">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="bedbe-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="bedbe-109">Filtrera till exempel fältet Användarnamn med värdet "alicia".</span><span class="sxs-lookup"><span data-stu-id="bedbe-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="bedbe-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bedbe-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bedbe-111">Klicka på Tilldela roller.</span><span class="sxs-lookup"><span data-stu-id="bedbe-111">Click Assign roles.</span></span>
5. <span data-ttu-id="bedbe-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bedbe-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="bedbe-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bedbe-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="bedbe-114">Aktivera listan åtkomstsäkerhet</span><span class="sxs-lookup"><span data-stu-id="bedbe-114">Enable access list security</span></span>
1. <span data-ttu-id="bedbe-115">Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.</span><span class="sxs-lookup"><span data-stu-id="bedbe-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="bedbe-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bedbe-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bedbe-117">Välj Organisation.</span><span class="sxs-lookup"><span data-stu-id="bedbe-117">Select Organization.</span></span>  
3. <span data-ttu-id="bedbe-118">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="bedbe-118">Click Edit.</span></span>
4. <span data-ttu-id="bedbe-119">Välj Ja i fältet Hierarki för åtkomstlista.</span><span class="sxs-lookup"><span data-stu-id="bedbe-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="bedbe-120">Klicka p Visa hierarki</span><span class="sxs-lookup"><span data-stu-id="bedbe-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="bedbe-121">Tilldela åtkomsträttigheter till användare</span><span class="sxs-lookup"><span data-stu-id="bedbe-121">Assign access rights to user</span></span>
1. <span data-ttu-id="bedbe-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bedbe-122">Click New.</span></span>
2. <span data-ttu-id="bedbe-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bedbe-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="bedbe-124">Ange eller välj ett värde i fältet Användar-ID.</span><span class="sxs-lookup"><span data-stu-id="bedbe-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="bedbe-125">Välj Administratör.</span><span class="sxs-lookup"><span data-stu-id="bedbe-125">Select Admin.</span></span>  
4. <span data-ttu-id="bedbe-126">Välj Organization\CEO\CFO\FIM i trädet.</span><span class="sxs-lookup"><span data-stu-id="bedbe-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="bedbe-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bedbe-127">Click New.</span></span>
6. <span data-ttu-id="bedbe-128">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bedbe-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="bedbe-129">Ange eller välj ett värde i fältet Användar-ID.</span><span class="sxs-lookup"><span data-stu-id="bedbe-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="bedbe-130">Välj Alicia.</span><span class="sxs-lookup"><span data-stu-id="bedbe-130">Select Alicia.</span></span>  
8. <span data-ttu-id="bedbe-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bedbe-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="bedbe-132">Aktivera åtkomsträttigheter i Kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="bedbe-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="bedbe-133">Gå till Kostnadsredovisning > Inställningar > Parametrar.</span><span class="sxs-lookup"><span data-stu-id="bedbe-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="bedbe-134">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="bedbe-134">Click the General tab.</span></span>
3. <span data-ttu-id="bedbe-135">Välj Ja i fältet Aktivera visningsåtkomst för kostnadsobjektets dimensionsmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="bedbe-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="bedbe-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bedbe-136">Click Save.</span></span>
5. <span data-ttu-id="bedbe-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bedbe-137">Close the page.</span></span>
6. <span data-ttu-id="bedbe-138">Gå till Kostnadsredovisning > Inställningar > Konfiguration av arbetsytan för kostnadsstyrning.</span><span class="sxs-lookup"><span data-stu-id="bedbe-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="bedbe-139">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="bedbe-139">Click Edit.</span></span>
8. <span data-ttu-id="bedbe-140">Välj Ja i fältet Publicerad.</span><span class="sxs-lookup"><span data-stu-id="bedbe-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="bedbe-141">Om du väljer Ja kan en användare med någon av följande fyra roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor, ansvarig kostnadsredovisare och kostnadsobjektcontroller.</span><span class="sxs-lookup"><span data-stu-id="bedbe-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="bedbe-142">Om du väljer Nej kan bara en användare med någon av följande fyra roller se rapporter: kostnadsredovisningschef, kostnadsrevisor och kostnadsredovisare.</span><span class="sxs-lookup"><span data-stu-id="bedbe-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="bedbe-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bedbe-143">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]