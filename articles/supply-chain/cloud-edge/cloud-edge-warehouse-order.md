---
title: Lagerställeorder för moln- och kantskalningsenheter
description: Det här ämnet ger information om den lagerställeorderkapacitet som används som en del av arbetsbelastningen för lagerställeenheter.
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f2401102ab44f5c24f5cd6f545f30438db0a36cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836696"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="b7c4b-103">Lagerställeorder för moln- och kantskalningsenheter</span><span class="sxs-lookup"><span data-stu-id="b7c4b-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="b7c4b-104">Inte alla företagsfunktioner stöds fullt ut i den allmänna förhandsgranskningen när enheter för belastningsenheter används.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="b7c4b-105">Om du använder skalningsenheter, se till att bara använda de processer som det här ämnet explicit beskriver som det stöds.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="b7c4b-106">Vad är lagerställeorder?</span><span class="sxs-lookup"><span data-stu-id="b7c4b-106">What are warehouse orders?</span></span>

<span data-ttu-id="b7c4b-107">*Lagerställeorder* är en typ av order som skapades för att stödja distributioner av hubb och lagerställe skalningsenheter.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="b7c4b-108">De låter dig ta emot lager när du kör en lagerställearbetsbelastning på en skalenhet.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="b7c4b-109">De används för närvarande bara för inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="b7c4b-110">Lagerställeorder används som en del av bearbetningen av lagerstyrning, till exempel när mobilappen för distributionslagerhantering används för att registrera fysisk lagerbehållning under bearbetning av en inkommande inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-110">Warehouse orders are used as part of warehouse management processing, such as when the Warehouse Management mobile app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="b7c4b-111">Lagerställeorder skapas som en del av processen *Släpp till distributionslager* som är tillgänglig för inköpsorder som anger ett lagerställe i skalningsenhet som är aktiverad för att använda lagerstyrningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7c4b-112">Lagerställeorder är bara tillgängliga i distributioner som använder [arbetsbelastning i distributionslagerhantering för moln- och kantskalningsenheter](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="b7c4b-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="b7c4b-113">Skapa en lagerorder</span><span class="sxs-lookup"><span data-stu-id="b7c4b-113">Create a warehouse order</span></span>

<span data-ttu-id="b7c4b-114">Följ dessa steg för att skapa en lagerorder.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="b7c4b-115">Logga in på instansen av Microsoft Dynamics 365 Supply Chain Management som körs i hubben.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="b7c4b-116">(Du måste initiera processen *Släpp till distributionslager* när du är inloggad på hubben.)</span><span class="sxs-lookup"><span data-stu-id="b7c4b-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="b7c4b-117">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="b7c4b-118">I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="b7c4b-119">För att se relaterade orderrader för lagerställe, öppna relevant inköpsorder, välj en rad i avsnittet **Inköpsorderrader** och sedan i verktygsfältet, välj **lagerställe \> orderrader för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="b7c4b-120">Om du vill visa alla raderna går du till **Hantering av distributionslager \> Förfrågningar och rapporter \> Orderrader för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

<span data-ttu-id="b7c4b-121">Du kan också utlösa processen *Frisläpp till lagerställe* från ett batchjobb genom att gå till **Lagerstyrning > Frisläpp till lagerställe > Automatisk frisläppning av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-121">You can also trigger the *Release to warehouse* process from a batch job by going to **Warehouse management > Release to warehouse > Automatic release of purchase orders**.</span></span> <span data-ttu-id="b7c4b-122">När du ställer in batchjobbet kan du välja specifika inköpsorderrader baserade på en fråga.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-122">When setting up the batch job, you can select specific purchase order lines based on a query.</span></span> <span data-ttu-id="b7c4b-123">Ett vanligt scenario är att ställa in ett återkommande batchjobb som frisläpper alla bekräftade inköpsorderrader som förväntas komma in nästa dag.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-123">A typical scenario would be to set up a recurrent batch job that releases all the confirmed purchase order lines expected to arrive the next day.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="b7c4b-124">Annullera en lagerorder</span><span class="sxs-lookup"><span data-stu-id="b7c4b-124">Cancel a warehouse order</span></span>

<span data-ttu-id="b7c4b-125">Som en del av processen *Släpp till distributionslager* är lagertransaktioner för inköpsorder kopplade till lagerorder och låsta från att uppdateras av hubben.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-125">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="b7c4b-126">Om du av misstag frisläppt till lagerstället, eller om du har någon annan orsak till att skapa orderrader för lagerställe, kan du begära att annullera orderraderna för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-126">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="b7c4b-127">Följ dessa steg för att annullera orderrader för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-127">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="b7c4b-128">Logga in på instansen av Supply Chain Management som körs i hubben.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-128">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="b7c4b-129">Gå till **Hantering av distributionslager \> Förfrågningar och rapporter \> Orderrader för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-129">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="b7c4b-130">Välj relevant rad.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-130">Select the relevant line.</span></span>
1. <span data-ttu-id="b7c4b-131">I åtgärdsfönstret, markera **Annullera orderrader för lagerstället**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-131">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c4b-132">En begäran om att annullera rader nekas för alla rader som redan väntar på att annulleras eller som har förs del i ett lagerställe där arbetsbelastningen körs på en skalningsenhet.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-132">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="b7c4b-133">Övervaka en lagerorder</span><span class="sxs-lookup"><span data-stu-id="b7c4b-133">Monitor a warehouse order</span></span>

<span data-ttu-id="b7c4b-134">I vyn **Orderrader för lagerställe** kan du övervaka förloppet för inkommande meddelanden genom att granska värdena i kolumnen **kvantitet kvar att inleverera**.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-134">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="b7c4b-135">Om du vill visa information om arbete som har utförts med hjälp av mobilappen för distributionslagerhantering följer du ett av stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-135">To view details that are related to work that is done by using the Warehouse Management mobile app, follow one of these steps.</span></span>

- <span data-ttu-id="b7c4b-136">Gå till **Hantering av distributionslager \> Förfrågningar och rapporter \> Orderrader för lagerställe** och använd filtret för att hitta de rader du letar efter.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-136">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="b7c4b-137">Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder** och öppna relevant inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-137">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="b7c4b-138">I avsnittet **Inköpsorderrader**, markera en eller flera rader och välj sedan **lagerställe \> Inleveransposter för lagerställe** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="b7c4b-138">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]