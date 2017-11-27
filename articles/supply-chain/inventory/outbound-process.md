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
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1b8b17b719713097d77a117cca53eff6886ff1c7
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="outbound-process"></a><span data-ttu-id="7694c-103">Utgående process</span><span class="sxs-lookup"><span data-stu-id="7694c-103">Outbound process</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7694c-104">I det här avsnittet finns en översikt över utgående processer inom lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="7694c-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="7694c-105">Utleveransorder</span><span class="sxs-lookup"><span data-stu-id="7694c-105">Output orders</span></span>

<span data-ttu-id="7694c-106">Utgående order används för att sammanlänka rader i försäljningsorder och rader i överföringsorder med de utgående plockprocesser som använder plocklistor.</span><span class="sxs-lookup"><span data-stu-id="7694c-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="7694c-107">När plocklistor skapas ur antingen försäljningsorder eller överföringsorder, skapas utgående order och leveranser automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7694c-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="7694c-108">En plocklista har en individuell relation till en leverans.</span><span class="sxs-lookup"><span data-stu-id="7694c-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="7694c-109">Överföringsorderns leverans eller försäljningsorderns packsedel kan bearbetas från leveransen.</span><span class="sxs-lookup"><span data-stu-id="7694c-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="7694c-110">Följande diagram visar en översikt över processen för utgående order.</span><span class="sxs-lookup"><span data-stu-id="7694c-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="7694c-111">[![Översikt över processen för utgående order](./media/outbound-order.png)](./media/outbound-order.png).</span><span class="sxs-lookup"><span data-stu-id="7694c-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="7694c-112">Du kan skapa regler för utgående order om du vill definiera hur programmet ska hantera den utgående processen.</span><span class="sxs-lookup"><span data-stu-id="7694c-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="7694c-113">Du kan använda dessa regler för att styra leveransprocessen.</span><span class="sxs-lookup"><span data-stu-id="7694c-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="7694c-114">Inte minst kan du använda reglerna för att styra det processtadium under vilket en leverans kan skickas.</span><span class="sxs-lookup"><span data-stu-id="7694c-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="7694c-115">Följande inställningar anger hur utgående processer hanteras.</span><span class="sxs-lookup"><span data-stu-id="7694c-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="7694c-116">Välja vidarebefordrandestatus för försäljnings- och överföringsorder</span><span class="sxs-lookup"><span data-stu-id="7694c-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="7694c-117">Gå till **Kundreskontra** \> **Inställningar** \> **Kundreskontraparametrar**. På fliken **Uppdateringar** väljer du sedan ett värde i fältet **Välja status för vidarebefordran**.</span><span class="sxs-lookup"><span data-stu-id="7694c-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="7694c-118">[![Välja statusfält för vidarebefordran för försäljningsorder](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="7694c-119">Om fältet **Välja status för vidarebefordran** har angetts som **Slutförd** sker plockförfarandet automatiskt som ett led i att generera plocklistor.</span><span class="sxs-lookup"><span data-stu-id="7694c-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="7694c-120">Om fältet har angetts som **Aktiverat** måste raderna för plocklistor uppdateras manuellt.</span><span class="sxs-lookup"><span data-stu-id="7694c-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="7694c-121">Samma inställning gäller överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="7694c-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="7694c-122">Gå till **Lagerhantering** \> **Inställningar** \> **Parametrar för lager- och lagerställehantering**. På fliken **Transport** väljer du sedan ett värde i fältet **Välja status för vidarebefordran**.</span><span class="sxs-lookup"><span data-stu-id="7694c-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="7694c-123">[![Välja statusfält för vidarebefordran för överföringsorder](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="7694c-124">Avsluta utgående lagerorder</span><span class="sxs-lookup"><span data-stu-id="7694c-124">End output inventory orders</span></span>

<span data-ttu-id="7694c-125">Gå till **Lagerhantering** \> **Inställningar** \> **Parametrar för lager- och lagerställehantering**. På fliken **Allmänt** väljer du sedan alternativet **Avsluta utgående lagerorder**.</span><span class="sxs-lookup"><span data-stu-id="7694c-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="7694c-126">[![Avsluta alternativet för utgående lagerorder](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="7694c-127">När lagerarbetaren minskar plocklistekvantiteter ska motsvarande lagerorderkvantiteter tas bort från leveransen.</span><span class="sxs-lookup"><span data-stu-id="7694c-127">When the warehouse worker reduces the picking list quantities, then the corresponding inventory order quantities will be removed from the shipment.</span></span> <span data-ttu-id="7694c-128">När plocklistan uppdateras vid en viss tidpunkt rapporteras återstående kvantiteter tillbaka ordern om alternativet **Avsluta utlagerorder** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7694c-128">When the picking list is updated at a point in time, the remaining quantities get reported back to the order if the **End output inventory order** option is set to **Yes**.</span></span> <span data-ttu-id="7694c-129">Om alternativet **Avsluta utlagerorder** är inställt på **Nr**, behålls återstående kvantiteterna som en öppen utgående orderkvantitet och måste läggas till en ny plocklista som en del av funktionen **öppna utleveransorder**.</span><span class="sxs-lookup"><span data-stu-id="7694c-129">If the **End output inventory order** option is set to **No**, the remaining quantities are kept as an open output order quantity and must be added to a new picking list as part of the **Open output orders** functionality.</span></span> 

<span data-ttu-id="7694c-130">[![Öppna kommandot för utgående order i funktionsmenyn](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-130">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="7694c-131">[![Funktionsmenyn på sidan för att öppna utgående order](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-131">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="7694c-132">Minska kvantiteten</span><span class="sxs-lookup"><span data-stu-id="7694c-132">Reduce quantity</span></span>

<span data-ttu-id="7694c-133">Den tredje parametern du kan använda som ett led i processen att skapa plocklistor är parametern **Minska kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="7694c-133">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="7694c-134">Inställningen för denna parameter samarbetar med inställningen **Reservation**, som utlöser en reservationsprocess som ett led i frisläppandet till lagret.</span><span class="sxs-lookup"><span data-stu-id="7694c-134">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="7694c-135">[![Parameter för kvantitetsminskning](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-135">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="7694c-136">Exempel på en utgående process för en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="7694c-136">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="7694c-137">För detta exempel finns en försäljningsorder för två artiklar.</span><span class="sxs-lookup"><span data-stu-id="7694c-137">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="7694c-138">I samband med att plocklistan skapas väljer du parametern **Minska kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="7694c-138">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="7694c-139">Du frisläpper och skapar plocklinor därför endast för tillgängliga varor.</span><span class="sxs-lookup"><span data-stu-id="7694c-139">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="7694c-140">Plocket måste rapporteras via en registreringsprocess för plocklistor (**Status för vidarebefordran av plock** = **Aktiverad**).</span><span class="sxs-lookup"><span data-stu-id="7694c-140">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="7694c-141">De varor som ännu inte har reserverats kommer att reserveras i samband med att plocklistan skapas.</span><span class="sxs-lookup"><span data-stu-id="7694c-141">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="7694c-142">Icke tillgängliga varor kan antingen plockas bort från försäljningsordern eller frisläppas till lagret för senare utgående bearbetning när varorna är tillgängliga för plock.</span><span class="sxs-lookup"><span data-stu-id="7694c-142">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="7694c-143">[![Uppdatera plocklistan](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-143">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="7694c-144">Så fort samtliga plocklinor har plockats på sidan **Registrera plocklist** har tillhörande leverans slutförts.</span><span class="sxs-lookup"><span data-stu-id="7694c-144">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="7694c-145">Processen för försäljningsordrarnas packsedlar kan edan initialiseras baserat på plockade varor.</span><span class="sxs-lookup"><span data-stu-id="7694c-145">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="7694c-146">[![Uppdatera utgående leveranser](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="7694c-146">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>

