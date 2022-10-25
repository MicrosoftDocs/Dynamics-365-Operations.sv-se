---
title: Översikt över efterfrågebaserad materialbehovsplanering (DDMRP)
description: Den här artikeln innehåller information om efterfrågeaktiverad materialbehovsplanering (DDMRP), en planeringsmetodik som baseras på avdelning av tillgång och efterfrågan.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 31b45fdb92cf8a590ff77104f0c8015fb4d329d5
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689499"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Översikt över efterfrågebaserad materialbehovsplanering (DDMRP)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

I flera år har företag använt materialbehovsplanering (MRP) som ett system för att beräkna de material och komponenter som krävs för att tillverka en produkt. Leveranskedjor har nu emellertid förändrats. Delar har längre ledtider eftersom de i allt större utsträckning har sitt ursprung utomlands. Därför har många företag rapporterat att de upplever tomma lager eller överlager, detta eftersom de inte vet hur mycket de ska ha i lager. Det finns också mer marknadsvariationer (ibland felaktigt prognostiserade) och kunderna kräver produkter med kort ledtid. Därför finns det underskott i leveranskedjan över hela världen. Dessutom ger MRP-verktyg ofta planerare tusentals åtgärder att utföra. Därför är det svårt att veta vad man ska fokusera på. Lösningen på många av dessa problem är ofta att växla till efterfrågebaserad materialbehovsplanering (Demand Driven Material Requirements Planning, DDMRP).

DDMRP är en planeringsmetodik som bygger på avdelning av tillgång och efterfrågan. Detta avdelning uppnås genom att konfigurera artiklar med avdelningspunkter. För dessa artiklar underhålls buffertar i syfte att säkerställa att rätt lagermängd innehålls. Avdelning av tillgång och efterfrågan bidrar till att förhindra "pisksnärteffekten", detta eftersom variationer inte vidarebefordras genom kedjan. (*Pisksnärteffekten* syftar på hur små variationer i efterfrågan på butiksnivå kan orsaka progressivt större variationer i efterfrågan på grossist-, leverantörs-, tillverknings- och råmaterialleverantörsnivå.) Varje buffert är avsedd att täcka genomsnittlig användning av en komponent och kan även justeras för att täcka toppar i efterfrågan.

DDMRP har visat sig vara en värdefull planeringsmetodik för variantmiljöer där kundtoleranstiderna är kortare än ackumulerade ledtider.

## <a name="the-five-components-of-ddmrp"></a>De fem komponenterna inom DDMRP

DDMRP har fem sekventiella komponenter (steg). De första tre komponenterna definierar i grund och botten den första konfigurationen för en efterfrågebaserad planeringsmodell för materialbehov. De två sista komponenterna definierar hur metoden används dagligen.

1. **[Strategisk lagerplacering](ddmrp-inventory-positioning.md)** – Identifiera avdelningspunkterna i leveranskedjenätverket. Avdelningspunkter är specifika punkter i din leveranskedja där du lägger en lagerbuffert som du sedan övervakar och fyller på.
2. **[Buffertprofiler och nivåer](ddmrp-buffer-profile-and-levels.md)** – Identifiera buffertstorlekar (minimikvantitet, maximikvantitet och beställningspunkt) samt beställningskvantitet för respektive avdelningspunkt.
3. **[Dynamiska buffertjusteringar](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)** – Justera buffertnivåer baserat på varierande driftparametrar eller planerade framtida händelser.
4. **[Efterfrågestyrd planering](ddmrp-planning.md)** – Generera leveransorder efter behov. Dessa leveransorder omfattar tillverkningsorder, inköpsorder och lageröverföringsorder
5. **[Ytterst samarbetsinriktad och synlig körning](ddmrp-visual-and-collaborative-execution.md)** – Kör leveransorder med hjälp av visualiseringar.

DDMRP används normalt av tillverkare som har en strukturlista med flera nivåer. Det kan emellertid även tillämpas på distributions- och butiksnätverk.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP i Dynamics 365 Supply Chain Management

DDMRP ingår i Microsoft Dynamics 365 Supply Chain Management och kräver inga ytterligare licensavgifter. I Supply Chain Management har DDMRP-funktioner lagts till i den befintliga modulen för **huvudplanering**. Det kräver dock att du använder tillägget Planeringsoptimering. 

DDMRP är integrerat i de befintliga planeringsinställningarna i Supply Chain Management och används tillsammans med dessa inställningar för att komma fram till rätt planeringskonfiguration för din verksamhet. Det styrs av en ny disponeringskod som är helt annorlunda än period, min/max, behov och så vidare. Den nya modulen ersätter inte befintliga planeringsfunktioner. Det ger dig emellertid fler funktioner att använda.
