---
title: Lägg till en föregångare i en produktionsflödesaktivitet
description: I ett produktionsflödesversionen måste alla aktiviteter planeras sekventiellt.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d76ec6ac928228011f42355bebd553576bcfd275
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255455"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="f187c-103">Lägg till en föregångare i en produktionsflödesaktivitet</span><span class="sxs-lookup"><span data-stu-id="f187c-103">Add a predecessor to a production flow activity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f187c-104">I ett produktionsflödesversionen måste alla aktiviteter planeras sekventiellt.</span><span class="sxs-lookup"><span data-stu-id="f187c-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="f187c-105">En aktivitet kan ha en eller flera föregående eller efterföljande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="f187c-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="f187c-106">I den här proceduren visas hur du kopplar en tidigare aktivitet till en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="f187c-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="f187c-107">För att utföra denna uppgift behöver du ett produktionsflöde som har utkastversionen med minst två aktiviteter som kan kopplas.</span><span class="sxs-lookup"><span data-stu-id="f187c-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="f187c-108">Mer information finns i dokumentet betitlat "Production flows and activities in lean manufacturing."</span><span class="sxs-lookup"><span data-stu-id="f187c-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="f187c-109">Hitta produktionsflöde och version</span><span class="sxs-lookup"><span data-stu-id="f187c-109">Find the production flow and version</span></span>
1. <span data-ttu-id="f187c-110">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="f187c-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="f187c-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f187c-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f187c-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f187c-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f187c-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f187c-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f187c-114">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="f187c-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="f187c-115">Välj en aktivitet och lägg till en föregående</span><span class="sxs-lookup"><span data-stu-id="f187c-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="f187c-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f187c-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="f187c-117">Klicka på Add predecessor.</span><span class="sxs-lookup"><span data-stu-id="f187c-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="f187c-118">Ange eller välj ett värde i fältet Activity.</span><span class="sxs-lookup"><span data-stu-id="f187c-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="f187c-119">Ange ett värde i fältet Grad för cykeltid.</span><span class="sxs-lookup"><span data-stu-id="f187c-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="f187c-120">Standardcykeltidsförhållande i en aktivitetsrelation är 1.</span><span class="sxs-lookup"><span data-stu-id="f187c-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="f187c-121">Detta förutsätter att båda aktiviteterna körs i samma takt eller takttid.</span><span class="sxs-lookup"><span data-stu-id="f187c-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="f187c-122">Om föregångaren körs med en högre hastighet (lägre takttid), bör förhållande vara lägre än 1; om föregångaren körs med en långsammare hastighet (högre takttid) är cykeltidsförhållandet större än 1.</span><span class="sxs-lookup"><span data-stu-id="f187c-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="f187c-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f187c-123">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]