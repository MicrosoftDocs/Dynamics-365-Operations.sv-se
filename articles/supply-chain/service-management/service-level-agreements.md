---
title: Servicenivåavtal – översikt
description: I ett serviceavtal går kunden med på en minimisvarstid från det att serviceföretaget registrerar ärendet tills det har lösts.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01cdfe519e55ca2a9aa17f4ac181ee675b2793cf
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982365"
---
# <a name="service-level-agreements-overview"></a><span data-ttu-id="76686-103">Servicenivåavtal – översikt</span><span class="sxs-lookup"><span data-stu-id="76686-103">Service level agreements overview</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="76686-104">Ett servicenivåavtal (SLA) är ett avtal mellan ett serviceföretag och en servicekund.</span><span class="sxs-lookup"><span data-stu-id="76686-104">A service level agreement (SLA) is an agreement between a service company and a service customer.</span></span> <span data-ttu-id="76686-105">I ett SLA går kunden med på en minimisvarstid från det att serviceföretaget registrerar ärendet tills det har lösts.</span><span class="sxs-lookup"><span data-stu-id="76686-105">In a SLA, the customer agrees to a minimum response time based on when the service company records the issue and when the issue is resolved.</span></span>

<span data-ttu-id="76686-106">Ett SLA utgör en standardmall för vilken servicenivå som erbjuds en kund, så att det blir lätt för serviceföretaget att se när ett servicejobb ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="76686-106">A SLA enforces a standard level of service that is offered to customers, and also makes it transparent to a service company when a service job should be completed.</span></span>

<span data-ttu-id="76686-107">Du kan skapa valfritt antal servicenivåavtal för att kunna erbjuda servicekunder olika servicenivåer.</span><span class="sxs-lookup"><span data-stu-id="76686-107">Any number of SLAs can be created to offer service customers different levels of service.</span></span>

## <a name="create-a-service-level-agreement"></a><span data-ttu-id="76686-108">Skapa ett servicenivåavtal.</span><span class="sxs-lookup"><span data-stu-id="76686-108">Create a service level agreement</span></span>

1.  <span data-ttu-id="76686-109">Klicka på **servicehantering** \> **inställningar** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="76686-109">Click **Service management** \> **Setup** \> **Service agreements** \> **Service level agreements**.</span></span>

2.  <span data-ttu-id="76686-110">Välj du ett namn för serviceavtal i fältet **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="76686-110">Type a name for the service level agreement in the **Service level agreement** field.</span></span>

3.  <span data-ttu-id="76686-111">Ange den tidpunkt då du vill att servicesamtal som är kopplade till serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="76686-111">Type the time that you want to allow for completion of service calls that are attached to the service level agreement.</span></span> <span data-ttu-id="76686-112">Välj en kalender om du vill basera serviceavtalet på för en specifik kalender.</span><span class="sxs-lookup"><span data-stu-id="76686-112">Then select a calendar if you want to base the service level agreement on a specific calendar.</span></span>

## <a name="apply-a-service-level-agreement"></a><span data-ttu-id="76686-113">Tillämpa ett servicenivåavtal</span><span class="sxs-lookup"><span data-stu-id="76686-113">Apply a service level agreement</span></span>

<span data-ttu-id="76686-114">Avtalet tillämpas direkt för ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="76686-114">The SLA is applied directly to a service agreement.</span></span>

<span data-ttu-id="76686-115">Serviceorder som du skapar manuellt och kopplar till ett serviceavtal med ett servicenivåavtal jämförs med detta servicenivåavtal.</span><span class="sxs-lookup"><span data-stu-id="76686-115">Service orders that you create manually and attach to a service agreement that has an SLA are measured against that SLA.</span></span>

<span data-ttu-id="76686-116">Serviceorder som skapas automatiskt kopplas inte till något servicenivåavtal.</span><span class="sxs-lookup"><span data-stu-id="76686-116">Service orders that you create automatically are not attached to an SLA.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a><span data-ttu-id="76686-117">Tillämpa servicenivåavtalet för ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="76686-117">Apply the service level agreement to the service agreement</span></span>

1.  <span data-ttu-id="76686-118">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="76686-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="76686-119">Välj det serviceavtal som du vill tillämpa serviceavtalet för och klicka på **redigera** på **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="76686-119">Select the service agreement that you want to apply the SLA to, and then click **Edit** on the **Action Pane**.</span></span>

2.  <span data-ttu-id="76686-120">I fältet **serviceavtal**, markera serviceavtalet som du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="76686-120">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a><span data-ttu-id="76686-121">Tillämpa servicenivåavtalet för en serviceavtalsgrupp</span><span class="sxs-lookup"><span data-stu-id="76686-121">Apply the service level agreement to the service agreement group</span></span>

1.  <span data-ttu-id="76686-122">Klicka på **servicehantering** \> **inställningar** \> **serviceavtal** \> **serviceavtalsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="76686-122">Click **Service management** \> **Setup** \> **Service agreements** \> **Service agreement groups**.</span></span>

2.  <span data-ttu-id="76686-123">I fältet **serviceavtal**, markera serviceavtalet som du vill tilldela.</span><span class="sxs-lookup"><span data-stu-id="76686-123">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="track-time-on-a-service-order-against-an-sla"></a><span data-ttu-id="76686-124">Spåra tid på en serviceorder mot ett servicenivåavtal</span><span class="sxs-lookup"><span data-stu-id="76686-124">Track time on a service order against an SLA</span></span>

<span data-ttu-id="76686-125">När du skapar en ny serviceorder för ett serviceavtal som har tilldelats ett serviceavtal initieras tidsintervallet för leverans av tjänsten och systemet börjar spåra leveranstiden.</span><span class="sxs-lookup"><span data-stu-id="76686-125">When you create a new service order for a service agreement that an SLA is assigned to, the time interval for the delivery of the service is initiated, and the system starts to track the delivery time.</span></span> <span data-ttu-id="76686-126">Du kan dessutom ange följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="76686-126">Additionally, you can set the following options:</span></span>

  - <span data-ttu-id="76686-127">Du kan starta och stoppa tidsregistreringen på serviceordern för att registrera den totala tid som läggs på en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="76686-127">You can start and stop time recording on the service order to register the total amount of time that is spent on service orders.</span></span>

  - <span data-ttu-id="76686-128">Du kan övervaka efterföljandegraden inom det intervall som har angetts i serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="76686-128">You can monitor compliance with the time interval that is set in the service level agreement.</span></span>

  - <span data-ttu-id="76686-129">Du kan definiera orsakskoder som måste anges om det intervall som har angetts i serviceavtalet överskrids.</span><span class="sxs-lookup"><span data-stu-id="76686-129">You can define reason codes that must be set if the time interval of the service level agreement is exceeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="76686-130">Se även</span><span class="sxs-lookup"><span data-stu-id="76686-130">See also</span></span>

[<span data-ttu-id="76686-131">Visa efterlevnad av servicenivåavtal</span><span class="sxs-lookup"><span data-stu-id="76686-131">View compliance with service level agreements</span></span>](view-compliance-with-service-level-agreements.md)

  


