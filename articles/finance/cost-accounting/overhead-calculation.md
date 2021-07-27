---
title: Beräkning av indirekta kostnader
description: Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 09d4516c40833771d27db13eac8228bd8c5e0e4a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355045"
---
# <a name="overhead-calculation"></a>Beräkning av indirekta kostnader

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.

## <a name="term-definition"></a>Termdefinition

Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst. Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter. Här följer några exempel på indirekta kostnader:

-   Hyra
-   Elektricitet
-   Administrativa löner

## <a name="overhead-calculation-overview"></a>Översikt över beräkning av indirekta kostnader
Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning. Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts. Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner. Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum. Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen. Det unika versions-ID:t består av följande element:

-   Versionstyp
-   Datum och tid
-   Huvudbok för kostnadsredovisning
-   Räkenskapsår
-   Räkenskapsperiod

Beräkningen av indirekta kostnader körs oberoende av versionen. Du kan därför beräkna budgetversionen innan den faktiska versionen. Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild. I varje steg skapas en journalrubrik med journalposter. Den här journalrubriken behåller indata för varje beräkningssteg. Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans. Därför måste du alltid ha fullständig spårning. 

[![Beräkning av indirekta kostnader.](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Beräkna och fördela den indirekta elkostnaden
I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma. Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning. I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer. Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning. I redovisning kan en elkostnad bokföras enligt tabellen nedan.

<table>
<thead>
<tr>
<th>Räkenskapsdatum</th>
<th colspan="2">Kostnadsställe</th>
<th colspan="2">Huvudkonto</th>
<th>Belopp i redovisningsvalutan</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 januari 2017</td>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>10 000,00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>Steg 1: Bearbeta beräkning av kostnadsbeteende

Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning. Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.

#### <a name="define-the-cost-behavior-rule"></a>Definiera kostnadsbeteenderegeln

I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning. Elräkningar matchar ofta denna definition. När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh). Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:

-   Fast belopp 1 000,00
    -   0 &lt;= 1 000,00 = fast
    -   1 000,01 &lt; N = variabel

##### <a name="journal"></a>Journal

<table>
<thead>
<tr>
<th>Journal</th>
<th>Journaltyp</th>
<th colspan="3">Räkenskapskalenderperiod</th>
<th>version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Journal för beräkning av kostnadsbeteende</td>
<td>Skatt</td>
<td>2017</td>
<td>Period 1</td>
<td>Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Journalposter (Journalposter för kostnadsobjektsaldo)

<table>
<thead>
<tr>
<th>Räkenskapsdatum</th>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 januari 2017</td>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Oklassificerade</td>
<td>10 000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Kostnadsposter

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
<th>Räkenskapsdatum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Oklassificerade</td>
<td>10 000,00</td>
<td>3 januari 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Oklassificerade</td>
<td>-10 000,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>1 000,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>9,000.00</td>
<td>31 januari 2017</td>
</tr>
</tbody>
</table>

För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).
### <a name="step-2-process-the-cost-distribution-calculation"></a>Steg 2: Bearbeta beräkning av kostnadsfördelning

Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag. Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.

#### <a name="define-the-cost-distribution-rule"></a>Definiera kostnadsfördelningsregeln

I affärsredovisning är elkostnader ofta registrerade som en klumpsumma. I kostnadsredovisning är inte denna metod tillräckligt detaljerad. Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt. Den mest logiska allokeringsbasen är elförbrukning (Kwh). En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs. Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>1 000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>6,000</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>0</td>
</tr>
</tbody>
</table>

I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>1 000</td>
<td>(1 000 ÷ 7 000) × 9 000,00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>6,000</td>
<td>(6 000 ÷ 7 000) × 9 000,00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>0</td>
<td>(0 ÷ 7 000) × 9 000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el. Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Formel</th>
<th>Storlek</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>(1 000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1 000,00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>(6 000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1 000,00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>(0 &gt; 0,00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1 000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Journal

<table>
<thead>
<tr>
<th>Journal</th>
<th>Journaltyp</th>
<th colspan="3">Räkenskapskalenderperiod</th>
<th>version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Beräkningsjournal för kostnadsfördelning</td>
<td>Skatt</td>
<td>2017</td>
<td>Period 1</td>
<td>Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Journalposter (Journalposter för kostnadsobjektsaldo)

<table>
<thead>
<tr>
<th>Räkenskapsdatum</th>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 januari 2017</td>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>1 000,00</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>9,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Kostnadsposter

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
<th>Räkenskapsdatum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>-1 000,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>500.00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>500.00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Standardkostnadscenter</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-9 000,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>1,285.71</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>7,714.29</td>
<td>31 januari 2017</td>
</tr>
</tbody>
</table>

För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md). 

### <a name="step-3-process-the-overhead-rate-calculation"></a>Steg 3: Bearbeta beräkning av indirekt kostnad

Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt. Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget. 

#### <a name="define-the-overhead-rate"></a>Definiera en indirekt kostnad

Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt. En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Timmar</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Projekt 1</td>
<td>3</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projekt 2</td>
<td>1</td>
</tr>
</tbody>
</table>

En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Enheter</th>
<th>Kurs</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Variabel kostnad</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
<th>Kostnadselement</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Projekt 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10,00</td>
<td>30,00</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projekt 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10,00</td>
<td>10,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Journal

<table>
<thead>
<tr>
<th>Journal</th>
<th>Journaltyp</th>
<th colspan="3">Räkenskapskalenderperiod</th>
<th>version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Journal för beräkning av indirekt kostnad</td>
<td>Skatt</td>
<td>2017</td>
<td>Period 1</td>
<td>Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)

<table>
<thead>
<tr>
<th>Räkenskapsdatum</th>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 januari 2017</td>
<td>Proj 1</td>
<td>Internt proj 1</td>
<td>3,00</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>Proj 2</td>
<td>Internt proj 2</td>
<td>1,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Kostnadsposter

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
<th>Räkenskapsdatum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-30,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Proj 1</td>
<td>Internt proj 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>30,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-10.00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Internt proj 2</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>10,00</td>
<td>31 januari 2017</td>
</tr>
</tbody>
</table>

För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).

### <a name="step-4-process-the-cost-allocation-calculation"></a>Steg 4: Bearbeta beräkning av kostnadsallokering

Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag. Finance stöder ömsesidig allokeringsmetod. I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt. Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i. Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag. Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds. Allokeringsordern styrs av kostnadskontrollenheten. 

[![Ömsesidig metod.](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>Definiera kostnadsallokering

Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet. Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt. En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>HR-tjänster</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10</td>
</tr>
</tbody>
</table>

Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt. En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Finanstjänster</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>35</td>
</tr>
</tbody>
</table>

Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt. En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Sammansättningstjänster (timmar)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>20</td>
</tr>
</tbody>
</table>

Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt. En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Förpackningstjänster (timmar)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>15</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen. Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template). Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
<th>Kostnadsbeteende</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>35</td>
<td>(35 ÷ 100) × 500,00</td>
<td>175.00</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>55</td>
<td>(55 ÷ 100) × 500,00</td>
<td>275.00</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10</td>
<td>(10 ÷ 100) × 500,00</td>
<td>50,00</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>35</td>
<td>(35 ÷ 100) × 1 245,71</td>
<td>436.00</td>
<td>Variabel kostnad</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>55</td>
<td>(55 ÷ 100) × 1 245,71</td>
<td>685.14</td>
<td>Variabel kostnad</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10</td>
<td>(10 ÷ 100) × 1 245,71</td>
<td>124.57</td>
<td>Variabel kostnad</td>
</tr>
</tbody>
</table>

Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
<th>Kostnadsbeteende</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>65</td>
<td>(65 ÷ 100) × (500,00 + 175,00)</td>
<td>438.75</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>35</td>
<td>(35 ÷ 100) × (500,00 + 175,00)</td>
<td>236.25</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>65</td>
<td>(65 ÷ 100) × (7 714,29 + 436,00)</td>
<td>5,297.69</td>
<td>Variabel kostnad</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>35</td>
<td>(35 ÷ 100) × (7 714,29 + 436,00)</td>
<td>2,852.60</td>
<td>Variabel kostnad</td>
</tr>
</tbody>
</table>

Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
<th>Kostnadsbeteende</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275,00 + 438,75)</td>
<td>535.31</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275,00 + 438,75)</td>
<td>178.44</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5 297,69 + 685,14)</td>
<td>4,487.12</td>
<td>Variabel kostnad</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5 297,69 + 685,14)</td>
<td>1,495.71</td>
<td>Variabel kostnad</td>
</tr>
</tbody>
</table>

Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th>Storlek</th>
<th>Allokeringsfaktor</th>
<th>Belopp</th>
<th>Kostnadsbeteende</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50,00 + 236,25)</td>
<td>241.05</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50,00 + 236,25)</td>
<td>45.20</td>
<td>Fast kostnad</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2 852,60 + 124,57)</td>
<td>2,507.09</td>
<td>Variabel kostnad</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2 852,60 + 124,57)</td>
<td>470.08</td>
<td>Variabel kostnad</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Journalposter (Journalposter för kostnadsobjektsaldo)

<table>
<thead>
<tr>
<th>Journal</th>
<th>Journaltyp</th>
<th colspan="3">Räkenskapskalenderperiod</th>
<th>version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Kostnadsallokeringsjournal</td>
<td>Skatt</td>
<td>2017</td>
<td>Period 1</td>
<td>Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Journalrader

<table>
<thead>
<tr>
<th>Räkenskapsdatum</th>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 januari 2017</td>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>500.00</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>1,245.71</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>675.00</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>8,150.29</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>713.75</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>5,982.83</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC003</td>
<td>Paketering</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>286.25</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>CC003</td>
<td>Paketering</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>2,977.17</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>776.36</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>6,994.21</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>Prod 2</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>223.64</td>
</tr>
<tr>
<td>31 januari 2017</td>
<td>Prod 2</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Kostnadsposter

<table>
<thead>
<tr>
<th colspan="2">Kostnadsobjekt</th>
<th colspan="2">Kostnadselement</th>
<th>Kostnadsbeteende</th>
<th>Belopp</th>
<th>Räkenskapsdatum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>-500,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>175.00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>275.00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>50,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>Personal</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-1 245,71</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>436.00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>685.14</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>124.57</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>-675,00</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>438.75</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>236.25</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finansiellt</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-8 150,29</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>5,297.69</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Paketering</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>2,852.60</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>-713,75</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>535.31</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>178.44</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-5 982,83</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>4,487.12</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>1,495.71</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>-286,25</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>241.05</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Fast kostnad</td>
<td>45.20</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Sammansättning</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>-2 977,17</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produkt 1</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>2,507.09</td>
<td>31 januari 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produkt 2</td>
<td>10001</td>
<td>Elektricitet</td>
<td>Variabel kostnad</td>
<td>470.08</td>
<td>31 januari 2017</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Slutsats
I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID. Därför vet kostnadsrevisorer att kostnaden måste allkoeras. I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas. Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Kostnadselement</th>
<th colspan="9">Kostnadsobjekt</th>
<th rowspan="2">Totalt</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proj 1</th>
<th>Proj 2</th>
<th>Prod 1</th>
<th>Prod 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Elektricitet</td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30.00</strong></td>
<td style="text-align: right;"><strong>10.00</strong></td>
<td style="text-align: right;"><strong>7,770.57</strong></td>
<td style="text-align: right;"><strong>2,189.43</strong></td>
<td style="text-align: right;"><strong>10,000.00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Oklassificerade</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Fast kostnad</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1,000.00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Variabel kostnad</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30,00</td>
<td style="text-align: right;">10,00</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9,000.00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten. Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen. Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden. Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden. Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]