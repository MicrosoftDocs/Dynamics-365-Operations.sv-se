---
title: Implementeringsalternativ för Content Delivery Network
description: Detta ämne granskar de olika alternativen för implementering av nätverk för innehållsleverans (CDN) som kan användas med with Microsoft Dynamics 365 Commerce miljöer. Dessa alternativ omfattar inbyggda, Commerce-försedd instanser av Azure Front Door och kundägda instanser av Azure Front Door.
author: BrianShook
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 73da1fff8f79b4fcde38f9da643b8a3479247959f763976d782279e4e2af7a33
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729924"
---
# <a name="content-delivery-network-implementation-options"></a>Implementeringsalternativ för Content Delivery Network

[!include [banner](includes/banner.md)]

Detta ämne granskar de olika alternativen för implementering av nätverk för innehållsleverans (CDN) som kan användas med with Microsoft Dynamics 365 Commerce miljöer. Dessa alternativ omfattar inbyggda, Commerce-försedd instanser av Azure Front Door och kundägda instanser av Azure Front Door.

Commerce-kunder har flera alternativ när de överväger vilken CDN-tjänst som ska användas med sin Commerce-miljö. Commerce släpps med grundläggande Azure Front Door support som omfattar grundläggande krav på värdskap och anpassade domänkrav. För företag som vill ha mer kontroll och specifika säkerhetsförmågor, till exempel en brandvägg för webbprogram (WAF), är det bästa alternativet att använda antingen en kundägd instans av Azure Front Door eller en extern CDN-tjänst.

Följande tre alternativ för CDN-implementering kan användas i Commerce-miljöer:

- Den Commerce-instans av Azure Front Door
- En kundägd instans av Azure Front Door (för ökad kontroll och ytterligare säkerhetsfunktioner)
- En extern CDN-tjänst

Alla tre implementeringsalternativen för CDN levererar endast dynamiskt HTML-innehåll från anpassade domäner. Commerce hanterar automatiskt alla JavaScript, Cascading Style Sheets (CSS), bilder, video och annat statiskt innehåll via Microsoft-hanterade CDN. Alternativet du väljer bestämmer vilka funktioner som finns tillgängliga för verksamheten, kontrollfunktionerna och ytterligare säkerhetsfunktioner.

Följande bild ger en översikt över ändringarna i Commerce-arkitektur.

![Översikt över Commerce-arkitekturen.](media/Commerce_CDN-Option_ComparisonModels.png)

Mer information om hur du ställer in en instans av Azure Front Door för din Commerce-webbplats finns i [Lägg till CDN-support](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>Använd Commerce som tillhandahålls av Azure Front Door-instansen

Följande tabell visar fördelar och nackdelar med att använda den förekomst av Commerce-instans av Azure Front Door för att hantera innehållsslutpunkter.

| Fördelar | Nackdelar |
|------|------|
| <ul><li>Instansen inkluderas i Commerce-kostnaden.</li><li>Eftersom instansen hanteras av Commerce-teamet krävs mindre underhåll och det finns delade inställningssteg.</li><li>Den infrastruktur som har Azure-värd är skalbar, säker och tillförlitlig.</li><li>SSL-certifikatet (Secure Sockets Layer) kräver en inställning vid ett tillfälle och förnyas automatiskt.</li><li>Instansen övervakas för fel och fel av Commerce-teamet.</li></ul> | <ul><li>En strukturlista stöds inte.</li><li>Det finns inga särskilda anpassningar eller inställningsjusteringar.</li><li>Instansen beror på om Commerce-teamet behöver uppdateringar eller ändringar.</li><li>En separat Azure Front Door-instans krävs för apex-domäner och extra arbete krävs för att integrera apex-domäner med Azure DNS.</li><li>Det finns ingen telemeter om svar per andra (RPS) eller så visas ingen felsats för kunden.</li></ul> |

Följande illustration visar arkitekturen för den Commerce Azure Front Door-instansen.

![Commerce-tillhandahållen Azure Front Door-instans.](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Använda en kundägd Azure Front Door-instans

Följande tabell visar fördelar och nackdelar med att använda en kundägd instans av Azure Front Door för att hantera innehållsslutpunkter.

| Fördelar | Nackdelar |
|------|------|
| <ul><li>Inställningarna är säkra och enkla att hantera.</li><li>Den infrastruktur som har Azure-värd är skalbar, säker och tillförlitlig.</li><li>Instansen tillåter WAF-integration och finregelkontroller för fingradig säkerhet som finjusteras specifikt för din site.</li><li>Instansen tillåter finare kontroll av SSL-certifikat (både kundägda och Azure Front Door-hanterade) och domänlänkning.</li><li>Instansen erbjuder en apex-domänlösning om den kopplas direkt till Azure DNS.</li><li>Telemeter och notifieringar visas.</li><li>SSL-certifikatet kräver en inställning vid ett tillfälle och förnyas automatiskt.</li></ul> | <ul><li>Instansen är självstyrd.</li><li>Den initiala kunskaperna som behövs.</li></ul> |

I följande bild visas en Commerce-infrastruktur som omfattar en kundägd Azure Front Door-instans.

![Commerce-infrastruktur som omfattar en kundägd Azure Front Door-instans.](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>Använd en extern CDN-tjänst

I följande tabell beskrivs fördelarna och fördelarna med att använda en extern CDN-tjänst för hantering av innehållsslutpunkter.

| Fördelar | Nackdelar |
|------|------|
| <ul><li>Det här alternativet är användbart när den befintliga domänen redan finns på ett externt CDN-nätverk.</li><li>Strukturlista: Beror på extern leverantör.</li></ul> | <ul><li>Ett separat kontrakt och ytterligare kostnader krävs.</li><li>SSL kan ådra sig ytterligare kostnader.</li><li>Eftersom tjänsten är skild från Azure molnbaserade struktur måste ytterligare infrastruktur hanteras.</li><li>Tjänsten kan kräva längre tidsplaceringar i slutpunkts- och säkerhetsinställningar.</li><li>Tjänsten är självstyrd.</li><li>Tjänsten är självövervakad.</li></ul> |

I följande bild visas en Commerce-infrastruktur med en extern CDN-tjänst.

![Commerce-infrastruktur som innehåller en extern CDN-tjänst.](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till stöd för nätverk för innehållsleverans](add-cdn-support.md)
