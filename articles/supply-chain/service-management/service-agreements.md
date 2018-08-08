---
title: Serviceavtal
description: "Ett serviceavtal låter dig definiera de resurser som används vid ett vanligt servicebesök och hur resurserna kan faktureras kunden."
author: ShylaThompson
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c6425dcf1c89f625d997be0dd4a52aaecb6e6d65
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="service-agreements"></a><span data-ttu-id="e5d5a-103">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="e5d5a-103">Service agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e5d5a-104">Ett serviceavtal låter dig definiera de resurser som används vid ett vanligt servicebesök och hur resurserna kan faktureras kunden.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="e5d5a-105">Alla serviceavtal kopplas till ett projekt och transaktioner bokförs och faktureras via detta.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="e5d5a-106">Du kan dock även fakturera serviceordertransaktioner direkt genom projektet utan att först behöva koppla serviceordern till ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="e5d5a-107">Du kanske vill göra detta om serviceordern är för ett engångsbesök och behovet av att bearbeta tjänstetransaktionerna snabbt uppväger behovet av att bibehålla detaljinformation om serviceavtalet för kunden över tid.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="e5d5a-108">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="e5d5a-108">Service agreement</span></span>

<span data-ttu-id="e5d5a-109">I ett serviceavtal måste du ange ett projekt, ett serviceavtals-ID samt en serviceavtalsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="e5d5a-110">Serviceavtalsgruppen kan användas för att sortera och organisera serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="e5d5a-111">Rubriken i ett serviceavtal innehåller inställningar som används för alla kopplade avtalsrader:</span><span class="sxs-lookup"><span data-stu-id="e5d5a-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="e5d5a-112">Information om huruvida serviceavtalet är uppskjutet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="e5d5a-113">Om avtalet är uppskjutet går det inte att skapa serviceorder från serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="e5d5a-114">Tidslängden för serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="e5d5a-115">Information om hur serviceorderrader ska kombineras till serviceorder.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="e5d5a-116">Information om huruvida serviceavtalet är en mall.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="e5d5a-117">I serviceavtalets rubrik ställer du också in serviceobjekt och serviceuppgifter som kan användas med serviceavtalet genom att ange specifika serviceuppgifter och serviceobjekt som ska kopplas till de olika raderna i avtalet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="e5d5a-118">Från avtalsrubriken kan du också kopiera serviceavtalsrader eller servicemallrader till det aktuella serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="e5d5a-119">Du kan skjuta upp serviceavtal och stoppa enskilda serviceavtalsrader.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="e5d5a-120">Om du markerar kryssrutan **uppskjuten** på ett serviceavtal kan du inte göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="e5d5a-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="e5d5a-121">Skapa serviceorder automatiskt eller manuellt från serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="e5d5a-122">Om du markerar kryssrutan **stoppad** för en serviceavtalsrad kan du inte göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="e5d5a-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="e5d5a-123">Skapa serviceorder automatiskt eller manuellt från serviceavtalsraden.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="e5d5a-124">Kopiera serviceavtalsraden till ett annat serviceavtal eller en annan serviceorder.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="e5d5a-125">Om ett serviceavtal skjuts upp stoppas alla kopplade rader oavsett radernas enskilda status.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="e5d5a-126">Serviceavtalsrader</span><span class="sxs-lookup"><span data-stu-id="e5d5a-126">Service-agreement lines</span></span>

<span data-ttu-id="e5d5a-127">Varje serviceavtalsrad beskriver i detalj vad som ingår i det föreslagna servicearbetet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="e5d5a-128">Raderna innehåller följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e5d5a-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="e5d5a-129">Transaktionstypen och en beskrivning av typen.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="e5d5a-130">Den medarbetare som utför servicearbetet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="e5d5a-131">De objekt som service ska utföras för enligt serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="e5d5a-132">Den frekvens som arbete ska utföras med och som associerade artikel-, utgifts- och avgiftstransaktioner ska registreras med.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="e5d5a-133">Det tidsfönster där serviceorderrader kan grupperas till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="e5d5a-134">De serviceuppgifter som används för att gruppera uppsättningar med avtalsrader till arbetsuppgifter och för att översiktligt beskriva för servicetekniker och kunder vilket servicearbete som ska utföras.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="e5d5a-135">Information om huruvida en rad har stoppats.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-135">Whether a line is stopped.</span></span> <span data-ttu-id="e5d5a-136">Om en rad har stoppats går det inte att skapa serviceorder för raden.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="e5d5a-137">Projektinställningar, t.ex. kategori och radegenskaper.</span><span class="sxs-lookup"><span data-stu-id="e5d5a-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5d5a-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e5d5a-138">Related topics</span></span>

[<span data-ttu-id="e5d5a-139">Skapa serviceavtal</span><span class="sxs-lookup"><span data-stu-id="e5d5a-139">Create service agreements</span></span>](create-service-agreements.md)

