---
title: Planera analys av optimeringsanpassning
description: I det här avsnittet beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i funktionen för planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 769bd84b4ba23c9de4638df9186381936221414a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437692"
---
# <a name="planning-optimization-fit-analysis"></a>Bristanalys för planeringsoptimering

[!include [banner](../../includes/banner.md)]

Du bör analysera resultatet från bristanalysen för planeringsoptimering som en del av migreringsprocessen. Observera att omfånget för planeringsoptimering inte är lika med den aktuella inbyggda huvudplaneringsfunktionen. Vi rekommenderar att du samarbetar med din partner och läser dokumentationen för att förbereda migreringen. 

Med planeringsoptimeringsanalys kan du identifiera var resultatet kan skilja sig mellan den inbyggda huvudplaneringsmotorn och planeringsoptimeringen. Den här analysen utförs baserat på dina aktuella inställningar och data. 

Om du vill se analysresultaten för planeringsoptimering går du till **Huvudplanering** \> **Inställningar** \> **Bristanalys för planeringsoptimering** och väljer **Kör analys**. Om analysen hittar eventuella inkonsekvenser visas de på samma sida. (Det kan ta några minuter att köra analysen.)

> [!NOTE]
> Om inkonsekvenser hittas kan du fortfarande använda planeringsoptimering. Resultaten av anpassningsanalysen visar bara platser där planeringstjänsten inte ska svara på den aktuella inställningen. Med andra ord visar de platser där vissa processer kan ignoreras eller kanske inte stöds.

## <a name="analysis-results-example-1"></a>Analysresultat: exempel 1

- **Funktion:** produktion
- **Problem:** artiklar med en strukturlistenivå högre än noll: 56
- **Förklaring:** anpassningsanalysen hittade 56 artiklar som har en inställning för strukturlista för produktion. Eftersom den aktuella versionen av planeringsoptimering inte stöder produktionen genererar planeringsoptimering planerade inköpsorder istället för planerade tillverkningsorder. Dessutom visas en varning med en lista över de objekt som påverkas.

## <a name="analysis-results-example-2"></a>Analysresultat: exempel 2

- **Funktion:** åtgärder
- **Problem:** Disponeringsgrupper med aktiverad åtgärdsberäkning: 6
- **Förklaring:** anpassningsanalysen hittade sex disponeringsgrupper där åtgärdsberäkning är aktiverad. Eftersom den aktuella versionen av planeringsoptimering inte stöder åtgärder kommer inga åtgärder att genereras under huvudplaneringen.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Översikt över möjliga resultat från bristanalysen

I följande tabell visas de olika resultat som kan visas efter en bristanalys. Nummertecken (_\#_) ersätts med ett tal som anger antalet poster som innehåller det listade problemet.

| Funktion | Listat problem | Förklaring | Förväntad tillgänglighet |
| --- | --- | --- | --- |
| Åtgärder | Disponeringsgrupper med åtgärdsberäkning aktiverat: _\#_ | Denna funktion väntar. För närvarande genereras inte åtgärder under huvudplaneringen när planeringsoptimering är aktiverad, oavsett den här inställningen. Det huvudsakliga syftet med åtgärder är att föreslå ändringar i befintliga order. Utvärdera om åtgärder aktivt används som en del av dina affärsprocesser eller om förseningsinformationen som är relaterad till ordern är tillräcklig. | 2021 oktober |
| Baskalendrar | Kalendrar som använder baskalendern: _\#_ | Denna funktion väntar. För närvarande ignoreras baskalendern när planeringsoptimering aktiveras. Utvärdera om baskalendern behövs för dina affärs processer eller om det är tillräckligt med direkt inställning i kalendrarna. | 2021 april | 
| Batchdispositionskoder | Ej nettoberäkningsbara batchdispositionshuvuden: _\#_ | Denna funktion väntar. För närvarande ignoreras batchdispositionskod när planeringsoptimering aktiveras. | 2021 oktober |
| CTP (capable to promise) | Standardorderinställningar med leveransdatumkontrollen inställd på CTP: _\#_ | Denna funktion väntar. För närvarande ignoreras CTP när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2021 oktober |
| Kopiera statisk till dynamisk plan | Kopiering av statisk till dynamisk plan har aktiverats i huvudplaneringsparametrarna. | Planeringsoptimering kopierar inte den statiska planen till den dynamiska planen, oavsett den här inställningen. I allmänhet är detta ett mindre relevant begrepp på grund av snabbheten och den fullständiga genereringen av planeringsoptimeringen. Om två eller flera planer används ska huvudplaneringen utlösas för varje plan. | 2021 oktober |
| Bekräftelse | Disponeringsgrupper med automatiskt bekräftad tidsgräns angiven: _\#_ | I version 10.0.7 och senare stöds bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för planeringsoptimering_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att produktionstiden behöver inkluderas i den bekräftade tidsgränsen. | Stöds |
| Bekräftelse | Poster för artikeldisponering med automatisk bekräftelse angivet: _\#_ | I version 10.0.7 och senare stöds automatiska bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för planeringsoptimering_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att produktionstiden behöver inkluderas i den bekräftade tidsgränsen. | Stöds |
| Bekräftelse | Huvudplaner med automatisk bekräftelse angivet: _\#_ | I version 10.0.7 och senare stöds automatiska bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för planeringsoptimering_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att produktionstiden behöver inkluderas i den bekräftade tidsgränsen. | Stöds |
| FitAnalysisPlanningItems | Planeringsartiklar: _\#_ | Denna funktion väntar. För närvarande hanteras planeringsartiklar som vanliga artiklar när planeringsoptimering aktiveras. | 2021 oktober |
| Prognos | Disponeringsgrupper med aktiverat "Inkludera koncerninterna order": _\#_ | Denna funktion väntar. För närvarande inkluderar inte underordnad planerad efterfrågan när planeringsoptimering är aktiverad, oavsett den här inställningen. Observera att släppta/bekräftade order fortfarande fungerar med de vanliga koncerninterna funktionerna och kommer att täcka de flesta scenarierna. | 2020 oktober |
| Prognos | Disponeringsgrupper med inställningen "minska prognos med" angiven till ett värde som skiljer sig från "Order": _\#_ | Som standard använder planeringsoptimeringen "reducera prognos efter" för order, oavsett den här inställningen. | November 2020 |
| Prognos | Prognosmodeller med undermodeller: _\#_ | Denna funktion väntar. För närvarande stöds inte prognoser som använder undermodeller när planeringsoptimering är aktiverat. De kommer att ignoreras oavsett den här inställningen. | 2021 april |
| Prognos | Huvudplaner med "inkludera leveransprognos" aktiverat: _\#_ | Denna funktion väntar. För närvarande stöds inte prognoser om tillgång när planeringsoptimering är aktiverat. De kommer att ignoreras oavsett den här inställningen. | 2021 oktober |
| Frystidsgräns | Disponeringsgrupper med frystidsgräns angiven: _\#_ | Frystidsgränsen används inte ofta och det finns för närvarande inga planer på att inkludera den för planeringsoptimering. För närvarande ignoreras inställning av frystidsgräns när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | Inte tillämpligt |
| Frystidsgräns | Poster för artikeldisponering med frystidsgräns angiven: _\#_ | Frystidsgränsen används inte ofta och det finns för närvarande inga planer på att inkludera den för planeringsoptimering. För närvarande ignoreras inställning av frystidsgräns när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | Inte tillämpligt |
| Frystidsgräns | Huvudplaner med frystidsgräns angiven: _\#_ | Frystidsgränsen används inte ofta och det finns för närvarande inga planer på att inkludera den för planeringsoptimering. För närvarande ignoreras inställning av frystidsgräns när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | Inte tillämpligt |
| Koncerninternt | Huvudplaner inklusive underordnad planerad efterfrågan: _\#_ | Denna funktion väntar. För närvarande inkluderar inte underordnad planerad efterfrågan när planeringsoptimering är aktiverad, oavsett den här inställningen. Observera att släppta/bekräftade order fortfarande fungerar med de normala koncerninterna funktionerna och kommer att täcka de flesta scenarierna. | 2020 oktober |
| Kanban | Poster för artikeldisponering med planerad ordertyp för kanban: _\#_ | Denna funktion väntar. För närvarande kommer artikeldisponering som anges till kanban att ignoreras när planeringsoptimering aktiveras. Den planerade order typen för kanban kommer att skapa en varning under huvudplaneringen och planerade inköpsorder skapas för att täcka det relaterade behovet. | 2021 oktober |
| Kanban | Artiklar med standardordertyp för kanban: _\#_ | För närvarande kommer en standardordertyp som anges till kanban att ignoreras när planeringsoptimering aktiveras. Den planerade standardordertypen för kanban kommer att skapa en varning under huvudplaneringen och planerade inköpsorder skapas för att täcka det relaterade behovet. | 2021 oktober |
| Produktens livscykeltillstånd   | Produktens livscykeltillstånd är inte aktivt för planering: _\#_ | Detta är en kommande funktion. För närvarande ignoreras produktens livscykeltillstånd med planeringsoptimering aktiverat. Du kan justera produktfiltret för plannivå för att undvika produkter där produktens livscykeltillstånd är inaktiverat för planering. | November 2020 |
| Produktion | Strukturlisterader med avrundning eller flera inställningar: _\#_ | Denna funktion väntar. För närvarande ignoreras avrundning och flera inställningar på strukturlisterader när planeringsoptimering är aktiverad, oavsett den här inställningen. | 2021 april |
| Produktion | Strukturliste-/formelrader med formelmätning: _\#_ | Denna funktion väntar. För närvarande ignoreras formelmätning på strukturliste- och formelrader när planeringsoptimering är aktiverad, oavsett den här inställningen. | 2021 oktober |
| Produktion | Strukturliste-/formelrader med artikelersättning (plangrupper): _\#_ | Denna funktion väntar. För närvarande ignoreras artikelersättning (plangrupper) på strukturliste- och formelrader när planeringsoptimering är aktiverad, oavsett den här inställningen. | 2021 oktober |
| Produktion | Strukturliste-/formelrader med negativ kvantitet: _\#_ | Denna funktion väntar. Strukturliste- och formelrader som har negativ kvantitet kommer att inkluderas med kvantiteten 0 (noll) och en varning utfärdas när planeringsoptimering aktiveras. Uppdatera huvuddata för att undvika varningar. | 2021 oktober |
| Produktion | Strukturliste-/formelrader med resursförbrukning: _\#_ | Denna funktion väntar. För närvarande kommer strukturliste- och formelrader som har resursförbrukning att ignoreras när planeringsoptimering aktiveras. När den här funktionen stöds kommer material kravet att ställas in på startdatum för produktion. För att den här funktionen ska kunna användas genereras inte krav för material som har markerats med en resurs förbrukningsflagga. | 2021 april |
| Produktion | Strukturliste-/formelrader med stegförbrukning: _\#_ | Denna funktion väntar. För närvarande kommer stegförbrukning på strukturliste- och formelrader att ignoreras när planeringsoptimering aktiveras. | 2021 oktober |
| Produktion | Strukturlistor med definierad konstant eller variabel kassation: _\#_ | Denna funktion väntar. För närvarande ignoreras konstant kassation och variabel kassation som definieras på strukturlistor när planeringsoptimering aktiveras. | 2021 oktober |
| Produktion | Strukturlistor med legotillverkning: _\#_ | Denna funktion väntar. För närvarande ignoreras inställning av legotillverkning på strukturlistor när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2021 oktober |
| Produktion | Strukturlistor utan plats: _\#_ | Denna funktion väntar. För närvarande ignoreras strukturlistor utan plats när planeringsoptimering aktiveras. | 2020 oktober |
| Produktion | Efterfrågan med specifika definierade strukturliste- eller flödeskrav: _\#_ | Denna funktion väntar. För närvarande ignoreras de specifika strukturliste- eller flödeskraven som har definierats på efterfrågan (t.ex. en understrukturlista eller underflöde på en försäljningsorder) när planeringsoptimering är aktiverad. Standardstrukturlistan eller flödet används oavsett den här inställningen. | 2021 oktober |
| Produktion | Formelversioner med sam-/biprodukter: _\#_ | Denna funktion väntar. För närvarande kommer samprodukter och biprodukter som är associerade med formelversionen att ignoreras när planeringsoptimering är aktiverad. | 2021 oktober |
| Produktion | Formelversioner med avkastning: _\#_ | Denna funktion väntar. För närvarande ignoreras avkastning som är associerad med formelversionen när planeringsoptimering är aktiverad. | 2021 oktober |
| Produktion | Planer med ordningsföljd: _\#_ | Denna funktion väntar. För närvarande ignoreras ordningsföljd när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2021 oktober |
| Produktion | Släppta eller startade produktionsorder som inte är startade, där planerad start är tidigare än: _\#_ | Denna funktion väntar. För närvarande, om en tillverkningsorder är försenad, kommer huvudplaneringen att förutsätta att den slutförs i dag. Detta är relevant för släppta produktionsorder där ett leveransdatum har passerats men ännu inte slutförts. | 2021 oktober |
| Produktion | Planerade resurser med begränsad kapacitet: _\#_ | Denna funktion väntar. För närvarande kommer resurser som har planerats med begränsad kapacitet att ignoreras när planeringsoptimering är aktiverad. Tidsplaneringen görs baserat på standardproduktionstiden från produkten. | 2021 april |
| Produktion | Flöden använda i planering: _\#_ | Denna funktion väntar. För närvarande ignoreras flöden när planeringsoptimering aktiveras. Standardproduktionstiden för produkten används. | 2021 april |
| Produktion | Reservation av försäljningsrad med nedbrytning: _\#_ | Reservation av försäljningsrad med nedbrytning stöds inte när planeringsoptimering aktiveras. | 2021 oktober |
| Produktion | Planering med nedbrytning av produktionsorder: _\#_ | Tidsplanering som använder nedbrytning av produktionsorder stöds inte när planeringsoptimering aktiveras. Tillverkningsorder kan tidsplaneras individuellt. | 2021 oktober |
| Anbudsförfrågningar | Huvudplaner med anbudsförfrågningar aktiverat: _\#_ | Denna funktion väntar. För närvarande anses inte anbudsförfrågningar vara efterfrågan när planeringsoptimering är aktiverad. De kommer att ignoreras oavsett den här inställningen. | 2021 oktober |
| Rekvisitioner | Huvudplaner med rekvisitioner aktiverat: _\#_ | Denna funktion väntar. För närvarande betraktas inte rekvisitioner när planeringsoptimering aktiveras. De kommer att ignoreras oavsett den här inställningen. | 2021 oktober |
| Säkerhetsmarginaler | Disponeringsgrupper med säkerhetsmarginal: _\#_ | Denna funktion väntar. För närvarande ignoreras säkerhetsmarginal när planeringsoptimering aktiveras. Du kan kompensera för det här problemet genom att öka produktionstiden så att den inkluderar säkerhetsmarginalen. | 2020 oktober |
| Säkerhetsmarginaler | Huvudplaner med säkerhetsmarginal: _\#_ | Denna funktion väntar. För närvarande ignoreras säkerhetsmarginal när planeringsoptimeringen är aktiverad, oavsett den här inställningen. Du kan kompensera för det här problemet genom att öka produktionstiden så att den inkluderar säkerhetsmarginalen. | 2020 oktober |
| Uppfyllelse av säkerhetslager | Poster för artikeldisponering med "uppfyllda minimum" som skiljer sig från "dagens datum + anskaffningstid": _\#_ | Planeringsoptimering använder alltid *dagens datum + anskaffningstid*. Den här ändringen görs för att förbereda för en förenklad planeringsinställning i framtiden och för att ge ett åtgärdbart resultat. Om anskaffningstiden inte finns med i säkerhetslagret försenas planerade order som skapas för aktuell lagerbehållning alltid på grund av produktionstiden. Det här beteendet kan orsaka betydande brus och oönskade planerade order. Det bästa tillvägagångssättet är att ändra inställningen så att *dagens datum + anskaffningstid* används. Uppdatera huvuddata för att undvika varningar. | Inte tillämpligt |
| Försäljningsofferter | Huvudplaner med försäljningsofferter aktiverade: _\#_ | Denna funktion väntar. För närvarande betraktas inte offerter när planeringsoptimering aktiveras. De kommer att ignoreras oavsett den här inställningen. | 2021 oktober |
| Hållbarhetstid | Huvudplaner med hållbarhetstid aktiverat: _\#_ | Denna funktion väntar. För närvarande beaktas inte hållbarhetstid när planeringsoptimeringen är aktiverad, oavsett den här inställningen. | 2021 oktober |

## <a name="additional-resources"></a>Ytterligare resurser

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Kom igång med planeringsoptimering](get-started.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)
