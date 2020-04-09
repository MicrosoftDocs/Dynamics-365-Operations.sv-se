---
title: Översikt över dubbelriktad skrivning
description: Det här ämnet ger en översikt över dubbelriktad skrivning. Dubbelriktad skrivning är en infrastruktur som ger nära realtids samverkan mellan Microsoft Dynamics 365 modellstyrda appar och Finance and Operations-appar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 64626ebdd7fbad3d47a4b4c6bbc45bf3bc0c8277
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172794"
---
# <a name="dual-write-overview"></a><span data-ttu-id="d6a68-104">Översikt över dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="d6a68-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="what-is-dual-write"></a><span data-ttu-id="d6a68-105">Vad är dubbelriktad skrivning?</span><span class="sxs-lookup"><span data-stu-id="d6a68-105">What is dual-write?</span></span>

<span data-ttu-id="d6a68-106">Dubbelriktad skrivning är en medföljande infrastruktur som ger nära realtidssamverkan mellan Microsoft Dynamics 365 och Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="d6a68-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="d6a68-107">När data om kunder, produkter, personer och verksamhet går utanför programgränser, är alla avdelningar i organisationen berättigade.</span><span class="sxs-lookup"><span data-stu-id="d6a68-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="d6a68-108">Dubbelriktad skrivning ger tätt kombinerad, dubbelriktad integration mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d6a68-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="d6a68-109">Alla dataändringar i Finance and Operations-appar orsakar skrivningar till Common Data Service och alla dataändringar i Common Data Service orsakar skrivningar till Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="d6a68-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="d6a68-110">Det här automatiserade dataflödet ger ett integrerat användargränssnitt mellan programmen.</span><span class="sxs-lookup"><span data-stu-id="d6a68-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Datarelation mellan appar](media/dual-write-overview.jpg)

<span data-ttu-id="d6a68-112">Dubbelriktad skrivning har två aspekter: en *infrastruktur* aspekt och en *applikation* aspekt.</span><span class="sxs-lookup"><span data-stu-id="d6a68-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="d6a68-113">Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="d6a68-113">Infrastructure</span></span>

<span data-ttu-id="d6a68-114">Infrastrukturen för dubbelriktad skrivning är utökningsbar och tillförlitlig och innehåller följande huvudfunktioner:</span><span class="sxs-lookup"><span data-stu-id="d6a68-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="d6a68-115">Synkront och dubbelriktat dataflöde mellan program</span><span class="sxs-lookup"><span data-stu-id="d6a68-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="d6a68-116">Synkronisering, tillsammans med lägena spela upp, pausa och sammanfattning för att stödja systemet i online- och offline-/asynkrona lägen.</span><span class="sxs-lookup"><span data-stu-id="d6a68-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="d6a68-117">Möjlighet att synkronisera ursprungliga data mellan programmen</span><span class="sxs-lookup"><span data-stu-id="d6a68-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="d6a68-118">Konsoliderad vy över aktivitet och felloggar för dataadministratörer</span><span class="sxs-lookup"><span data-stu-id="d6a68-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="d6a68-119">Möjlighet att konfigurera anpassade aviseringar och tröskelvärden samt att prenumerera på meddelanden</span><span class="sxs-lookup"><span data-stu-id="d6a68-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="d6a68-120">Intuitivt användargränssnitt (UI) för filtrering och transformeringar</span><span class="sxs-lookup"><span data-stu-id="d6a68-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="d6a68-121">Möjlighet att ställa in och visa enhetsberoenden och relationer</span><span class="sxs-lookup"><span data-stu-id="d6a68-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="d6a68-122">Utökningsbarhet för både standard- och anpassade entiteter och kartor</span><span class="sxs-lookup"><span data-stu-id="d6a68-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="d6a68-123">Tillförlitlig program livscykelhantering</span><span class="sxs-lookup"><span data-stu-id="d6a68-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="d6a68-124">Installations upplevelse utanför lådan för nya kunder</span><span class="sxs-lookup"><span data-stu-id="d6a68-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="d6a68-125">Ansökning</span><span class="sxs-lookup"><span data-stu-id="d6a68-125">Application</span></span>

<span data-ttu-id="d6a68-126">Dubbelriktad skrivning skapar en mappning mellan koncept i Finance and Operations-appar och koncept i modellstyrda appar i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6a68-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="d6a68-127">Denna integration stöder följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="d6a68-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="d6a68-128">Integrerad kundmaster</span><span class="sxs-lookup"><span data-stu-id="d6a68-128">Integrated customer master</span></span>
+ <span data-ttu-id="d6a68-129">Tillgång till kundförmånskort och belöningspoäng</span><span class="sxs-lookup"><span data-stu-id="d6a68-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="d6a68-130">Enhetlig produkthanteringsupplevelse</span><span class="sxs-lookup"><span data-stu-id="d6a68-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="d6a68-131">Medvetenhet över organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="d6a68-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="d6a68-132">Integrerat leverantörshuvud</span><span class="sxs-lookup"><span data-stu-id="d6a68-132">Integrated vendor master</span></span>
+ <span data-ttu-id="d6a68-133">Åtkomst till ekonomi- och momsreferensdata</span><span class="sxs-lookup"><span data-stu-id="d6a68-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="d6a68-134">Prismotor upplevelse på begäran</span><span class="sxs-lookup"><span data-stu-id="d6a68-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="d6a68-135">Integrerad potentiell kund till pengar-upplevelse</span><span class="sxs-lookup"><span data-stu-id="d6a68-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="d6a68-136">Möjlighet att betjäna både interna tillgångar och kundtillgångar via fältagenter</span><span class="sxs-lookup"><span data-stu-id="d6a68-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="d6a68-137">Integrerat procure-to-pay-upplevelse</span><span class="sxs-lookup"><span data-stu-id="d6a68-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="d6a68-138">Integrerade aktiviteter och anteckningar för kunddata och dokument</span><span class="sxs-lookup"><span data-stu-id="d6a68-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="d6a68-139">Möjlighet att söka efter tillgänglighet för lagerbehållning och information</span><span class="sxs-lookup"><span data-stu-id="d6a68-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="d6a68-140">Projekt till kontanter-upplevelse</span><span class="sxs-lookup"><span data-stu-id="d6a68-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="d6a68-141">Möjlighet att hantera flera adresser och roller via partens begrepp</span><span class="sxs-lookup"><span data-stu-id="d6a68-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="d6a68-142">En källhantering för användare</span><span class="sxs-lookup"><span data-stu-id="d6a68-142">Single source management for users</span></span>
+ <span data-ttu-id="d6a68-143">Integrerade kanaler för återförsäljning och marknadsföring</span><span class="sxs-lookup"><span data-stu-id="d6a68-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="d6a68-144">Synlighet för erbjudanden och rabatter</span><span class="sxs-lookup"><span data-stu-id="d6a68-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="d6a68-145">Funktioner för service för begäran</span><span class="sxs-lookup"><span data-stu-id="d6a68-145">Request-for-service functions</span></span>
+ <span data-ttu-id="d6a68-146">Förenklade tjänsteåtgärder</span><span class="sxs-lookup"><span data-stu-id="d6a68-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="d6a68-147">Främsta anledningar att använda dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="d6a68-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="d6a68-148">Dubbelriktad skrivning ger dataintegrering i Microsoft Dynamics 365-program.</span><span class="sxs-lookup"><span data-stu-id="d6a68-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="d6a68-149">Detta robusta ramverk länkar sig till miljöer och gör att olika affärsprogram kan fungera tillsammans.</span><span class="sxs-lookup"><span data-stu-id="d6a68-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="d6a68-150">Här följer de viktigaste skälen till varför du bör använda dubbelriktad skrivning:</span><span class="sxs-lookup"><span data-stu-id="d6a68-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="d6a68-151">Dubbelriktad skrivning ger tätt sammankopplade, nära realtid och dubbelriktad integration mellan Finance and Operations-appar och modellstyrda appar i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6a68-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="d6a68-152">Den här integrationen gör Microsoft Dynamics 365 en enda kontaktpunkt för alla dina affärslösningar.</span><span class="sxs-lookup"><span data-stu-id="d6a68-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="d6a68-153">Kunder som använder Dynamics 365 Finance och Dynamics 365 Supply Chain Management, men som inte använder Microsoft-lösningar för hantering av kundrelationer (CRM), flyttar till Dynamics 365 för sitt stöd till dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="d6a68-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="d6a68-154">Data från kunder, produkter, åtgärder, projekt och sakernas Internet (IoT) skickas automatiskt till Common Data Service via dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="d6a68-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="d6a68-155">Denna anslutning är mycket användbar för företag som är intresserade av Microsoft Power Platform expansioner.</span><span class="sxs-lookup"><span data-stu-id="d6a68-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="d6a68-156">Infrastrukturen för dubbelriktad skrivning följer principen för ingen kod/ingen kod.</span><span class="sxs-lookup"><span data-stu-id="d6a68-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="d6a68-157">Minsta tekniska ansträngning krävs för att utöka standardmappningarna mellan tabeller och för att inkludera anpassade kartor.</span><span class="sxs-lookup"><span data-stu-id="d6a68-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="d6a68-158">Dubbelriktad skrivning stöder både online-läge och offline-läge.</span><span class="sxs-lookup"><span data-stu-id="d6a68-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="d6a68-159">Microsoft är det enda företaget som har stöd för online- och offline-lägen.</span><span class="sxs-lookup"><span data-stu-id="d6a68-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="d6a68-160">Vad betyder dubbelriktad skrivning för användare och arkitekter av CRM-produkter?</span><span class="sxs-lookup"><span data-stu-id="d6a68-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="d6a68-161">Vid dubbelriktad skrivning automatiseras dataflödet mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d6a68-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="d6a68-162">I framtida versioner kommer begreppen i modellstyrda appar i Dynamics 365 (t.ex. kund, kontakt, offert och order) att skalas till mellan marknaden och kunder på den övre marknaden.</span><span class="sxs-lookup"><span data-stu-id="d6a68-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="d6a68-163">I den första versionen hanteras den mesta av automatisering av lösningar för dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="d6a68-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="d6a68-164">I framtida versioner kommer dessa lösningar att bli en del av Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d6a68-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="d6a68-165">Genom att förstå de kommande ändringarna i Common Data Service, kan du spara pengar på lång sikt.</span><span class="sxs-lookup"><span data-stu-id="d6a68-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="d6a68-166">Här är några av de avgörande förändringarna:</span><span class="sxs-lookup"><span data-stu-id="d6a68-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="d6a68-167">Common Data Service kommer att ha nya begrepp, t.ex. företag och part.</span><span class="sxs-lookup"><span data-stu-id="d6a68-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="d6a68-168">Dessa begrepp påverkar alla program som är byggda på Common Data Service, till exempel Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service och Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="d6a68-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="d6a68-169">Aktiviteter och anteckningar är enhetliga och expanderade för att stödja både C1s (användare av systemet) och C2s (kunder i systemet).</span><span class="sxs-lookup"><span data-stu-id="d6a68-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="d6a68-170">Här är några av de kommande ändringarna i Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="d6a68-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="d6a68-171">Den decimala datatypen ersätter datatypen pengar.</span><span class="sxs-lookup"><span data-stu-id="d6a68-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="d6a68-172">Gäller från kommer att stödja tidigare, nuvarande och framtida data på samma ställe.</span><span class="sxs-lookup"><span data-stu-id="d6a68-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="d6a68-173">Det kommer att bli mer stöd för valuta och valutakurser och API:n **Valutakurs** kommer att revideras.</span><span class="sxs-lookup"><span data-stu-id="d6a68-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="d6a68-174">Enhetskonverteringar stöds.</span><span class="sxs-lookup"><span data-stu-id="d6a68-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="d6a68-175">Mer information om kommande ändringar finns i [Data i Common Data Service – fas 1 och 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).</span><span class="sxs-lookup"><span data-stu-id="d6a68-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).</span></span>
