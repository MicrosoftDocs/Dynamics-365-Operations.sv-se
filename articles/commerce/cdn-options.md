---
title: Implementeringsalternativ för Content Delivery Network
description: Detta ämne granskar de olika alternativen för implementering av nätverk för innehållsleverans (CDN) som kan användas med with Microsoft Dynamics 365 Commerce miljöer. Dessa alternativ omfattar inbyggda, Commerce-försedd instanser av Azure Front Door och kundägda instanser av Azure Front Door.
author: BrianShook
manager: AnnBe
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ae0769b7e19f80244186c51454444c499c5e497f
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582813"
---
# <a name="content-delivery-network-implementation-options"></a><span data-ttu-id="5cd86-104">Implementeringsalternativ för Content Delivery Network</span><span class="sxs-lookup"><span data-stu-id="5cd86-104">Content delivery network implementation options</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5cd86-105">Detta ämne granskar de olika alternativen för implementering av nätverk för innehållsleverans (CDN) som kan användas med with Microsoft Dynamics 365 Commerce miljöer.</span><span class="sxs-lookup"><span data-stu-id="5cd86-105">This topic reviews the different options for content delivery network (CDN) implementation that can be used with Microsoft Dynamics 365 Commerce environments.</span></span> <span data-ttu-id="5cd86-106">Dessa alternativ omfattar inbyggda, Commerce-försedd instanser av Azure Front Door och kundägda instanser av Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="5cd86-106">These options include native, Commerce-provided instances of Azure Front Door and customer-owned instances of Azure Front Door.</span></span>

<span data-ttu-id="5cd86-107">Commerce-kunder har flera alternativ när de överväger vilken CDN-tjänst som ska användas med sin Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="5cd86-107">Commerce customers have several options when they are considering which CDN service to use with their Commerce environment.</span></span> <span data-ttu-id="5cd86-108">Commerce släpps med grundläggande Azure Front Door support som omfattar grundläggande krav på värdskap och anpassade domänkrav.</span><span class="sxs-lookup"><span data-stu-id="5cd86-108">Commerce is released with basic Azure Front Door support that covers basic hosting and custom domain requirements.</span></span> <span data-ttu-id="5cd86-109">För företag som vill ha mer kontroll och specifika säkerhetsförmågor, till exempel en brandvägg för webbprogram (WAF), är det bästa alternativet att använda antingen en kundägd instans av Azure Front Door eller en extern CDN-tjänst.</span><span class="sxs-lookup"><span data-stu-id="5cd86-109">For companies that want more control and more specific security abilities, such as a web application firewall (WAF), the best option might be to use either a customer-owned instance of Azure Front Door or an external CDN service.</span></span>

<span data-ttu-id="5cd86-110">Följande tre alternativ för CDN-implementering kan användas i Commerce-miljöer:</span><span class="sxs-lookup"><span data-stu-id="5cd86-110">The following three CDN implementation options can be used with Commerce environments:</span></span>

- <span data-ttu-id="5cd86-111">Den Commerce-instans av Azure Front Door</span><span class="sxs-lookup"><span data-stu-id="5cd86-111">The Commerce-provided instance of Azure Front Door</span></span>
- <span data-ttu-id="5cd86-112">En kundägd instans av Azure Front Door (för ökad kontroll och ytterligare säkerhetsfunktioner)</span><span class="sxs-lookup"><span data-stu-id="5cd86-112">A customer-owned instance of Azure Front Door (for increased control and additional security features)</span></span>
- <span data-ttu-id="5cd86-113">En extern CDN-tjänst</span><span class="sxs-lookup"><span data-stu-id="5cd86-113">An external CDN service</span></span>

<span data-ttu-id="5cd86-114">Alla tre implementeringsalternativen för CDN levererar endast dynamiskt HTML-innehåll från anpassade domäner.</span><span class="sxs-lookup"><span data-stu-id="5cd86-114">All three CDN implementation options deliver only dynamic HTML content from custom domains.</span></span> <span data-ttu-id="5cd86-115">Commerce hanterar automatiskt alla JavaScript, Cascading Style Sheets (CSS), bilder, video och annat statiskt innehåll via Microsoft-hanterade CDN.</span><span class="sxs-lookup"><span data-stu-id="5cd86-115">Commerce automatically handles all JavaScript, Cascading Style Sheets (CSS), images, video, and other static content through Microsoft-managed CDNs.</span></span> <span data-ttu-id="5cd86-116">Alternativet du väljer bestämmer vilka funktioner som finns tillgängliga för verksamheten, kontrollfunktionerna och ytterligare säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="5cd86-116">The option that you choose determines the operational capabilities, control capabilities, and additional security capabilities that are available.</span></span>

<span data-ttu-id="5cd86-117">Följande bild ger en översikt över ändringarna i Commerce-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="5cd86-117">The following illustration shows an overview of the Commerce architecture.</span></span>

![Översikt över Commerce-arkitektur](media/Commerce_CDN-Option_ComparisonModels.png)

<span data-ttu-id="5cd86-119">Mer information om hur du ställer in en instans av Azure Front Door för din Commerce-webbplats finns i [Lägg till CDN-support](add-cdn-support.md).</span><span class="sxs-lookup"><span data-stu-id="5cd86-119">For more information about how to set up an instance of Azure Front Door for your Commerce site, see [Add CDN Support](add-cdn-support.md).</span></span>

## <a name="use-the-commerce-provided-azure-front-door-instance"></a><span data-ttu-id="5cd86-120">Använd Commerce som tillhandahålls av Azure Front Door-instansen</span><span class="sxs-lookup"><span data-stu-id="5cd86-120">Use the Commerce-provided Azure Front Door instance</span></span>

<span data-ttu-id="5cd86-121">Följande tabell visar fördelar och nackdelar med att använda den förekomst av Commerce-instans av Azure Front Door för att hantera innehållsslutpunkter.</span><span class="sxs-lookup"><span data-stu-id="5cd86-121">The following table lists the pros and cons of using the Commerce-provided instance of Azure Front Door to manage content endpoints.</span></span>

| <span data-ttu-id="5cd86-122">Fördelar</span><span class="sxs-lookup"><span data-stu-id="5cd86-122">Pros</span></span> | <span data-ttu-id="5cd86-123">Nackdelar</span><span class="sxs-lookup"><span data-stu-id="5cd86-123">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="5cd86-124">Instansen inkluderas i Commerce-kostnaden.</span><span class="sxs-lookup"><span data-stu-id="5cd86-124">The instance is included in the Commerce cost.</span></span></li><li><span data-ttu-id="5cd86-125">Eftersom instansen hanteras av Commerce-teamet krävs mindre underhåll och det finns delade inställningssteg.</span><span class="sxs-lookup"><span data-stu-id="5cd86-125">Because the instance is managed by the Commerce team, less maintenance is required, and there are shared setup steps.</span></span></li><li><span data-ttu-id="5cd86-126">Den infrastruktur som har Azure-värd är skalbar, säker och tillförlitlig.</span><span class="sxs-lookup"><span data-stu-id="5cd86-126">The Azure-hosted infrastructure is scalable, secure, and reliable.</span></span></li><li><span data-ttu-id="5cd86-127">SSL-certifikatet (Secure Sockets Layer) kräver en inställning vid ett tillfälle och förnyas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5cd86-127">The Secure Sockets Layer (SSL) certificate requires a one-time setup and is automatically renewed.</span></span></li><li><span data-ttu-id="5cd86-128">Instansen övervakas för fel och fel av Commerce-teamet.</span><span class="sxs-lookup"><span data-stu-id="5cd86-128">The instance is monitored for errors and anomalies by the Commerce team.</span></span></li></ul> | <ul><li><span data-ttu-id="5cd86-129">En WAF stöds inte.</span><span class="sxs-lookup"><span data-stu-id="5cd86-129">A WAF isn't supported.</span></span></li><li><span data-ttu-id="5cd86-130">Det finns inga särskilda anpassningar eller inställningsjusteringar.</span><span class="sxs-lookup"><span data-stu-id="5cd86-130">There are no specific customizations or setting adjustments.</span></span></li><li><span data-ttu-id="5cd86-131">Instansen beror på om Commerce-teamet behöver uppdateringar eller ändringar.</span><span class="sxs-lookup"><span data-stu-id="5cd86-131">The instance depends on the Commerce team for updates or changes.</span></span></li><li><span data-ttu-id="5cd86-132">En separat Azure Front Door-instans krävs för apex-domäner och extra arbete krävs för att integrera apex-domäner med Azure DNS.</span><span class="sxs-lookup"><span data-stu-id="5cd86-132">A separate Azure Front Door instance is required for apex domains, and extra work is required to integrate apex domains with Azure DNS.</span></span></li><li><span data-ttu-id="5cd86-133">Det finns ingen telemeter om svar per andra (RPS) eller så visas ingen felsats för kunden.</span><span class="sxs-lookup"><span data-stu-id="5cd86-133">No telemetry about responses per second (RPS) or the error rate is provided to the customer.</span></span></li></ul> |

<span data-ttu-id="5cd86-134">Följande illustration visar arkitekturen för den Commerce Azure Front Door-instansen.</span><span class="sxs-lookup"><span data-stu-id="5cd86-134">The following illustration shows the architecture of the Commerce-provided Azure Front Door instance.</span></span>

![Commerce som tillhandahålls av Azure Front Door-instansen](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a><span data-ttu-id="5cd86-136">Använda en kundägd Azure Front Door-instans</span><span class="sxs-lookup"><span data-stu-id="5cd86-136">Use a customer-owned Azure Front Door instance</span></span>

<span data-ttu-id="5cd86-137">Följande tabell visar fördelar och nackdelar med att använda en kundägd instans av Azure Front Door för att hantera innehållsslutpunkter.</span><span class="sxs-lookup"><span data-stu-id="5cd86-137">The following table lists the pros and cons of using a customer-owned instance of Azure Front Door to manage content endpoints.</span></span>

| <span data-ttu-id="5cd86-138">Fördelar</span><span class="sxs-lookup"><span data-stu-id="5cd86-138">Pros</span></span> | <span data-ttu-id="5cd86-139">Nackdelar</span><span class="sxs-lookup"><span data-stu-id="5cd86-139">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="5cd86-140">Inställningarna är säkra och enkla att hantera.</span><span class="sxs-lookup"><span data-stu-id="5cd86-140">Setup is secure and easy to manage.</span></span></li><li><span data-ttu-id="5cd86-141">Den infrastruktur som har Azure-värd är skalbar, säker och tillförlitlig.</span><span class="sxs-lookup"><span data-stu-id="5cd86-141">The Azure-hosted infrastructure is scalable, secure, and reliable.</span></span></li><li><span data-ttu-id="5cd86-142">Instansen tillåter WAF-integration och finregelkontroller för fingradig säkerhet som finjusteras specifikt för din site.</span><span class="sxs-lookup"><span data-stu-id="5cd86-142">The instance allows for WAF integration and granular rule controls for finer-grade security that is tuned specifically for your site.</span></span></li><li><span data-ttu-id="5cd86-143">Instansen tillåter finare kontroll av SSL-certifikat (både kundägda och Azure Front Door-hanterade) och domänlänkning.</span><span class="sxs-lookup"><span data-stu-id="5cd86-143">The instance allows for finer control of SSL certificates (both customer-owned and Azure Front Door–managed) and domain linking.</span></span></li><li><span data-ttu-id="5cd86-144">Instansen erbjuder en apex-domänlösning om den kopplas direkt till Azure DNS.</span><span class="sxs-lookup"><span data-stu-id="5cd86-144">The instance offers an apex domain solution if it's paired directly with Azure DNS.</span></span></li><li><span data-ttu-id="5cd86-145">Telemeter och notifieringar visas.</span><span class="sxs-lookup"><span data-stu-id="5cd86-145">Telemetry and alerting are provided.</span></span></li><li><span data-ttu-id="5cd86-146">SSL-certifikatet kräver en inställning vid ett tillfälle och förnyas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5cd86-146">The SSL certificate requires a one-time setup and is automatically renewed.</span></span></li></ul> | <ul><li><span data-ttu-id="5cd86-147">Instansen är självstyrd.</span><span class="sxs-lookup"><span data-stu-id="5cd86-147">The instance is self-managed.</span></span></li><li><span data-ttu-id="5cd86-148">Den initiala kunskaperna som behövs.</span><span class="sxs-lookup"><span data-stu-id="5cd86-148">Initial knowledge ramp-up is required.</span></span></li></ul> |

<span data-ttu-id="5cd86-149">I följande bild visas en Commerce-infrastruktur som omfattar en kundägd Azure Front Door-instans.</span><span class="sxs-lookup"><span data-stu-id="5cd86-149">The following illustration shows a Commerce infrastructure that includes a customer-owned Azure Front Door instance.</span></span>

![Commerce-infrastruktur som omfattar en kundägd Azure Front Door-instans.](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a><span data-ttu-id="5cd86-151">Använd en extern CDN-tjänst</span><span class="sxs-lookup"><span data-stu-id="5cd86-151">Use an external CDN service</span></span>

<span data-ttu-id="5cd86-152">I följande tabell beskrivs fördelarna och fördelarna med att använda en extern CDN-tjänst för hantering av innehållsslutpunkter.</span><span class="sxs-lookup"><span data-stu-id="5cd86-152">The following table lists the pros and cons of using an external CDN service to manage content endpoints.</span></span>

| <span data-ttu-id="5cd86-153">Fördelar</span><span class="sxs-lookup"><span data-stu-id="5cd86-153">Pros</span></span> | <span data-ttu-id="5cd86-154">Nackdelar</span><span class="sxs-lookup"><span data-stu-id="5cd86-154">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="5cd86-155">Det här alternativet är användbart när den befintliga domänen redan finns på ett externt CDN-nätverk.</span><span class="sxs-lookup"><span data-stu-id="5cd86-155">This option is useful when the existing domain is already hosted on an external CDN.</span></span></li><li><span data-ttu-id="5cd86-156">Konkurrentens CDN (till exempel Akamai) kan ha fler WAF-funktioner.</span><span class="sxs-lookup"><span data-stu-id="5cd86-156">Competitor CDNs (for example, Akamai) might have more WAF capabilities.</span></span></li></ul> | <ul><li><span data-ttu-id="5cd86-157">Ett separat kontrakt och ytterligare kostnader krävs.</span><span class="sxs-lookup"><span data-stu-id="5cd86-157">A separate contract and additional costing are required.</span></span></li><li><span data-ttu-id="5cd86-158">SSL kan ådra sig ytterligare kostnader.</span><span class="sxs-lookup"><span data-stu-id="5cd86-158">SSL might incur additional costs.</span></span></li><li><span data-ttu-id="5cd86-159">Eftersom tjänsten är skild från Azure molnbaserade struktur måste ytterligare infrastruktur hanteras.</span><span class="sxs-lookup"><span data-stu-id="5cd86-159">Because the service is separate from the Azure cloud structure, additional infrastructure must be managed.</span></span></li><li><span data-ttu-id="5cd86-160">Tjänsten kan kräva längre tidsplaceringar i slutpunkts- och säkerhetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="5cd86-160">The service might require longer time investments in endpoint and security setup.</span></span></li><li><span data-ttu-id="5cd86-161">Tjänsten är självstyrd.</span><span class="sxs-lookup"><span data-stu-id="5cd86-161">The service is self-managed.</span></span></li><li><span data-ttu-id="5cd86-162">Tjänsten är självövervakad.</span><span class="sxs-lookup"><span data-stu-id="5cd86-162">The service is self-monitored.</span></span></li></ul> |

<span data-ttu-id="5cd86-163">I följande bild visas en Commerce-infrastruktur med en extern CDN-tjänst.</span><span class="sxs-lookup"><span data-stu-id="5cd86-163">The following illustration shows a Commerce infrastructure that includes an external CDN service.</span></span>

![Commerce-infrastruktur som innehåller en extern CDN-tjänst](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a><span data-ttu-id="5cd86-165">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5cd86-165">Additional resources</span></span>

[<span data-ttu-id="5cd86-166">Lägga till stöd för nätverk för innehållsleverans</span><span class="sxs-lookup"><span data-stu-id="5cd86-166">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
