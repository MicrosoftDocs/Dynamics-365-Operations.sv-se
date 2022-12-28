---
title: Förebyggande kvalitetsuppdateringar
description: I den här artikeln finns information om förebyggande leverans av kvalitetsuppdateringar.
author: rashmansur
ms.date: 11/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7d8de017c54a13a9935d74d33a57813922c9f823
ms.sourcegitcommit: 8aee31d6dffabe13969dd5b9de4e0bf95f53e67e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887141"
---
# <a name="proactive-quality-updates"></a>Förebyggande kvalitetsuppdateringar

[!include[banner](../includes/banner.md)]

Under de senaste åren har Microsoft gjort kontinuerliga framsteg i vad vi kallar [en version](../../dev-itpro/lifecycle-services/oneversion-overview.md). För en version är det enkelt: ju närmare vi kan komma att ha alla kunder i samma programvaruversion, desto högre kvalitet kan vi leverera. Vi hittar och löser problem en gång och får dessa lösningar snabbare till fler kunder.

Denna förutsättning bekräftas av resultaten: lägre antal incident inom alla våra produkter. När kunder inte har samma version ser vi konsekvent att de påverkas av problem som en lösning redan finns tillgänglig för. Vi har redan gjort stora framsteg med Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations och Dynamics 365 Commerce, och tack vare de senaste tekniska framstegen är det nu möjligt att ta nästa steg. Följande information får veta vad vi ska göra, vad vi redan har gjort för att ställa in fasen och hur och när vi kommer att införa den nya kapaciteten utan störningar.

## <a name="what-you-need-to-know"></a>Vad du behöver veta

- Förebyggande kvalitetsuppdateringar (PQU) tillämpas varje månad.
- Undantag för förebyggande kvalitetsuppdateringar tillåts för kunder som är reglerade av den amerikanska Food and Drug Administration (FDA).
- Förebyggande kvalitetsuppdateringar försämrar aldrig miljön eller uppgraderar automatiskt från en serviceuppdateringsversion till en annan. 
- Microsoft bestämmer hur förebyggande kvalitetsuppdateringar ska hanteras för reglerade miljöer, och för kunder med förebyggande åtgärder och för myndighetskunder.
- Meddelanden relaterade till förebyggande kvalitetsuppdateringar bokförs i [Microsoft 365 meddelandecenter](https://admin.microsoft.com/AdminPortal/).
- Fem dagar innan en förebyggande kvalitetsuppdatering tillämpas i en miljö får kunder information om att uppdateringen ska ske.
- Kunder kan inte avbryta eller skjuta upp förebyggande kvalitetsuppdateringar.
- Förebyggande kvalitetsuppdateringar installeras under det regionspecifika [fönstret för planerat underhåll](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
- Kvalitetsuppdateringar är utformade så att risken för problem eller problem är låg och den stöds av Microsoft-data.
- Microsoft rekommenderar riktad testning för specifika problem eller specifika snabbkorrigeringar som hör till en förebyggande kvalitetsuppdatering.
- ALLA sandbox-miljöer, förutom de som har ett tidsbegränsningsundantag beroende på lagstadgade orsaker, kommer att vara registrerade 7 januari 2023.
- Produktionsregistrering för förebyggande kvalitetsuppdateringar kommer att börja från den 21 januari 2023. 
- Produktionsregistrering kommer endast att starta för Lifecycle Services-projekt som har sandbox-miljöer registrerade och där fram tills nu får förebyggande kvalitetsuppdateringar regelbundet för alla supportade serviceuppdateringsversioner. Detta gäller endast för kundmiljöer som inte har tillhandahållits undantag på grund av lagstadgade eller andra juridiska orsaker.
- Nedan finns en fullständig tidsplan med förebyggande kvalitetsuppdateringar för sandbox-miljöer och produktionsmiljöer under 2023.
- Varje serviceuppdatering har minst en PQU-version som pågår eller planeras att påbörjas. När dina miljöer har förflyttats till PQU-processen kan du få en förplanerad förebyggande kvalitetsuppdatering av dem alla när du flyttar till en nyare version av serviceuppdateringen. Kontrollera schemat för att avgöra när en PQU för en serviceuppdatering är tidsplanerad om du tänker uppgradera till en nyare version av tjänsten. 

> [!Note]
> Standardprestandatest (nivå4), premium prestandatest (nivå5) sandbox-miljöer och produktionsmiljöer får PQU på veckoslut. 

## <a name="focus-on-quality-updates"></a>Fokusera på kvalitetsuppdateringar

Vi tillhandahåller för närvarande sju [serviceuppdateringar](public-preview-releases.md) per år. Version 10.0.29 är till exempel en serviceuppdatering. Tills nyligen gjordes åtta uppdateringar per år. Vi har dock utelämnat en uppdatering på grund av feedback från kunder som visar en vilja att undvika ändringar i slutet av kalenderåret.

Vi ändrar inte takten för serviceuppdateringarna. I stället fokuseras nästa steg framåt i en versionen på *kvalitetsuppdateringar*. Kvalitetsuppdateringar är ackumulerade versioner av snabbkorrigeringar. De innehåller inga nya funktioner. När som helst sprids hela communityn med kunder mellan de tre eller fyra senaste serviceuppdateringarna. För en given serviceuppdatering kan dock dussintals olika kvalitetsuppdateringsversioner användas inom gruppen, beroende på vilka datum som personer distribueras. I nästa steg skickar vi kvalitetsuppdateringar i förebyggande syfte. Vi använder redan den här modellen för våra Dataverse-baserade program och har sett de förväntade resultaten av förbättrad kvalitet och minskat support.

En reducering av defekter kan givetvis minska eller eliminera behovet av kvalitetsuppdateringar. Vi har flera initiativ inom företaget för att minska de fel som kräver kvalitetsuppdateringar. Även när nyttolasterna minskar i kvalitetsuppdateringen kommer konsekvens över hela kundbasen att förbättra stödet, få förbättringar till kunderna snabbare och minska frekvensen av kunder som stöter på problem som lösningar redan finns för.

## <a name="making-proactive-distribution-possible"></a>Göra förebyggande distribution möjlig

Flera framsteg har redan distribuerats som aktiverar förebyggande leverans av kvalitetsuppdateringar:

- **Uppdatera nära noll driftstoppstid** – För att driva på mer frekventa miljöer är det viktigt att påverkan på miljötillgängligheten minskas för att bevara Dynamics 365 servicenivåavtal (SLA). Uppdatering av nära noll driftstoppstid finns ursprungligen för att förbättra den månatliga operativsystemets uppdatering genom att använda ett kluster-underkluster för att aktivera den uppdaterade bilden med minimal påverkan. Mekanismen för att tillämpa uppdateringar förbättras så att den är ännu mindre störande och den kommer att täcka både korrigering av operativsystem och distribution av kvalitetsuppdateringar.

    För interaktiva användare kan en aktiv session avbrytas, och det nya försöket går till den nu uppdaterade miljön. Med introduktionen av [prioriterad batchplanering](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), batchschemaläggning och bearbetning omedelbart efter uppdateringen. Prioriterad batchplanering gäller för kunder innan de börjar delta i förebyggande distribution av kvalitetsuppdateringar för sina produktionsmiljöer.

- **Mörka timmar** – Mörka timmar definieras för varje Azure-region, och uppdateringar av tiden nära noll inträffar under den mörktimmarsperioden.

## <a name="the-proactive-update-process"></a>Den förebyggande uppdateringsprocessen

När förebyggande kvalitetsuppdateringar distribueras följer en SDP (Safe Deployment Process). SDP specifika uppgifter kommer att förändras, men kvalitetsuppdateringar distribueras inledningsvis till sandbox-miljöer. Allt eftersom procentandelen av de distribuerade koderna ökar, börjar distributionen till produktionsmiljöerna. Ett system för övervakning av telemetri- och aktiv webbplats-incidenter och därför stoppas sammanslagningen av en specifik version om någon av dem hittas. Kunderna kan fortfarande hämta kvalitetsuppdateringarna före förebyggande användning om de vill.

Aktuella data för hantering av frisläppning visar att mindre än 3 procent av dessa finns med i kvalitetsuppdateringar. Med ökat fokus på att eliminera regression och en förbättrad SDP, kommer den potentiella effekten av regressioner att bli dramatiskt lägre än de kvalitetsvinster som uppnås genom att snabbare få en bred distribuering av korrigeringar till kunder.

## <a name="process-changes"></a>Bearbeta ändringar

En uppsättning processändringar implementeras innan förebyggande kvalitetsuppdatering aktiveras:

- **Schema** – Verktyget säkerställer att versioner med kvalitetsuppdatering endast inkluderar schemaändringar som kan användas när tjänsten är online. Denna metod gör det möjligt att tillämpa uppdateringen med nära noll driftstoppstid.
- **Större förändring som påverkar arbetet** – För närvarande finns det redan ett extra processsteg för att godkänna ändringar för inkludering i en kvalitetsuppdatering. Den som inte är noggrann i det extra steget ökar för att minska potentialen för något. Dela upp ändringar är inte tillåtet i kvalitetsuppdateringar och den större ändringen som påverkar säkerheten hjälper dig att se till att vi uppfyller detta mål.
- **Synlighet** – Meddelanden skickas via administrationscenter, Lifecycle Services och andra tillgängliga kanaler för kommande förebyggande kvalitetsuppdateringar. Supportteams och incident leads kommer dessutom att ha god insyn i var kvalitetsuppdateringar har distribuerats i förebyggande syfte.

    > [!NOTE]
    > Microsoft Communications-teamet undersöker en pågående pågående oavvishet vad gäller e-postverktyget som förhindrar att e-postmeddelanden skickas. Fortsätt att övervaka Microsoft 365 meddelandecenter för inkommande och meddelanden som är relaterade till meddelanden.

- **Felsäker via förhandsversion** – Förhandsversionen kommer att användas för ändring av kod, där det är tillämpligt i en kvalitetsuppdatering eller för att använda den befintliga funktion som är relevant för korrigeringen. Om en reserv eller en ändring måste stängas av efter en förebyggande distribution, kan den göras via systemet för förhandsversionen för att undvika ytterligare fel.
- **Synkroniserad sandbox beteckning** – förskjuten uppdatering till en vald isolerad sandbox-miljö tillsammans med produktion stöds inte just nu. Alla nivå-2- och nivå-3-tjänster får förebyggande uppdateringar minst 7 dagar före produktionsmiljön i ett Lifecycle Services-projekt. Detta gäller endast för kundmiljöer som inte har tillhandahållits undantag på grund av lagstadgade eller andra juridiska orsaker.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Vad är det för fel på sammanslagningen som gäller för kvalitetsuppdateringar?

Distributionen av förebyggande kvalitetsuppdateringar för kvalitetsmiljöer börjar i september eller oktober 2022 för kunder i Azure offentligt moln. Den 1 januari 2023 kommer vi att slutföra 99 % av koderna till förebyggande kvalitetsuppdateringar.

Undantag till den förebyggande uppdaterade distributionsprocessen tillåts bara för FDA-reglerade kunder. Vi arbetar fortfarande med hur reglerade miljöer och myndighets molnbaserade kunder ska hanteras. 

Eftersom kunderna regelbundet får mindre nyttolaster, förväntar vi oss att processen med nuvarande situation blir enklare. Vi justerar frekvensen för uppdatering av distributionen när vi demonstrerar möjligheten att köra processen utan störningar. Denna process fungerar redan effektivt för vår Dataverse plattform och våra program och levererar de förväntade förbättringarna av servicekvalitet. Vi ser fram emot att ta samma steg framåt för appar för ekonomi och drift.


## <a name="when-will-quality-updates-start-for-production-environments"></a>När startas kvalitetsuppdateringar för produktionsmiljöer?
Under de första månaderna av 2023, med början den 15 januari – kommer vi att börja integrera produktionsmiljöer till proaktiva uppdateringar och gradvis öka andelen produktionsmiljöer som får proaktiva uppdateringar. Vi tänker bara hitta en produktionsmiljö i ett Lifecycle Services-projekt där miljöerna redan finns tillgängliga för att ta emot förebyggande uppdateringar. Innan en uppdatering görs får kunder med egen tillverkningsmiljöer information via meddelandecenter eller Lifecycle Services-bannern. Nedan finns en fullständig tidsplan med förebyggande kvalitetsuppdateringar för sandbox-miljöer och produktionsmiljöer under 2023.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Vad är schemat för förebyggande kvalitetsuppdateringar av sandbox?
Mer information om mörka timmar för varje region finns i [Vilka är de planerade underhållsfönstren per region?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a> Förebyggande kvalitetsuppdateringar: 10.0.29
**Programversion: 10.0.1326.70**  
**Motsvarande senaste KB-artikel: 750332**

| Station | Regioner | Slutfört schema | Kommande schema för sandbox|
|---|---|---|---|
| Station 1 | Kanada, centrala, Kanada, östra, Frankrike, centrala, Indien, centrala, Norge, östra, Schweiz, västra | 14 oktober till 17 oktober 2022, 2 november till 5 november 2022, 13 november till 16 november 2022, 5 december till 8 december 2022 | 2 januari till 5 januari 2023 |
| Station 2 | Frankrike, södra, Indien, södra, Norge, västra, Schweiz, norra, Sydafrika, norra, Australien, östra, Storbritannien, södra, Förenade Arabemiraten Nord, Japan, östra, Australien, sydöstra, Sydostasien | 15 oktober till 18 oktober 2022, 2 november till 5 november 2022, 13 november till 16 november 2022, 5 december till 8 december 2022 | 2 januari till 5 januari 2023 |
| Station 3 | Asien, östra, Storbritannien, västra, Japan, västra, Brasilien, södra, Europa, västra, USA, östra, Förenade Arabemiraten, centrala | 16 oktober till 19 oktober 2022, 2 november till 5 november 2022, 13 november till 16 november 2022, 5 december till 8 december 2022 | 2 januari till 5 januari 2023 |
| Station 4 | Europa, norra, USA, centrala, USA, västra | 17 oktober till 20 oktober 2022, 2 november till 5 november 2022, 15 november till 18 november 2022, 5 december till 8 december 2022 | 2 januari till 5 januari 2023 |
| Station 5 | DoD, Government Community Cloud, Kina | Inte schemalagt | Inte schemalagt |

### <a name="proactive-quality-update-release-10030"></a><a name="schedule"></a> Förebyggande kvalitetsuppdateringar: 10.0.30
**Appversion: 10.0.1362.77**
**Motsvarande senaste KB artikel: 767597**

| Station | Regioner | Slutfört schema | Kommande schema för sandbox |
|---|---|---|---|
| Station 1 | Kanada, centrala, Kanada, östra, Frankrike, centrala, Indien, centrala, Norge, östra, Schweiz, västra | 1 december till 4 december 2022 |  13 december till 16 december 2022 | 
| Station 2 | Frankrike, södra, Indien, södra, Norge, västra, Schweiz, norra, Sydafrika, norra, Australien, östra, Storbritannien, södra, Förenade Arabemiraten Nord, Japan, östra, Australien, sydöstra, Sydostasien | 2 december till 5 december 2022 |  13 december till 16 december 2022 | 
| Station 3 | Asien, östra, Storbritannien, västra, Japan, västra, Brasilien, södra, Europa, norra, USA, östra, Förenade Arabemiraten, centrala | 3 december till 6 december 2022 |  13 december till 16 december 2022 | 
| Station 4 | Europa, västra, USA, centrala, USA, västra | 4 december till 7 december 2022 |  13 december till 16 december 2022 | 
| Station 5 | DoD, Government Community Cloud, Kina | Inte schemalagt | Inte schemalagt |

### <a name="proactive-quality-update-calendar-year-2023-schedule"></a><a name="schedule"></a> Planering för förebyggande kvalitetsuppdatering per kalenderår 2023

#### <a name="stations-to-region-mapping"></a><a name="Stations-Regions"></a> Stationer till regionmappning

| Stationer | Regioner |
|---|---|
| Station 1 | Ska definieras |
| Station 2 | Kanada, centrala, Kanada, östra, Frankrike, centrala, Indien, centrala, Norge, östra, Schweiz, västra |
| Station 3 | Frankrike, södra, Indien, södra, Norge, västra, Schweiz, norra, Sydafrika, norra, Australien, östra, Storbritannien, södra, Förenade Arabemiraten Nord, Japan, östra, Australien, sydöstra, Sydostasien |
| Station 4 | Asien, östra, Storbritannien, västra, Japan, västra, Brasilien, södra, Europa, norra, USA, östra, Förenade Arabemiraten, centrala |
| Station 5 | Europa, västra, USA, centrala, USA, västra |
| Station 6 | DoD, Government Community Cloud, Kina |


> [!IMPORTANT]
> Det här är en tidsplan på hög nivå för år 2023. För en mer konkret tidsplan kan du läsa exemplet nedan för 10.0.30 version-2. Det exakta schemat och appversionen uppdateras 7 dagar innan kvalitetsuppdatering av versionsflöde startas.

> [!Note]
> Endast de egenbyggda produktionsmiljöerna får uppdateringen för 10.0.30 version-2 versionsflöde, registrerade miljöer får explicit kommunikation.

| Kvalitetsuppdatering versionsflöde | Frisläpp | Versionsflödets varaktighet |
|---|---|---|
| 10.0.30 version-2 | 16 december 2022 | 2 januari till 29 januari 2023 |
| 10.0.30 version-3 | 13 januari 2023 | 30 januari till 25 februari 2023 |
| 10.0.30 version-4 | 24 februari 2023 | 6 mars till 8 april 2023 |
| 10.0.31 version-1 | 3 februari 2023 | 13 februari 2023 till 18 mars 2023|
| 10.0.31 version-2 | 3 mars 2023 | 13 mars till 15 april 2023|
| 10.0.31 version-3 | 14 april 2023 | 24 april 2023 till 27 maj 2023|
| 10.0.32 version-1 | 31 mars 2023 | 10 april 2023 till 13 maj 2023|
| 10.0.32 version-2 | 28 april 2023 | 8 maj 2023 till 10 juni 2023|
| 10.0.32 version-3 | 26 maj 2023 | 5 juni 2023 till 8 juli 2023|
| 10.0.33 version-1 | 28 april 2023 | 8 maj 2023 till 10 juni 2023|
| 10.0.33 version-2 | 26 maj 2023 | 5 juni 2023 till 8 juli 2023|
| 10.0.33 version-3 | 14 juli 2023 | 24 juli till 26 augusti 2023|
| 10.0.34 version-1 | 23 juni 2023 | 3 juli till 5 augusti 2023|
| 10.0.34 version-2 | 21 juli 2023 | 31 juli till 2 september 2023|
| 10.0.34 version-3 | 1 september 2023 | 11 september till 14 oktober 2023|
| 10.0.35 version-1 | 28 juli 2023 | 7 augusti till 9 september 2023|
| 10.0.35 version-2 | 25 augusti 2023 | 4 september till 7 oktober 2023|
| 10.0.35 version-3 | 20 oktober 2023 | 30 oktober till 16 december 2023|
| 10.0.36 version-1 | 29 september 2023 | 9 oktober 2023 till 11 november 2023|
| 10.0.36 version-2 | 27 oktober 2023 | 6 november till 16 december 2023|
| 10.0.36 version-3 | 12 januari 2024 | 22 januari 2023 till 24 februari 2024|
| 10.0.37 version-1 | 3 november 2023 | 13 november 2023 till 6 januari 2024|
| 10.0.37 version-2 | 30 december 2023 | 8 januari 2024 till 10 februari 2024|
| 10.0.37 version-3 | 27 januari 2024 | 5 februari 2024 till 9 mars 2024|
| 10.0.37 version-4 | 23 februari 2024 | 4 mars till 6 april 2024|

### <a name="proactive-quality-update-upcoming-10030-release-2-train-schedule"></a><a name="schedule"></a> Kommande förebyggande kvalitetsuppdateringar 10.0.30 version-2 versionsflöde
**Programversion: 10.0.1362.99**

| Stationer | Kommande schema för sandbox | Kommande tidsplan för produktion |
|---|---|---|
| Station 1 | NA | NA |
| Station 2 | 2 januari till 5 januari 2023 | 21 januari till 22 januari 2023 |
| Station 3 | 3 januari till 6 januari 2023 | 28 januari till 29 januari 2023 |
| Station 4 | 9 januari till 12 januari 2023 | NA |
| Station 5 | 16 januari till 19 januari 2023 | NA |
| Station 6 | NA | NA |

> [!IMPORTANT] 
> Fem dagar i förväg uppdaterar Microsoft föregående schema och skickar ett meddelande till de miljöer som har tidsplanerats att få dessa kvalitetsuppdateringar. Föregående schema kan endast tillämpas på de miljöer som har meddelats om en kommande uppdatering. Mer information om mörka timmar för varje region finns i [Vilka är de planerade underhållsfönstren per region?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
>
> För varje regiongrupp, eller *station* en kvalitetsuppdatering för närvarande ska rullas ut, visar schemat ett intervall på fyra dagar. Kvalitetsuppdateringar startar enbart med sandbox-miljöer. Sedan, när andelen framgångsrikt implementerade sandbox ökar, kommer distributionen till produktionsmiljöer att börja med förhandsmeddelanden till kunder.
> 
> Kvalitetsuppdateringar kommer alltid att ske på ett rullande sätt som gör det möjligt för oss att rikta in oss på en uppsättning miljöer per schema och slutföra alla uppsättningar i slutet av den fjärde dagen för en station. Detta innebär dock inte att en miljöuppdatering kommer att omfatta fyra dagar. Det innebär bara att vi inte kan förutbestämma vilken uppsättning miljöer som ska uppdateras en viss dag inom fyradagarsintervallet. Alla uppdateringar görs under mörka timmar, med nära noll-drifttid. Uppdateringar avslutas regelbundet inom ett mörktimmarsfönster i en viss region.

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Hur hanteras de mörka timmarna för kunder som har en instans för appar för ekonomi och drift men är aktiva i flera tidszoner? 
Det finns inga speciella tidsplaner utanför de mörka timmarna där det finns instanser av appar för ekonomi och drift eftersom vi planerar att distribuera kvalitetsuppdateringar med minimal avbrott med [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="what-is-the-current-rollout-cadence-for-proactive-quality-updates"></a>Vad är den aktuella lanseringen av proaktiva kvalitetsuppdateringar?
Förebyggande kvalitetsuppdateringar levereras för närvarande en gång per månad för varje version av en serviceuppdatering som stöds. Bara en uppdatering per månad flyttas för valda sandbox-miljöer om inte kunderna flyttar till en ny serviceuppdateringsversion. I så fall kan de få en förplanerad PQU som en del av ett befintligt tåg för den nya serviceuppdateringen. När den globala sammanslagningen är slutförd 2023, ökar frekvensen för dessa uppdateringar. Du kommer alltid att få minst en månads uppsägningstid när det sker en ändring i leveranskadensen.

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>Hur kan Microsoft säkerställa kvaliteten på dessa uppdateringar?
Microsoft arbetar med att hålla frisläppningspipeline effektiv nog att leverera små nyttolaster för att hålla valideringskostnaden låg. Varje åtgärd i en kvalitetsuppdatering får en fullständig och säker distributionsprocess som förbättrar kvaliteten och tillförlitligheten och minskar därmed kundens inverkan. Distributionen sker i faser i sandbox-miljöer först, följt av produktion. Mellanlagrade distributioner gör det möjligt att övervaka om ytterligare distribution är säker. Vi stoppar distributionen om problem upptäcks med varje grupp av kunder som distribueras och ser till att varje steg i distributionen har tillräckligt med tid för att problem ska uppstå. Vid varje kommande kvalitetsuppdatering gör vi oss synliga i schemat via uppdateringar av offentlig dokumentation och e-post, så att kunderna kan planera i förväg.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>Kan kunder försena, omplanera eller göra en kvalitetsuppdatering?
Nr. Målet med kvalitetsuppdateringar är att säkerställa grundläggande rättigheter som säkerhet, integritet, tillförlitlighet, tillgänglighet och prestanda kontinuerligt förbättras för våra kunder. Det är en risk att en uppdatering, säkerhet, tillgänglighet och tillförlitlighet försenas eller pausas.

## <a name="how-do-i-know-what-set-of-changes-went-into-a-quality-update-payload"></a>Hur kan jag veta vilken uppsättning som har gått in i en uppdatering av nyttolast av kvalitet?
Följ anvisningarna nedan för att identifiera listan med ändringar som går till en nyttolast för kvalitetsuppdatering. 

Använd 10.0.28 uppdatering för kvalitetsuppdateringsspåret och den relaterade 10.0.1265.89.

1. I Lifecycle Services öppna sidan **Miljöinformation** för din sandbox. 
2. I avsnittet **Tillgängliga uppdateringar**, välj **Visa uppdatering** för senaste kvalitetsuppdatering version. 
3. Exportera versionen till en CSV eller Microsoft Excel-filen.
4. Filtrera i den exporterade filen och välj den **version** som är mindre än eller lika med versionsnummer 10.0.1265.89. Du bör nu kunna se delta över nyttolast
 
> [!NOTE]
> Exporten till en CSV- eller Excel-fil måste ske innan miljön uppdateras. Annars kan du använda en miljö med en liknande konfiguration som inte har uppdateringen installerad och följer stegen ovan.

[![Exempel på miljö med kvalitetsuppdatering.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Vad är processen om ett viktigt problem hittas efter en kvalitetsuppdatering?
Ett kritiskt problem eller en eller flera händelser som vanligtvis gör att flera kunder har en försämrad erfarenhet av en eller flera av våra tjänster. Dessa problem kan orsaka oplanerade driftstider inklusive otillgänglighet, prestanda, effektivitet och påverkan på servicehanteringen. Om det finns en stor kundpåverkan på grund av sådana problem kommer vi att stoppa sammanslagningen av en kvalitetsuppdatering tills vi kan kommunicera och åtgärda problemet. Nästa kvalitetsuppdatering har vanligtvis den rätta tiden så att sammanslagningen kan återupptas.

Om en enskild kundmiljö påverkas kontaktar du Microsofts support för att öppna en lott. Med utgångspunkt i berättigandet stoppar vi kvalitetsuppdateringsutrullningen i alla andra miljöer i det projektet tills problemet har åtgärdats.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lifecycle-services"></a>Kan kunder fortfarande använda snabbkorrigeringsuppdateringar från Lifecycle Services manuellt?
Ja. För att säkerställa löpande paritet med hur snabbkorrigeringar fungerar kan snabbkorrigeringsuppdateringar fortfarande tillämpas på kundmiljöer i Lifecycle Services. Det är dock viktigt att observera att snabbkorrigeringar som distribueras som en del av en kvalitetsuppdatering går igenom standard-SDP innan uppdateringen distribueras. Detta minskar risken för fel på grund av högre kvalitet. Vi rekommenderar att du väljer en kvalitetsuppdatering manuellt med hjälp av snabbkorrigeringar för ökad tillförlitlighet.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>Kan kunder förebyggande installera en kvalitetsuppdateringsversion själva före tidsplanen?
Ja. Du kan installera en kvalitetsuppdatering i förebyggande syfte. Microsoft hoppar över uppdateringen om miljöns aktuella version är lika med eller högre än kvalitetsuppdateringen i fråga.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Om en miljö har en kommande tidsplanerad månatlig serviceuppdatering inom en vecka, kommer den fortfarande att få kvalitetsuppdateringar?
- Kvalitetsuppdateringar tillämpas inte till produktionsmiljöer det finns en nära förestående serviceuppdatering planerad inom en vecka från det att kvalitetsuppdateringen planeras.
- Om en miljö har samma eller högre version än den nära förestående kvalitetsuppdateringen hoppas den över.
- Om en produktionsmiljö har samma eller högre version än den nära förestående kvalitetsuppdateringen hoppas den över.
- Om en sandbox har samma eller högre version på grund av en kvalitetsuppdatering eller en manuell uppdatering av produktionen får produktionen fortfarande den planerade versionen av den månatliga serviceuppdateringen. Om du inte vill att den tidsplanerade produktionsmiljön ska uppdateras till serviceuppdateringsversionen kan du göra en paus i serviceuppdateringen från Lifecycle Services. 
- Vi rekommenderar att du använder den senaste kvalitetsuppdateringsbyggen för att testa dina ändringar för en kommande serviceuppdatering för bättre prestanda och resultat.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Om en miljö har en kommande tidsplanerad åtgärd och en tidsplanerad kvalitetsuppdatering i samma underhållsfönster, kommer den fortfarande att få kvalitetsuppdateringen?
Om det finns någon information med en förplanerad åtgärd, t.ex. en Återställning till tidpunkt (PITR), tidsplaneras kvalitetsuppdateringen om till nästa tillgängliga underhållsfönstret inom fyradagarsfönstret. Mer information om schema finns i [Vad är schemat för förebyggande kvalitetsuppdateringar?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Kan en miljö föras tillbaka till sitt tidigare tillstånd om det finns problem efter att en kvalitetsuppdatering har tillämpats?
När en kvalitetsuppdatering har tillämpats finns ingen återställning under några omständigheter. Det finns bara tillgängliga alternativ för uppdatering framåt för att minska problemen.

## <a name="what-about-fda-regulation-and-gxp"></a>Vad säger du om FDA-regler och GxP?
Planen för kunder som omfattas av FDA-validering och -bestämmelse är fortfarande arbetsföring. Förvänta dig fler uppdateringar på detta område inom kort. För tillfället är alla sådana kunder undantagna från kvalitetsuppdateringar. För att säkerställa att en kund faller under FDA-föreskrifter, besök [Microsoft Azure GxP-erbjudanden](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Vilka versioner av serviceuppdateringar som stöds av dessa kvalitetsuppdateringar?
Kunder på alla versioner av tjänstuppdateringar som stöds kvalificerar sig för kvalitetsuppdateringar. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retail-sdk"></a>I appar för ekonomi och drift som distribueras med butikskomponenter krävs vanligtvis mer arbete förutom att du måste omdistribuera MPOS. Hur påverkar dessa kvalitetsuppdateringar Retail SDK? 
Eftersom själva snabbkorrigeringen inte ändras i nyttolasten för kvalitetsuppdateringar, förväntar vi oss inte någon ytterligare påverkan specifikt relaterad till detaljhandelskomponenter för närvarande.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>Påverkas de molnbaserade miljöerna (CHE)? 
CHE-miljöer har inte utrymme för kvalitetsuppdateringar eftersom de ligger utanför Microsoft Purview.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Finns det några integrationsproblem med Microsoft Dataverse? 
Det finns inga kända integrationsproblem för kvalitetsuppdateringar med Dataverse.

