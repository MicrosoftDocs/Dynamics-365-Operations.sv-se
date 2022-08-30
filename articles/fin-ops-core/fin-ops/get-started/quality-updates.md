---
title: Förebyggande kvalitetsuppdateringar
description: I den här artikeln finns information om förebyggande leverans av kvalitetsuppdateringar.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338149"
---
# <a name="proactive-quality-updates"></a>Förebyggande kvalitetsuppdateringar

[!include[banner](../includes/banner.md)]

Under de senaste åren har Microsoft gjort kontinuerliga framsteg i vad vi kallar [en version](../../dev-itpro/lifecycle-services/oneversion-overview.md). För en version är det enkelt: ju närmare vi kan komma att ha alla kunder i samma programvaruversion, desto högre kvalitet kan vi leverera. Vi hittar och löser problem en gång och får dessa lösningar snabbare till fler kunder.

Denna förutsättning bekräftas av resultaten: lägre antal incident inom alla våra produkter. När kunder inte har samma version ser vi konsekvent att de påverkas av problem som en lösning redan finns tillgänglig för. Vi har redan gjort stora framsteg med Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations och Dynamics 365 Commerce, och tack vare de senaste tekniska framstegen är det nu möjligt att ta nästa steg. Följande information får veta vad vi ska göra, vad vi redan har gjort för att ställa in fasen och hur och när vi kommer att införa den nya kapaciteten utan störningar.

## <a name="focus-on-quality-updates"></a>Fokusera på kvalitetsuppdateringar

Vi tillhandahåller för närvarande sju [serviceuppdateringar](public-preview-releases.md) per år. Version 10.0.29 är till exempel en serviceuppdatering. Tills nyligen gjordes åtta uppdateringar per år. Vi har dock utelämnat en uppdatering på grund av feedback från kunder som visar en vilja att undvika ändringar i slutet av kalenderåret.

Vi ändrar inte takten för serviceuppdateringarna. I stället fokuseras nästa steg framåt i en versionen på *kvalitetsuppdateringar*. Kvalitetsuppdateringar är ackumulerade versioner av snabbkorrigeringar. De innehåller inga nya funktioner. När som helst sprids hela communityn med kunder mellan de tre eller fyra senaste serviceuppdateringarna. För en given serviceuppdatering kan dock dussintals olika kvalitetsuppdateringsversioner användas inom gruppen, beroende på vilka datum som personer distribueras. I nästa steg skickar vi kvalitetsuppdateringar i förebyggande syfte. Vi använder redan den här modellen för våra Dataverse-baserade program och har sett de förväntade resultaten av förbättrad kvalitet och minskat support.

En reducering av defekter kan givetvis minska eller eliminera behovet av kvalitetsuppdateringar. Vi har flera initiativ inom företaget för att minska de fel som kräver kvalitetsuppdateringar. Även när nyttolasterna minskar i kvalitetsuppdateringen kommer konsekvens över hela kundbasen att förbättra stödet, få förbättringar till kunderna snabbare och minska frekvensen av kunder som stöter på problem som lösningar redan finns för.

## <a name="making-proactive-distribution-possible"></a>Göra förebyggande distribution möjlig

Flera framsteg har redan distribuerats som aktiverar förebyggande leverans av kvalitetsuppdateringar:

- **Uppdatera nära noll driftstoppstid** – För att driva på mer frekventa miljöer är det viktigt att påverkan på miljötillgängligheten minskas för att bevara Dynamics 365 servicenivåavtal (SLA). Uppdatering av nära noll driftstoppstid finns ursprungligen för att förbättra den månatliga operativsystemets uppdatering genom att använda ett kluster-underkluster för att aktivera den uppdaterade bilden med minimal påverkan. Mekanismen för att tillämpa uppdateringar förbättras så att den är ännu mindre störande och den kommer att täcka både korrigering av operativsystem och distribution av kvalitetsuppdateringar.

    För interaktiva användare kan en aktiv session avbrytas, och det nya försöket går till den nu uppdaterade miljön. Med introduktionen av [prioriterad batchplanering](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), som nu är tillgänglig på väljbasis, återställs och återupptas batchschemaläggning och bearbetning omedelbart efter uppdateringen. Prioriterad batchplanering gäller för kunder innan de börjar delta i förebyggande distribution av kvalitetsuppdateringar för sina produktionsmiljöer.

- **Mörka timmar** – Mörka timmar definieras för varje Azure-region, och uppdateringar av tiden nära noll inträffar under den mörktimmarsperioden.

## <a name="the-proactive-update-process"></a>Den förebyggande uppdateringsprocessen

När förebyggande kvalitetsuppdateringar distribueras följer en SDP (Safe Deployment Process). SDP specifika uppgifter kommer att förändras, men kvalitetsuppdateringar distribueras inledningsvis till sandbox-miljöer. Processen startar med miljöer där du kan välja att använda den tidigare distributionen. Allt eftersom procentandelen av de distribuerade koderna ökar, börjar distributionen till produktionsmiljöerna. Återigen startar processen med miljöer där du kan välja att använda den tidigare distributionen. Ett system för övervakning av telemetri- och aktiv webbplats-incidenter och därför stoppas sammanslagningen av en specifik version om någon av dem hittas. Kunderna kan fortfarande hämta kvalitetsuppdateringarna före förebyggande användning om de vill.

Aktuella data för hantering av frisläppning visar att mindre än 3 procent av dessa finns med i kvalitetsuppdateringar. Med ökat fokus på att eliminera regression och en förbättrad SDP, kommer den potentiella effekten av regressioner att bli dramatiskt lägre än de kvalitetsvinster som uppnås genom att snabbare få en bred distribuering av korrigeringar till kunder.

## <a name="process-changes"></a>Bearbeta ändringar

En uppsättning processändringar implementeras innan förebyggande kvalitetsuppdatering aktiveras:

- **Schema** – Verktyget säkerställer att versioner med kvalitetsuppdatering endast inkluderar schemaändringar som kan användas när tjänsten är online. Denna metod gör det möjligt att tillämpa uppdateringen med nära noll driftstoppstid.
- **Större förändring som påverkar arbetet** – För närvarande finns det redan ett extra processsteg för att godkänna ändringar för inkludering i en kvalitetsuppdatering. Den som inte är noggrann i det extra steget ökar för att minska potentialen för något. Dela upp ändringar är inte tillåtet i kvalitetsuppdateringar och den större ändringen som påverkar säkerheten hjälper dig att se till att vi uppfyller detta mål.
- **Synlighet** – Vi skickar meddelanden via e-post och Lifecycle Services (LCS) för kommande förebyggande kvalitetsuppdateringar. Supportteams och incident leads kommer dessutom att ha god insyn i var kvalitetsuppdateringar har distribuerats i förebyggande syfte.
- **Version reserv** – Förhandsversion kommer att användas för att gruppera alla ändringar i en proaktiv kvalitetsuppdatering. Om reserv krävs efter en förebyggande distribution kan den göras med hjälp av det system för förhandsversionen.
- **Synkroniserad sandbox beteckning** – Mindre än 20 procent av kunderna har idag flera problem och har en distribution där versionen matchar produktionen som hjälp vid felsökning. Inom en snar framtid kommer vi att introducera möjligheten för kunder att specificera en sandbox-miljö som inte ska ta emot den proaktiva kvalitetsuppdateringsdistributionen tillsammans med andra sandbox men som istället ska få den senare, tillsammans med produktionsmiljön. Observera att om en kund använder en sandbox för att testa en nyare version än produktionen kommer den sandbox att få kvalitetsuppdateringar av den nyare versionen.
- 
## <a name="when-will-proactive-quality-updates-start"></a>När startas förebyggande kvalitetsuppdateringar?

Distributionen av förebyggande kvalitetsuppdateringar för kvalitetsmiljöer förväntas börja i slutet av september eller oktober 2022 för kunder i Azure offentligt moln. Utvärderingsmiljöer börjar också att motta förebyggande uppdatering vid den tidpunkten. I september skickas ett meddelande till varje kund om det förväntade schemat för deras miljöer. Undantag till den förebyggande uppdaterade distributionsprocessen tillåts bara för FDA-reglerade kunder. Vi arbetar fortfarande med hur reglerade miljöer och myndighets molnbaserade kunder ska hanteras.

Under den kommande sexmånadersperioden kommer vi gradvis att öka andelen sandbox-miljöer som får proaktiva uppdateringar, tills alla utsedda miljöer är inkluderade och går vidare till uppdatering av produktionsmiljöer. Under hela perioden kommer vi att övervaka att distributionsprocessen är sömlös och att vi får tillbaka målet att inte avbryta nyttolast.

Eftersom kunderna regelbundet får mindre nyttolaster, förväntar vi oss att processen med nuvarande situation blir enklare. Vi justerar frekvensen för uppdatering av distributionen när vi demonstrerar möjligheten att köra processen utan störningar. Denna process fungerar redan effektivt för vår Dataverse plattform och våra program och levererar de förväntade förbättringarna av servicekvalitet. Vi ser fram emot att ta samma steg framåt för appar för ekonomi och drift.
