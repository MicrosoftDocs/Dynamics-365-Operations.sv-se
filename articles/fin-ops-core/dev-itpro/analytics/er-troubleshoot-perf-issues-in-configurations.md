---
title: Felsöka prestandaproblem i ER-konfigurationer
description: I det här avsnittet beskrivs hur du hittar och åtgärdar prestandaproblem i ER-konfigurationer (elektronisk rapportering).
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b5f5308f171b6cd4224debec897dbde133e6d8424673aabfab51e6b83b9014e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744396"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Felsöka prestandaproblem i ER-konfigurationer

I det här avsnittet beskrivs hur du hittar och löser prestandaproblem i [ER](general-electronic-reporting.md)-[konfigurationer (ER)](general-electronic-reporting.md#Configuration).

Vanligtvis består prestandaundersökningen av flera steg.

1. [Samla in](#collecting-data) data.
2. Analysera insamlade data.
3. Baserat på resultaten av analysen använder du ER-konfigurationer för att [göra ändringar](#making-changes) eller bestämmer dig för att samla in mer data.

## <a name="troubleshooting"></a>Felsökning

### <a name="analyze-execution-time"></a>Analysera körningstid

Körningstiden kan bero på oförutsägbara faktorer, till exempel andra aktiviteter som körs i samma miljö och cachelagring som använder data när de anropas för första gången. Därför bör du upprepa körningen och mätningen flera gånger.

Ibland orsakas prestandaproblem inte av en ER-formatkonfiguration som används för rapportering. Istället orsakas de av X++ -koden som används för att öppna ER-formatkonfigurationen.

1. I antingen [Åtgärdscentret](#infolog-time) eller [händelseloggen](#event-log-time) tittar du på rapportens körningstid.
2. Jämför körningstiden för rapporten med den totala körningstiden i scenariot.
3. Om körningstiden för rapporten är mycket kortare än den totala körningstiden bör du tänka på hur mycket data rapporten bearbetar:

    - Om rapporten bearbetar en liten mängd data kan problemet inbegripa inläsningstiden för konfigurationen.
    - Om rapporten bearbetar en stor mängd data kan problemet inbegripa förbearbetning av X++. Använd [Trace parser](#analyze-trace-parser-trace) för att analysera det här fallet.

    I andra fall, se nästa avsnitt.

4. Kör flera tester som involverar olika mängder data för att avgöra hur körningstiden beror på mängden data.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Analysera Trace parser-spår

Förbered ett mindre exempel eller samla in flera spår under slumpmässiga delar av rapportgenereringen.

I [Trace parser](#trace-parser) gör du sedan en standardanalys nedifrån och upp och besvarar följande frågor:

- Vilka är de bästa metoderna när det gäller tidsförbrukning?
- Vilken del av den totala tiden använder dessa metoder?

Besvara samma frågor för frågor.

Om du ser att metoderna föregås av "ER" går du vidare till nästa avsnitt.

Om du ser att metoder eller frågor har sitt ursprung i programsviten bör du överväga allmänna optimeringar (till exempel skapa index).

Analysera antalet anrop. Om antalet är betydligt högre än förväntat bör du överväga att cachelagra motsvarande noder i konfigurationen.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Analysera databasanrop

Förbered ett exempel som har en liten mängd data, så att du kan samla in en [ER-spårning](#electronic-reporting-traces).

Öppna sedan spårningen i ER-modellmappningsdesignern och titta längst ned på sidan. Besvara följande frågor:

- Finns det några frågedubbletter? Om så är fallet, överväg någon av följande korrigeringar:

    - [Använd cachelagring](#use-caching) om du tror att det finns flera anrop i en enda överordnad post.
    - [Använd ett cachelagrat, parametriserat beräknat fält](#cached-parameterized) om du tror att det finns anrop till samma post i olika poster.
    - [Använd en **KOPPLA**-datakälla](#use-join-datasource) om du måste läsa till ett stort antal olika poster från en databas.

- Motsvarar antalet frågor och hämtade poster den totala mängden data? Om ett dokument till exempel har 10 rader, visar då statistiken att rapporten extraherar 10 rader eller 1 000 rader? Om du har ett stort antal hämtade poster bör du överväga någon av följande korrigeringar:

    - [Använd funktionern **FILTER** istället för funktionen **VAR**](#filter) för att bearbeta data på SQL Server-sidan.
    - Använd cachelagring för att undvika att hämta samma data.
    - [Använd insamlade datafunktioner](#collected-data) för att undvika att hämta samma data för summering.

### <a name="analyze-perfview-traces"></a>Analysera PerfView-spår

[PerfView](#perfview) är ett verktyg för erfarna utvecklare. Mer detaljerad information om följande steg finns i [Utredningsgrunder för processtid](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).

1. Samla in en spårning med hjälp av trådtid.
2. Inkludera endast staplar som använder **runUnattended** för att endast filtrera tråden som har konfigurationskörning. (Lägg till **runUnattended** i indatarutan **IncPats**.)
3. Vik all processor-, nätverks- och blockerad tid.
4. Läs in [ER-förinställningar för PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Välj **ER** \> **Annan förinställning**.
6. Titta på namnen:

    - Du kommer förmodligen att se den plattformskod som förbrukar mest tid.
    - Du kan dubbeltrycka (eller dubbelklicka) och gå upp via **mottagare**.

        Om du hittar klasser som har prefixet "ERExpression", och om dessa är funktioner som är relaterade till formler kan du gissa funktionsnamnet baserat på klassnamnet och du kan titta på ER-lagringsplatsen för att visa attributen.

### <a name="fixes"></a>Korrigeringar

- Om du ser att större delen av processortiden förbrukas av frågor försöker du minska antalet frågor:

    - [Granska ER-spårningen](#analyze-database-calls) för duplicerade frågor.
    - Se hur många poster som hämtas och utvärdera hur mycket data som teoretiskt ska hämtas.

- Om du ser att större delen av processortiden förbrukas av de funktioner som används kan du försöka hitta den plats i konfigurationen som förbrukar flest resurser.
- Om du ser att större delen av processortiden förbrukas av datainsamlingsfunktioner bör du överväga att ersätta dem med *SQL-grupp efter* på modellmappningssidan.

### <a name="collecting-data"></a><a name="collecting-data"></a>Datainsamling

Beroende på din miljö finns det flera sätt att samla in tillgängliga data:

- Få den totala körningstiden:

    - Från åtgärdscentret
    - Från händelseloggen

- Profilera körningen:

    - Genom att använda ER-verktyg
    - Genom att använda Trace parser
    - Genom att använda PerfView

#### <a name="collecting-data-in-a-production-environment"></a>Samla in data i en produktionsmiljö

Ibland kan problem endast reproduceras i en produktionsmiljö. Data kan samlas in på följande sätt:

- Genom att använda [Trace parser](../perf-test/trace-trace-tutorial.md)spår.
- Genom att använda spårningar efter [ER-körning](trace-execution-er-troubleshoot-perf.md)
- Genom att använda den totala körningstiden

#### <a name="collecting-data-in-a-development-environment"></a>Samla in data i en utvecklingsmiljö

Förutom de verktyg som kan användas i en produktionsmiljö finns det flera verktyg du kan använda i en utvecklingsmiljö:

- Händelselogg (Microsoft-Dynamics-ElectronicReporting). Denna logg kan ge dig den totala körningstiden.
- Vanliga .NET-verktyg, till exempel PerfView.

Dessutom ger en utvecklingsmiljö dig mer flexibilitet att experimentera. Du kan till exempel stänga av delar av rapporter för att se hur körningstiden påverkas.

### <a name="tools"></a><a name="tools"></a>Verktyg

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Körningstid i åtgärdscentret

ER kan visa körningstiden för konfigurationen i åtgärdscentret. Detta alternativ fungerar bara för en viss användare och ett visst företag, och endast för interaktiva sessioner. Följ dessa steg för att göra denna funktion tillgänglig.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. I dialogrutan **Användarparametrar** anger du alternativet **Visa genereringstid för fil** som **Ja**.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Körningstid i händelseloggen

1. Öppna Loggboken i Windows.
2. Under **Program- och tjänsteloggar** öppnar du **Microsoft-Dynamics-ElectronicReporting/Operational**.
3. Leta efter **FormatMapingRun**-händelser där **EventID=2**, detta eftersom dessa händelser innehåller information om förfluten tid.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Trace parser-spår 

Eftersom ER implementeras i X++kan du använda vanliga X++ -verktyg för att analysera prestanda. Mer information finns i [Spåra med hjälp av Trace parser](../perf-test/trace-trace-tutorial.md).

Det finns några begränsningar i samband med detta tillvägagångssätt. Eftersom en del av ER implementeras i C# kommer inte alla detaljer att vara tillgängliga. Du kan dock visa detaljerad information om dataanvändningen. Dessutom kan långa rapportkörningar komma att överskrida begränsningar för spårningslagring.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>ER-spår

ER kan samla sina egna spår, och har visualiserings- och analysverktyg för dessa spår. För mer information, se [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Eftersom både X++ och ER implementeras ovanpå .NET-plattformen kan du använda vanliga .NET-verktyg. Du kan till exempel använda det kostnadsfria verktyget [PerfView](https://github.com/Microsoft/perfview).

Du kan också samla in data från kommandoraden. Följande Windows PowerShell-skript samlar till exempel in körningstiden tills alla formatkörningar stoppats på datorn.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

Det finns några begränsningar i samband med detta tillvägagångssätt. Du måste ha administratörsåtkomst till maskinen. Du måste dessutom vara en erfaren utvecklare, detta eftersom inlärningskurvan är brant.

### <a name="making-changes"></a><a name="making-changes"></a>Göra ändringar

#### <a name="use-caching"></a><a name="use-caching"></a>Använd cachelagring

Även om cachelagring minskar den tid som krävs för att hämta data igen, så kostar den minne. Använd cachelagring i de fall där mängden hämtade data inte är särskilt stor. Mer information och ett exempel som visar hur du använder cachelagring finns i [Förbättra modellmappningen baserat på information från körningsspårningen](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Använd ett cachelagrat, parameteriserat beräknat fält

Ibland måste värdena sökas upprepade gånger. Exempel på detta är kontonamn och kontonummer. För att spara tid kan du skapa ett beräknat fält som har parametrar på den översta nivån och sedan lägga till fältet i cacheminnet.

Vi rekommenderar att du bara använder den här metoden när storleken på cachelagrade data är liten. Mer information finns i [Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT](er-calculated-field-ds-performance.md).

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Använd en KOPPLA-datakälla

Med en **KOPPLA**-datakälla kan flera anslutna poster hämtas av en enda fråga. En separat fråga behöver inte användas för att hämta varje ansluten post. Om du till exempel har 1 000 rader och hämtar artikeldata för respektive rad efter relation, får du 1 001 frågor (= 1 000 + 1). Om du använder en **KOPPLA**-datakälla använder du bara en enda fråga för att hämta samma data. Se [Använd KOPPL-datakällor i ER-modellmappningar för att hämta data från flera programtabeller](er-join-data-sources.md) om du vill ha mer information.

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Använd funktionen FILTER istället för funktionen VAR

Funktionen **[FILTER](er-functions-list-filter.md)** kör villkor på SQL Server, medan funktionen **VAR** hämtar alla data i listan - en post i taget - och applicerar villkoret för respektive post. Du vill till exempel välja en enda post av 1 000 poster. Om du använder **VAR** hämtas alla 1 000 poster. Om du emellertid använder **FILTER** hämtas exakt en (1) post. **FILTER** kan också använda index på databassidan.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Använda insamlade datafunktioner eller en ackumulerad datakälla

Om konfigurationen har en *gruppera efter*-komponent som sammanfattar tidigare hämtade data efter rapport, hämtar komponenten alla data igen. Genom att använda insamlade datafunktioner gör du det möjligt för ER att samla in data under den första hämtningen. Mer information finns i [Konfigurera format för inventering och summering i ER](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>Skriva om delar av konfigurationen i X++

ER stöder anropmetoder för tabeller och klasser, inklusive tillägg. Överväg att skriva om delar av modellmappningen i X++ för att förbättra prestandan.

ER kan använda data från följande källor:

- Klasser (datakällorna **objekt** och **klass**)
- Tabeller (datakällorna **tabell** och **tabellposter**)

[ER-API:n](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) ger också ett sätt att skicka förberäknade data från den anropande koden. Programserien innehåller många exempel på den här metoden.
