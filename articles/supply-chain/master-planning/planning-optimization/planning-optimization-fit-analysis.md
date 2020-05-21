---
title: Planera analys av optimeringsanpassning
description: I det här avsnittet beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i funktionen för planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
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
ms.openlocfilehash: 9bf19604d246988e05b91c8a41b1f57b523d2192
ms.sourcegitcommit: 73ae66c9464bcc9ddc1efbf4e76abb2758862fe6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346663"
---
# <a name="planning-optimization-fit-analysis"></a>Planera analys av optimeringsanpassning

[!include [banner](../../includes/banner.md)]

Om du vill se hur kompatibla aktuella inställningar och data är med funktionen för planeringsoptimering går du till **Huvudplanering** \> **Inställningar** \> **Planera analys av optimeringsanpassning** och väljer sedan **Kör analys**. Om analysen hittar eventuella inkonsekvenser visas de på samma sida. (Det kan ta några minuter att köra analysen.)

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

| Funktion | Listat problem | Förklaring |
| --- | --- | --- |
| Åtgärder | Disponeringsgrupper med åtgärdsberäkning aktiverat: _\#_ | Denna funktion väntar. För närvarande genereras inte åtgärder under huvudplaneringen när planeringsoptimering är aktiverad, oavsett den här inställningen. Det huvudsakliga syftet med åtgärder är att föreslå ändringar i befintliga order. |
| Baskalendrar | Kalendrar som använder baskalendern: _\#_ | Denna funktion väntar. För närvarande ignoreras baskalendern när planeringsoptimering aktiveras. |
| Batchdispositionskoder | Ej nettoberäkningsbara batchdispositionshuvuden: _\#_ | Denna funktion väntar. För närvarande ignoreras batchdispositionskod när planeringsoptimering aktiveras. |
| CTP (capable to promise) | Standardorderinställningar med leveransdatumkontrollen inställd på CTP: _\#_ | Denna funktion väntar. För närvarande ignoreras CTP när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |
| Kopiera statisk till dynamisk plan | Kopiering av statisk till dynamisk plan har aktiverats i huvudplaneringsparametrarna. | Planeringsoptimering kopierar inte den statiska planen till den dynamiska planen, oavsett den här inställningen. I allmänhet är detta ett mindre relevant begrepp på grund av snabbheten och den fullständiga genereringen av planeringsoptimeringen. Om två eller flera planer används ska huvudplaneringen utlösas för varje plan. |
| Bekräftelse | Disponeringsgrupper med automatiskt bekräftad tidsgräns angiven: _\#_ | I version 10.0.7 och senare stöds bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för planeringsoptimering_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att produktionstiden behöver inkluderas i den bekräftade tidsgränsen. |
| Bekräftelse | Poster för artikeldisponering med automatisk bekräftelse angivet: _\#_ | I version 10.0.7 och senare stöds automatiska bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för planeringsoptimering_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att produktionstiden behöver inkluderas i den bekräftade tidsgränsen. |
| Bekräftelse | Huvudplaner med automatisk bekräftelse angivet: _\#_ | I version 10.0.7 och senare stöds automatiska bekräftelser som ett separat bekräftat batchjobb när huvudplaneringen är slutförd (förutsatt att funktionen _Automatisk bekräftelse för planeringsoptimering_ har aktiverats i [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Observera att automatisk bekräftelse för planeringsoptimering baseras på orderdatum (startdatum), inte behovsdatum (slutdatum). Det här beteendet säkerställer att bekräftelse av planerade order sker i tid, utan att produktionstiden behöver inkluderas i den bekräftade tidsgränsen. |
| FitAnalysisPlanningItems | Planeringsartiklar: _\#_ | Denna funktion väntar. För närvarande hanteras planeringsartiklar som vanliga artiklar när planeringsoptimering aktiveras. |
| Prognos | Disponeringsgrupper med aktiverat "Inkludera koncerninterna order": _\#_ | Denna funktion väntar. För närvarande inkluderar inte underordnad planerad efterfrågan när planeringsoptimering är aktiverad, oavsett den här inställningen. Observera att släppta/bekräftade order fortfarande fungerar med de vanliga koncerninterna funktionerna och kommer att täcka de flesta scenarierna. |
| Prognos | Disponeringsgrupper med inställningen "minska prognos med" angiven till ett värde som skiljer sig från "Order": _\#_ | Som standard använder planeringsoptimeringen "reducera prognos efter" för order, oavsett den här inställningen. |
| Prognos | Prognosmodeller med undermodeller: _\#_ | Denna funktion väntar. För närvarande stöds inte prognoser som använder undermodeller när planeringsoptimering är aktiverat. De kommer att ignoreras oavsett den här inställningen. |
| Prognos | Huvudplaner med "inkludera leveransprognos" aktiverat: _\#_ | Denna funktion väntar. För närvarande stöds inte prognoser om tillgång när planeringsoptimering är aktiverat. De kommer att ignoreras oavsett den här inställningen. |
| Frystidsgräns | Disponeringsgrupper med frystidsgräns angiven: _\#_ | Frystidsgränsen används inte ofta och det finns för närvarande inga planer på att inkludera den för planeringsoptimering. För närvarande ignoreras inställning av frystidsgräns när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |
| Frystidsgräns | Poster för artikeldisponering med frystidsgräns angiven: _\#_ | Frystidsgränsen används inte ofta och det finns för närvarande inga planer på att inkludera den för planeringsoptimering. För närvarande ignoreras inställning av frystidsgräns när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |
| Frystidsgräns | Huvudplaner med frystidsgräns angiven: _\#_ | Frystidsgränsen används inte ofta och det finns för närvarande inga planer på att inkludera den för planeringsoptimering. För närvarande ignoreras inställning av frystidsgräns när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |
| Koncerninternt | Huvudplaner inklusive underordnad planerad efterfrågan: _\#_ | Denna funktion väntar. För närvarande inkluderar inte underordnad planerad efterfrågan när planeringsoptimering är aktiverad, oavsett den här inställningen. Observera att släppta/bekräftade order fortfarande fungerar med de normala koncerninterna funktionerna och kommer att täcka de flesta scenarierna. |
| Kanban | Poster för artikeldisponering med planerad ordertyp för kanban: _\#_ | Denna funktion väntar. För närvarande kommer artikeldisponering som anges till kanban att ignoreras när planeringsoptimering aktiveras. Den planerade order typen för kanban kommer att skapa en varning under huvudplaneringen och planerade inköpsorder skapas för att täcka det relaterade behovet. |
| Kanban | Artiklar med standardordertyp för kanban: _\#_ | För närvarande kommer en standardordertyp som anges till kanban att ignoreras när planeringsoptimering aktiveras. Den planerade standardordertypen för kanban kommer att skapa en varning under huvudplaneringen och planerade inköpsorder skapas för att täcka det relaterade behovet. |
| Produktens livscykeltillstånd   | Produktens livscykeltillstånd är inte aktivt för planering: _\#_ | Detta är en kommande funktion. För närvarande ignoreras produktens livscykeltillstånd med planeringsoptimering aktiverat. Du kan justera produktfiltret för plannivå för att undvika produkter där produktens livscykeltillstånd är inaktiverat för planering. |
| Produktion | Strukturlisterader med avrundning eller flera inställningar: _\#_ | Denna funktion väntar. För närvarande ignoreras avrundning och flera inställningar på strukturlisterader när planeringsoptimering är aktiverad, oavsett den här inställningen. |
| Produktion | Strukturliste-/formelrader med formelmätning: _\#_ | Denna funktion väntar. För närvarande ignoreras formelmätning på strukturliste- och formelrader när planeringsoptimering är aktiverad, oavsett den här inställningen. |
| Produktion | Strukturliste-/formelrader med artikelersättning (plangrupper): _\#_ | Denna funktion väntar. För närvarande ignoreras artikelersättning (plangrupper) på strukturliste- och formelrader när planeringsoptimering är aktiverad, oavsett den här inställningen. |
| Produktion | Strukturliste-/formelrader med negativ kvantitet: _\#_ | Denna funktion väntar. Strukturliste- och formelrader som har negativ kvantitet kommer att inkluderas med kvantiteten 0 (noll) och en varning utfärdas när planeringsoptimering aktiveras. |
| Produktion | Strukturliste-/formelrader med resursförbrukning: _\#_ | Denna funktion väntar. För närvarande kommer strukturliste- och formelrader som har resursförbrukning att ignoreras när planeringsoptimering aktiveras. |
| Produktion | Strukturliste-/formelrader med stegförbrukning: _\#_ | Denna funktion väntar. För närvarande kommer stegförbrukning på strukturliste- och formelrader att ignoreras när planeringsoptimering aktiveras. |
| Produktion | Strukturlistor med definierad konstant eller variabel kassation: _\#_ | Denna funktion väntar. För närvarande ignoreras konstant kassation och variabel kassation som definieras på strukturlistor när planeringsoptimering aktiveras. |
| Produktion | Strukturlistor med legotillverkning: _\#_ | Denna funktion väntar. För närvarande ignoreras inställning av legotillverkning på strukturlistor när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |
| Produktion | Strukturlistor utan plats: _\#_ | Denna funktion väntar. För närvarande ignoreras strukturlistor utan plats när planeringsoptimering aktiveras. |
| Produktion | Efterfrågan med specifika definierade strukturliste- eller flödeskrav: _\#_ | Denna funktion väntar. För närvarande ignoreras de specifika strukturliste- eller flödeskraven som har definierats på efterfrågan (t.ex. en understrukturlista eller underflöde på en försäljningsorder) när planeringsoptimering är aktiverad. Standardstrukturlistan eller flödet används oavsett den här inställningen. |
| Produktion | Formelversioner med sam-/biprodukter: _\#_ | Denna funktion väntar. För närvarande kommer samprodukter och biprodukter som är associerade med formelversionen att ignoreras när planeringsoptimering är aktiverad. |
| Produktion | Formelversioner med avkastning: _\#_ | Denna funktion väntar. För närvarande ignoreras avkastning som är associerad med formelversionen när planeringsoptimering är aktiverad. |
| Produktion | Planer med ordningsföljd: _\#_ | Denna funktion väntar. För närvarande ignoreras ordningsföljd när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |
| Produktion | Släppta eller startade produktionsorder som inte är startade, där planerad start är tidigare än: _\#_ | Denna funktion väntar. |
| Produktion | Planerade resurser med begränsad kapacitet: _\#_ | Denna funktion väntar. För närvarande kommer resurser som har planerats med begränsad kapacitet att ignoreras när planeringsoptimering är aktiverad. Tidsplaneringen görs baserat på standardproduktionstiden från produkten. |
| Produktion | Flöden använda i planering: _\#_ | Denna funktion väntar. För närvarande ignoreras flöden när planeringsoptimering aktiveras. Standardproduktionstiden för produkten används. |
| Produktion | Reservation av försäljningsrad med nedbrytning: _\#_ | Reservation av försäljningsrad med nedbrytning stöds inte när planeringsoptimering aktiveras. |
| Produktion | Planering med nedbrytning av produktionsorder: _\#_ | Tidsplanering som använder nedbrytning av produktionsorder stöds inte när planeringsoptimering aktiveras. Tillverkningsorder kan tidsplaneras individuellt. |
| Anbudsförfrågningar | Huvudplaner med anbudsförfrågningar aktiverat: _\#_ | Denna funktion väntar. För närvarande anses inte anbudsförfrågningar vara efterfrågan när planeringsoptimering är aktiverad. De kommer att ignoreras oavsett den här inställningen. |
| Rekvisitioner | Huvudplaner med rekvisitioner aktiverat: _\#_ | Denna funktion väntar. För närvarande betraktas inte rekvisitioner när planeringsoptimering aktiveras. De kommer att ignoreras oavsett den här inställningen. |
| Säkerhetsmarginaler | Disponeringsgrupper med säkerhetsmarginal: _\#_ | Denna funktion väntar. För närvarande ignoreras säkerhetsmarginal när planeringsoptimering aktiveras. Du kan kompensera för det här problemet genom att öka produktionstiden så att den inkluderar säkerhetsmarginalen. |
| Säkerhetsmarginaler | Huvudplaner med säkerhetsmarginal: _\#_ | Denna funktion väntar. För närvarande ignoreras säkerhetsmarginal när planeringsoptimeringen är aktiverad, oavsett den här inställningen. Du kan kompensera för det här problemet genom att öka produktionstiden så att den inkluderar säkerhetsmarginalen. |
| Uppfyllelse av säkerhetslager | Poster för artikeldisponering med "uppfyllda minimum" som skiljer sig från "dagens datum + anskaffningstid": _\#_ | Planeringsoptimering använder alltid *dagens datum + anskaffningstid*. Den här ändringen görs för att förbereda för en förenklad planeringsinställning i framtiden och för att ge ett åtgärdbart resultat. Om anskaffningstiden inte finns med i säkerhetslagret försenas planerade order som skapas för aktuell lagerbehållning alltid på grund av produktionstiden. Det här beteendet kan orsaka betydande brus och oönskade planerade order. Det bästa tillvägagångssättet är att ändra inställningen så att *dagens datum + anskaffningstid* används. |
| Försäljningsofferter | Huvudplaner med försäljningsofferter aktiverade: _\#_ | Denna funktion väntar. För närvarande betraktas inte offerter när planeringsoptimering aktiveras. De kommer att ignoreras oavsett den här inställningen. |
| Hållbarhetstid | Huvudplaner med hållbarhetstid aktiverat: _\#_ | Denna funktion väntar. För närvarande beaktas inte hållbarhetstid när planeringsoptimeringen är aktiverad, oavsett den här inställningen. |

## <a name="additional-resources"></a>Ytterligare resurser

[Planeringsoptimering – översikt](planning-optimization-overview.md)

[Kom igång med planeringsoptimering](get-started.md)

[Visa planhistorik och planeringsloggar](plan-history-logs.md)

[Använda filter på en plan](plan-filters.md)

[Annullera ett planeringsjobb](cancel-planning-job.md)
