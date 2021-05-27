---
title: Du kan inte bekräfta en försändelse eftersom kvantiteten överstiger procentsatsen för överleverans
description: Du kan inte bekräfta en försändelse eftersom kvantiteten överstiger procentsatsen för överleverans
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
ms.openlocfilehash: c9b5ba8dedb927ee049d7e53e9a666902f563f49
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938556"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a><span data-ttu-id="39e35-103">Du kan inte bekräfta en försändelse eftersom kvantiteten överstiger procentsatsen för överleverans</span><span class="sxs-lookup"><span data-stu-id="39e35-103">You can't confirm a shipment because the quantity exceeds the overdelivery percentage</span></span>

<span data-ttu-id="39e35-104">Felkod: WAX1687</span><span class="sxs-lookup"><span data-stu-id="39e35-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="39e35-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="39e35-105">Symptoms</span></span>

<span data-ttu-id="39e35-106">När du försöker bekräfta en leverans visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="39e35-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="39e35-107">Försändelsen för beläggning %1 har inte bekräftats eftersom för artikeln %2 överskrider procenttalet som har definierats för överleverans.</span><span class="sxs-lookup"><span data-stu-id="39e35-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for overdelivery.</span></span>

<span data-ttu-id="39e35-108">Du kan därför inte bekräfta leveransen för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="39e35-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="39e35-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="39e35-109">Cause</span></span>

<span data-ttu-id="39e35-110">Kvantiteten för beläggningen eller leveransen har bara delvis plockats.</span><span class="sxs-lookup"><span data-stu-id="39e35-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="39e35-111">Kvantiteten överskrider för närvarande den plockade kvantiteten med en procentsats som ligger utanför den tillåtna överleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="39e35-111">The quantity currently exceeds the picked quantity by a percentage that is outside the allowed overdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="39e35-112">Upplösning</span><span class="sxs-lookup"><span data-stu-id="39e35-112">Resolution</span></span>

<span data-ttu-id="39e35-113">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="39e35-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="39e35-114">Ställ in kvantiteten för beläggningsrad.</span><span class="sxs-lookup"><span data-stu-id="39e35-114">Set the load line quantity.</span></span>
- <span data-ttu-id="39e35-115">Ange procentsats för överleverans.</span><span class="sxs-lookup"><span data-stu-id="39e35-115">Set the overdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="39e35-116">Ställ in kvantiteten för beläggningsrad</span><span class="sxs-lookup"><span data-stu-id="39e35-116">Set the load line quantity</span></span>

<span data-ttu-id="39e35-117">Gör på följande sätt om du vill ställa in kvantitet för beläggningsrad:</span><span class="sxs-lookup"><span data-stu-id="39e35-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="39e35-118">Gå till **Lagerstyrning \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="39e35-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="39e35-119">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="39e35-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="39e35-120">På snabbfliken **Läs in rader** markerar du inläsningsraden för den artikel som överskrider överleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="39e35-120">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="39e35-121">På snabbfliken **Radinformation** väljer du **Order**.</span><span class="sxs-lookup"><span data-stu-id="39e35-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="39e35-122">I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att försändelsebekräftelse kan ske.</span><span class="sxs-lookup"><span data-stu-id="39e35-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-overdelivery-percentage"></a><span data-ttu-id="39e35-123">Ange procentsats för överleverans</span><span class="sxs-lookup"><span data-stu-id="39e35-123">Set the overdelivery percentage</span></span>

<span data-ttu-id="39e35-124">Gör på följande sätt om du vill ställa in procentsats för underleverans:</span><span class="sxs-lookup"><span data-stu-id="39e35-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="39e35-125">Gå till **Lagerstyrning \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="39e35-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="39e35-126">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="39e35-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="39e35-127">På snabbfliken **Läs in rader** markerar du inläsningsraden för den artikel som överskrider överleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="39e35-127">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="39e35-128">På snabbfliken **Radinformation** väljer du **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="39e35-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="39e35-129">I fältet **Överleverans** anger du värdet som en större procentsats som rymmer den kvantitet som har plockats mot beläggningskvantiteten, detta så att leveransbekräftelse kan ske.</span><span class="sxs-lookup"><span data-stu-id="39e35-129">In the **Overdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>