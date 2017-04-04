---
title: "Momsrapportering för Europa"
description: "Det här avsnittet innehåller allmän information om inställning och skapande av programsatsen moms (VAT) för vissa länder."
author: ShylaThompson
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266844
ms.assetid: 06798e29-6140-489e-9b4e-66b45b26be2b
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 84a639b25c64821e00ca4397f42f69298953e599
ms.lasthandoff: 03/31/2017


---

# <a name="vat-reporting-for-europe"></a>Momsrapportering för Europa

Det här avsnittet innehåller allmän information om inställning och skapande av programsatsen moms (VAT) för vissa länder.

Det här avsnittet finns en allmän metod för inställning och skapande av momsrapporten. Den här metoden är vanligt att användare i juridiska personer i följande länder/regioner:

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

## <a name="vat-statement-overview"></a>MOMS utdrag – översikt
Momsrapporten utifrån skatt transaktionens belopp. Generera en momsrapport som ingår i betalningsprocessen moms som implementeras med funktionen inlösta och bokföra moms. Den här funktionen beräknar moms som ska betalas för en given period. Kvittningsberäkningarna innefattar den bokförda momsen för kvittningsperioden för skattetransaktionerna. Processen för att beräkna data för en momsrapport som baseras på förhållandet mellan momskoder och momsrapporteringskoder, där moms rapporteringskoder matchar moms utdrag rutor (eller taggar i XML). För varje momskod moms rapporteringskoder ska ställa in för varje typ av transaktion, till exempel Skattepliktig försäljning skattepliktiga inköp beskattningsbar import. Följande typ av transaktioner som beskrivs i den [momskoder för momsrapportering](#Sales tax codes for VAT reporting) längre fram i det här avsnittet.

En specifik rapportlayout för varje momsrapporteringskod, bör fastställas. Momskoder samtidigt, är länkade till en viss momsmyndighet via Momskvittningsperioder. En specifik rapportlayout för varje momsmyndighet bör fastställas. Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en skattemyndighet i Momskvittningsperioder för momskoden markeras i rapportinställningar för momskoden. En momstransaktion skapas vid bokföring av en order eller en journal innehåller en momskod, moms källa, momsriktningen och Transaktionsbelopp (Momsbasbeloppet och momsbelopp i redovisningsvaluta, moms, valuta och transaktionsvalutan). Baserat på kombinationen av skatt transaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder för momskoder. Följande bild visar förhållandet data.

![diagram](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a>Utdraget momsinst
Om du vill generera en momsrapport måste du konfigurera följande.

### <a name="sales-tax-authorities-for-vat-reporting"></a>Momsmyndigheter för momsrapportering

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-authorities/). -->
Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten. I den **skattemyndigheter** sidan i den **allmänna** väljer en **rapportlayout**. Den här layouten används när du ställer in Momsrapporteringskoder.

### <a name="sales-tax-reporting-codes"></a>Momsrapporteringskoder

Rapporteringskoder moms är rutan koder moms utdrag eller tagg namn i XML-format. Koderna används för att sammanställa och förbereda beloppen i rapporten. Namnen på belopp som resultatet kommer att användas när du konfigurerar de elektroniska rapporteringsformulär av momsrapporten. Du kan skapa och hantera momsrapporteringskoder på de **momsrapporteringskoder** sida. Du måste tilldela en rapportlayout varje kod. När du har skapat den momsrapporteringskoder kan du koderna i den **inställningar** avsnitt på den **momskoder** sida. <!---For more information, see [Set up sales tax reporting codes](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-reporting-codes/) and [Sales tax reporting codes page (Field descriptions)](http://ax.help.dynamics.com/en/wiki/sales-tax-reporting-codes-page-field-descriptions/).-->

### <a name="sales-tax-codes-for-vat-reporting"></a>Momskoder för momsrapportering

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-codes/).-->Basera belopp och momsbelopp mängder transaktioner kan aggregeras moms på rapporteringskoder i momsrapporten (XML-taggar eller deklarationen rutor). Du kan konfigurera detta genom att associera momsrapporteringskoder för olika transaktionstyper för momskoder på de **momskoder** sida. Följande tabell beskriver transaktionstyperna i rapportinställningar för momskoder. Beräkningen innefattar transaktioner för alla typer av källor utom moms.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Transaction type</strong></td>
<td><strong>Beskrivning av transaktioner och beloppen räknas på transaktionstypen</strong></td>
</tr>
<tr class="even">
<td><strong>Skattepliktig försäljning</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden /</li>
<li>Försäljningen är lokalt (<strong>skatt riktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Skattefri försäljning</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Försäljningen är export (<strong>skatt riktning</strong> är <strong>Skattefri försäljning</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Sales tax payable</strong></td>
<td>Summan av <strong>skatt belopp</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Försäljningen är lokalt (<strong>skatt riktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Taxable sales credit note</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Försäljningen är lokalt (<strong>skatt riktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Fax Momsbefriad försäljningskreditfaktura</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Försäljningen är export (<strong>skatt riktning</strong> är <strong>Skattefri försäljning</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Sales tax on sales credit note</strong></td>
<td>Summan av <strong>skatt belopp</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Försäljningen är lokalt (<strong>skatt riktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxable purchases</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Inköpet är lokalt (<strong>skatt riktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Tax-free purchase</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Inköpet är import (<strong>skatt riktning</strong> är <strong>Skattefritt inköp</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Sales tax receivable</strong></td>
<td>Summan av <strong>skatt belopp</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Inköpet är lokalt (<strong>skatt riktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Taxable purchase credit note</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Inköpet är lokalt (<strong>skatt riktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Tax exempt purchase credit note</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Inköpet är import (<strong>skatt riktning</strong> är <strong>Skattefritt inköp</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Sales tax on purchase credit note</strong></td>
<td>Summan av <strong>skatt belopp</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Inköpet är lokalt (<strong>skatt riktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxable import</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li><strong>Skatt riktning</strong> är <strong>importavgift</strong></li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Offset taxable import</strong></td>
<td>Återförda summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li><strong>Skatt riktning</strong> är <strong>importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxable import credit note</strong></td>
<td>Summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
e<li><strong>Skatt riktning</strong> är <strong>importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Offset taxable import credit note</strong></td>
<td>Återförda summan av <strong>grundbelopp skatt</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li>Momsriktning är <strong>importavgift</strong>.</li>
d<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Use tax</strong></td>
<td>Summan av <strong>skatt belopp</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li><strong>Skatt riktning</strong> är <strong>importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Offset use tax</strong></td>
<td>Återförda summan av <strong>skatt belopp</strong> av momstransaktionerna som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet finns i den valda perioden.</li>
<li><strong>Skatt riktning</strong> är <strong>importavgift</strong>.</li>
<li>Transaktionens <strong>Momsbasbeloppet</strong> eller <strong>momsbelopp</strong>&gt; 0.</li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Tabellen ovan förutsätts att följande kriterier uppfylls: 
> -   Grundläggande skattebeloppet är ett transaktionsbelopp från den **ursprung i redovisningsvalutan** fält.
> -   Momsbeloppet är en övergång från den **Faktiskt momsbelopp i redovisningsvaluta** fält.

### <a name="configure-the-er-model-and-format-for-the-report"></a>Konfigurera modell för ER och format för rapporten

Du kan använda elektronisk rapportering (ER) konfigurerar rapport och rapporter och exportera data olika elektroniska format utan att ändra X ++-kod. Mer information:

-   [Översikt över elektronisk rapportering](/dynamics365/operations/dev-itpro/dev-itpro/analytics/general-electronic-reporting)
-   [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)
-   [Krav för lokalisering – skapa en konfiguration för Tyskland](/dynamics365/operations/dev-itpro/analytics/electronic-reporting-configuration)

## <a name="countryspecific-resources-for-vat-statements"></a>Countryspecific resurser för momsrapporter
Momsrapporten för varje land skall uppfylla kraven i landets lagstiftning. Det finns fördefinierade allmänna modeller och format för momsrapporter för länder som anges i tabellen nedan.


| Land        | Ytterligare information                                                          |
|----------------|---------------------------------------------------------------------------------|
| Österrike        |  [Utdraget momsinformation för Österrike](emea-aut-vat-statement-details.md)         |
| Belgien        |                                                                                 |
| Tjeckien |  [Utdraget momsinformation för Tjeckien](emea-cze-vat-statement-details.md)   |
| Estland        |  [Utdraget momsinformation för Estland](emea-est-vat-statement-details.md) |
| Finland        |                                                                                 |
| Tyskland        |                                                                                 |
| Italien          | [Utdraget momsinformation för Italien](emea-ita-vat-statements-details.md)            |
| Lettland         | [Utdraget momsinformation för Lettland](emea-lva-vat-statement-details.md)           |
| Litauen      | [Utdraget momsinformation för Litauen](emea-ltu-vat-statement-details.md)         |
| Nederländerna    |                                                                                 |
| Sverige         |                                                                                 |




