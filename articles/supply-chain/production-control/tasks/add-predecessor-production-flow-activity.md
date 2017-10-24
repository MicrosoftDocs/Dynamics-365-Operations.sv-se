--- 
title: "Lägg till en föregångare i en produktionsflödesaktivitet"
description: "I ett produktionsflödesversionen måste alla aktiviteter planeras sekventiellt."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d19fb20e8cc941daeaa506e4bf1cb0c7031cf2ee
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="52d83-103">Lägg till en föregångare i en produktionsflödesaktivitet</span><span class="sxs-lookup"><span data-stu-id="52d83-103">Add a predecessor to a production flow activity</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="52d83-104">I ett produktionsflödesversionen måste alla aktiviteter planeras sekventiellt.</span><span class="sxs-lookup"><span data-stu-id="52d83-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="52d83-105">En aktivitet kan ha en eller flera föregående eller efterföljande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="52d83-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="52d83-106">I den här proceduren visas hur du kopplar en tidigare aktivitet till en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="52d83-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="52d83-107">För att utföra denna uppgift behöver du ett produktionsflöde som har utkastversionen med minst två aktiviteter som kan kopplas.</span><span class="sxs-lookup"><span data-stu-id="52d83-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="52d83-108">Mer information finns i dokumentet betitlat "Production flows and activities in lean manufacturing."</span><span class="sxs-lookup"><span data-stu-id="52d83-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="52d83-109">Hitta produktionsflöde och version</span><span class="sxs-lookup"><span data-stu-id="52d83-109">Find the production flow and version</span></span>
1. <span data-ttu-id="52d83-110">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="52d83-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="52d83-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="52d83-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="52d83-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="52d83-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="52d83-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="52d83-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="52d83-114">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="52d83-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="52d83-115">Välj en aktivitet och lägg till en föregående</span><span class="sxs-lookup"><span data-stu-id="52d83-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="52d83-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="52d83-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="52d83-117">Klicka på Add predecessor.</span><span class="sxs-lookup"><span data-stu-id="52d83-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="52d83-118">Ange eller välj ett värde i fältet Activity.</span><span class="sxs-lookup"><span data-stu-id="52d83-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="52d83-119">Ange ett värde i fältet Grad för cykeltid.</span><span class="sxs-lookup"><span data-stu-id="52d83-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="52d83-120">Standardcykeltidsförhållande i en aktivitetsrelation är 1.</span><span class="sxs-lookup"><span data-stu-id="52d83-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="52d83-121">Detta förutsätter att båda aktiviteterna körs i samma takt eller takttid.</span><span class="sxs-lookup"><span data-stu-id="52d83-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="52d83-122">Om föregångaren körs med en högre hastighet (lägre takttid), bör förhållande vara lägre än 1; om föregångaren körs med en långsammare hastighet (högre takttid) är cykeltidsförhållandet större än 1.</span><span class="sxs-lookup"><span data-stu-id="52d83-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="52d83-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="52d83-123">Click OK.</span></span>


