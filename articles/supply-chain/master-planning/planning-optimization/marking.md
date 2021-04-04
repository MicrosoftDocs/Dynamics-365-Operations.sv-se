---
title: Lagermarkeringen med Planeringsoptimering
description: I det här avsnittet finns information om alternativen som är tillgängliga för markering av lager i bekräftade order när du använder planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7813f570afb0260e6740507c9504320c3e87be93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263360"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="01185-103">Lagermarkeringen med Planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="01185-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01185-104">I det här avsnittet finns information om alternativen som är tillgängliga för markering av lager i bekräftade order när du använder planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="01185-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="01185-105">*Märkning* används för att koppla tillgång och efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="01185-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="01185-106">Den påminner om *pegging*, som visar hur efter frågan förväntas täcka huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="01185-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="01185-107">Ur en planeringssynpunkt är den huvudsakliga skillnaden att markeringen är mer permanent än pegging.</span><span class="sxs-lookup"><span data-stu-id="01185-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="01185-108">Markering har införts för att stödja särskilda kostnadsscenarier för först in, först ut (FIFO) och sist in, först ut (LIFO).</span><span class="sxs-lookup"><span data-stu-id="01185-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="01185-109">Den används dock också för vissa icke-kostnadsscenarier.</span><span class="sxs-lookup"><span data-stu-id="01185-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="01185-110">Att markera mellan tillgång och efterfrågan är valfritt och nästan permanent.</span><span class="sxs-lookup"><span data-stu-id="01185-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="01185-111">Markering kan tas bort manuellt av en användare, eller så kan du ta bort den genom att köra en nedbrytning av en försäljningsorderrad där alternativet **ta bort markering** har valts.</span><span class="sxs-lookup"><span data-stu-id="01185-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="01185-112">Pegging styrs av huvudplanering vid disponering för att länka efterfrågan med den leverans som krävs.</span><span class="sxs-lookup"><span data-stu-id="01185-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="01185-113">Pegging kan uppdateras för varje planeringskörning för att optimera leveransen som krävs för att täcka efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="01185-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="01185-114">När huvudplaneringen uppdaterar pegging-information respekteras eventuell befintlig markering.</span><span class="sxs-lookup"><span data-stu-id="01185-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="01185-115">Pegging startar genom att inkludera relevanta markeringar, lagerbehållningar och reservationer på order i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="01185-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="01185-116">Markera mellan efterfrågan och leverans</span><span class="sxs-lookup"><span data-stu-id="01185-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="01185-117">Lagerbehållningar</span><span class="sxs-lookup"><span data-stu-id="01185-117">On-hand reservations</span></span>
1. <span data-ttu-id="01185-118">Reservationer på order</span><span class="sxs-lookup"><span data-stu-id="01185-118">On-order reservations</span></span>

<span data-ttu-id="01185-119">När du bekräftar en planerad order innehåller dialogrutan **Bekräftelse** ett fält för **Uppdatera markering** som du använder för att ställa in markeringsalternativ för de beställningar som skapas under bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="01185-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="01185-120">Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="01185-120">Select one of the following values:</span></span>

- <span data-ttu-id="01185-121">**Nej** – ingen lagermarkering används.</span><span class="sxs-lookup"><span data-stu-id="01185-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="01185-122">**Standard** – Lagermarkeringen uppdateras baserat på pegging.</span><span class="sxs-lookup"><span data-stu-id="01185-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="01185-123">Posterna i en order (efterfrågan) markeras i jämförelse med en uppfyllelseorder (tillgång).</span><span class="sxs-lookup"><span data-stu-id="01185-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="01185-124">Om en kvantitet finns kvar i uppfyllelseorder markeras den inte och referensinformationen lämnas tom.</span><span class="sxs-lookup"><span data-stu-id="01185-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="01185-125">Om till exempel en försäljningsorder för 100 ea peggas mot en inköpsorder för 150 ea, tilldelas referensinformation endast till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="01185-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="01185-126">**Utökad** – Både behovsordern (efterfrågan) och uppfyllelseordern (tillgång) markeras, oberoende av om någon kvantitet återstår i uppfyllelseordern.</span><span class="sxs-lookup"><span data-stu-id="01185-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="01185-127">Om till exempel en försäljningsorder för 100 ea peggas mot en inköpsorder för 150 ea, tilldelas referensinformation till både försäljningsordern och inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="01185-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]