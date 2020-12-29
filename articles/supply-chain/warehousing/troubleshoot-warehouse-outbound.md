---
title: Felsöka åtgärder för utgående distributionslager
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med utgående distributionslager i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 56bd91d8a6fe895317021d806e180df3a2db302b
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645463"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="a1c39-103">Felsöka åtgärder för utgående distributionslager</span><span class="sxs-lookup"><span data-stu-id="a1c39-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1c39-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med utgående distributionslager i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a1c39-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="a1c39-105">Följande felmeddelande visas: "försäljningsordern kan inte frisläppas".</span><span class="sxs-lookup"><span data-stu-id="a1c39-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a1c39-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="a1c39-106">Issue description</span></span>

<span data-ttu-id="a1c39-107">Det här problemet kan uppstå av flera orsaker.</span><span class="sxs-lookup"><span data-stu-id="a1c39-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="a1c39-108">Till exempel är ordern i kredithanteringsspärr och inga försändelser kan skapas förrän en giltig postadress anges för alla försäljningsrader som är kopplade till en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a1c39-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="a1c39-109">Alternativt finns det ett orderspärr som måste åtgärdas innan ordern kan frisläppas till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="a1c39-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="a1c39-110">Det här undantaget kan vara kundspecifikt, eller så kan det finnas på kundkontot.</span><span class="sxs-lookup"><span data-stu-id="a1c39-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a1c39-111">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="a1c39-111">Issue resolution</span></span>

<span data-ttu-id="a1c39-112">Lägg till eller uppdatera adressen på försäljningsordern och orderraderna och släpp sedan ordern på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="a1c39-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="a1c39-113">Order kan bara frisläppas till lagerstället om de har en giltig leveransadress (per adressformats inställningar i modulen **organisationsadministration**).</span><span class="sxs-lookup"><span data-stu-id="a1c39-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="a1c39-114">Undersök orderspärren och åtgärda utleveranserna.</span><span class="sxs-lookup"><span data-stu-id="a1c39-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="a1c39-115">Ta sedan bort spärren från ordern eller kunden och släpp ordern på lagerstället.</span><span class="sxs-lookup"><span data-stu-id="a1c39-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="a1c39-116">Följande meddelande visas: "försändelsen för inläsningen 1 % har bekräftats."</span><span class="sxs-lookup"><span data-stu-id="a1c39-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="a1c39-117">Inga rader bokförs dock.</span><span class="sxs-lookup"><span data-stu-id="a1c39-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a1c39-118">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="a1c39-118">Issue description</span></span>

<span data-ttu-id="a1c39-119">En leverans av en last har bekräftats, men ingen ytterligare bokföring utfördes.</span><span class="sxs-lookup"><span data-stu-id="a1c39-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a1c39-120">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="a1c39-120">Issue resolution</span></span>

<span data-ttu-id="a1c39-121">Försändelsebekräftelse påverkar inte bokföring.</span><span class="sxs-lookup"><span data-stu-id="a1c39-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="a1c39-122">Den uppdaterar bara försändelsen och laststatus.</span><span class="sxs-lookup"><span data-stu-id="a1c39-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="a1c39-123">Bokföring måste ske i en separat process.</span><span class="sxs-lookup"><span data-stu-id="a1c39-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="a1c39-124">Följande felmeddelande visas: "direktleverans kan inte behandla för lagerställe 1 % eftersom lager styrning har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="a1c39-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="a1c39-125">Ange ett annat lagerställe som inte är aktiverat för lagerstyrning".</span><span class="sxs-lookup"><span data-stu-id="a1c39-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a1c39-126">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="a1c39-126">Issue description</span></span>

<span data-ttu-id="a1c39-127">En artikel läggs till på en försäljningsrad för direktleverans från ett lagerställe som är aktiverat för lagerstyrning (WMS).</span><span class="sxs-lookup"><span data-stu-id="a1c39-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="a1c39-128">Det här felmeddelandet visas när försäljningsraden uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a1c39-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="a1c39-129">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="a1c39-129">Issue resolution</span></span>

<span data-ttu-id="a1c39-130">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="a1c39-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="a1c39-131">För närvarande stöder inte WMS direktleverans.</span><span class="sxs-lookup"><span data-stu-id="a1c39-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="a1c39-132">Om du vill använda direktleverans måste du därför välja en icke-WMS artikel och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a1c39-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>
