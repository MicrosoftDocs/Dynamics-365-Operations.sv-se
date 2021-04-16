---
title: Koncernintern planering
description: Det här ämnet beskriver koncernintern planering och förklarar hur du konfigurerar koncernintern planering med planeringsoptimering i Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5c9ab724034a9bb40cfe155b748a0c7e25978add
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833363"
---
# <a name="intercompany-planning"></a><span data-ttu-id="b2486-103">Koncernintern planering</span><span class="sxs-lookup"><span data-stu-id="b2486-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b2486-104">För vissa organisationer är logistikoperationer beroende av andra juridiska personer (företag) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b2486-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="b2486-105">Dessa operationer hanteras med koncernintern försäljning och inköp eftersom varje juridisk person har en separat kontoplan.</span><span class="sxs-lookup"><span data-stu-id="b2486-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="b2486-106">Det här ämnet beskriver koncernintern planering och förklarar hur du konfigurerar koncernintern planering med planeringsoptimering i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b2486-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b2486-107">I det här avsnittet används följande viktiga koncerninterna termer:</span><span class="sxs-lookup"><span data-stu-id="b2486-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="b2486-108">**Uppström** – en relativ referens i en firma eller leveranskedja.</span><span class="sxs-lookup"><span data-stu-id="b2486-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="b2486-109">Den visar rörelsen i råvaruleverantörens riktning.</span><span class="sxs-lookup"><span data-stu-id="b2486-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="b2486-110">**Nedström** – en relativ referens i en firma eller leveranskedja.</span><span class="sxs-lookup"><span data-stu-id="b2486-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="b2486-111">Den visar rörelsen i kundens riktning.</span><span class="sxs-lookup"><span data-stu-id="b2486-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="b2486-112">**Planerad koncernintern efterfrågan** – planerad efterfrågan för en produkt i ett företag, baserat på planerad efter frågan för produkten från ett underordnat företag.</span><span class="sxs-lookup"><span data-stu-id="b2486-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="b2486-113">Vid huvudplanering kan en plan i ett företag inkludera planerad koncernintern efter frågan som är relaterad till planerade order från en plan i ett annat företag.</span><span class="sxs-lookup"><span data-stu-id="b2486-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="b2486-114">Den här funktionen är användbar eftersom den ger full insyn i planerade order mellan företag.</span><span class="sxs-lookup"><span data-stu-id="b2486-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="b2486-115">Det säkerställer också att alla begärda planerade leveransorder skapas, utan att kräva att planerade order måste bekräftas för det koncerninterna behovet.</span><span class="sxs-lookup"><span data-stu-id="b2486-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="b2486-116">Om du kör huvudplaneringen från en huvudplan som inkluderar planerad efterföljande efterfrågan, tas planerade inköpsorder från de relaterade koncerninterna leverantörerna med i planen som efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="b2486-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="b2486-117">Obligatorisk inställning</span><span class="sxs-lookup"><span data-stu-id="b2486-117">Required setup</span></span>

<span data-ttu-id="b2486-118">Om du vill använda koncernintern planering måste du förbereda systemet på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="b2486-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="b2486-119">De relevanta produkterna måste frisläppas på alla berörda företag.</span><span class="sxs-lookup"><span data-stu-id="b2486-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="b2486-120">Mer information finns i [Konfigurera och använd koncernintern handel i Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) på Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="b2486-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="b2486-121">Efterföljande efterfrågan måste täckas av inköp från en leverantör som har en koncernintern relation till det överordnade företaget och relevanta standard lagerdimensioner (webbplats och lagerställe) för kunden.</span><span class="sxs-lookup"><span data-stu-id="b2486-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="b2486-122">Mer information finns i [Konfigurera och använd koncernintern handel i Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) på Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="b2486-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="b2486-123">Huvudplanen i det överordnade företaget måste inkludera planerad efterföljande efterfrågan och det relevanta företaget och huvudplanen måste anges i de efterföljande planerna.</span><span class="sxs-lookup"><span data-stu-id="b2486-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="b2486-124">Inkludera underordnad planerad efterfrågan</span><span class="sxs-lookup"><span data-stu-id="b2486-124">Include planned downstream demand</span></span>

<span data-ttu-id="b2486-125">Följ dessa steg för att konfigurera huvudplanen så att den omfattar planerad efterföljande efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="b2486-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="b2486-126">Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.</span><span class="sxs-lookup"><span data-stu-id="b2486-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="b2486-127">Välj eller skapa en huvudplan.</span><span class="sxs-lookup"><span data-stu-id="b2486-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="b2486-128">På snabbfliken **Koncernintern planering** anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="b2486-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="b2486-129">**Inkludera planerad efterföljande efterfrågan** – Ange det här alternativet till *Ja* om du vill aktivera koncern internplanering för huvudplanen.</span><span class="sxs-lookup"><span data-stu-id="b2486-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="b2486-130">**Efterföljande planer** – Om du anger alternativet **Inkludera planerad efterföljande efterfrågan** till *Ja*, använd verktygsfältet och rutnätet för att lägga till önskade huvudplaner från andra företag.</span><span class="sxs-lookup"><span data-stu-id="b2486-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="b2486-131">Peg över flera företag med hjälp av pegging på flera nivåer</span><span class="sxs-lookup"><span data-stu-id="b2486-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="b2486-132">I pegging på flera nivåer kan du visa pegging över flera företag för att visa den initiala källan för efterfrågan som täcks av en tillgång.</span><span class="sxs-lookup"><span data-stu-id="b2486-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="b2486-133">Följ stegen nedan om du vill visa pegging-information på flera nivåer.</span><span class="sxs-lookup"><span data-stu-id="b2486-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="b2486-134">Gå till **Huvudplanering \> Huvudplanering \> Planerade order**.</span><span class="sxs-lookup"><span data-stu-id="b2486-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="b2486-135">Välj eller öppna en planerad order.</span><span class="sxs-lookup"><span data-stu-id="b2486-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="b2486-136">I åtgärdsfönstret på fliken **Visa** i gruppen **Krav**, välj **Pegging på flera nivåer**.</span><span class="sxs-lookup"><span data-stu-id="b2486-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="b2486-137">Koncerninternt exempel som inbegriper två företag</span><span class="sxs-lookup"><span data-stu-id="b2486-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="b2486-138">I det här exemplet skapas en planerad tillverkningsorder i USMF-företaget för att täcka en försäljningsorder i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="b2486-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="b2486-139">I USMF är direkt efterfrågan planerad koncernintern efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="b2486-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="b2486-140">För att denna efterfrågan ska visas i USMF körs huvudplaneringen först i DEMF och sedan i USMF.</span><span class="sxs-lookup"><span data-stu-id="b2486-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="b2486-141">Följande illustration visar hur det här exemplet kan visas på sidan **Pegging på flera nivåer** för den planerade tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="b2486-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Koncerninternt exempel som inbegriper två företag](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="b2486-143">Koncerninternt exempel som inbegriper tre företag</span><span class="sxs-lookup"><span data-stu-id="b2486-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="b2486-144">I det här exemplet skapas en planerad inköpsorder i USMF-företaget för att täcka en försäljningsorder i FRRT-företaget.</span><span class="sxs-lookup"><span data-stu-id="b2486-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="b2486-145">I DEMF- och USMF-företag är direkt efterfrågan planerad koncernintern efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="b2486-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="b2486-146">För att denna efterfrågan ska visas i USMF körs huvudplaneringen först i FRRT, sedan i DEMF och slutligen i USMF.</span><span class="sxs-lookup"><span data-stu-id="b2486-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="b2486-147">Följande illustration visar hur det här exemplet kan visas på sidan **Pegging på flera nivåer** för den planerade tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="b2486-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Koncerninternt exempel som inbegriper tre företag](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]