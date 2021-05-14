---
title: Du kan inte bekräfta en leverans eftersom kvantiteten är noll
description: Du kan inte bekräfta en leverans eftersom kvantiteten är noll
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938552"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="251a3-103">Du kan inte bekräfta en leverans eftersom kvantiteten är noll</span><span class="sxs-lookup"><span data-stu-id="251a3-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="251a3-104">Felkod: LoadLineArbetsbelastningningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="251a3-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="251a3-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="251a3-105">Symptoms</span></span>

<span data-ttu-id="251a3-106">När du försöker bekräfta en leverans visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="251a3-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="251a3-107">Beläggningsraden för artikel %1 och leveransen %2 har uppdaterats till noll kvantitet på grund av underleveranskonfigurationen som inte tillåter leverans av någon kvantitet för den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="251a3-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="251a3-108">Du kan därför inte bekräfta leveransen för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="251a3-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="251a3-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="251a3-109">Cause</span></span>

<span data-ttu-id="251a3-110">Systemet utvärderar om den plockade kvantiteten ligger inom de förväntade gränserna, baserat på plockad kvantitet, beläggningsradkvantitet och underleveransprocent.</span><span class="sxs-lookup"><span data-stu-id="251a3-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="251a3-111">Om systemet finner att den plockade kvantiteten på beläggningsraden är 0 (noll) kan du inte bekräfta försändelsen.</span><span class="sxs-lookup"><span data-stu-id="251a3-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="251a3-112">Detta problem kan till exempel uppstå om arbete har avbrutits och procentsatsen för underleverans på beläggningsraden är 100 procent.</span><span class="sxs-lookup"><span data-stu-id="251a3-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="251a3-113">Upplösning</span><span class="sxs-lookup"><span data-stu-id="251a3-113">Resolution</span></span>

<span data-ttu-id="251a3-114">Kontrollera beläggningsraderna för att se till att procentsatsen och kvantiteterna för underleverans stämmer överens med det plockade arbetet.</span><span class="sxs-lookup"><span data-stu-id="251a3-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="251a3-115">Gå till **Lagerstyrning \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="251a3-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="251a3-116">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="251a3-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="251a3-117">På snabbfliken **Beläggningsrader** markerar du beläggningsraden för den artikel som överskrider underleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="251a3-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="251a3-118">Justera värdet i fältet **Underleverans** **Kvantitet** efter behov.</span><span class="sxs-lookup"><span data-stu-id="251a3-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="251a3-119">Om problemet består måste du kanske slutföra mer plockningsarbete för relaterade försäljningsorder eller överföringsorder tills den tillgängliga kvantiteten stämmer överens med beläggningen eller försändelsen.</span><span class="sxs-lookup"><span data-stu-id="251a3-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
