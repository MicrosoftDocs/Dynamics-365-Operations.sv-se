---
title: Bristanalys för Planeringsoptimering
description: I denna artikel beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i Planeringsoptimering.
author: t-benebo
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: e3e20b0dc782ed56e256f8fa9540f4a7a3f32ef0
ms.sourcegitcommit: 84e9946509c34a67d88c9dd9cc934d7d245ddb27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2022
ms.locfileid: "9093846"
---
# <a name="planning-optimization-fit-analysis"></a>Bristanalys för Planeringsoptimering

[!include [banner](../../includes/banner.md)]

Du bör analysera resultatet från bristanalysen för Planeringsoptimering som en del av migreringsprocessen. Observera att omfånget för Planeringsoptimering inte är lika med den aktuella inbyggda huvudplaneringsfunktionen. Vi rekommenderar att du samarbetar med din partner och läser dokumentationen för att förbereda migreringen. 

Med Planeringsoptimerinsanalys kan du identifiera var resultatet kan skilja sig mellan den inbyggda huvudplaneringsmotorn och Planeringsoptimeringen. Den här analysen utförs baserat på dina aktuella inställningar och data. 

Om du vill se analysresultaten för Planeringsoptimering går du till **Huvudplanering** \> **Inställningar** \> **Bristanalys för Planeringsoptimering** och väljer **Kör analys**. Om analysen hittar eventuella inkonsekvenser visas de på samma sida. (Det kan ta några minuter att köra analysen.)

> [!NOTE]
> Om inkonsekvenser hittas kan du fortfarande använda Planeringsoptimering. Resultaten av anpassningsanalysen visar bara platser där planeringstjänsten inte ska svara på den aktuella inställningen. Med andra ord visar de platser där vissa processer kan ignoreras eller kanske inte stöds.

## <a name="analysis-results-example-1"></a>Analysresultat: exempel 1

- **Funktion:** produktion
- **Problem:** artiklar med en strukturlistenivå högre än noll: 56
- **Förklaring:** anpassningsanalysen hittade 56 artiklar som har en inställning för strukturlista för produktion. Eftersom den aktuella versionen av Planeringsoptimering inte stöder produktionen genererar Planeringsoptimering planerade inköpsorder istället för planerade produktionsorder. Dessutom visas en varning med en lista över de objekt som påverkas.

## <a name="analysis-results-example-2"></a>Analysresultat: exempel 2

- **Funktion:** åtgärder
- **Problem:** Disponeringsgrupper med aktiverad åtgärdsberäkning: 6
- **Förklaring:** anpassningsanalysen hittade sex disponeringsgrupper där åtgärdsberäkning är aktiverad. Eftersom den aktuella versionen av Planeringsoptimering inte stöder åtgärder kommer inga åtgärder att genereras under huvudplaneringen.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Översikt över möjliga resultat från bristanalysen

I följande tabell visas de olika resultat som kan visas efter en bristanalys. Nummertecken (_\#_) ersätts med ett tal som anger antalet poster som innehåller det listade problemet. Funktionerna som stöds eller förhandsgranskas är tillgängliga med version 10.0.9 eller senare (såvida inte ett högre versionsnummer visas i kolumnen "Förväntad tillgänglighet").

> [!NOTE]
> Vissa inkonsekvenser kan inte identifieras i analysen Planeringsoptimering. Mer information finns i [Skillnader mellan klassisk huvudplanering och Planeringsoptimering](planning-optimization-differences-with-built-in.md).

| Funktion | Listat problem | Förklaring | Förväntad tillgänglighet |
| --- | --- | --- | --- |
| Åtgärder | Disponeringsgrupper med åtgärdsberäkning aktiverat: _\#_ | Denna funktion stöds nu. | Stöds |
| Baskalendrar | Kalendrar som använder baskalendern: _\#_ | Denna funktion stöds nu. | Stöds | 
| Batchdispositionskoder | Ej nettoberäkningsbara batchdispositionshuvuden: _\#_ | Denna funktion väntar. För närvarande ignoreras batchdispositionskod när Planeringsoptimering aktiveras. | 2022 oktober |
| CTP (capable to promise) | Standardorderinställningar med leveransdatumkontrollen inställd på CTP: _\#_ | I Supply Chain Management 10.0.28 och nyare gör en process kallad *CTP för planeringsoptimering* bekräftade transport- och inleveransdatum tillgängliga när den dynamiska planen har körts. För äldre versioner av Supply Chain Management ignoreras den äldre CTP-inställningen när Planeringsoptimering aktiveras. | Stöds |
| Kopiera statisk till dynamisk plan | Kopiering av statisk till dynamisk plan har aktiverats i huvudplaneringsparametrarna. | Planeringsoptimering kopierar inte den statiska planen till den dynamiska planen, oavsett den här inställningen. I allmänhet är detta ett mindre relevant begrepp på grund av snabbheten och den fullständiga genereringen av Planeringsoptimeringen. Om två eller flera planer används ska huvudplaneringen utlösas för varje plan. | Inte tillämpligt |
| Bekräftelse | Disponeringsgrupper med automatisk bekräftelse av tidsgräns angiven: _\#_ | I version 10.0.7 och senare stöds bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för Planeringsoptimerin_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för Planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att ledtiden behöver inkluderas i den bekräftade tidsgränsen. | Stöds |
| Bekräftelse | Poster för artikeldisponering med automatisk bekräftelse angivet: _\#_ | I version 10.0.7 och senare stöds automatiska bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för Planeringsoptimerin_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för Planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att ledtiden behöver inkluderas i den bekräftade tidsgränsen. | Stöds |
| Bekräftelse | Huvudplaner med automatisk bekräftelse angivet: _\#_ | I version 10.0.7 och senare stöds automatiska bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för Planeringsoptimerin_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för Planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att ledtiden behöver inkluderas i den bekräftade tidsgränsen. | Stöds |
| FitAnalysisPlanningItems | Planeringsartiklar: _\#_ | Denna funktion väntar. För närvarande hanteras planeringsartiklar som vanliga artiklar när Planeringsoptimering aktiveras. | Oktober 2022 eller senare |
| Prognos | Disponeringsgrupper med aktiverat "Inkludera koncerninterna order": _\#_ | Denna funktion stöds nu. Mer information finns i [Koncernintern planering](Intercompany-planning.md) | Stöds |
| Prognos | Disponeringsgrupper med inställningen "minska prognos med" angiven till ett värde som skiljer sig från "Order": _\#_ | Denna funktion stöds nu. För mer information, se [Huvudplanering med efterfrågeprognoser](demand-forecast.md). | Stöds |
| Prognos | Prognosmodeller med undermodeller: _\#_ |  Denna funktion stöds nu. För mer information, se [Huvudplanering med efterfrågeprognoser](demand-forecast.md). | Stöds |
| Prognos | Huvudplaner med "inkludera leveransprognos" aktiverat: _\#_ | Denna funktion väntar. För närvarande stöds inte prognoser om tillgång när Planeringsoptimering är aktiverat. De kommer att ignoreras oavsett den här inställningen. | Oktober 2022 eller senare |
| Frystidsgräns | Disponeringsgrupper med frystidsgräns angiven: _\#_ | Denna funktion väntar. För närvarande ignoreras inställning av frystidsgräns när Planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2022 oktober |
| Frystidsgräns | Poster för artikeldisponering med frystidsgräns angiven: _\#_ | Denna funktion väntar. För närvarande ignoreras inställning av frystidsgräns när Planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2022 oktober |
| Frystidsgräns | Huvudplaner med frystidsgräns angiven: _\#_ | Denna funktion väntar. För närvarande ignoreras inställning av frystidsgräns när Planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2022 oktober |
| Koncerninternt | Huvudplaner inklusive underordnad planerad efterfrågan: _\#_ | Denna funktion stöds nu. Mer information finns i [Koncernintern planering](Intercompany-planning.md) | Stöds |
| Kanban | Poster för artikeldisponering med planerad ordertyp för kanban: _\#_ | Denna funktion väntar. För närvarande kommer artikeldisponering som anges till kanban att ignoreras när Planeringsoptimering aktiveras. Den planerade order typen för kanban kommer att skapa en varning under huvudplaneringen och planerade inköpsorder skapas för att täcka det relaterade behovet. | 2023 eller senare |
| Kanban | Artiklar med standardordertyp för kanban: _\#_ | För närvarande kommer en standardordertyp som anges till kanban att ignoreras när Planeringsoptimering aktiveras. Den planerade standardordertypen för kanban kommer att skapa en varning under huvudplaneringen och planerade inköpsorder skapas för att täcka det relaterade behovet. | 2023 eller senare |
| Produktens livscykeltillstånd | Produktens livscykeltillstånd är inte aktivt för planering: _\#_ | Denna funktion stöds nu. Mer information finns i [Exkludera produkter som har specifika produktens livscykeltillstånd](product-lifecycle-state.md) | Stöds |
| Produktion | Strukturlisterader med avrundning eller flera inställningar: _\#_ | Denna funktion väntar. För närvarande ignoreras avrundning och flera inställningar på strukturlisterader när Planeringsoptimering är aktiverad, oavsett den här inställningen. | 2021 oktober |
| Produktion | Strukturliste-/formelrader med formelmätning: _\#_ | Denna funktion väntar. För närvarande ignoreras formelmätning på strukturliste- och formelrader när Planeringsoptimering är aktiverad, oavsett den här inställningen. | 2022 oktober |
| Produktion | Strukturliste-/formelrader med artikelersättning (plangrupper): _\#_ | Denna funktion väntar. För närvarande ignoreras artikelersättning (plangrupper) på strukturliste- och formelrader när Planeringsoptimering är aktiverad, oavsett den här inställningen. | 2022 december |
| Produktion | Strukturliste-/formelrader med negativ kvantitet: _\#_ | Denna funktion väntar. Strukturliste- och formelrader som har negativ kvantitet kommer att inkluderas med kvantiteten 0 (noll) och en varning utfärdas när Planeringsoptimering aktiveras. Uppdatera huvuddata för att undvika varningar. | 2022 december |
| Produktion | Strukturliste-/formelrader med resursförbrukning: _\#_ | Denna funktion väntar. För närvarande kommer strukturliste- och formelrader som har resursförbrukning att ignoreras när Planeringsoptimering aktiveras. När den här funktionen stöds kommer material kravet att ställas in på startdatum för produktion. För att den här funktionen ska kunna användas genereras inte krav för material som har markerats med en resurs förbrukningsflagga. | 2022 december |
| Produktion | Strukturliste-/formelrader med stegförbrukning: _\#_ | Denna funktion väntar. För närvarande kommer stegförbrukning på strukturliste- och formelrader att ignoreras när Planeringsoptimering aktiveras. | 2022 december |
| Produktion | Strukturlistor med definierad konstant eller variabel kassation: _\#_ | Denna funktion väntar. För närvarande ignoreras konstant kassation och variabel kassation som definieras på strukturlistor när Planeringsoptimering aktiveras. | 2022 oktober |
| Produktion | Strukturlistor med legotillverkning: _\#_ | Denna funktion stöds nu. | Stöds |
| Produktion | Strukturlistor utan plats: _\#_ | Denna funktion stöds nu. Mer information finns i [Produktionsplanering](production-planning.md) | Stöds |
| Produktion | Efterfrågan med specifika definierade strukturliste- eller flödeskrav: _\#_ | Denna funktion väntar. För närvarande ignoreras de specifika strukturliste- eller flödeskraven som har definierats på efterfrågan (t.ex. en understrukturlista eller underflöde på en försäljningsorder) när Planeringsoptimering är aktiverad. Standardstrukturlistan eller flödet används oavsett den här inställningen. | 2022 december |
| Produktion | Formelversioner med sam-/biprodukter: _\#_ | Denna funktion väntar. För närvarande kommer samprodukter och biprodukter som är associerade med formelversionen att ignoreras när Planeringsoptimering är aktiverad. | 2022 december |
| Produktion | Formelversioner med avkastning: _\#_ | Denna funktion väntar. För närvarande ignoreras avkastning som är associerad med formelversionen när Planeringsoptimering är aktiverad. | 2022 december |
| Produktion | Planer med ordningsföljd: _\#_ | Denna funktion väntar. För närvarande ignoreras ordningsföljd när Planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2022 december |
| Produktion | Släppta eller startade produktionsorder som inte är startade, där planerad start är tidigare än: _\#_ | Denna funktion väntar. För närvarande, om en produktionsorder är försenad, kommer huvudplaneringen att förutsätta att den slutförs i dag. Detta är relevant för släppta produktionsorder där ett leveransdatum har passerats men ännu inte slutförts. | 2023 eller senare |
| Produktion | Planerade resurser med begränsad kapacitet: _\#_ | Denna funktion väntar. För närvarande kommer resurser som har planerats med begränsad kapacitet att ignoreras när Planeringsoptimering är aktiverad. Tidsplaneringen görs baserat på standardledtiden från produkten. | 2022 oktober |
| Produktion | Flöden använda i planering: _\#_ | Denna funktion stöds. | Stöds |
| Produktion | Reservation av försäljningsrad med nedbrytning: _\#_ | Reservation av försäljningsrad med nedbrytning stöds inte när Planeringsoptimering aktiveras. | 2023 eller senare |
| Produktion | Planering med nedbrytning av produktionsorder: _\#_ | Tidsplanering som använder nedbrytning av produktionsorder stöds inte när Planeringsoptimering aktiveras. Produktionsorder kan tidsplaneras individuellt. | 2023 eller senare |
| Anbudsförfrågningar | Huvudplaner med anbudsförfrågningar aktiverat: _\#_ | Denna funktion väntar. För närvarande anses inte anbudsförfrågningar vara efterfrågan när Planeringsoptimering är aktiverad. De kommer att ignoreras oavsett den här inställningen. | 2022 december |
| Rekvisitioner | Huvudplaner med rekvisitioner aktiverat: _\#_ | Denna funktion stöds nu. Mer information finns i [inköpsrekvisition](purchase-requisitions.md) | Stöds |
| Säkerhetsmarginaler | Disponeringsgrupper med säkerhetsmarginal: _\#_ | Denna funktion stöds nu. Mer information finns i [Säkerhetsmarginaler](safety-margins.md) | Stöds |
| Säkerhetsmarginaler | Huvudplaner med säkerhetsmarginal: _\#_ | Denna funktion stöds nu. Mer information finns i [Säkerhetsmarginaler](safety-margins.md) |  Stöds |
| Uppfyllelse av säkerhetslager | Poster för artikeldisponering med "uppfyllda minimum" som skiljer sig från "dagens datum + anskaffningstid": _\#_ | Planeringsoptimering använder alltid *dagens datum + anskaffningstid*. Den här ändringen görs för att förbereda för en förenklad planeringsinställning i framtiden och för att ge ett åtgärdbart resultat. Om anskaffningstiden inte finns med i säkerhetslagret försenas planerade order som skapas för aktuell lagerbehållning alltid på grund av ledtiden. Det här beteendet kan orsaka betydande brus och oönskade planerade order. Det bästa tillvägagångssättet är att ändra inställningen så att *dagens datum + anskaffningstid* används. Uppdatera huvuddata för att undvika varningar. | Inte tillämpligt |
| Försäljningsofferter | Huvudplaner med försäljningsofferter aktiverade: _\#_ | Denna funktion väntar. För närvarande betraktas inte offerter när Planeringsoptimering aktiveras. De kommer att ignoreras oavsett den här inställningen. | Oktober 2022 eller senare |
| Hållbarhetstid | Huvudplaner med hållbarhetstid aktiverat: _\#_ | Denna funktion väntar. För närvarande beaktas inte hållbarhetstid när Planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2022 juni |

## <a name="additional-resources"></a>Ytterligare resurser

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Kom igång med Planeringsoptimering](get-started.md)

[Skillnader mellan klassisk huvudplanering och Planeringsoptimering](planning-optimization-differences-with-built-in.md)

[Parametrar som inte används i Planeringsoptimering](not-used-parameters.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
