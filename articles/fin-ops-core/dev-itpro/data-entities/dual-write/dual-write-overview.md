---
title: Översikt över dubbelriktad skrivning
description: Det här ämnet ger en översikt över dubbelriktad skrivning som ger en medföljande infrastruktur mellan kundengagemangsappar och Finance and Operations-appar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6cc02b483a2975dd3be28032ea7e90b540945492
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561288"
---
# <a name="dual-write-overview"></a><span data-ttu-id="ca1ea-103">Översikt över dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="ca1ea-103">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a><span data-ttu-id="ca1ea-104">Vad är dubbelriktad skrivning?</span><span class="sxs-lookup"><span data-stu-id="ca1ea-104">What is dual-write?</span></span>

<span data-ttu-id="ca1ea-105">Dubbelriktad skrivning är en medföljande infrastruktur som ger nära realtidssamverkan mellan kundengagemangsappar och Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-105">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between customer engagement apps and Finance and Operations apps.</span></span> <span data-ttu-id="ca1ea-106">När data om kunder, produkter, personer och verksamhet går utanför programgränser, är alla avdelningar i organisationen berättigade.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-106">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="ca1ea-107">Dubbelriktad skrivning ger tätt kombinerad, dubbelriktad integration mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-107">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="ca1ea-108">Alla dataändringar i Finance and Operations-appar orsakar skrivningar till Dataverse och alla dataändringar i Dataverse orsakar skrivningar till Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-108">Any data change in Finance and Operations apps causes writes to Dataverse, and any data change in Dataverse causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="ca1ea-109">Det här automatiserade dataflödet ger ett integrerat användargränssnitt mellan programmen.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-109">This automated data flow provides an integrated user experience across the apps.</span></span>

![Datarelation mellan appar](media/dual-write-overview.jpg)

<span data-ttu-id="ca1ea-111">Dubbelriktad skrivning har två aspekter: en *infrastruktur* aspekt och en *applikation* aspekt.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-111">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="ca1ea-112">Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="ca1ea-112">Infrastructure</span></span>

<span data-ttu-id="ca1ea-113">Infrastrukturen för dubbelriktad skrivning är utökningsbar och tillförlitlig och innehåller följande huvudfunktioner:</span><span class="sxs-lookup"><span data-stu-id="ca1ea-113">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="ca1ea-114">Synkront och dubbelriktat dataflöde mellan program</span><span class="sxs-lookup"><span data-stu-id="ca1ea-114">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="ca1ea-115">Synkronisering, tillsammans med lägena spela upp, pausa och sammanfattning för att stödja systemet i online- och offline-/asynkrona lägen.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-115">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="ca1ea-116">Möjlighet att synkronisera ursprungliga data mellan programmen</span><span class="sxs-lookup"><span data-stu-id="ca1ea-116">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="ca1ea-117">Kombinerad vy över aktivitet och felloggar för dataadministratörer</span><span class="sxs-lookup"><span data-stu-id="ca1ea-117">Combined view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="ca1ea-118">Möjlighet att konfigurera anpassade aviseringar och tröskelvärden samt att prenumerera på meddelanden</span><span class="sxs-lookup"><span data-stu-id="ca1ea-118">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="ca1ea-119">Intuitivt användargränssnitt (UI) för filtrering och transformeringar</span><span class="sxs-lookup"><span data-stu-id="ca1ea-119">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="ca1ea-120">Möjlighet att ställa in och visa tabellberoenden och relationer</span><span class="sxs-lookup"><span data-stu-id="ca1ea-120">Ability to set and view table dependencies and relationships</span></span>
+ <span data-ttu-id="ca1ea-121">Utökningsbarhet för både standard- och anpassade tabeller och mappningar</span><span class="sxs-lookup"><span data-stu-id="ca1ea-121">Extensibility for both standard and custom tables and maps</span></span>
+ <span data-ttu-id="ca1ea-122">Tillförlitlig program livscykelhantering</span><span class="sxs-lookup"><span data-stu-id="ca1ea-122">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="ca1ea-123">Installations upplevelse utanför lådan för nya kunder</span><span class="sxs-lookup"><span data-stu-id="ca1ea-123">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="ca1ea-124">Ansökning</span><span class="sxs-lookup"><span data-stu-id="ca1ea-124">Application</span></span>

<span data-ttu-id="ca1ea-125">Dubbelriktad skrivning skapar en mappning mellan koncept i Finance and Operations-appar och koncept i kundengagemangsappar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-125">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in customer engagement apps.</span></span> <span data-ttu-id="ca1ea-126">Denna integration stöder följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="ca1ea-126">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="ca1ea-127">Integrerad kundmaster</span><span class="sxs-lookup"><span data-stu-id="ca1ea-127">Integrated customer master</span></span>
+ <span data-ttu-id="ca1ea-128">Tillgång till kundförmånskort och belöningspoäng</span><span class="sxs-lookup"><span data-stu-id="ca1ea-128">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="ca1ea-129">Enhetlig produkthanteringsupplevelse</span><span class="sxs-lookup"><span data-stu-id="ca1ea-129">Unified product mastering experience</span></span>
+ <span data-ttu-id="ca1ea-130">Medvetenhet över organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="ca1ea-130">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="ca1ea-131">Integrerat leverantörshuvud</span><span class="sxs-lookup"><span data-stu-id="ca1ea-131">Integrated vendor master</span></span>
+ <span data-ttu-id="ca1ea-132">Åtkomst till ekonomi- och momsreferensdata</span><span class="sxs-lookup"><span data-stu-id="ca1ea-132">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="ca1ea-133">Prismotor upplevelse på begäran</span><span class="sxs-lookup"><span data-stu-id="ca1ea-133">On-demand price engine experience</span></span>
+ <span data-ttu-id="ca1ea-134">Integrerad potentiell kund till pengar-upplevelse</span><span class="sxs-lookup"><span data-stu-id="ca1ea-134">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="ca1ea-135">Möjlighet att betjäna både interna tillgångar och kundtillgångar via fältagenter</span><span class="sxs-lookup"><span data-stu-id="ca1ea-135">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="ca1ea-136">Integrerat procure-to-pay-upplevelse</span><span class="sxs-lookup"><span data-stu-id="ca1ea-136">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="ca1ea-137">Integrerade aktiviteter och anteckningar för kunddata och dokument</span><span class="sxs-lookup"><span data-stu-id="ca1ea-137">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="ca1ea-138">Möjlighet att söka efter tillgänglighet för lagerbehållning och information</span><span class="sxs-lookup"><span data-stu-id="ca1ea-138">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="ca1ea-139">Projekt till kontanter-upplevelse</span><span class="sxs-lookup"><span data-stu-id="ca1ea-139">Project-to-cash experience</span></span>
+ <span data-ttu-id="ca1ea-140">Möjlighet att hantera flera adresser och roller via partens begrepp</span><span class="sxs-lookup"><span data-stu-id="ca1ea-140">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="ca1ea-141">En källhantering för användare</span><span class="sxs-lookup"><span data-stu-id="ca1ea-141">Single source management for users</span></span>
+ <span data-ttu-id="ca1ea-142">Integrerade kanaler för återförsäljning och marknadsföring</span><span class="sxs-lookup"><span data-stu-id="ca1ea-142">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="ca1ea-143">Synlighet för erbjudanden och rabatter</span><span class="sxs-lookup"><span data-stu-id="ca1ea-143">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="ca1ea-144">Funktioner för service för begäran</span><span class="sxs-lookup"><span data-stu-id="ca1ea-144">Request-for-service functions</span></span>
+ <span data-ttu-id="ca1ea-145">Förenklade tjänsteåtgärder</span><span class="sxs-lookup"><span data-stu-id="ca1ea-145">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="ca1ea-146">Främsta anledningar att använda dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="ca1ea-146">Top reasons to use dual-write</span></span>

<span data-ttu-id="ca1ea-147">Dubbelriktad skrivning ger dataintegrering i Microsoft Dynamics 365-program.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-147">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="ca1ea-148">Detta robusta ramverk länkar sig till miljöer och gör att olika affärsprogram kan fungera tillsammans.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-148">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="ca1ea-149">Här följer de viktigaste skälen till varför du bör använda dubbelriktad skrivning:</span><span class="sxs-lookup"><span data-stu-id="ca1ea-149">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="ca1ea-150">Dubbelriktad skrivning ger tätt sammankopplade, nära realtid och dubbelriktad integration mellan Finance and Operations-appar och modellstyrda appar i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-150">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="ca1ea-151">Den här integrationen gör Microsoft Dynamics 365 en enda kontaktpunkt för alla dina affärslösningar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-151">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="ca1ea-152">Kunder som använder Dynamics 365 Finance och Dynamics 365 Supply Chain Management, men som inte använder Microsoft-lösningar för hantering av kundrelationer (CRM), flyttar till Dynamics 365 för sitt stöd till dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-152">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="ca1ea-153">Data från kunder, produkter, åtgärder, projekt och sakernas Internet (IoT) skickas automatiskt till Dataverse via dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-153">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Dataverse through dual-write.</span></span> <span data-ttu-id="ca1ea-154">Denna anslutning är användbar för företag som är intresserade av Power Platform expansioner.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-154">This connection is useful for businesses that are interested in Power Platform expansions.</span></span>
+ <span data-ttu-id="ca1ea-155">Infrastrukturen för dubbelriktad skrivning följer principen för ingen kod/ingen kod.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-155">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="ca1ea-156">Minsta tekniska ansträngning krävs för att utöka standardmappningarna mellan tabeller och för att inkludera anpassade kartor.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-156">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="ca1ea-157">Dubbelriktad skrivning stöder både online-läge och offline-läge.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-157">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="ca1ea-158">Microsoft är det enda företaget som har stöd för online- och offline-lägen.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-158">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a><span data-ttu-id="ca1ea-159">Vad innebär dubbla skrivmedel för utvecklare och arkitekter av kundengagemangsappar?</span><span class="sxs-lookup"><span data-stu-id="ca1ea-159">What does dual-write mean for developers and architects of customer engagement apps?</span></span>

<span data-ttu-id="ca1ea-160">Vid dubbelriktad skrivning automatiseras dataflödet mellan Finance and Operations-appar och kundengagemangsappar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-160">Dual-write automates the data flow between Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="ca1ea-161">Dubbelriktad skrivning består av två AppSource-lösningar som är installerade på Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-161">Dual-write consists of two AppSource solutions that are installed on Dataverse.</span></span> <span data-ttu-id="ca1ea-162">Lösningarna utökar tabellens schema, plugin-program och arbetsflöden i Dataverse så att de kan skalas till ERP-storlek.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-162">The solutions expand the table schema, plugins, and workflows on Dataverse so that they can scale to ERP size.</span></span> <span data-ttu-id="ca1ea-163">För att implementeringen ska lyckas måste utvecklare och arkitekter av kundengagemangsappar kunna känna till dessa ändringar och samarbeta med deras motsvarigheter på Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-163">For a successful implementation, developers and architects of customer engagement apps must understand these changes and collaborate with their counterparts on Finance and Operations apps.</span></span>

<span data-ttu-id="ca1ea-164">Om du vill skapa paritet med Finance and Operations-appar gör dubbelriktad skrivning några viktiga ändringar i Dataverse-schemat.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-164">To create parity with Finance and Operations applications, dual-write makes some crucial changes in the Dataverse schema.</span></span> <span data-ttu-id="ca1ea-165">Om du förstår planen kan du undvika att en del design och utveckling fungerar i framtiden.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-165">If you understand the plan, you can avoid some design and development rework in the future.</span></span>

+ <span data-ttu-id="ca1ea-166">När AppSource-paketet för dubbelriktad skrivning är installerat får Dataverse nya begrepp som företag och part.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-166">When the dual-write AppSource package is installed, Dataverse will have new concepts such as company and party.</span></span> <span data-ttu-id="ca1ea-167">De här begreppen hjälper appar som bygger på Dataverse, bland annat Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service och Dynamics 365 Field Service , för att interagera sömlöst med Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-167">These concepts help applications built on Dataverse, including Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service, to interact seamlessly with Finance and Operations apps.</span></span>

+ <span data-ttu-id="ca1ea-168">Aktiviteter och anteckningar är enhetliga och expanderade för att stödja både C1s (användare av systemet) och C2s (kunder i systemet).</span><span class="sxs-lookup"><span data-stu-id="ca1ea-168">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>

+ <span data-ttu-id="ca1ea-169">För att förhindra att data går förlorade under överföring mellan olika Finance and Operations-appar och i Dataverse kan du öka antalet decimaler i datatypen kundengagemangsappar.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-169">To prevent data loss during currency transmission between Finance and Operations apps and the Dataverse, you'll be able to extend the number of decimal places in the currency data type of customers engagement apps.</span></span> <span data-ttu-id="ca1ea-170">Funktionen översätter befintliga rader till det nya utökade tillståndet i metadata-skiktet.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-170">The feature autotranslates existing rows to the new extended state at the metadata layer.</span></span> <span data-ttu-id="ca1ea-171">Under den här processen översätts valutavärdet till decimal data snarare än pengadata och valuta värdet stöder 10 decimaler.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-171">During this process, the currency value is translated to decimal data rather than money data, and the currency value supports 10 decimal places.</span></span> <span data-ttu-id="ca1ea-172">Den här funktionen är inte skrivskyddad och organisationer som inte behöver mer än 4 decimalers precision behöver inte välja något.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-172">This feature is opt-in, and organizations that don't need more than 4 decimal places of precision do not need to opt in.</span></span> <span data-ttu-id="ca1ea-173">Mer information finns i [Migrering av valutadatatyp för dubbelriktad skrivning](currrency-decimal-places.md) .</span><span class="sxs-lookup"><span data-stu-id="ca1ea-173">For more information, see [Currency data-type migration for dual-write](currrency-decimal-places.md).</span></span>

+ <span data-ttu-id="ca1ea-174">[Gäller från](../../dev-tools/date-effectivity.md) kommer att läggas till i Dataverse .</span><span class="sxs-lookup"><span data-stu-id="ca1ea-174">[Date effectivity](../../dev-tools/date-effectivity.md) will be added to Dataverse.</span></span> <span data-ttu-id="ca1ea-175">Det kommer att stödja tidigare, nuvarande och framtida data om samma tabell.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-175">It will support past, present, and future data on the same table.</span></span>

+ <span data-ttu-id="ca1ea-176">Produkt [enhetskonverteringar](../../../../supply-chain/pim/tasks/manage-unit-measure.md) stöds för produkter, offerter, order och fakturor.</span><span class="sxs-lookup"><span data-stu-id="ca1ea-176">Product [unit conversions](../../../../supply-chain/pim/tasks/manage-unit-measure.md) are supported for products, quotes, orders, and invoices.</span></span>

<span data-ttu-id="ca1ea-177">Mer information om kommande ändringar finns i [nyheter och ändringar i dubbelriktad skrivning](whats-new-dual-write.md) .</span><span class="sxs-lookup"><span data-stu-id="ca1ea-177">For more information about upcoming changes, see [What's new or changed in dual-write](whats-new-dual-write.md).</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]