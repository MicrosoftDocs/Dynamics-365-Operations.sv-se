---
title: Tjänsthantering – översikt
description: Använd Servicehantering för att fastställa serviceavtal och serviceabonnemang, hantera serviceordrar och kundförfrågningar, och för att hantera och analysera leverans av tjänster till kunder.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd2f27c5797fbd34674e39013ed3e0e40cdb28b2
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251142"
---
# <a name="service-management-overview"></a><span data-ttu-id="9ccaa-103">Tjänsthantering – översikt</span><span class="sxs-lookup"><span data-stu-id="9ccaa-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9ccaa-104">Använd **Servicehantering** för att fastställa serviceavtal och serviceabonnemang, hantera serviceordrar och kundförfrågningar, och för att hantera och analysera leverans av tjänster till kunder.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="9ccaa-105">Du kan använda serviceavtal när du vill definiera resurser som används vid ett vanligt servicebesök.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="9ccaa-106">Du kan också använda serviceavtal du vill visa hur resurserna kan faktureras kunden.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="9ccaa-107">Ett serviceavtal kan även innehålla ett serviceavtal som anger svarstider, och erbjuder verktyg för att registrera den faktiska tiden.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="9ccaa-108">Du kan skapa serviceorder du vill hantera information om schemalagda och icke tidsplanerade servicebesök av en servicetekniker till en kunds anläggning.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="9ccaa-109">Serviceorder innehåller information som:</span><span class="sxs-lookup"><span data-stu-id="9ccaa-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="9ccaa-110">Arbetstiderna som serviceteknikern ska utföra</span><span class="sxs-lookup"><span data-stu-id="9ccaa-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="9ccaa-111">Typ av tjänst eller reparation</span><span class="sxs-lookup"><span data-stu-id="9ccaa-111">The type of service or repair</span></span>

3.  <span data-ttu-id="9ccaa-112">Artikeln som ska repareras, inklusive information om symptom och diagnoser</span><span class="sxs-lookup"><span data-stu-id="9ccaa-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="9ccaa-113">Utgifter och avgifter som är relaterade till tjänsten eller reparationen</span><span class="sxs-lookup"><span data-stu-id="9ccaa-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="9ccaa-114">Du kan ta emot, behandla och skicka ut tjänstefrågor.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="9ccaa-115">När du har skapat en serviceorder kan du använda servicefaser för att övervaka förlopp och ange regler som styr vilka åtgärder som ska aktiveras i varje fas.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="9ccaa-116">När en serviceorder är avslutad, kan du godkänna ordern för att bekräfta att den är slutförd, och sedan bokföra ordern för att starta fakturaprocessen.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="9ccaa-117">Använd rapporteringsverktygen för att övervaka serviceordermarginaler och abonnemangstransaktioner, och skriva ut arbetsbeskrivningar och arbetsinleveranser.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="9ccaa-118">Affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="9ccaa-118">Business processes</span></span>

<span data-ttu-id="9ccaa-119">I bilden nedan visas högnivåaffärsprocesserna för Servicehantering och var **tjänstprocesser** integreras med andra moduler.</span><span class="sxs-lookup"><span data-stu-id="9ccaa-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="9ccaa-120">[![Affärsprocessdiagram för servicehantering](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="9ccaa-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="9ccaa-121">Snabb överblick över servicehantering</span><span class="sxs-lookup"><span data-stu-id="9ccaa-121">Service management at a glance</span></span>

|<span data-ttu-id="9ccaa-122">Viktiga uppgifter</span><span class="sxs-lookup"><span data-stu-id="9ccaa-122">Important tasks</span></span>           | <span data-ttu-id="9ccaa-123">Primära sidor</span><span class="sxs-lookup"><span data-stu-id="9ccaa-123">Primary pages</span></span>                         |<span data-ttu-id="9ccaa-124">Populära rapporter</span><span class="sxs-lookup"><span data-stu-id="9ccaa-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="9ccaa-125">Uppfyll serviceavtal</span><span class="sxs-lookup"><span data-stu-id="9ccaa-125">Fulfill service agreements</span></span>|<span data-ttu-id="9ccaa-126">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="9ccaa-126">Service agreements</span></span>                     |<span data-ttu-id="9ccaa-127">Serviceordermarginal</span><span class="sxs-lookup"><span data-stu-id="9ccaa-127">Service order margin</span></span>         |
|<span data-ttu-id="9ccaa-128">Hantera kundförfrågningar</span><span class="sxs-lookup"><span data-stu-id="9ccaa-128">Handle customer inquiries</span></span> |<span data-ttu-id="9ccaa-129">Serviceorder</span><span class="sxs-lookup"><span data-stu-id="9ccaa-129">Service orders</span></span>                         |<span data-ttu-id="9ccaa-130">Arbetsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="9ccaa-130">Work description</span></span>             |
|                          |<span data-ttu-id="9ccaa-131">Utförseltavla</span><span class="sxs-lookup"><span data-stu-id="9ccaa-131">Dispatch board</span></span>                         |<span data-ttu-id="9ccaa-132">Transaktion - abonnemang</span><span class="sxs-lookup"><span data-stu-id="9ccaa-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="9ccaa-133">Abonnemangsavgiftstransaktioner</span><span class="sxs-lookup"><span data-stu-id="9ccaa-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="9ccaa-134">Integrering av servicehantering</span><span class="sxs-lookup"><span data-stu-id="9ccaa-134">Integration of Service management</span></span>

<span data-ttu-id="9ccaa-135">Servicehantering kan integreras med följande moduler:</span><span class="sxs-lookup"><span data-stu-id="9ccaa-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="9ccaa-136">Försäljning och marknadsföring</span><span class="sxs-lookup"><span data-stu-id="9ccaa-136">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="9ccaa-137">Personal</span><span class="sxs-lookup"><span data-stu-id="9ccaa-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

