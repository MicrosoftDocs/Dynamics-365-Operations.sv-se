---
title: Karantänorder
description: Detta ämne beskriver hur du använder karantänorder för att blockera lager.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956192"
---
# <a name="quarantine-orders"></a><span data-ttu-id="39e5f-103">Karantänorder</span><span class="sxs-lookup"><span data-stu-id="39e5f-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39e5f-104">Detta ämne beskriver hur du använder karantänorder för att blockera lager.</span><span class="sxs-lookup"><span data-stu-id="39e5f-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="39e5f-105">Med karantänorder kan du spärra lager.</span><span class="sxs-lookup"><span data-stu-id="39e5f-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="39e5f-106">Du kanske vill sätta artiklar i karantän på grund av kvalitetskontroll.</span><span class="sxs-lookup"><span data-stu-id="39e5f-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="39e5f-107">Lager som har varit i karantän överförs till ett karantänlagerställe.</span><span class="sxs-lookup"><span data-stu-id="39e5f-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="39e5f-108">Om du använder avancerade lagerstyrningsprocesser (i Lagerstyrning) används bearbetning i karantänorder endast för returförsäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="39e5f-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="39e5f-109">Sätta lagerbehållningsartiklar i karantän</span><span class="sxs-lookup"><span data-stu-id="39e5f-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="39e5f-110">När du sätter objekt i karantän kan du antingen skapa karantänorder manuellt eller ställa in systemet för att skapa dem automatiskt under inkommande bearbetning.</span><span class="sxs-lookup"><span data-stu-id="39e5f-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="39e5f-111">Om du vill ställa in systemet att automatiskt generera karantänorder följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="39e5f-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="39e5f-112">Gå till **Lagerhantering \> Inställningar \> Lager \> Modellgrupper för artiklar**.</span><span class="sxs-lookup"><span data-stu-id="39e5f-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="39e5f-113">Välj en relevant modellgrupp i listfönstret eller skapa en ny modellgrupp.</span><span class="sxs-lookup"><span data-stu-id="39e5f-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="39e5f-114">På snabbfliken **Lagerpolicyer** väljer du kryssrutan **Karantänhantering**.</span><span class="sxs-lookup"><span data-stu-id="39e5f-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="39e5f-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="39e5f-115">Close the page.</span></span>
1. <span data-ttu-id="39e5f-116">I fältet **Karantänlagerställe** för mottagande lagerställen anger du ett förvalt karantänlagerställe.</span><span class="sxs-lookup"><span data-stu-id="39e5f-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="39e5f-117">När en artikel som registreras som inleverans på lagerstället tillhör en modellgrupp där kryssrutan **Karantänhantering** har valts, kommer systemet att generera en karantänorder för den.</span><span class="sxs-lookup"><span data-stu-id="39e5f-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="39e5f-118">Karantänordern ger medarbetare instruktioner att flytta artikeln till karantänlagerstället.</span><span class="sxs-lookup"><span data-stu-id="39e5f-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="39e5f-119">När du skapar karantänorder manuellt på sidan **Karantänorder** måste inte artikeln vara inställd för karantänhantering i den associerade artikelmodellgruppen.</span><span class="sxs-lookup"><span data-stu-id="39e5f-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="39e5f-120">För den här processen måste du ange lagerbehållning som ska finns i karantän och karantänlagerstället som ska användas.</span><span class="sxs-lookup"><span data-stu-id="39e5f-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="39e5f-121">Du kan använda karantänorderstatusen för att planera processen.</span><span class="sxs-lookup"><span data-stu-id="39e5f-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="39e5f-122">Karantänorder status</span><span class="sxs-lookup"><span data-stu-id="39e5f-122">Quarantine order statuses</span></span>

<span data-ttu-id="39e5f-123">Karantänorder kan ha följande status:</span><span class="sxs-lookup"><span data-stu-id="39e5f-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="39e5f-124">Skapad</span><span class="sxs-lookup"><span data-stu-id="39e5f-124">Created</span></span>
- <span data-ttu-id="39e5f-125">Startat</span><span class="sxs-lookup"><span data-stu-id="39e5f-125">Started</span></span>
- <span data-ttu-id="39e5f-126">Rapporterat som färdigt</span><span class="sxs-lookup"><span data-stu-id="39e5f-126">Reported as finished</span></span>
- <span data-ttu-id="39e5f-127">Avslutat</span><span class="sxs-lookup"><span data-stu-id="39e5f-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="39e5f-128">Skapad</span><span class="sxs-lookup"><span data-stu-id="39e5f-128">Created</span></span>

<span data-ttu-id="39e5f-129">När en karantänorder skapats manuellt, men posten är inte lagt i karantänlagerställe, karantänordern har status **Skapad**.</span><span class="sxs-lookup"><span data-stu-id="39e5f-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="39e5f-130">Två lagertransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="39e5f-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="39e5f-131">En transaktion är en utlevererad transaktion som kan ha status **Har beställts**, **Fysiskt reserverat**, eller **Plockad**.</span><span class="sxs-lookup"><span data-stu-id="39e5f-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="39e5f-132">Den andra transaktionen är en inleveranstransaktionen som kan ha statusen **Beställd** eller **Registrerad** vid karantänlagerstället.</span><span class="sxs-lookup"><span data-stu-id="39e5f-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="39e5f-133">Du kan reservera, plocka och registrera uppdateringar i lagret med vanliga processer.</span><span class="sxs-lookup"><span data-stu-id="39e5f-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="39e5f-134">Startat</span><span class="sxs-lookup"><span data-stu-id="39e5f-134">Started</span></span>

<span data-ttu-id="39e5f-135">När en karantänorder har statusen **Startat** lagret överförs från det vanliga lagret till karantänlagerstället och två lagertransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="39e5f-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="39e5f-136">En transaktion har status **dras av** och den andra transaktionen har status **Mottaget**.</span><span class="sxs-lookup"><span data-stu-id="39e5f-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="39e5f-137">Samtidigt två lagertransaktioner skapas för att hantera transfer tur och retur.</span><span class="sxs-lookup"><span data-stu-id="39e5f-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="39e5f-138">Dessa transaktioner är inte daterade.</span><span class="sxs-lookup"><span data-stu-id="39e5f-138">These transactions aren't dated.</span></span> <span data-ttu-id="39e5f-139">En transaktion har status **Reserverad fysiska**, och den andra transaktionen har status som **beställts**.</span><span class="sxs-lookup"><span data-stu-id="39e5f-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="39e5f-140">Rapporterat som färdigt</span><span class="sxs-lookup"><span data-stu-id="39e5f-140">Reported as finished</span></span>

<span data-ttu-id="39e5f-141">Om du vill rapportera en startad karantänorder som färdig, öppnar du ordern och väljer **Rapportera som färdig** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="39e5f-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="39e5f-142">Posten är frisläppt från karantänen men ännu inte flyttad tillbaka till det vanliga lagerstället.</span><span class="sxs-lookup"><span data-stu-id="39e5f-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="39e5f-143">Förflyttningen tillbaka till det vanliga lagerstället kan bearbetas via en journal för artikelinförsel som kan initieras under rapporteringen som en färdig process.</span><span class="sxs-lookup"><span data-stu-id="39e5f-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="39e5f-144">Avslutat</span><span class="sxs-lookup"><span data-stu-id="39e5f-144">Ended</span></span>

<span data-ttu-id="39e5f-145">När en karantänorder avslutas, objektet flyttas från karantänlagerstället tillbaka till vanliga lagret.</span><span class="sxs-lookup"><span data-stu-id="39e5f-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="39e5f-146">Status för objekt transaktion *säljs* på karantänlagerställe och *köpas* på regelbundna lager.</span><span class="sxs-lookup"><span data-stu-id="39e5f-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="39e5f-147">Karantänorder skrot</span><span class="sxs-lookup"><span data-stu-id="39e5f-147">Quarantine order scrap</span></span>

<span data-ttu-id="39e5f-148">Som en del av karantänorderprocessen du kan kassera lagerartiklar.</span><span class="sxs-lookup"><span data-stu-id="39e5f-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="39e5f-149">När du bearbetar kassationer kommer lagerstatusen att anges som *Sålt* genom en ärendetransaktion från karantänlagerstället.</span><span class="sxs-lookup"><span data-stu-id="39e5f-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39e5f-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="39e5f-150">Additional resources</span></span>

- [<span data-ttu-id="39e5f-151">Lagerspärr</span><span class="sxs-lookup"><span data-stu-id="39e5f-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
