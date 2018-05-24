---
title: Servicehantering
description: "Använd Servicehantering för att fastställa serviceavtal och serviceabonnemang, hantera serviceordrar och kundförfrågningar, och för att hantera och analysera leverans av tjänster till kunder."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: sv-se
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="32e71-103">Servicehantering</span><span class="sxs-lookup"><span data-stu-id="32e71-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="32e71-104">Använd **Servicehantering** för att fastställa serviceavtal och serviceabonnemang, hantera serviceordrar och kundförfrågningar, och för att hantera och analysera leverans av tjänster till kunder.</span><span class="sxs-lookup"><span data-stu-id="32e71-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="32e71-105">Du kan använda serviceavtal när du vill definiera resurser som används vid ett vanligt servicebesök.</span><span class="sxs-lookup"><span data-stu-id="32e71-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="32e71-106">Du kan också använda serviceavtal du vill visa hur resurserna kan faktureras kunden.</span><span class="sxs-lookup"><span data-stu-id="32e71-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="32e71-107">Ett serviceavtal kan även innehålla ett serviceavtal som anger svarstider, och erbjuder verktyg för att registrera den faktiska tiden.</span><span class="sxs-lookup"><span data-stu-id="32e71-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="32e71-108">Du kan skapa serviceorder du vill hantera information om schemalagda och icke tidsplanerade servicebesök av en servicetekniker till en kunds anläggning.</span><span class="sxs-lookup"><span data-stu-id="32e71-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="32e71-109">Serviceorder innehåller information som:</span><span class="sxs-lookup"><span data-stu-id="32e71-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="32e71-110">Arbetstiderna som serviceteknikern ska utföra</span><span class="sxs-lookup"><span data-stu-id="32e71-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="32e71-111">Typ av tjänst eller reparation</span><span class="sxs-lookup"><span data-stu-id="32e71-111">The type of service or repair</span></span>

3.  <span data-ttu-id="32e71-112">Artikeln som ska repareras, inklusive information om symptom och diagnoser</span><span class="sxs-lookup"><span data-stu-id="32e71-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="32e71-113">Utgifter och avgifter som är relaterade till tjänsten eller reparationen</span><span class="sxs-lookup"><span data-stu-id="32e71-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="32e71-114">Kunder kan skicka in serviceförfrågningar via Internet med hjälp av Enterprise Portal.</span><span class="sxs-lookup"><span data-stu-id="32e71-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="32e71-115">Du kan ta emot, behandla och skicka ut dessa frågor.</span><span class="sxs-lookup"><span data-stu-id="32e71-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="32e71-116">När du har skapat en serviceorder kan du använda servicefaser för att övervaka förlopp och ange regler som styr vilka åtgärder som ska aktiveras i varje fas.</span><span class="sxs-lookup"><span data-stu-id="32e71-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="32e71-117">När en serviceorder är avslutad, kan du godkänna ordern för att bekräfta att den är slutförd, och sedan bokföra ordern för att starta fakturaprocessen.</span><span class="sxs-lookup"><span data-stu-id="32e71-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="32e71-118">Använd rapporteringsverktygen för att övervaka serviceordermarginaler och abonnemangstransaktioner, och skriva ut arbetsbeskrivningar och arbetsinleveranser.</span><span class="sxs-lookup"><span data-stu-id="32e71-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="32e71-119">Affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="32e71-119">Business processes</span></span>

<span data-ttu-id="32e71-120">I följande diagram illustreras den höga nivån av affärsprocesser för **servicehantering**, och visar var serviceprocesser integreras med andra moduler i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32e71-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="32e71-121">[![Affärsprocessdiagram för servicehantering](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="32e71-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="32e71-122">Snabb överblick över servicehantering</span><span class="sxs-lookup"><span data-stu-id="32e71-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="32e71-123">Viktiga uppgifter</span><span class="sxs-lookup"><span data-stu-id="32e71-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="32e71-124">Primära formulär</span><span class="sxs-lookup"><span data-stu-id="32e71-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="32e71-125">Populära rapporter</span><span class="sxs-lookup"><span data-stu-id="32e71-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32e71-126">Uppfyll serviceavtal</span><span class="sxs-lookup"><span data-stu-id="32e71-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="32e71-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Serviceavtal (formulär)</a></span><span class="sxs-lookup"><span data-stu-id="32e71-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="32e71-128"><strong>Serviceordermarginal</strong></span><span class="sxs-lookup"><span data-stu-id="32e71-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32e71-129">Hantera kundförfrågningar</span><span class="sxs-lookup"><span data-stu-id="32e71-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="32e71-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Serviceorder (formulär)</a></span><span class="sxs-lookup"><span data-stu-id="32e71-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="32e71-131"><strong>Arbetsbeskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="32e71-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="32e71-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Utförseltavla (formulär)</a></span><span class="sxs-lookup"><span data-stu-id="32e71-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="32e71-133"><strong>Transaktion - abonnemang</strong></span><span class="sxs-lookup"><span data-stu-id="32e71-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="32e71-134"><strong>Abonnemangsavgiftstransaktioner</strong></span><span class="sxs-lookup"><span data-stu-id="32e71-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="32e71-135">Integrering av servicehantering</span><span class="sxs-lookup"><span data-stu-id="32e71-135">Integration of Service management</span></span>

<span data-ttu-id="32e71-136">Servicehanteringen kan integreras med följande moduler i Microsoft Dynamics 365 for Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="32e71-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="32e71-137">Försäljning och marknadsföring</span><span class="sxs-lookup"><span data-stu-id="32e71-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="32e71-138">Personal</span><span class="sxs-lookup"><span data-stu-id="32e71-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


