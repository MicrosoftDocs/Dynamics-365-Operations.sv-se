---
title: Skapa aktivitetsrelation - Efterträdare
description: Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46dda12d4ad2b23ee86d240e6cdd8a1d46f1838
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829244"
---
# <a name="create-activity-relation---successor"></a><span data-ttu-id="50a56-103">Skapa aktivitetsrelation - Efterträdare</span><span class="sxs-lookup"><span data-stu-id="50a56-103">Create activity relation - Successor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="50a56-104">Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer.</span><span class="sxs-lookup"><span data-stu-id="50a56-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="50a56-105">Den här inspelningen visar hur du skapar en aktivitetsrelation.</span><span class="sxs-lookup"><span data-stu-id="50a56-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="50a56-106">Förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="50a56-106">Prerequisites:</span></span>

- <span data-ttu-id="50a56-107">Ett produktionsflöde och en version i utkastläge.</span><span class="sxs-lookup"><span data-stu-id="50a56-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="50a56-108">Två aktiviteter som följer på varandra i produktionsflödet skapas, men är inte relaterade.</span><span class="sxs-lookup"><span data-stu-id="50a56-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="50a56-109">Hitta produktionsflödesversionen</span><span class="sxs-lookup"><span data-stu-id="50a56-109">Find the production flow version</span></span> 
1. <span data-ttu-id="50a56-110">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="50a56-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="50a56-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="50a56-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="50a56-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="50a56-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="50a56-113">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="50a56-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="50a56-114">Välj en utkastversion i listan.</span><span class="sxs-lookup"><span data-stu-id="50a56-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="50a56-115">Aktivitetsrelationer kan läggas till både i utkastversioner och aktiva versioner av ett produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="50a56-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="50a56-116">Öppna aktivitetsöversikten</span><span class="sxs-lookup"><span data-stu-id="50a56-116">Open the activity overview</span></span>
1. <span data-ttu-id="50a56-117">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="50a56-117">Click Activities.</span></span>
    * <span data-ttu-id="50a56-118">Observera att formuläret visar alla aktiviteter i produktionsflödet som tilldelats versionen av de produktionsflöden som du arbetar i.</span><span class="sxs-lookup"><span data-stu-id="50a56-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="50a56-119">Lägg till en efterträdare</span><span class="sxs-lookup"><span data-stu-id="50a56-119">Add a Successor</span></span>
1. <span data-ttu-id="50a56-120">Klicka på Lägg till efterträdare.</span><span class="sxs-lookup"><span data-stu-id="50a56-120">Click Add successor.</span></span>
2. <span data-ttu-id="50a56-121">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Aktivitet.</span><span class="sxs-lookup"><span data-stu-id="50a56-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="50a56-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="50a56-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="50a56-123">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="50a56-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="50a56-124">Markera kryssrutan Begränsning.</span><span class="sxs-lookup"><span data-stu-id="50a56-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="50a56-125">Ange ett värde i fältet Begränsningsvärde.</span><span class="sxs-lookup"><span data-stu-id="50a56-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="50a56-126">Begränsningstiden att tiden som ska schemaläggas mellan det schemalagda slutet av företrädaren (förfallodatum och tid) och den schemalagda starten av efterträdaren.</span><span class="sxs-lookup"><span data-stu-id="50a56-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="50a56-127">Skriv ett värde i fältet Enheter.</span><span class="sxs-lookup"><span data-stu-id="50a56-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="50a56-128">Ange ett värde i fältet Grad för cykeltid.</span><span class="sxs-lookup"><span data-stu-id="50a56-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="50a56-129">Om båda verksamheterna körs i samma takt, ska cykeltidsförhållande vara 1.</span><span class="sxs-lookup"><span data-stu-id="50a56-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="50a56-130">Om den föregående aktiviteten körs med dubbel hastighet på efterföljande ska förhållandet vara 2.</span><span class="sxs-lookup"><span data-stu-id="50a56-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="50a56-131">Cykeltidsförhållandena används för att beräkna de enskilda cykeltiderna för aktiviteterna i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="50a56-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="50a56-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="50a56-132">Click OK.</span></span>
10. <span data-ttu-id="50a56-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="50a56-133">Close the page.</span></span>
11. <span data-ttu-id="50a56-134">Klicka på fliken GridPanel.</span><span class="sxs-lookup"><span data-stu-id="50a56-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="50a56-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="50a56-135">Close the page.</span></span>
13. <span data-ttu-id="50a56-136">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="50a56-136">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]