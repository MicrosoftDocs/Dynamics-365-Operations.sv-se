---
title: Översikt över kredit och inkasso
description: Detta ämne ger en översikt över funktionaliteten för kredit och inkasso.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7929150cd9f6c28620f4c4d4cb7b57b02d27a104
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835422"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="05be3-103">Översikt över kredit och inkasso</span><span class="sxs-lookup"><span data-stu-id="05be3-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05be3-104">Du kan hantera kreditgränser för dina kunder och utföra inkassoaktiviteter när de blir nödvändiga.</span><span class="sxs-lookup"><span data-stu-id="05be3-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="05be3-105">Kredithantering</span><span class="sxs-lookup"><span data-stu-id="05be3-105">Credit management</span></span>

<span data-ttu-id="05be3-106">Med hjälp av hantering av kundkredit kan du hantera kreditgränser och styra flödet av försäljningsorder via bokföringsprocessen baserat på de kreditregler som du skapar.</span><span class="sxs-lookup"><span data-stu-id="05be3-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="05be3-107">Processen för att använda kredithantering kan omfatta en del av eller alla av följande steg:</span><span class="sxs-lookup"><span data-stu-id="05be3-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="05be3-108">Uppdatera kreditattribut för kunder som ger ytterligare information om deras kreditvärdighet.</span><span class="sxs-lookup"><span data-stu-id="05be3-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="05be3-109">Skapa kreditgränser för kunder genom att använda kreditgränsjusteringar.</span><span class="sxs-lookup"><span data-stu-id="05be3-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="05be3-110">Skapa tillfälliga kreditgränser för kunder genom att använda kreditgränsjusteringar.</span><span class="sxs-lookup"><span data-stu-id="05be3-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="05be3-111">På det här sättet kan du tillfälligt öka eller minska kundens kreditgränser, baserat på affärsbehoven.</span><span class="sxs-lookup"><span data-stu-id="05be3-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="05be3-112">Lägg till information som kan påverka kreditgränsen, t.ex. information om försäkring och garantier.</span><span class="sxs-lookup"><span data-stu-id="05be3-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="05be3-113">Skapa kundkreditgrupper som kopplar samman kunder så att de kan dela en enda kreditgräns.</span><span class="sxs-lookup"><span data-stu-id="05be3-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="05be3-114">Tilldela riskpoäng till kunder och använd sedan poängen för att automatiskt generera kreditgränser för kunder genom att använda kreditgränsjusteringar.</span><span class="sxs-lookup"><span data-stu-id="05be3-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="05be3-115">Skapa spärrningsregler som gör att en order spärras under en eller flera bokföringsprocesser baserat på faktorer som risk, betalningsvillkor, kreditgränser, förfallna belopp och procent av kreditgräns som används.</span><span class="sxs-lookup"><span data-stu-id="05be3-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="05be3-116">Hantera en lista över försäljningsorder som är spärrade, granska orsakerna till undantaget och minska problemen.</span><span class="sxs-lookup"><span data-stu-id="05be3-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="05be3-117">Frisläpp försäljningsorder och tillåt det att fortsätta under bokföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="05be3-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="05be3-118">Ställ in arbetsflöde för att hantera godkännandet av kreditgränsändringar och frisläppning av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="05be3-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="05be3-119">Inkassohantering</span><span class="sxs-lookup"><span data-stu-id="05be3-119">Collections management</span></span>

<span data-ttu-id="05be3-120">Sidan **Inkasso** ger en centraliserad vy där information om inkasso av kundfordringar hanteras.</span><span class="sxs-lookup"><span data-stu-id="05be3-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="05be3-121">Inkassoansvariga kan använda denna centraliserade vy för att hantera inkasseringar.</span><span class="sxs-lookup"><span data-stu-id="05be3-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="05be3-122">Inkassohandläggare kan börja inkassoprocessen från kundlistor som genereras med hjälp av fördefinierade inkassokriterier eller från sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="05be3-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="05be3-123">Innan du börjar ställa in eller arbeta med kassaavstämningar, ska du förstå följande begrepp:</span><span class="sxs-lookup"><span data-stu-id="05be3-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="05be3-124">Ögonblicksbilder av åldersfördelningen för kunder innehåller information om åldersfördelade saldon vid en specifik tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="05be3-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="05be3-125">Inkassokundpooler hjälper dig att organisera arbetet.</span><span class="sxs-lookup"><span data-stu-id="05be3-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="05be3-126">Inkassohandläggare kan ha sina egna kundpooler.</span><span class="sxs-lookup"><span data-stu-id="05be3-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="05be3-127">Listsidor organiserar inkassokunder, aktiviteter och fall.</span><span class="sxs-lookup"><span data-stu-id="05be3-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="05be3-128">All information om inkasso för en kund finns på sidan, och du kan vidta åtgärder från den sidan.</span><span class="sxs-lookup"><span data-stu-id="05be3-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="05be3-129">Ränta och avgifter kan avfärdas, återinsättas eller återföras i ett steg.</span><span class="sxs-lookup"><span data-stu-id="05be3-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="05be3-130">Avskrivningstransaktioner kan skapas i ett steg.</span><span class="sxs-lookup"><span data-stu-id="05be3-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="05be3-131">NSF-transaktioner (otillräckliga medel) kan bearbetas i ett steg.</span><span class="sxs-lookup"><span data-stu-id="05be3-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="05be3-132">Beskrivningar av dessa begrepp finns i [nyckelbegrepp för inkassohantering](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="05be3-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05be3-133">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="05be3-133">Additional resources</span></span>

[<span data-ttu-id="05be3-134">Inställningar för parametrar för kundkredithantering</span><span class="sxs-lookup"><span data-stu-id="05be3-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="05be3-135">Inställningar för information för kundkredithantering</span><span class="sxs-lookup"><span data-stu-id="05be3-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="05be3-136">Lägg till information för kredithantering för en kund</span><span class="sxs-lookup"><span data-stu-id="05be3-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="05be3-137">Kreditgrupper för kund</span><span class="sxs-lookup"><span data-stu-id="05be3-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="05be3-138">Justering av kundkreditgräns</span><span class="sxs-lookup"><span data-stu-id="05be3-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="05be3-139">Kreditspärrar för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="05be3-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="05be3-140">Periodiska kredithanteringsuppgifter för kund</span><span class="sxs-lookup"><span data-stu-id="05be3-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]