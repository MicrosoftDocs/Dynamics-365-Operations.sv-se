---
title: "Följesedelsuppdateringar för returer"
description: "Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den order som artiklarna tillhör."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7532c5b1debdb498c2d6bab129208a412387c8fa
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="926ea-103">Följesedelsuppdateringar för returer</span><span class="sxs-lookup"><span data-stu-id="926ea-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="926ea-104">Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den order som artiklarna tillhör.</span><span class="sxs-lookup"><span data-stu-id="926ea-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="926ea-105">Liksom fakturauppdateringsprocessen är uppdateringen av den ekonomiska transaktionen, uppdateringen av följesedeln den fysiska uppdateringen av lagerposten, vilket innebär att det förbinder ändringar i lager.</span><span class="sxs-lookup"><span data-stu-id="926ea-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="926ea-106">Vid returer implementeras stegen som tilldelas dispositionsåtgärden under uppdateringen av följesedeln.</span><span class="sxs-lookup"><span data-stu-id="926ea-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="926ea-107">Följesedelsuppdateringen kan genomföras antingen i artikelinförseljournalen eller returordern.</span><span class="sxs-lookup"><span data-stu-id="926ea-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="926ea-108">Som en del av bokföringsprocessen för följesedeln kan eventuellt referensnumret från kundens leveransdokument kopplas till orderraderna.</span><span class="sxs-lookup"><span data-stu-id="926ea-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="926ea-109">Denna koppling är valfri och är endast för referens.</span><span class="sxs-lookup"><span data-stu-id="926ea-109">This association is optional and for reference only.</span></span> <span data-ttu-id="926ea-110">Den skapar inga transaktionsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="926ea-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="926ea-111">Om inte alla förväntade returer har anlänt inkluderar du endast mottagen kvantitet i följesedelsuppdateringen.</span><span class="sxs-lookup"><span data-stu-id="926ea-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="926ea-112">Lämna återstående artiklar på ordern tills resten av returleveransen anländer.</span><span class="sxs-lookup"><span data-stu-id="926ea-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="926ea-113">Om en artikel skickas tillbaka från karantänen till avdelningen för skeppning och inleverans, t.ex. när karantäninspektören inte vet var han eller hon ska placera artikeln i lagret, måste motsvarande följesedel uppdateras för att registreringen och hanteringen av dispositionskoden som har angetts som ett resultat av karantänen ska bli korrekt.</span><span class="sxs-lookup"><span data-stu-id="926ea-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="926ea-114">När du uppdaterar en följesedel för en returnerad artikel från ett försäljningsavtal uppdateras försäljningsavtalutfästelsen för artikeln automatiskt om du vill visa ändringarna i kvantiteten eller beloppet.</span><span class="sxs-lookup"><span data-stu-id="926ea-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="926ea-115">Se även</span><span class="sxs-lookup"><span data-stu-id="926ea-115">See also</span></span>

[<span data-ttu-id="926ea-116">Utföra fakturauppdateringar för returer</span><span class="sxs-lookup"><span data-stu-id="926ea-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  


