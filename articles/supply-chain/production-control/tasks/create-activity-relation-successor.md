---
title: Skapa aktivitetsrelation - Efterträdare
description: Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f10ecb8e579975327440ede6ea383226645c8cf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255311"
---
# <a name="create-activity-relation---successor"></a><span data-ttu-id="394e3-103">Skapa aktivitetsrelation - Efterträdare</span><span class="sxs-lookup"><span data-stu-id="394e3-103">Create activity relation - Successor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="394e3-104">Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer.</span><span class="sxs-lookup"><span data-stu-id="394e3-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="394e3-105">Den här inspelningen visar hur du skapar en aktivitetsrelation.</span><span class="sxs-lookup"><span data-stu-id="394e3-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="394e3-106">Förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="394e3-106">Prerequisites:</span></span>

- <span data-ttu-id="394e3-107">Ett produktionsflöde och en version i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="394e3-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="394e3-108">Två aktiviteter som följer på varandra i produktionsflödet skapas, men är inte relaterade.</span><span class="sxs-lookup"><span data-stu-id="394e3-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="394e3-109">Hitta produktionsflödesversionen</span><span class="sxs-lookup"><span data-stu-id="394e3-109">Find the production flow version</span></span> 
1. <span data-ttu-id="394e3-110">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="394e3-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="394e3-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="394e3-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="394e3-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="394e3-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="394e3-113">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="394e3-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="394e3-114">Välj en utkastversion i listan.</span><span class="sxs-lookup"><span data-stu-id="394e3-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="394e3-115">Aktivitetsrelationer kan läggas till både i utkastversioner och aktiva versioner av ett produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="394e3-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="394e3-116">Öppna aktivitetsöversikten</span><span class="sxs-lookup"><span data-stu-id="394e3-116">Open the activity overview</span></span>
1. <span data-ttu-id="394e3-117">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="394e3-117">Click Activities.</span></span>
    * <span data-ttu-id="394e3-118">Observera att formuläret visar alla aktiviteter i produktionsflödet som tilldelats versionen av de produktionsflöden som du arbetar i.</span><span class="sxs-lookup"><span data-stu-id="394e3-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="394e3-119">Lägg till en efterträdare</span><span class="sxs-lookup"><span data-stu-id="394e3-119">Add a Successor</span></span>
1. <span data-ttu-id="394e3-120">Klicka på Lägg till efterträdare.</span><span class="sxs-lookup"><span data-stu-id="394e3-120">Click Add successor.</span></span>
2. <span data-ttu-id="394e3-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Aktivitet.</span><span class="sxs-lookup"><span data-stu-id="394e3-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="394e3-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="394e3-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="394e3-123">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="394e3-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="394e3-124">Markera kryssrutan Begränsning.</span><span class="sxs-lookup"><span data-stu-id="394e3-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="394e3-125">Ange ett värde i fältet Begränsningsvärde.</span><span class="sxs-lookup"><span data-stu-id="394e3-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="394e3-126">Begränsningstiden att tiden som ska schemaläggas mellan det schemalagda slutet av företrädaren (förfallodatum och tid) och den schemalagda starten av efterträdaren.</span><span class="sxs-lookup"><span data-stu-id="394e3-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="394e3-127">Skriv ett värde i fältet Enheter.</span><span class="sxs-lookup"><span data-stu-id="394e3-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="394e3-128">Ange ett värde i fältet Grad för cykeltid.</span><span class="sxs-lookup"><span data-stu-id="394e3-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="394e3-129">Om båda verksamheterna körs i samma takt, ska cykeltidsförhållande vara 1.</span><span class="sxs-lookup"><span data-stu-id="394e3-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="394e3-130">Om den föregående aktiviteten körs med dubbel hastighet på efterföljande ska förhållandet vara 2.</span><span class="sxs-lookup"><span data-stu-id="394e3-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="394e3-131">Cykeltidsförhållandena används för att beräkna de enskilda cykeltiderna för aktiviteterna i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="394e3-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="394e3-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="394e3-132">Click OK.</span></span>
10. <span data-ttu-id="394e3-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="394e3-133">Close the page.</span></span>
11. <span data-ttu-id="394e3-134">Klicka på fliken GridPanel.</span><span class="sxs-lookup"><span data-stu-id="394e3-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="394e3-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="394e3-135">Close the page.</span></span>
13. <span data-ttu-id="394e3-136">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="394e3-136">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]