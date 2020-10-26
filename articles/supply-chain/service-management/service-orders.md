---
title: Serviceorder
description: En serviceorder representerar ett besök av en servicetekniker hos en kund ett specifikt datum.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b049b166edf2b5a318a4b1af85e7f74cfe433f2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975474"
---
# <a name="service-orders"></a><span data-ttu-id="5afaa-103">Serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afaa-103">Service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5afaa-104">En serviceorder representerar ett besök av en servicetekniker hos en kund ett specifikt datum.</span><span class="sxs-lookup"><span data-stu-id="5afaa-104">A service order represents a visit that a service technician makes to a customer site on a specific date.</span></span> <span data-ttu-id="5afaa-105">Varje serviceorder består av en eller flera serviceorderrader.</span><span class="sxs-lookup"><span data-stu-id="5afaa-105">Each service order consists of one or more service order lines.</span></span> <span data-ttu-id="5afaa-106">Serviceorderrader representerar de arbetstimmar som måste utföras av serviceteknikern samt artiklar, utgifter och avgifter.</span><span class="sxs-lookup"><span data-stu-id="5afaa-106">Service order lines represent the hours of work that must be performed by the service technician, and the related items, expenses, and fees.</span></span>

<span data-ttu-id="5afaa-107">Du kan koppla uppgifter och objekt till en serviceorderrad.</span><span class="sxs-lookup"><span data-stu-id="5afaa-107">You can attach tasks and objects to a service order line.</span></span> <span data-ttu-id="5afaa-108">Du kan sedan gruppera serviceorderrader efter vilken uppgift eller av objektet.</span><span class="sxs-lookup"><span data-stu-id="5afaa-108">You can then group service order lines by task or by object.</span></span> <span data-ttu-id="5afaa-109">Du kan även koppla artiklar som listas i lagret till serviceorderrader.</span><span class="sxs-lookup"><span data-stu-id="5afaa-109">You can also attach items that are listed in inventory to service order lines.</span></span>

## <a name="create-service-orders"></a><span data-ttu-id="5afaa-110">Skapa serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afaa-110">Create service orders</span></span>

<span data-ttu-id="5afaa-111">Du kan skapa serviceorder utifrån serviceavtalet och raderna för avtalet.</span><span class="sxs-lookup"><span data-stu-id="5afaa-111">You can create service orders based on a service agreement and the lines that are contained in that agreement.</span></span> <span data-ttu-id="5afaa-112">Du kan dock skapa serviceorder som är kopplade till ett serviceavtal endast under den period som anges i avtalet.</span><span class="sxs-lookup"><span data-stu-id="5afaa-112">However, you can create service orders that are associated with a service agreement only in the period that is specified in the agreement.</span></span> <span data-ttu-id="5afaa-113">Om ett serviceavtal är giltig för kalenderåret 2011 kan skapa du serviceorder för avtalet från den 1 januari 2011 och den 31 December 2011.</span><span class="sxs-lookup"><span data-stu-id="5afaa-113">For example, if a service agreement is valid for the 2011 calendar year, you can create service orders for the agreement from January 1, 2011, and December 31, 2011.</span></span>

<span data-ttu-id="5afaa-114">Du kan skapa serviceorder individuellt utan att associera dem till ett avtal.</span><span class="sxs-lookup"><span data-stu-id="5afaa-114">You can also create service orders individually, without associating them with an agreement.</span></span> <span data-ttu-id="5afaa-115">Dessa kan användas för att hantera en enstaka eller oplanerat servicebesök.</span><span class="sxs-lookup"><span data-stu-id="5afaa-115">These service orders can be used to handle unscheduled or one-time service visits.</span></span> <span data-ttu-id="5afaa-116">I mars vill kunden ha service utförd på två maskiner utöver dem som har angetts i serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="5afaa-116">For example, in the month of March, your customer wants service to be performed on two machines, in addition to the machines that are specified in the service agreement.</span></span> <span data-ttu-id="5afaa-117">För den här uppgiften skapar du serviceorder men associerar inte dem med ett avtal.</span><span class="sxs-lookup"><span data-stu-id="5afaa-117">For this task, you create service orders but do not associate them with an agreement.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5afaa-118">Om du vill skapa serviceorder som inte är associerade med ett serviceavtal måste du välja kryssrutan <STRONG>Tillåt utan serviceavtal</STRONG> i formuläret <STRONG>Serviceparametrar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5afaa-118">To create service orders that are not associated with a service agreement, you must select the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form.</span></span></P>

<span data-ttu-id="5afaa-119">**Scenario**</span><span class="sxs-lookup"><span data-stu-id="5afaa-119">**Scenario**</span></span>

<span data-ttu-id="5afaa-120">I följande scenario beskrivs en annan situation där det är praktiskt att skapa en serviceorder som inte är kopplad till ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="5afaa-120">The following scenario describes another situation where it is useful to create a service order that is not associated with a service agreement.</span></span>

<span data-ttu-id="5afaa-121">Företagets klarerare tar mot ett samtal med en begäran om akut service på en hiss.</span><span class="sxs-lookup"><span data-stu-id="5afaa-121">The company dispatcher receives a call requesting emergency service on an elevator.</span></span> <span data-ttu-id="5afaa-122">Det finns ingen tid att skapa ett serviceavtal och ett projekt.</span><span class="sxs-lookup"><span data-stu-id="5afaa-122">There is no time to set up a service agreement and a project for the service.</span></span> <span data-ttu-id="5afaa-123">Därför skapar klareraren en serviceorder direkt i formuläret **serviceorder** och kopplar serviceordern till ett befintligt projekt och skapar serviceorderraderna.</span><span class="sxs-lookup"><span data-stu-id="5afaa-123">Therefore, the dispatcher creates a service order directly in the **Service orders** form, attaches the service order to an existing project, and creates the service order lines.</span></span> <span data-ttu-id="5afaa-124">Klareraren skapa också en uppgift eller objektrelation för en befintlig serviceorder om du behöver registrera arbete som inte hör till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="5afaa-124">The dispatcher also creates a task or object relation for an existing service order, to record work that is not related to the service agreement.</span></span> <span data-ttu-id="5afaa-125">Mer information finns i [skapa serviceorder manuellt](create-service-orders-manually.md) och [Skapa serviceuppgiftsrelationer](create-service-task-relations.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-125">For more information, see [Create service orders manually](create-service-orders-manually.md) and [Create service task relations](create-service-task-relations.md).</span></span>

## <a name="monitor-the-progress-of-service-orders"></a><span data-ttu-id="5afaa-126">Övervaka förlopp för serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afaa-126">Monitor the progress of service orders</span></span>

<span data-ttu-id="5afaa-127">För att övervaka förloppet hos serviceorder genom olika grupper och arbetsprocesser kan du ställa in ett system med faser och orsakskoder för serviceorder.</span><span class="sxs-lookup"><span data-stu-id="5afaa-127">To monitor the progress of a sales order through the different teams and work processes, you can set up a system of stages and reason codes for service orders.</span></span> <span data-ttu-id="5afaa-128">För varje fas kan du ange tillåtna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5afaa-128">For each stage, you can specify the actions that are allowed.</span></span> <span data-ttu-id="5afaa-129">Mer information finns i [Skapa orsakskoder](create-reason-codes.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-129">For more information, see [Create reason codes](create-reason-codes.md).</span></span>

<span data-ttu-id="5afaa-130">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="5afaa-130">**Example**</span></span>

<span data-ttu-id="5afaa-131">En serviceorder godkänns av klareraren.</span><span class="sxs-lookup"><span data-stu-id="5afaa-131">A service order is approved by the dispatcher.</span></span> <span data-ttu-id="5afaa-132">Klareraren uppdaterar fasen för serviceordern och anger en orsakskod som visar att serviceordern har frisläppts till teknikern.</span><span class="sxs-lookup"><span data-stu-id="5afaa-132">The dispatcher updates the stage of the service order and specifies a reason code that indicates that the service order has been released to the service technician.</span></span> <span data-ttu-id="5afaa-133">Serviceteknikern besöker kunden och utför serviceordern.</span><span class="sxs-lookup"><span data-stu-id="5afaa-133">The technician goes to the customer site and performs the service.</span></span>

## <a name="specify-item-requirements-for-service-orders"></a><span data-ttu-id="5afaa-134">Ange artikelbehov för serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afaa-134">Specify item requirements for service orders</span></span>

<span data-ttu-id="5afaa-135">Du kan ange lagerartiklar som krävs för serviceorder.</span><span class="sxs-lookup"><span data-stu-id="5afaa-135">You can specify the inventory items that are required for service orders.</span></span> <span data-ttu-id="5afaa-136">Dock måste serviceordern vara kopplad till ett projekt.</span><span class="sxs-lookup"><span data-stu-id="5afaa-136">However, the service order must be associated with a project.</span></span> <span data-ttu-id="5afaa-137">Artikelbehov för serviceorder bearbetas via ett projekt.</span><span class="sxs-lookup"><span data-stu-id="5afaa-137">Item requirements for service orders are processed through a project.</span></span> 

<span data-ttu-id="5afaa-138">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="5afaa-138">**Example**</span></span>

<span data-ttu-id="5afaa-139">Serviceorder som skapas från serviceavtalet behandlas sedan av klareraren.</span><span class="sxs-lookup"><span data-stu-id="5afaa-139">The service orders that are created from the service agreement are processed by the dispatcher.</span></span> <span data-ttu-id="5afaa-140">På den första serviceordern ser klareraren att teknikern behöver en viktig reservdel som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="5afaa-140">For the first service order, the dispatcher realizes that the service technician requires an important spare part that is not in the on-hand inventory.</span></span> <span data-ttu-id="5afaa-141">Därför skapar klareraren ett artikelkrav för reservdelen direkt från serviceordern.</span><span class="sxs-lookup"><span data-stu-id="5afaa-141">Therefore, the dispatcher creates an item requirement for the spare part directly from the service order.</span></span>

## <a name="move-and-post-lines"></a><span data-ttu-id="5afaa-142">Flytta och bokföra rader</span><span class="sxs-lookup"><span data-stu-id="5afaa-142">Move and post lines</span></span>

<span data-ttu-id="5afaa-143">När serviceteknikern återkommer från besöket ändrar och uppdaterar teknikern serviceorderraderna.</span><span class="sxs-lookup"><span data-stu-id="5afaa-143">A service technician returns from a service visit, and then modifies and updates the service order lines.</span></span> <span data-ttu-id="5afaa-144">När han är på sitt servicebesök utför han även ett servicejobb som skulle ha utförts under nästa servicebesök.</span><span class="sxs-lookup"><span data-stu-id="5afaa-144">During the service visit, the technician performed a service job that was scheduled for the next service visit.</span></span> <span data-ttu-id="5afaa-145">Därför flyttar han raderna från det följande servicebesöket till det aktuella (E).</span><span class="sxs-lookup"><span data-stu-id="5afaa-145">Therefore, the technician moves the lines from the next service visit to the current service visit.</span></span> <span data-ttu-id="5afaa-146">Därefter bokför han serviceordern.</span><span class="sxs-lookup"><span data-stu-id="5afaa-146">The technician then posts the service order.</span></span> <span data-ttu-id="5afaa-147">Mer information finns i [Flytta serviceorderrader](move-service-order-lines.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-147">For more information, see [Move service order lines](move-service-order-lines.md).</span></span>

## <a name="cancel-service-orders"></a><span data-ttu-id="5afaa-148">Avbryt serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afaa-148">Cancel service orders</span></span>

<span data-ttu-id="5afaa-149">En annan serviceorder som hade genererats för januari blir föråldrad eftersom jobbet annulleras.</span><span class="sxs-lookup"><span data-stu-id="5afaa-149">One of the other service orders that was generated for the month of January becomes obsolete, because the job is canceled.</span></span> <span data-ttu-id="5afaa-150">Därför annullerar serviceklareraren serviceordern.</span><span class="sxs-lookup"><span data-stu-id="5afaa-150">Therefore, the service dispatcher cancels the service order.</span></span> <span data-ttu-id="5afaa-151">Mer information finns i [Avbryt serviceorder](cancel-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-151">For more information, see [Cancel service orders](cancel-service-orders.md).</span></span>

## <a name="post-from-projects"></a><span data-ttu-id="5afaa-152">Bokföra från Projekt</span><span class="sxs-lookup"><span data-stu-id="5afaa-152">Post from projects</span></span>

<span data-ttu-id="5afaa-153">I slutet av varje vecka vill klareraren bokföra alla serviceorder som är knutna till ett visst projekt.</span><span class="sxs-lookup"><span data-stu-id="5afaa-153">At the end of each week, the dispatcher wants to post all service orders that are attached to a specific project.</span></span> <span data-ttu-id="5afaa-154">Därför letar klareraren reda på det relevanta projektet i formuläret **projekt** och bokför serviceorder som har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5afaa-154">Therefore, the dispatcher locates the relevant project in the **Projects** form and posts the service orders that have been completed.</span></span> <span data-ttu-id="5afaa-155">Mer information finns i [Bokföra serviceorder automatiskt (klassformulär)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="5afaa-155">For more information, see [Post service orders (class form)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).</span></span>

## <a name="delete-service-orders"></a><span data-ttu-id="5afaa-156">Ta bort serviceorder</span><span class="sxs-lookup"><span data-stu-id="5afaa-156">Delete service orders</span></span>

<span data-ttu-id="5afaa-157">Under andra halvåret upptäcker kunden att servicebesöken inträffar alltför sällan.</span><span class="sxs-lookup"><span data-stu-id="5afaa-157">During the second half of the year, your customer decides that the service visits are too infrequent.</span></span> <span data-ttu-id="5afaa-158">Du måste skapa nya, mer frekventa servicebesök för resten av serviceavtalets giltighet.</span><span class="sxs-lookup"><span data-stu-id="5afaa-158">You must create a new, more frequent series of service visits for the remaining time on the service agreement.</span></span> <span data-ttu-id="5afaa-159">Därför måste du ta bort de befintliga serviceorder som har skapats (I) och skapa nya serviceorder.</span><span class="sxs-lookup"><span data-stu-id="5afaa-159">Therefore, you must delete the existing service orders and create new service orders.</span></span> <span data-ttu-id="5afaa-160">Mer information finns i [Ta bort serviceorder](delete-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="5afaa-160">For more information, see [Delete service orders](delete-service-orders.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5afaa-161">Se även</span><span class="sxs-lookup"><span data-stu-id="5afaa-161">See also</span></span>

<span data-ttu-id="5afaa-162">[Serviceorder (formulär)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="5afaa-162">[Service orders (form)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))</span></span>

  


