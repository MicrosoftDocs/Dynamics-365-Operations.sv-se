---
title: "Transporthanteringsöversikt"
description: "I det här avsnittet finns en översikt över transporthanteringsfunktionen i Microsoft Dynamics 365 for Finance and Operations."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 94ab026e44254f0f05b56dfb53738d14e8dd272d
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="transportation-management-overview"></a><span data-ttu-id="f56f2-103">Transporthanteringsöversikt</span><span class="sxs-lookup"><span data-stu-id="f56f2-103">Transportation management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f56f2-104">I det här avsnittet finns en översikt över transporthanteringsfunktionen i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f56f2-104">This topic gives an overview of the transportation management functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="f56f2-105">Transporthantering låter dig använda företagets transporter och även identifiera leverantörs- och ruttlösningar för ingående och utgående order.</span><span class="sxs-lookup"><span data-stu-id="f56f2-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="f56f2-106">Du kan till exempel identifiera det snabbaste flödet eller den minst kostsamma tariffen för en leverans.</span><span class="sxs-lookup"><span data-stu-id="f56f2-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="f56f2-107">I tabellen nedan beskrivs de huvudsakliga scenarierna för att använda Transporthantering i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f56f2-107">The following table describes the main scenarios for using Transportation management in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f56f2-108">Scenario</span><span class="sxs-lookup"><span data-stu-id="f56f2-108">Scenario</span></span></th>
<th><span data-ttu-id="f56f2-109">Hur transporthantering kan hjälpa</span><span class="sxs-lookup"><span data-stu-id="f56f2-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f56f2-110">Använd externa logistikleverantörer för transportaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="f56f2-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="f56f2-111">Använd transporthantering för ingående och/eller utgående transporter.</span><span class="sxs-lookup"><span data-stu-id="f56f2-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f56f2-112">Företagets egen flotta är tillgänglig för leverans/upphämtning och leveransavgifter skickas till kunder.</span><span class="sxs-lookup"><span data-stu-id="f56f2-112">The company&#39;s own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="f56f2-113">För utgående processer kan du använda transporthantering för att bestämma transportkostnaderna och skicka dem vidare till kunderna.</span><span class="sxs-lookup"><span data-stu-id="f56f2-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="f56f2-114">Processen för avstämning av transportföretagets faktura krävs inte.</span><span class="sxs-lookup"><span data-stu-id="f56f2-114">However, the carrier invoice reconciliation process isn&#39;t required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f56f2-115">Företagets egen flotta är tillgänglig för leverans/upphämtning men leveransavgifter skickas inte till kunder, eftersom produktpriser inkluderar transport.</span><span class="sxs-lookup"><span data-stu-id="f56f2-115">The company&#39;s own fleet is available for delivery/pickup, but delivery charges aren&#39;t passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="f56f2-116">Många av transporthanteringsfunktionerna krävs inte.</span><span class="sxs-lookup"><span data-stu-id="f56f2-116">A lot of the Transportation management functionality isn&#39;t required.</span></span> <span data-ttu-id="f56f2-117">Du kan däremot använda transporthantering för att bestämma transporttarifferna och anpassa försäljningspriset efter detta.</span><span class="sxs-lookup"><span data-stu-id="f56f2-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f56f2-118">Logistiktjänst tillhandahålls av en annan juridisk person inom samma företag.</span><span class="sxs-lookup"><span data-stu-id="f56f2-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="f56f2-119">Du kan använda transporthantering genom att hantera den andra juridiska personen som alla andra transportföretag.</span><span class="sxs-lookup"><span data-stu-id="f56f2-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="f56f2-120">Du kan inte automatisera de ekonomiska transaktionerna mellan juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="f56f2-120">You can&#39;t automate the economic transactions between legal entities.</span></span> <span data-ttu-id="f56f2-121">Därför måste du hantera dessa transaktioner manuellt (exempelvis genom att skapa en inköpsorder).</span><span class="sxs-lookup"><span data-stu-id="f56f2-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="f56f2-122">I den juridiska person som tillhandahåller logistiktjänsterna, transporthantering kan användas för att bestämma transporttariffer.</span><span class="sxs-lookup"><span data-stu-id="f56f2-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-finance-and-operations"></a><span data-ttu-id="f56f2-123">Planera transport i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f56f2-123">Planning transportation in Finance and Operations</span></span>
<span data-ttu-id="f56f2-124">I transporthantering, transportplaneringen baseras antingen på order eller på försändelserna som skapas baserat på dessa order.</span><span class="sxs-lookup"><span data-stu-id="f56f2-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="f56f2-125">Försändelserna alltid finns någon gång i tiden men krävs inte för transportplanering.</span><span class="sxs-lookup"><span data-stu-id="f56f2-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="f56f2-126">Överföringsorder är en del av det utgående scenariot och kan planeras tillsammans med försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="f56f2-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Lastuttag](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="f56f2-128">Ingående transport</span><span class="sxs-lookup"><span data-stu-id="f56f2-128">Inbound transportation</span></span>
<span data-ttu-id="f56f2-129">När du beställer artiklar från en leverantör och artiklarna måste levereras till ditt lagerställe, kanske du vill ordna själva transporten av artiklarna.</span><span class="sxs-lookup"><span data-stu-id="f56f2-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="f56f2-130">Du kan använda Finance and Operations för att planera transporten och inleveransen av den ingående lasten.</span><span class="sxs-lookup"><span data-stu-id="f56f2-130">You can use Finance and Operations to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="f56f2-131">I bilden nedan visas affärsprocessflödet för planering av transport för en inkommande beläggning.</span><span class="sxs-lookup"><span data-stu-id="f56f2-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Affärsprocessflöde för transport av inkommande last](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="f56f2-133">Utgående transport</span><span class="sxs-lookup"><span data-stu-id="f56f2-133">Outbound transportation</span></span>
<span data-ttu-id="f56f2-134">Du kan planera och bearbeta en utgående last för att skicka vissa artiklar från ett företags lager till en kund.</span><span class="sxs-lookup"><span data-stu-id="f56f2-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="f56f2-135">Du kan använda Finance and Operations för att planera transporten och leveransen av den utgående lasten.</span><span class="sxs-lookup"><span data-stu-id="f56f2-135">You can use Finance and Operations to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="f56f2-136">I bilden nedan visas affärsprocessflödet för planering och bearbetning av utgående beläggningar för leverans.</span><span class="sxs-lookup"><span data-stu-id="f56f2-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Planera och bearbeta utgående laster](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="f56f2-138">Lastuppbyggnad</span><span class="sxs-lookup"><span data-stu-id="f56f2-138">Load building</span></span>
<span data-ttu-id="f56f2-139">Finance and Operations innehåller en lastuppbyggnadsstrategi med namnet Volymbaserad lastuppbyggnadsstrategi.</span><span class="sxs-lookup"><span data-stu-id="f56f2-139">Finance and Operations provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="f56f2-140">Denna strategi låter dig använda de angivna maximivärdena som specificerats för höjd och vikt i lastmallen eller så kan du åsidosätta inställningarna genom att ange nya värden.</span><span class="sxs-lookup"><span data-stu-id="f56f2-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="f56f2-141">För att använda denna strategi, välj den i fältet **Lastuppbyggnadsstrategi** på snabbfliken **Inställningar** på sidan **Workbench för lastuppbyggnad**.</span><span class="sxs-lookup"><span data-stu-id="f56f2-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="f56f2-142">Dessutom kan du lägga till dina egna uppbyggnadsstrategier genom att skapa en ny klass i programobjektträdet.</span><span class="sxs-lookup"><span data-stu-id="f56f2-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>




