---
title: "Momsrapporter för Europa"
description: "Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (moms) för vissa europeiska länder."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: f76e431320414b508728cbe9fe20456f107cbe40
ms.openlocfilehash: 7dc6a32a9babc95cfa4ad031534404cae6fa37ea
ms.contentlocale: sv-se
ms.lasthandoff: 06/09/2017

---

# Momsrapporter för Europa
<a id="vat-reporting-for-europe" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller allmän information om inställning och skapande av mervärdesskattutdrag (moms) för vissa europeiska länder.

Det här avsnittet innehåller en allmän metod för inställning och skapande av momsrapporten. Den här metoden används ofta av användare i juridiska personer i följande länder/regioner:

-   Österrike
-   Belgien
-   Tjeckien
-   Estland
-   Finland
-   Tyskland
-   Lettland
-   Litauen
-   Nederländerna
-   Sverige

## Översikt över momsrapport
<a id="vat-statement-overview" class="xliff"></a>
Moms-utdraget baseras på beloppen i momstransaktionerna. Att generera ett momsrapport ingår i betalningsprocessen för moms, som implementeras med funktionen Kvitta och bokföra moms. Den här funktionen beräknar momsen som ska betalas för en given period. Kvittningsberäkningen innehåller bokförd moms för den valda kvittningsperioden för momstransaktionen. Processen för att beräkna data för en momsrapport baseras på förhållandet mellan momskoder och momsrapporteringskoder, där momsrapporteringskoderna matchar rutorna för momsrapporter (eller taggar i XML). För varje momskod bör momsrapporteringskoder ställas in för varje transaktionstyp, till exempel skattepliktig försäljning, skattepliktiga inköp och skattepliktig import. Följande typ av transaktioner beskrivs i avsnittet Momskoder för momsrapportering längre fram i det här avsnittet.

En specifik rapportlayout för varje momsrapporteringskod bör fastställas. Momskoder är samtidigt länkade till en viss momsmyndighet via momskvittningsperioder. En specifik rapportlayout för varje momsmyndighet bör fastställas. Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en momsmyndighet i momskvittningsperioder för momskoden markeras i rapportinställningarna för momskoden. En momstransaktion skapas vid bokföring av en order eller en journal, innehåller en momskod, momskälla, momsriktning och transaktionsbelopp (momsbasbelopp och momsbelopp i redovisningsvaluta, momsvaluta och transaktionsvaluta). Baserat på kombinationen av momstransaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder som angetts för momskoder. Illustrationen som följer visar datarelationen.

![diagram](./media/diagram4.jpg)

## Inställningar för momsrapport
<a id="vat-statement-setup" class="xliff"></a>
Om du vill generera en momsrapport måste du konfigurera följande:

### Momsmyndigheter för momsrapportering
<a id="sales-tax-authorities-for-vat-reporting" class="xliff"></a>

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-authorities/). -->
Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten. På sidan **Momsmyndigheter**, i avsnittet **Allmänt**, väljer du en **Rapportlayout**. Den här layouten används när du ställer in momsrapporteringskoder.

### Momsrapporteringskoder
<a id="sales-tax-reporting-codes" class="xliff"></a>

Momsrapporteringskoder är rutkoder i momsrapporten eller taggnamn i XML-format. Koderna används för att sammanställa och förbereda beloppen för rapporten. Namnen på resulterande belopp används när du konfigurerar det elektroniska rapporteringsformatet för momsrapporten. Du kan skapa och hantera momsrapporteringskoder på sidan **Momsrapporteringskoder**. Du måste tilldela en rapportlayout åt varje kod. När du har skapat momsrapporteringskoderna kan du välja dem i avsnittet **Rapportinställningar** på sidan **Momskoder**. <!---For more information, see [Set up sales tax reporting codes](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-reporting-codes/).-->

### Momskoder för momsrapportering
<a id="sales-tax-codes-for-vat-reporting" class="xliff"></a>

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-codes/).--> Base amounts and tax amounts of sales tax transactions can be aggregated on reporting codes in the VAT statement (XML tags or declaration boxes). You can set this up by associating sales tax reporting codes for different transaction types for sales tax codes on the **Sales tax codes** page. The following table describes the transaction types in the report setup for sales tax codes. The calculation includes transactions for all types of sources except sales tax.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Transaktionstyp</strong></td>
<td><strong>Beskrivning av transaktioner och belopp som ska räknas in i transaktionstypen</strong></td>
</tr>
<tr class="even">
<td><strong>Momspliktig försäljning</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden/</li>
<li>Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Skattefri försäljning</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsskuld</strong></td>
<td>Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Momspliktiga försäljningskreditfakturor</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsbefriad försäljningskreditfaktura</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är export (<strong>Momsriktning</strong> är <strong>Skattefri försäljning</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Moms på försäljningskreditfaktura</strong></td>
<td>Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är lokal (<strong>Momsriktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Skattepliktiga inköp</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Skattefritt inköp</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsfordran</strong></td>
<td>Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Momspliktig inköpskreditfaktura</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsbefriad inköpskreditfaktura</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Inköpet är import (<strong>Momsriktning</strong> är <strong>Skattefritt inköp</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Moms på inköpskreditfaktura</strong></td>
<td>Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Momsriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Skattepliktig import</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Momsriktningen</strong> är <strong>Importavgift</strong></li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Motbokning momspliktig import</strong></td>
<td>Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momspliktig importkreditfaktura</strong></td>
<td>Summan av <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
e<li><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Motbokad momspliktig importkreditfaktura</strong></td>
<td>Återförd summa för <strong>Momsunderlagsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Momsriktningen är <strong>Importavgift</strong>.</li>
d<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Importavgift</strong></td>
<td>Summan av <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Motbokning av importavgift</strong></td>
<td>Återförd summa för <strong>Momsbelopp</strong> för de momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Momsriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbelopp</strong> eller <strong>Momsbelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> För tabellen ovan förutsätts att följande kriterier uppfylls: 
> -   Momsunderlagsbeloppet är ett transaktionsbelopp från fältet **Ursprung i redovisningsvaluta**.
> -   Momsbeloppet är ett transaktionsbelopp från fältet **Faktiskt momsbelopp i redovisningsvaluta**.

### Konfigurera ER-modell och format för rapporten
<a id="configure-the-er-model-and-format-for-the-report" class="xliff"></a>

Du kan använda elektronisk rapportering (ER) för att konfigurera utdrag och rapporter, samt för att exportera datavarierande elektroniska format utan att ändra X++ -koden. För mer information:

-   [Översikt över elektronisk rapportering](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting)
-   [Hämta konfigurationer för elektronisk rapportering från Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)
-   [Lokaliseringskrav – Skapa en GER-konfiguration](/dynamics365/unified-operations/dev-itpro/analytics/electronic-reporting-configuration)

## Landspecifika resurser för momsrapporter
<a id="countryspecific-resources-for-vat-statements" class="xliff"></a>
Momsrapporten för varje land måste uppfylla kraven i landets lagstiftning. Det finns fördefinierade allmänna modeller och format för momsrapporter för de länder som anges i tabellen nedan.


| Land        | Ytterligare information                                                          |
|----------------|---------------------------------------------------------------------------------|
| Österrike        |  [Detaljerad momsinformation för Österrike](emea-aut-vat-statement-details.md)         |
| Belgien        |                                                                                 |
| Tjeckien |  [Detaljerad momsrapport för Tjeckien](emea-cze-vat-statement-details.md)   |
| Estland        |  [Detaljerad momsinformation för Estland](emea-est-vat-statement-details.md) |
| Finland        |                                                                                 |
| Tyskland        |                                                                                 |
| Italien          | [Detaljerad momsinformation för Italien](emea-ita-vat-statements-details.md)            |
| Lettland         | [Detaljerad momsinformation för Lettland](emea-lva-vat-statement-details.md)           |
| Litauen      | [Detaljerad momsinformation för Litauen](emea-ltu-vat-statement-details.md)         |
| Nederländerna    |                                                                                 |
| Sverige         |                                                                                 |






