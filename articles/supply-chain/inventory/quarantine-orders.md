---
title: "Karantänorder"
description: "Den här artikeln beskriver hur karantänorder används för att blockera lagret."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 17dde4a4e3380beb98eeb71c719fb898b40a94f7
ms.contentlocale: sv-se
ms.lasthandoff: 09/12/2017

---

# <a name="quarantine-orders"></a><span data-ttu-id="f69cc-103">Karantänorder</span><span class="sxs-lookup"><span data-stu-id="f69cc-103">Quarantine orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f69cc-104">Den här artikeln beskriver hur karantänorder används för att blockera lagret.</span><span class="sxs-lookup"><span data-stu-id="f69cc-104">This article describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="f69cc-105">Karantänorder kan användas för att blockera lagret.</span><span class="sxs-lookup"><span data-stu-id="f69cc-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="f69cc-106">Du kanske vill sätta artiklar i karantän på grund av kvalitetskontroll.</span><span class="sxs-lookup"><span data-stu-id="f69cc-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="f69cc-107">Lager som har varit i karantän överförs till ett karantänlagerställe.</span><span class="sxs-lookup"><span data-stu-id="f69cc-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="f69cc-108">**Obs!** Om du använder avancerade lagerstyrningsprocesser (i Lagerstyrning) används bearbetning i karantänorder endast för returförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="f69cc-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-onhand-inventory-items"></a><span data-ttu-id="f69cc-109">Sätta lagerbehållningsartiklar i karantän</span><span class="sxs-lookup"><span data-stu-id="f69cc-109">Quarantine onhand inventory items</span></span>
<span data-ttu-id="f69cc-110">När du sätter objekt i karantän kan du antingen skapa karantänorder manuellt eller ställa in systemet för att skapa karantänorder automatiskt under inkommande bearbetning.</span><span class="sxs-lookup"><span data-stu-id="f69cc-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="f69cc-111">Skapa karantänorder automatiskt genom att välja alternativet **Karantänhantering** på fliken **Lagerpolicyer** på sidan **Artikelmodellgrupper**.</span><span class="sxs-lookup"><span data-stu-id="f69cc-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="f69cc-112">Du måste även ange ett standardkarantänlagerställe i **Karantänlagerställe**-fältet för mottagande lagerställen.</span><span class="sxs-lookup"><span data-stu-id="f69cc-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="f69cc-113">När det fysiska, tillgängliga lagret registreras i en inköpsorder eller produktionsorder, flyttas objekt i karantän automatisk till ett karantänlagerställe i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f69cc-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f69cc-114">Dessa förflyttningar inträffar eftersom karantänorderns status ändras till **Startat**.</span><span class="sxs-lookup"><span data-stu-id="f69cc-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="f69cc-115">När du skapar karantänorder manuellt, artikeln måste inte vara inställd för karantänhantering i den associerade artikelmodellgruppen.</span><span class="sxs-lookup"><span data-stu-id="f69cc-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="f69cc-116">För den här processen måste du ange lagerbehållning som ska finns i karantän och karantänlagerstället som ska användas.</span><span class="sxs-lookup"><span data-stu-id="f69cc-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="f69cc-117">Du kan använda karantänorderstatusen för att planera processen.</span><span class="sxs-lookup"><span data-stu-id="f69cc-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="f69cc-118">Karantänorder status</span><span class="sxs-lookup"><span data-stu-id="f69cc-118">Quarantine order statuses</span></span>
<span data-ttu-id="f69cc-119">Karantänorder kan ha följande status:</span><span class="sxs-lookup"><span data-stu-id="f69cc-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="f69cc-120">Skapad</span><span class="sxs-lookup"><span data-stu-id="f69cc-120">Created</span></span>
-   <span data-ttu-id="f69cc-121">Startat</span><span class="sxs-lookup"><span data-stu-id="f69cc-121">Started</span></span>
-   <span data-ttu-id="f69cc-122">Rapporterat som färdigt</span><span class="sxs-lookup"><span data-stu-id="f69cc-122">Reported as finished</span></span>
-   <span data-ttu-id="f69cc-123">Avslutat</span><span class="sxs-lookup"><span data-stu-id="f69cc-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="f69cc-124">Skapad</span><span class="sxs-lookup"><span data-stu-id="f69cc-124">Created</span></span>

<span data-ttu-id="f69cc-125">När en karantänorder skapats manuellt, men posten är inte lagt i karantänlagerställe, karantänordern har status **Skapad**.</span><span class="sxs-lookup"><span data-stu-id="f69cc-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="f69cc-126">Två lagertransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="f69cc-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="f69cc-127">En transaktion är en utlevererad transaktion som kan ha status **Har beställts**, **Fysiskt reserverat**, eller **Plockad**.</span><span class="sxs-lookup"><span data-stu-id="f69cc-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="f69cc-128">Den andra transaktionen är en inleveranstransaktionen som kan ha statusen **Beställd** eller **Registrerad** vid karantänlagerstället.</span><span class="sxs-lookup"><span data-stu-id="f69cc-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="f69cc-129">Du kan reservera, plocka och registrera uppdateringar i lagret med vanliga processer.</span><span class="sxs-lookup"><span data-stu-id="f69cc-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="f69cc-130">Startat</span><span class="sxs-lookup"><span data-stu-id="f69cc-130">Started</span></span>

<span data-ttu-id="f69cc-131">När en karantänorder har statusen **Startat** lagret överförs från det vanliga lagret till karantänlagerstället och två lagertransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="f69cc-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="f69cc-132">En transaktion har status **dras av** och den andra transaktionen har status **Mottaget**.</span><span class="sxs-lookup"><span data-stu-id="f69cc-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="f69cc-133">Samtidigt två lagertransaktioner skapas för att hantera transfer tur och retur.</span><span class="sxs-lookup"><span data-stu-id="f69cc-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="f69cc-134">Dessa transaktioner är inte daterade.</span><span class="sxs-lookup"><span data-stu-id="f69cc-134">These transactions aren't dated.</span></span> <span data-ttu-id="f69cc-135">En transaktion har status **Reserverad fysiska**, och den andra transaktionen har status som **beställts**.</span><span class="sxs-lookup"><span data-stu-id="f69cc-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="f69cc-136">Rapporterat som färdigt</span><span class="sxs-lookup"><span data-stu-id="f69cc-136">Reported as finished</span></span>

<span data-ttu-id="f69cc-137">Genom att klicka på **rapportera som färdiga**, du kan rapportera en började karantänorder som färdiga.</span><span class="sxs-lookup"><span data-stu-id="f69cc-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="f69cc-138">Posten är frisläppt från karantänen men ännu inte flyttad tillbaka till den vanliga lager.</span><span class="sxs-lookup"><span data-stu-id="f69cc-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="f69cc-139">Förflyttningen tillbaka till det vanliga lagret kan vara bearbetad via en alternativ artikelinförsel som kan initieras under processen Rapportera som färdig.</span><span class="sxs-lookup"><span data-stu-id="f69cc-139">The movement back to the regular warehouse can be procesed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="f69cc-140">Avslutat</span><span class="sxs-lookup"><span data-stu-id="f69cc-140">Ended</span></span>

<span data-ttu-id="f69cc-141">När en karantänorder avslutas, objektet flyttas från karantänlagerstället tillbaka till vanliga lagret.</span><span class="sxs-lookup"><span data-stu-id="f69cc-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="f69cc-142">Status för objekt transaktion **säljs** på karantänlagerställe och **köpas** på regelbundna lager.</span><span class="sxs-lookup"><span data-stu-id="f69cc-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="f69cc-143">Karantänorder skrot</span><span class="sxs-lookup"><span data-stu-id="f69cc-143">Quarantine order scrap</span></span>
<span data-ttu-id="f69cc-144">Som en del av karantänorderprocessen du kan kassera lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="f69cc-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="f69cc-145">När du bearbetar kassationer, lagerstatusen kommer att sättas till **Sålt** genom en inleveranstransaktion från karantänlagerstället.</span><span class="sxs-lookup"><span data-stu-id="f69cc-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="see-also"></a><span data-ttu-id="f69cc-146">Se även</span><span class="sxs-lookup"><span data-stu-id="f69cc-146">See also</span></span>
--------

[<span data-ttu-id="f69cc-147">Lagerspärr</span><span class="sxs-lookup"><span data-stu-id="f69cc-147">Inventory blocking</span></span>](inventory-blocking.md)

