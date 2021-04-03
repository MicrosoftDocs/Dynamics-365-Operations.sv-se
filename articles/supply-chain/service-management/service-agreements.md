---
title: Ta fram och upprätta avtal – översikt
description: Ett serviceavtal låter dig definiera de resurser som används vid ett vanligt servicebesök och hur resurserna kan faktureras kunden.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86855e8893cdf5d6e53cb34465480ade06a6da95
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258504"
---
# <a name="develop-and-establish-service-agreements-overview"></a><span data-ttu-id="b0e7c-103">Ta fram och upprätta avtal – översikt</span><span class="sxs-lookup"><span data-stu-id="b0e7c-103">Develop and establish service agreements overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0e7c-104">Ett serviceavtal låter dig definiera de resurser som används vid ett vanligt servicebesök och hur resurserna kan faktureras kunden.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="b0e7c-105">Alla serviceavtal kopplas till ett projekt och transaktioner bokförs och faktureras via detta.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="b0e7c-106">Du kan dock även fakturera serviceordertransaktioner direkt genom projektet utan att först behöva koppla serviceordern till ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="b0e7c-107">Du kanske vill göra detta om serviceordern är för ett engångsbesök och behovet av att bearbeta tjänstetransaktionerna snabbt uppväger behovet av att bibehålla detaljinformation om serviceavtalet för kunden över tid.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="b0e7c-108">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="b0e7c-108">Service agreement</span></span>

<span data-ttu-id="b0e7c-109">I ett serviceavtal måste du ange ett projekt, ett serviceavtals-ID samt en serviceavtalsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="b0e7c-110">Serviceavtalsgruppen kan användas för att sortera och organisera serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="b0e7c-111">Rubriken i ett serviceavtal innehåller inställningar som används för alla kopplade avtalsrader:</span><span class="sxs-lookup"><span data-stu-id="b0e7c-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="b0e7c-112">Information om huruvida serviceavtalet är uppskjutet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="b0e7c-113">Om avtalet är uppskjutet går det inte att skapa serviceorder från serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="b0e7c-114">Tidslängden för serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="b0e7c-115">Information om hur serviceorderrader ska kombineras till serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="b0e7c-116">Information om huruvida serviceavtalet är en mall.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="b0e7c-117">I serviceavtalets rubrik ställer du också in serviceobjekt och serviceuppgifter som kan användas med serviceavtalet genom att ange specifika serviceuppgifter och serviceobjekt som ska kopplas till de olika raderna i avtalet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="b0e7c-118">Från avtalsrubriken kan du också kopiera serviceavtalsrader eller servicemallrader till det aktuella serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="b0e7c-119">Du kan skjuta upp serviceavtal och stoppa enskilda serviceavtalsrader.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="b0e7c-120">Om du markerar kryssrutan **uppskjuten** på ett serviceavtal kan du inte göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="b0e7c-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="b0e7c-121">Skapa serviceorder automatiskt eller manuellt från serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="b0e7c-122">Om du markerar kryssrutan **stoppad** för en serviceavtalsrad kan du inte göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="b0e7c-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="b0e7c-123">Skapa serviceorder automatiskt eller manuellt från serviceavtalsraden.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="b0e7c-124">Kopiera serviceavtalsraden till ett annat serviceavtal eller en annan serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="b0e7c-125">Om ett serviceavtal skjuts upp stoppas alla kopplade rader oavsett radernas enskilda status.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="b0e7c-126">Serviceavtalsrader</span><span class="sxs-lookup"><span data-stu-id="b0e7c-126">Service-agreement lines</span></span>

<span data-ttu-id="b0e7c-127">Varje serviceavtalsrad beskriver i detalj vad som ingår i det föreslagna servicearbetet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="b0e7c-128">Raderna innehåller följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b0e7c-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="b0e7c-129">Transaktionstypen och en beskrivning av typen.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="b0e7c-130">Den medarbetare som utför servicearbetet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="b0e7c-131">De objekt som service ska utföras för enligt serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="b0e7c-132">Den frekvens som arbete ska utföras med och som associerade artikel-, utgifts- och avgiftstransaktioner ska registreras med.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="b0e7c-133">Det tidsfönster där serviceorderrader kan grupperas till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="b0e7c-134">De serviceuppgifter som används för att gruppera uppsättningar med avtalsrader till arbetsuppgifter och för att översiktligt beskriva för servicetekniker och kunder vilket servicearbete som ska utföras.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="b0e7c-135">Information om huruvida en rad har stoppats.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-135">Whether a line is stopped.</span></span> <span data-ttu-id="b0e7c-136">Om en rad har stoppats går det inte att skapa serviceorder för raden.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="b0e7c-137">Projektinställningar, t.ex. kategori och radegenskaper.</span><span class="sxs-lookup"><span data-stu-id="b0e7c-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0e7c-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b0e7c-138">Related topics</span></span>

[<span data-ttu-id="b0e7c-139">Skapa serviceavtal</span><span class="sxs-lookup"><span data-stu-id="b0e7c-139">Create service agreements</span></span>](create-service-agreements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]