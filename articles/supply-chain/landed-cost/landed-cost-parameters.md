---
title: Inställningar av parametrar för hemtagningskostnad
description: I det här avsnittet beskrivs hur du ställer in allmän information och konfigurationsinställningar som används i modulen hemtagningskostnad för bokföring, statusuppdateringar, nummerserier och beteende.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 489c0db50d52c1e58eab73ad19a73babf22b4de7
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500776"
---
# <a name="landed-cost-parameters-setup"></a>Inställningar av parametrar för hemtagningskostnad

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Du använder sidan **parametrar för hemtagningskostnad** för att ställa in allmän information och konfigurationsinställningar som används i modulen **hemtagningskostnad** för bokföring, statusuppdateringar, nummerserier och beteende. Parameterinställningarna delas av juridiska personer och kan ändras av en administratör.

## <a name="open-the-landed-cost-parameters-page"></a>Öppna sidan parametrar för hemtagningskostnad

Om du vill arbeta med parametrarna går du till **hemtagningskostnad \> inställningar \> parametrar för hemtagningskostnad** och ställ sedan in fälten som beskrivs i följande underavsnitt.

![Sidan parametrar för hemtagningskostnad](media/landed-cost-parameters.png "Sidan parametrar för hemtagningskostnad")

## <a name="general-tab"></a>Fliken Allmänt

### <a name="general-fasttab"></a>Snabbfliken Allmänt

I följande tabell beskrivs fälten som är tillgängliga på snabbfliken **Allmänt** på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**.

| Inställning | beskrivning |
|---|---|
| Använd leveranstariff | En leveranskostnad anges för en angiven period och används för uppskattade kostnader för varor som använder flera valutor. Ställ in det här alternativet till *Ja* om du vill använda en leveranskostnad. |
| Valutakurstyp | Standardinsamlingen av valutakurser som används för beräkningar av flera valutor för en färd- och färdkostnader. |
| Uppdatera kvantiteten för inköpsorder | Välj vad som händer om en användare ändrar kvantiteten på en inköpsorderrad:<ul><li>**Acceptera** – färdkvantiteten justeras automatiskt.</li><li>**Varning** – Om raden är kopplad till en varning visas en varning, men färdkvantiteten uppdateras.</li><li>**Fel** – Om raden är kopplad till ett fel visas ett felmeddelande och inköpsordern kan inte uppdateras. Därför måste orderraden först tas bort från den.</li></ul> |
| Uppdatera antal kartonger automatiskt | När det här alternativet är inställt på *Ja*, läggs alla kartonger samman och visas på färd-/behållarnivåerna. När det ställs in på *Nej* har antalet kartonger satts inledningsvis till 0 (noll) och kan redigeras manuellt efter behov. |

### <a name="costing-fasttab"></a>Snabbflik för kostnadsredovisning

I följande tabell beskrivs fälten som är tillgängliga på snabbfliken **Kostnadsredovisning** på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**.

| Inställning | beskrivning |
|---|---|
| Bokföringsspecifikation | Välj värdejustering i redovisningen:<ul><li>**Summa** – En total siffra bokförs i redovisningen.</li><li>**Artikelgrupp** – justeringen anges per artikelgrupp.</li><li>**Artikelnummer** – justeringen anges per artikel. Det här värdet ger mest detaljer.</li></ul> |
| Tillåt noll kostnader | Ange alternativet *Nej* om ett fel ska visas om en användare försöker bokföra en kostnadsuppskattning för en faktura eller inköpsorder som inte innehåller något värde för den förväntade färdkostnaden. Felmeddelandet visar att kostnaden 0 (noll) inte kan fördelas och att fakturabokföringen misslyckas. I detta fall kan användaren uppdatera uppskattningen manuellt (eller omkonfigurera automatiska kostnaden) och sedan antingen hämta in det uppdaterade värdet eller radera kostnaden om den inte gäller.<p>Ställ in detta alternativ till *Ja* om du vill tillåta att färdkostnaden är tom. I det här fallet fördelas priset 0 (noll) enligt kostnadsområdet. En leverantörskostnadsfaktura kan sedan bearbetas mot nollpriskostnaden när färden inlevereras.</p><p>Vi rekommenderar att du konfigurerar uppskattningen på posten för automatisk kostnad för att förhindra att en nollpriskostnad visas. Även om denna uppskattning inte är helt korrekt bör den fortfarande vara mer exakt än en antagen nollkostnad.</p> |
| Bokföringsdatum för justering | När du bokar en färdkostnadsfaktura för leverantörsreskontra uppdateras även kvittningstabellen (lagerjusteringar). Välj det datum som är inställt som standard på **Välj färdkostnader** när du är i fakturajournalen:<ul><li>**Transaktionsdatum** – Använd datum för journalen (bokföringsdatum).</li><li>**Fakturadatum för inköpsorder** – Använd det ekonomiska bokföringsdatumet för lagerfakturan (inköpsorder).</li><li>**Markerat datum** – Användaren kan ange ett bokföringsdatum. Även om datumet kan lämnas tomt, om det fortfarande är tomt när kostnadsfakturan bokförs, får användaren ett felmeddelande.</li></ul> |
| Använd verifikation för inköpsfaktura | När det här alternativet ställs in på *Ja*, kommer periodiseringstransaktioner för kostnader att använda samma verifikationsnummer som används för inköpsfakturan. När det är inställt på *Nej* använder systemet nästa tillgängliga nummer för nummerserien **verifikation av periodiserad kostnad** som anges på fliken **nummerserier** på sidan **Parametrar hemtagningskostnad**.<p>Det här alternativet gäller endast när alternativet **Bokför till debiteringskonto i redovisning** är inställt på *Ja* på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra**.</p> |
| Spärra manuell bokföring på clearingkonto | Ställ in detta alternativ till *Ja* för att förhindra bokföring till clearingkonton där transaktionen inte har kopplats till en sådan genom att välja **Funktioner \> Välj färdkostnader** i åtgärdsfönstret i leverantörsfakturajournalen. Vi rekommenderar att du ställer in detta alternativ till *Ja*, så att färden och clearingkontot kan kvittas korrekt. |
| Använd avgiftsperiodiseringskontots kostnadstypen | När det här alternativet ställs in på *Ja*, används det periodiseringskonto för debitering som konfigurerats för den relevanta kostnadstypskoden på sidan **Kostnadstypkoder** för att periodisera kostnader som en utgift.<p>Det här alternativet gäller endast när alternativet **Bokför till debiteringskonto i redovisning** är inställt på *Ja* på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra**. |
| Bokför justeringar som avvikelse | När det här alternativet ställs in på *Ja* åsidosätter det standardfunktionen och tvingar lagerjusteringstransaktionerna som är relaterade till avvikelser mellan uppskattade kostnader och faktiska kostnader att bokföras på ett avvikelsekonto.<p>När det här alternativet ställs in på *Nej*, hanteras lagerjusteringstransaktionerna som hör till avvikelserna baserat på konfigurationen för kostnadsmetoden och kostnadstypkoden. För standardkostnader bokförs avvikelser fortfarande på avvikelsekontot. Vid förflyttning av viktat medelvärde (WMA) bokförs avvikelser antingen på avvikelsekontot eller i lagret.</p><p>Det här alternativet gäller endast när alternativet **Bokför till debiteringskonto i redovisning** är inställt på *Ja* på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra**.</p> |

### <a name="validation-fasttab"></a>Snabbflik för validering

I följande tabell beskrivs fälten som är tillgängliga på snabbfliken **Validering** på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**.

| Inställning | beskrivning |
|---|---|
| Flera kostnadsfakturor | Välj vad som inträffar om mer än en faktura bearbetas mot en kund, en kund eller en behållare för samma tillägg.<ul><li>**Godta** – Systemet ska tillåta flera kostnadsfakturor.</li><li>**Varning** – En varning visas.</li><li>**Fel** - Ett felmeddelande visas.</li></ul> |
| Flera leverantörer per folio | Välj vad som inträffar om mer än en leverantörs inköpsorder läggs till i en folio.<ul><li>**Godta** – Åtgärden ska tillåtas i systemet.</li><li>**Varning** – En varning visas, men åtgärden kan fortfarande utföras.</li><li>**Fel** – Ett felmeddelande visas och åtgärden förhindras.</li></ul><p>Ditt tullombud eller lokala lagar kan bestämma ett visst värde för det här fältet.</p> |
| Tolerans för flera leveranssätt | Välj vad som inträffar om varor från en inköpsorder som har ett annat leveranssätt än leveranssättet läggs till i den ordningen.<ul><li>**Godta** – Åtgärden ska tillåtas i systemet.</li><li>**Varning** – En varning visas, men åtgärden kan fortfarande utföras.</li><li>**Fel** – Ett felmeddelande visas och åtgärden förhindras.</li></ul> |
| Tolerans för flera distributionslager | Välj vad som händer om en färd innehåller flera orderrader som måste levereras till olika lagerställen. Dessa orderrader kan vara fördelade på en eller flera inköpsorder.<ul><li>**Godta** – Åtgärden ska tillåtas i systemet.</li><li>**Varning** – En varning visas.</li><li>**Fel** - Ett felmeddelande visas.</li></ul> |
| Volym saknas | Välj vad som händer om en användare lägger till en artikel utan volym i en färd.<ul><li>**Godta** – Åtgärden ska acceptera artikeln.</li><li>**Varning** – En varning visas.</li><li>**Fel** - Ett felmeddelande visas.</li></ul><p>Om volymer används för att beräkna och fördela kostnader rekommenderar vi att du väljer antingen *Varning* eller *Fel*.</p> |
| Tjänstleverantör utan sjötransportkostnad | Välj vad som händer om en användare försöker bearbeta en faktura för en leverantör som inte har kopplats till en färd. <ul><li>**Godta** – Åtgärden ska tillåtas i systemet.</li><li>**Varning** – En varning visas.</li><li>**Fel** - Ett felmeddelande visas.</li></ul><p>Vi rekommenderar att du väljer *Varning*.</p> |

### <a name="defaults-fasttab"></a>Snabbfliken Standardvärden

I följande tabell beskrivs fälten som är tillgängliga på snabbfliken **Standardvärden** på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**.

| Inställning | beskrivning |
|---|---|
| Journalnamn | Välj den standardjournal som ska användas för funktionen *Skapa införseljournal*. |
| Sjötransportens status | Välj vilken status en användare måste ha innan de kan ställa in en leveransbehållare som används i systemet. Den här åtgärden inträffar normalt när varorna är på väg eller vid lastplatsen. |
| Resemall | Välj den standardmall som ska användas för nya hyrda leveransbehållare. Du väljer vanligtvis en resemall som inkluderar hyreskostnader. |
| Rörelse | Om över-/underkvantiteten för en leverans ligger inom den definierade toleransen bearbetas en rörelsejournal automatiskt. Välj den standardrörelsejournal som ska användas. Fältet **Motkonto** för det valda namnet på rörelsejournalen måste ha ett värde. |
| Överför | När en underleverans bearbetas överförs den kortinleveranskvantiteten till ett underleveranslagerställe. Välj den standard överföringsjournal som ska användas. |
| Inaktivera inköpsorder utan sjötransport | Stäng av funktionen för över-/underleverans av hemtagningskostnad för inköpsorder som inte är kopplade till en färd. |
| Inaktivera inköpsorder för varor som inte är på väg | Stäng av funktionen för över-/underleverans av hemtagningskostnad för inköpsorder som inte använder funktionen varor på väg. |
| Respitperiod för inleverans av varor på väg | Ange hur många dagar efter den första inleveransen av en leveransbehållare som ytterligare överinleveranser fortfarande kan genomföras för den leveransbehållaren. |

## <a name="status-updates-tab"></a>Fliken Statusuppdateringar

Systemet använder statusvärden för att ange status för varje färd. Statusvärden för färd kan användas automatiskt för färder via spårning av färd eller periodiska batchjobb. Alternativt kan du tillämpa dem manuellt genom att öppna färden och sedan välja en status i gruppen **Färduppdatering** slut på fliken **Hantera** i åtgärdsfönstret. 

Du kan skapa så många färdstatusvärden du vill. Fyra av dem måste dock definieras som använda av ett särskilt syfte på fliken **Statusuppdateringar** på sidan **Parametrar för hemtagningskostnad**. Följande register beskriver de fält som är tillgängliga.

| Inställning | beskrivning |
|---|---|
| Kostnadsberäknats | Välj den färdstatus som anger att en sådan färd har genomförts. |
| På väg | Välj den färdstatus som anger att en sådan färd är i transit. |
| Klar för kostnadsredovisning | Välj den färdstatus som anger att en sådan färd är redo för kostnadsredovisning. Den här statusen används när alla lagerinköpsfakturor och färdkostnadsfakturor där fältet **Kredit i färdkostnad** är inställt på *Leverantör* har bearbetats för denna kund. Färder där kostnadsprocessen misslyckas får statusen *Redo för kostnadsredovisning*.|
| Före kostnadsberäkning | Välj den färdstatus som anger att en sådan färd är förberedd för kostnadsredovisning. Det här statusvärdet används när en ny kostnadstransaktion läggs till i en senare transaktion efter att den redan har kostnadsberäknats. Nya kostnadstransaktioner kan läggas till i en tidigare kostnadsberäknad färd när en andra fraktfaktura eller en oväntat demurrage tas emot. Den här statusen tillämpas automatiskt när en ny färdkostnad läggs till i en kostnadsberäknad färd. |

## <a name="voyage-creator-tab"></a>Fliken Skapare av färd

I följande tabell beskrivs avsnitten på fliken **Skapare av färd** på sidan **Parametrar för hemtagningskostnader**.

| Avsnitt | beskrivning |
|---|---|
| Toleranser | Fälten **Tolerans för extern volym** och **Tolerans för extern vikt** definierar trösklar över vilka varor anses vara över volym och över vikt. När en användare lägger till varor på sidan **Färdredigerare** visar systemet en varning om volym eller vikt överstiger värdet du anger här. Värdet för varje fält uttrycks som en procentandel av den maximala volym eller vikt som är inställd för den relevanta leveransbehållartypen. Vi rekommenderar att värdet ligger mellan 5 och 10 procent av den maximala volymen eller vikten. |
| Inställningar för att skapa folio | Systemet kan skapa flera av dem under skapandet av färd. Använd det här avsnittet om du vill definiera när en folio ska skapas. För varje rad i det här avsnittet kontrollerar systemet det angivna registret och det angivna fältet och skapar en folio för varje unikt fältvärde. |

## <a name="cost-estimates-tab"></a>Fliken kostnadsuppskattningar

Fliken **kostnadsuppskattningar** på sidan **parametrar för hemtagningskostnad** innehåller bara ett fält: **standardversion för kostnadsredovisning**. Det här fältet används bara om kostnadsredovisningsmetoden är *Standardkostnadsredovisning*. Välj den standardkostnadsversion som ska användas för periodisk uppgift för *Uppdatering av självkostnad för artikel*. Du kanske måste ändra den här inställningen varje gång ett nytt räkenskapsår börjar.

## <a name="inventory-dimensions-tab"></a>Fliken Lagerdimensioner

På fliken **Lagerdimensioner** på sidan **parametrar för hemtagningskostnad** för att för att kontrollera vilka tillgängliga lagerdimensioner som ska visas som standard på varje sida för hemtagningskostnad där dimensioner används.

Välj en dimension och ställ sedan in alternativet **Färdrader**, **Varor på väg** och/eller **Kostnadsuppskattningar** till *Ja* för varje sida där den dimensionen ska visas som standard. Upprepa det här steget för övriga dimensioner om det behövs.

Inställningarna på den här fliken skapar standarddimensionerna för varje särskild sida för juridiska personer. Användare som arbetar på en av de angivna sidorna kan dock åsidosätta standarddimensionerna genom att välja **Lager \> Visningsdimensione** i åtgärdsfönstret.

## <a name="number-sequences-tab"></a>Fliken Nummerserie

Fliken **Nummerserier** på sidan **Parametrar för hemtagningskostnad** anger varje typ av referensnummerföljd som hemtagningskostnad kräver, men som inte delas mellan juridiska personer. För varje referens i listan väljer du en nummersekvenskod.

> [!NOTE]
> I en konfiguration med flera företag måste olika nummerserier skapas för varje företag (juridisk person).

## <a name="shared-number-sequences-tab"></a>Fliken Delade nummerserie

Fliken **Delade nummerserier** på sidan **Parametrar för hemtagningskostnad** anger varje typ av referensnummerföljd som delas mellan juridiska personer för hemtagningskostnad. För närvarande finns det bara en nummerserie i listan. Den här nummerserien används för legitimations-ID:t.

På sidan **Alla myndigheter** kan användare visa alla färder i alla juridiska personer. Om användarna ska kunna redigera och bearbeta dem måste de finnas med i den juridiska personen för den valda posten.

## <a name="feature-visibility-tab"></a>Fliken Funktionssynlighet

Hemtagningskostnad lägger till funktioner (fält och funktioner) till flera vanliga sidor i Microsoft Dynamics 365 Supply Chain Management. Dessa sidor innehåller sidor som är relaterade till leverantörens huvuddata, frisläppta produkter, inköpsorder, överföringsorder och inställningar för lagerställen. Om du använder hemtagningskostnad måste du göra dessa funktioner synliga överallt innan du kan dra fördel av dem. Om du inte använder hemtagningskostnad kan du dölja funktionerna för att hålla dem utanför vägen.

På fliken **Funktionssynlighet** på sidan **Parametrar för hemtagningskostnad** ange alternativet **Aktivera** till *Ja* för att göra funktionerna hemtagningskostnad var de än är tillgängliga. Ange *Nej* om du vill dölja funktionerna på gemensamma sidor utanför hemtagningskostnaden. Även om alternativet ställs in på *Nej*, är modulen, inklusive sidan **parametrar för hemtagningskostnad**, förblir tillgänglig för användare som har rätt behörighet att komma åt den.
