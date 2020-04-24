---
title: Frisläppning i batch av delvis reserverade överföringsorder
description: Detta avsnitt beskriver hur du ställer in och använder batchfrisläppning av delvis reserverade överföringsorder från en mobil enhet.
author: pjacobse
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0707731caaf9b4852e3c19be899ad92f5b84e29
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201305"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a><span data-ttu-id="c786a-103">Frisläppning i batch av delvis reserverade överföringsorder</span><span class="sxs-lookup"><span data-stu-id="c786a-103">Batch release of partially reserved transfer orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c786a-104">Funktionerna för batchfrisläppande av delvis reserverade överföringsorder gör att du delvis kan frisläppa överföringsorder till ett lager med hjälp av ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="c786a-104">The functionality for batch release of partially reserved transfer orders lets you partially release transfer orders to a warehouse by using a batch job.</span></span>
<span data-ttu-id="c786a-105">Eftersom du kan välja att frisläppa en delkvantitet behöver du inte vänta på att hela orderkvantiteten ska vara tillgänglig i distributionslagret innan du frisläpper en order.</span><span class="sxs-lookup"><span data-stu-id="c786a-105">Because you have the option to release a partial quantity, you don’t have to wait for the whole order quantity to be available in the warehouse before you release an order.</span></span>

<span data-ttu-id="c786a-106">Frisläppandet av order till ett lagerställe är en avancerad lagerhanteringsprocess.</span><span class="sxs-lookup"><span data-stu-id="c786a-106">The release of orders to a warehouse is an advanced warehouse management process.</span></span> <span data-ttu-id="c786a-107">Denna process involverar aktiviteter, till exempel plockning, paketering och frakt, som en lagerarbetare kan utföra med en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="c786a-107">This process involves activities, such as picking, packing, and shipping, that a warehouse worker can perform by using a mobile device.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="c786a-108">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="c786a-108">Where it applies</span></span>

<span data-ttu-id="c786a-109">För den här funktionen frisläpps överföringsorder till ett lagerställe med hjälp av ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="c786a-109">For this functionality, transfer orders are released to a warehouse by using a batch job.</span></span> <span data-ttu-id="c786a-110">Denna funktion är användbar när det inte finns tillräckligt mycket lager men du ändå vill överföra artiklar från ett lagerställe till ett annat.</span><span class="sxs-lookup"><span data-stu-id="c786a-110">This functionality is useful when you don’t have enough inventory in the warehouse, but you still want to transfer items from one warehouse to another.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="c786a-111">Inställningar</span><span class="sxs-lookup"><span data-stu-id="c786a-111">How it is set up</span></span>

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="c786a-112">Ange uppfyllandevillkor för överförings- och försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c786a-112">Specify fulfillment criteria for transfer orders and sales orders</span></span>

<span data-ttu-id="c786a-113">Innan en order kan delvis frisläppas till ett lager som en batch, måste uppfyllandevillkoret uppfyllas.</span><span class="sxs-lookup"><span data-stu-id="c786a-113">Before an order can be partially released to a warehouse in a batch, the fulfillment criteria must be met.</span></span> <span data-ttu-id="c786a-114">Dessa uppfyllandekriterier utförande bestäms av uppfyllandepolicyn.</span><span class="sxs-lookup"><span data-stu-id="c786a-114">These fulfillment criteria are determined by the fulfillment policy.</span></span>

<span data-ttu-id="c786a-115">Uppfyllandepolicyer för överförings- och försäljningsorder anges på företagsnivå.</span><span class="sxs-lookup"><span data-stu-id="c786a-115">Fulfillment policies for transfer orders and sales orders are specified at the company level.</span></span> <span data-ttu-id="c786a-116">Beroende på inställningarna för uppfyllandepolicyn kommer orderfrisläppandet i batch att godtas eller avvisas.</span><span class="sxs-lookup"><span data-stu-id="c786a-116">Depending on the setup of the fulfillment policy, the release of orders in a batch will be accepted or rejected.</span></span> <span data-ttu-id="c786a-117">Alla order kommer sedan att behandlas därefter.</span><span class="sxs-lookup"><span data-stu-id="c786a-117">The orders will then be processed accordingly.</span></span>

-   <span data-ttu-id="c786a-118">Om du vill skapa uppfyllandepolicyer för överförings- och försäljningsorder klickar du på **Lagerstyrning** \> **Inställningar** \> **Frisläpp till lagerställe** \> **Uppfyllelsepolicy**, och skapar sedan en uppfyllandepolicy genom att ange ett namn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="c786a-118">To create fulfillment policies for transfer orders and sales orders, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then create a fulfillment policy by entering a name and a description.</span></span>

-   <span data-ttu-id="c786a-119">Om du vill ange en uppfyllandekvot, en värdetyp samt det meddelande som ska visas om uppfyllandepolicyn överträds klickar du på **Lagerstyrning** \> **Inställningar** \> **Frisläpp till lagerställe** \> **Uppfyllandepolicy**, och fyller sedan i fälten **Uppfyllandekvot**, **Värdetyp** och **Meddelande om brott mot uppfyllande**.</span><span class="sxs-lookup"><span data-stu-id="c786a-119">To specify a fulfillment rate, a value type, and the message that is shown if the fulfillment policy is violated, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then set the **Fulfillment rate**, **Value type**, and **Fulfillment violation message** fields.</span></span>

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="c786a-120">Ange uppfyllandevillkoren för överförings- och försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c786a-120">Set the fulfillment policies for transfer orders and sales orders</span></span>

-   <span data-ttu-id="c786a-121">Om du vill ange villkoren för överföringsorder klickar du på **Lagerstyrning** \> **Inställningar** \> **Parametrar för lager och lagerstyrning** \> **Överföringsorder** \> **Lagerstyrning**, och väljer sedan uppfyllelsevillkor för överföringsorder.</span><span class="sxs-lookup"><span data-stu-id="c786a-121">To set the fulfillment policies for transfer orders, click **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters** \> **Transfer orders** \> **Warehouse management**, and then select a transfer order fulfillment policy.</span></span>

-   <span data-ttu-id="c786a-122">Om du vill ange uppfyllelsevillkor för försäljningsorder klickar du på **Kundreskontra** \> **Inställningar** \> **Parametrar för kundreskontra** \> **Lagerstyrning** och väljer sedan villkor för uppfyllandet av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c786a-122">To set the fulfillment policies for sales orders, click **Accounts receivable** \> **Setup** \> **Accounts receivable parameters** \> **Warehouse management**, and then select a sales order fulfillment policy.</span></span>

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a><span data-ttu-id="c786a-123">Tillåt frisläpp i batch, och ange den kvantitet som ska frisläppas i batch</span><span class="sxs-lookup"><span data-stu-id="c786a-123">Allow release in a batch and specify the quantity that should be release in a batch</span></span>

<span data-ttu-id="c786a-124">Ett batch-jobb används för att frisläppa order till ett lager i batch.</span><span class="sxs-lookup"><span data-stu-id="c786a-124">A batch job is used to release orders to a warehouse in a batch.</span></span> <span data-ttu-id="c786a-125">De parametrar som särskiljer de order som ska köras i ett batchjobb anges i själva batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="c786a-125">The parameters that distinguish the orders that should be run in a batch job are set on the batch job itself.</span></span>

<span data-ttu-id="c786a-126">Parametern **Kvantitet** anger om hela kvantiteten eller den fysiskt reserverade kvantiteten ska frisläppas i batchen.</span><span class="sxs-lookup"><span data-stu-id="c786a-126">The **Quantity** parameter specifies whether the whole quantity or the physically reserved quantity should be released in the batch.</span></span> <span data-ttu-id="c786a-127">Parametern **Tillåt frisläppning av delvis frisläppta order** avgör om order i batchen godkänns eller avvisas om de tidigare delvis har frisläppts.</span><span class="sxs-lookup"><span data-stu-id="c786a-127">The **Allow release of partially released orders** parameter determines whether orders in the batch should be accepted or rejected if they were partially released earlier.</span></span>

-   <span data-ttu-id="c786a-128">För att ange parametrarna **Kvantitet** och **Tillåt frisläpp av delvis frisläppta order** för överföringsorder klickar du på **Lagerstyrning** \> **Frisläpp till lagerställe** \> **Automatisk frisläppning av överföringsorder**.</span><span class="sxs-lookup"><span data-stu-id="c786a-128">To set the **Quantity** and **Allow release of partially released orders** parameters for transfer orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of transfer orders**.</span></span>

-   <span data-ttu-id="c786a-129">För att ange parametrarna **Kvantitet** och **Tillåt frisläppning av delvis frisläppta order** för försäljningsorder klickar du på **Lagerstyrning** \> **Frisläpp till lagerställe** \> **Automatisk frisläppning av försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="c786a-129">To set the **Quantity** and **Allow release of partially released orders** parameters for sales orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of sales orders**.</span></span>
