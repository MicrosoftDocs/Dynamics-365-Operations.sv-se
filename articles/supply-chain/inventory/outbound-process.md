---
title: "Utgående process"
description: "I det här avsnittet finns en översikt över utgående processer inom lagerhantering."
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 9c09a7bd314bb9005eb0b6c69d7cccad1c30cfdb
ms.openlocfilehash: 7b395cab2184f8f9f3f50a7a595c6ed782645323
ms.contentlocale: sv-se
ms.lasthandoff: 10/04/2017

---

# <a name="outbound-process"></a><span data-ttu-id="0cce6-103">Utgående process</span><span class="sxs-lookup"><span data-stu-id="0cce6-103">Outbound process</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0cce6-104">I det här avsnittet finns en översikt över utgående processer inom lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="0cce6-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="0cce6-105">Utleveransorder</span><span class="sxs-lookup"><span data-stu-id="0cce6-105">Output orders</span></span>

<span data-ttu-id="0cce6-106">Utgående order används för att sammanlänka rader i försäljningsorder och rader i överföringsorder med de utgående plockprocesser som använder plocklistor.</span><span class="sxs-lookup"><span data-stu-id="0cce6-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="0cce6-107">När plocklistor skapas ur antingen försäljningsorder eller överföringsorder, skapas utgående order och leveranser automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0cce6-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="0cce6-108">En plocklista har en individuell relation till en leverans.</span><span class="sxs-lookup"><span data-stu-id="0cce6-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="0cce6-109">Överföringsorderns leverans eller försäljningsorderns packsedel kan bearbetas från leveransen.</span><span class="sxs-lookup"><span data-stu-id="0cce6-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="0cce6-110">Följande diagram visar en översikt över processen för utgående order.</span><span class="sxs-lookup"><span data-stu-id="0cce6-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="0cce6-111">[![Översikt över processen för utgående order](./media/outbound-order.png)](./media/outbound-order.png).</span><span class="sxs-lookup"><span data-stu-id="0cce6-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="0cce6-112">Du kan skapa regler för utgående order om du vill definiera hur programmet ska hantera den utgående processen.</span><span class="sxs-lookup"><span data-stu-id="0cce6-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="0cce6-113">Du kan använda dessa regler för att styra leveransprocessen.</span><span class="sxs-lookup"><span data-stu-id="0cce6-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="0cce6-114">Inte minst kan du använda reglerna för att styra det processtadium under vilket en leverans kan skickas.</span><span class="sxs-lookup"><span data-stu-id="0cce6-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="0cce6-115">Följande inställningar anger hur utgående processer hanteras.</span><span class="sxs-lookup"><span data-stu-id="0cce6-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="0cce6-116">Välja vidarebefordrandestatus för försäljnings- och överföringsorder</span><span class="sxs-lookup"><span data-stu-id="0cce6-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="0cce6-117">Gå till **Kundreskontra** \> **Inställningar** \> **Kundreskontraparametrar**. På fliken **Uppdateringar** väljer du sedan ett värde i fältet **Välja status för vidarebefordran**.</span><span class="sxs-lookup"><span data-stu-id="0cce6-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="0cce6-118">[![Välja statusfält för vidarebefordran för försäljningsorder](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="0cce6-119">Om fältet **Välja status för vidarebefordran** har angetts som **Slutförd** sker plockförfarandet automatiskt som ett led i att generera plocklistor.</span><span class="sxs-lookup"><span data-stu-id="0cce6-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="0cce6-120">Om fältet har angetts som **Aktiverat** måste raderna för plocklistor uppdateras manuellt.</span><span class="sxs-lookup"><span data-stu-id="0cce6-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="0cce6-121">Samma inställning gäller överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="0cce6-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="0cce6-122">Gå till **Lagerhantering** \> **Inställningar** \> **Parametrar för lager- och lagerställehantering**. På fliken **Transport** väljer du sedan ett värde i fältet **Välja status för vidarebefordran**.</span><span class="sxs-lookup"><span data-stu-id="0cce6-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="0cce6-123">[![Välja statusfält för vidarebefordran för överföringsorder](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="0cce6-124">Avsluta utgående lagerorder</span><span class="sxs-lookup"><span data-stu-id="0cce6-124">End output inventory orders</span></span>

<span data-ttu-id="0cce6-125">Gå till **Lagerhantering** \> **Inställningar** \> **Parametrar för lager- och lagerställehantering**. På fliken **Allmänt** väljer du sedan alternativet **Avsluta utgående lagerorder**.</span><span class="sxs-lookup"><span data-stu-id="0cce6-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="0cce6-126">[![Avsluta alternativet för utgående lagerorder](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="0cce6-127">Ibland kan visa lagerartiklar inte plockas som ett led i processen för plocklista.</span><span class="sxs-lookup"><span data-stu-id="0cce6-127">Sometimes, some items in inventory can't be picked as part of the picking list process.</span></span> <span data-ttu-id="0cce6-128">Denna situation kan exempelvis uppstå om en magermedarbetare minskar kvantiteterna i plocklinorna och bearbetar plocklistan.</span><span class="sxs-lookup"><span data-stu-id="0cce6-128">For example, this situation might occur if a warehouse worker reduces the quantities on picking lines and processes the picking list.</span></span> <span data-ttu-id="0cce6-129">Om alternativet **Avsluta utgående lagerorder** anges som **Ja** kommer återstående, icke plockade kvantiteter att rapporteras tillbaka till ordernivån.</span><span class="sxs-lookup"><span data-stu-id="0cce6-129">If the **End output inventory order** option is set to **Yes**, the remaining unpicked quantities are reported back to the order level.</span></span> <span data-ttu-id="0cce6-130">Om alternativet är inställt på **Nej** kommer återstående icke-plockade kvantiteter att även fortsatt att utgöra öppna orderkvantiteter.</span><span class="sxs-lookup"><span data-stu-id="0cce6-130">If the option is set to **No**, the remaining unpicked quantities are kept as an open output order quantity.</span></span> <span data-ttu-id="0cce6-131">I ett sådant fall förblir kvantiteterna frisläppta till lagret och måste läggas till i en ny plocklista som ett led i funktionen **Öppna utgående order**.</span><span class="sxs-lookup"><span data-stu-id="0cce6-131">In this case, the quantities remain released to the warehouse and must be added to a new picking list as part of the **Open output orders** functionality.</span></span>

<span data-ttu-id="0cce6-132">[![Öppna kommandot för utgående order i funktionsmenyn](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-132">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="0cce6-133">[![Funktionsmenyn på sidan för att öppna utgående order](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-133">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="0cce6-134">Minska kvantiteten</span><span class="sxs-lookup"><span data-stu-id="0cce6-134">Reduce quantity</span></span>

<span data-ttu-id="0cce6-135">Den tredje parametern du kan använda som ett led i processen att skapa plocklistor är parametern **Minska kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0cce6-135">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="0cce6-136">Inställningen för denna parameter samarbetar med inställningen **Reservation**, som utlöser en reservationsprocess som ett led i frisläppandet till lagret.</span><span class="sxs-lookup"><span data-stu-id="0cce6-136">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="0cce6-137">[![Parameter för kvantitetsminskning](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-137">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="0cce6-138">Exempel på en utgående process för en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="0cce6-138">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="0cce6-139">För detta exempel finns en försäljningsorder för två artiklar.</span><span class="sxs-lookup"><span data-stu-id="0cce6-139">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="0cce6-140">I samband med att plocklistan skapas väljer du parametern **Minska kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="0cce6-140">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="0cce6-141">Du frisläpper och skapar plocklinor därför endast för tillgängliga varor.</span><span class="sxs-lookup"><span data-stu-id="0cce6-141">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="0cce6-142">Plocket måste rapporteras via en registreringsprocess för plocklistor (**Status för vidarebefordran av plock** = **Aktiverad**).</span><span class="sxs-lookup"><span data-stu-id="0cce6-142">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="0cce6-143">De varor som ännu inte har reserverats kommer att reserveras i samband med att plocklistan skapas.</span><span class="sxs-lookup"><span data-stu-id="0cce6-143">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="0cce6-144">Icke tillgängliga varor kan antingen plockas bort från försäljningsordern eller frisläppas till lagret för senare utgående bearbetning när varorna är tillgängliga för plock.</span><span class="sxs-lookup"><span data-stu-id="0cce6-144">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="0cce6-145">[![Uppdatera plocklistan](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-145">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="0cce6-146">Så fort samtliga plocklinor har plockats på sidan **Registrera plocklist** har tillhörande leverans slutförts.</span><span class="sxs-lookup"><span data-stu-id="0cce6-146">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="0cce6-147">Processen för försäljningsordrarnas packsedlar kan edan initialiseras baserat på plockade varor.</span><span class="sxs-lookup"><span data-stu-id="0cce6-147">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="0cce6-148">[![Uppdatera utgående leveranser](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="0cce6-148">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>

