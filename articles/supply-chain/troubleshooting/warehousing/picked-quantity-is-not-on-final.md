---
title: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
description: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938553"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="2b6aa-103">Du kan inte bekräfta en leverans eftersom inga artiklar har plockats</span><span class="sxs-lookup"><span data-stu-id="2b6aa-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="2b6aa-104">Felkod: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="2b6aa-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="2b6aa-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="2b6aa-105">Symptoms</span></span>

<span data-ttu-id="2b6aa-106">När du försöker bekräfta en leverans visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="2b6aa-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="2b6aa-107">Vissa av de artiklar som behövs för lasten %1 har ännu inte plockats och förflyttats till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="2b6aa-108">Du kan därför inte bekräfta leveransen för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="2b6aa-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="2b6aa-109">Cause</span></span>

<span data-ttu-id="2b6aa-110">Beläggningen eller leveransen kan inte bekräftas i sitt aktuella tillstånd eftersom något av följande villkor kan finnas:</span><span class="sxs-lookup"><span data-stu-id="2b6aa-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="2b6aa-111">Det relaterade arbetet har ännu inte plockats och flyttats till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="2b6aa-112">Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="2b6aa-113">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2b6aa-113">Resolution</span></span>

<span data-ttu-id="2b6aa-114">Kontrollera relaterade försäljningsorder eller överföringsorder för beläggningen eller leveransen.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="2b6aa-115">Se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="2b6aa-116">Gå till **Lagerstyrning \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="2b6aa-117">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="2b6aa-118">På snabbfliken **Beläggningsrader** väljer du beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="2b6aa-119">Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="2b6aa-120">I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="2b6aa-121">Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="2b6aa-122">Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="2b6aa-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
