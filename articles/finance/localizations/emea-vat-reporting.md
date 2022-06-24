---
title: Momsrapporter för Europa
description: Den här artikeln innehåller allmän information om inställning och skapande av mervärdesskattutdrag (skatt) för vissa europeiska länder.
author: ShylaThompson
ms.date: 03/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e25b01133bfaa84186faf82c80f24a119b40ac2e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856543"
---
# <a name="vat-reporting-for-europe"></a>Momsrapporter för Europa

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller allmän information om inställning och skapande av mervärdesskattutdrag (skatt) för vissa europeiska länder.

Den här artikeln innehåller en allmän metod för inställning och skapande av momsrapporten. Den här metoden används ofta av användare i juridiska personer i följande länder/regioner:

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

> [!IMPORTANT]
> Funktioner som beskrivs i den här artikeln för Österrike, Tjeckien, Tyskland, Nederländerna och Sverige avskrivs. Mer information finns i beskrivningen av [borttagna eller gamla funktioner](../get-started/removed-deprecated-features-finance.md).
> Med länkarna i följande tabell kan du lära dig mer om den nya utformningen av momsdeklarationer i motsvarande länder.
> 
>
> | Land        | Ytterligare information                                                          |
> |----------------|---------------------------------------------------------------------------------|
> | Österrike        | [Momsdeklaration för (Österrike)](emea-aut-vat-declaration-austria.md)       |                                                                           
> | Tjeckien | [Momsdeklaration (Tjeckien)](emea-cze-vat-declaration-tax-declaration-model.md) |
> | Danmark        | [Momsdeklaration (Danmark)](emea-dnk-vat-declaration-denmark.md)         |
> | Frankrike         | [Momsdeklaration (Frankrike)](emea-fra-vat-declaration-preview-france.md)       |
> | Tyskland        | [Momsdeklaration för (Tyskland)](emea-deu-vat-declaration-germany.md)           |
> | Nederländerna    | [Momsdeklaration (Nederländerna)](emea-nl-vat-declaration-netherlands.md)    |
> | Norge         | [Momsretur med direkt överföring till Altinn](emea-nor-vat-return.md) |
> | Spanien          | [Momsdeklaration (Spanien)](emea-esp-vat-declaration-spain.md)              |
> | Sverige         | [Momsdeklaration (Sverige)](emea-swe-vat-declaration-sweden.md)          |
> | Schweiz    | [Momsdeklaration (Schweiz)](emea-che-vat-declaration-switzerland.md) |
> | Storbritannien             | [Förbered för integration med MRD för moms](emea-gbr-mtd-vat-integration.md) |

## <a name="vat-statement-overview"></a>Översikt över momsrapport
Skatteutdraget baseras på beloppen i momstransaktionerna. Att skapa ett momsrapport ingår i betalningsprocessen för moms, som implementeras med funktionen Kvitta och bokföra moms. Den här funktionen beräknar momsen som ska betalas för en given period. Kvittningsberäkningen innehåller bokförd moms för den valda kvittningsperioden för momstransaktionen. Processen för att beräkna data för en momsrapport baseras på förhållandet mellan momskoder och momsrapporteringskoder, där momsrapporteringskoderna matchar rutorna för momsrapporter (eller taggar i XML). För varje momskod bör momsrapporteringskoder ställas in för varje transaktionstyp, till exempel skattepliktig försäljning, skattepliktiga inköp och skattepliktig import. Följande typ av transaktioner beskrivs i avsnittet Momskoder för momsrapportering längre fram i den här artikeln.

En specifik rapportlayout för varje momsrapporteringskod bör fastställas. Momskoder är samtidigt länkade till en viss momsmyndighet via momskvittningsperioder. En specifik rapportlayout för varje momsmyndighet bör fastställas. Därför kan endast momsrapporteringskoder med samma rapportlayout som har ställts in för en momsmyndighet i momskvittningsperioder för momskoden markeras i rapportinställningarna för momskoden. En momstransaktion skapas vid bokföring av en order eller en journal, innehåller en momskod, momskälla, momsriktning och transaktionsbelopp (momsbasbelopp och momsbelopp i redovisningsvaluta, momsvaluta och transaktionsvaluta). Baserat på kombinationen av momstransaktionsattribut utgör transaktionsbeloppen totalbelopp för momsrapporteringskoder som angetts för momskoder. Illustrationen som följer visar datarelationen.

![diagram.](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a>Inställningar för momsrapport
Om du vill skapa en momsrapport måste du konfigurera följande:

### <a name="sales-tax-authorities-for-vat-reporting"></a>Momsmyndigheter för momsrapportering

Innan du kan ställa in momsrapporteringskoder måste du välja rätt rapportlayout för momsmyndigheten. På sidan **Momsmyndigheter**, i avsnittet **Allmänt**, väljer du en **Rapportlayout**. Den här layouten används när du ställer in momsrapporteringskoder.

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a>Momsrapporteringskoder

Momsrapporteringskoder är rutkoder i momsrapporten eller taggnamn i XML-format. Koderna används för att sammanställa och förbereda beloppen för rapporten. Namnen på resulterande belopp används när du konfigurerar det elektroniska rapporteringsformatet för momsrapporten. Du kan skapa och hantera momsrapporteringskoder på sidan **Momsrapporteringskoder**. Du måste tilldela en rapportlayout åt varje kod. När du har skapat momsrapporteringskoderna kan du välja dem i avsnittet **Rapportinställningar** på sidan **Momskoder**. <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a>Momskoder för momsrapportering

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).-->  Basbelopp och momsbelopp för momstransaktioner kan sammanställas baserade på rapporteringskoder i momsrapporten (XML-taggar eller deklarationsrutor). Du kan konfigurera detta genom att associera momsrapporteringskoder för olika transaktionstyper för momskoder på sidan <strong>Momskoder</strong>. Följande tabell beskriver transaktionstyperna i rapportinställningarna för momskoder. Beräkningen innefattar transaktioner för alla typer av källor utom moms.

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
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden/</li>
<li>Försäljningen är lokal (<strong>Skatteriktning</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Skattefri försäljning</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är export (<strong>Skatteriktning</strong> är <strong>Skattefri försäljning</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsskuld</strong></td>
<td>Summan av <strong>Skattebeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är lokal (<strong>Skatteriktningen</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Momspliktiga försäljningskreditfakturor</strong></td>
<td>Summan av <strong>Skatteunderlagsbeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är lokal (<strong>Skatteriktningen</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsbefriad försäljningskreditfaktura</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är export (<strong>Skatteriktningen</strong> är <strong>Skattefri försäljning</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Moms på försäljningskreditfaktura</strong></td>
<td>Summan av <strong>Skattebeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är lokal (<strong>Skatteriktningen</strong> är <strong>Momsskuld</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Skattepliktiga inköp</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Skatteriktningen</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Skattefritt inköp</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Inköpet är import (<strong>Skatteriktningen</strong> är <strong>Skattefritt inköp</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsfordran</strong></td>
<td>Summan av <strong>Skattebeloppen</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Skatteriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Momspliktig inköpskreditfaktura</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Skatteriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momsbefriad inköpskreditfaktura</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Inköpet är import (<strong>Skatteriktning</strong> är <strong>Skattefritt inköp</strong>).</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Moms på inköpskreditfaktura</strong></td>
<td>Summan av <strong>Skattebelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Försäljningen är inhemsk (<strong>Skatteriktning</strong> är <strong>Momsfordran</strong>).</li>
<li>Transaktionens <strong>Skattbasbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Skattepliktig import</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Skatteriktningen</strong> är <strong>Importavgift</strong></li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Motbokning momspliktig import</strong></td>
<td>Återförd summa för <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Skattbasbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Momspliktig importkreditfaktura</strong></td>
<td>Summan av <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
e<li><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Motbokad momspliktig importkreditfaktura</strong></td>
<td>Återförd summa för <strong>Skatteunderlagsbelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li>Skatteriktningen är <strong>Importavgift</strong>.</li>
d<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &lt; 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Importavgift</strong></td>
<td>Summan av <strong>Skattebelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Motbokning av importavgift</strong></td>
<td>Återförd summa för <strong>Skattebelopp</strong> för de skattetransaktioner som uppfyller följande villkor:
<ul>
<li>Transaktionsdatumet ligger i den valda perioden.</li>
<li><strong>Skatteriktningen</strong> är <strong>Importavgift</strong>.</li>
<li>Transaktionens <strong>Skatteunderlagsbelopp</strong> eller <strong>Skattebelopp</strong> &gt; 0.</li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> För tabellen ovan förutsätts att följande kriterier uppfylls: 
> -   Skatteunderlagsbeloppet är ett transaktionsbelopp från fältet **Ursprung i redovisningsvaluta**.
> -   Skattebeloppet är ett transaktionsbelopp från fältet **Faktiskt skattebelopp i redovisningsvaluta**.

### <a name="configure-the-er-model-and-format-for-the-report"></a>Konfigurera ER-modell och format för rapporten

Du kan använda elektronisk rapportering (ER) för att konfigurera utdrag och rapporter, samt för att exportera datavarierande elektroniska format utan att ändra X++ -koden. För mer information:

-   [Översikt över elektronisk rapportering](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)
-   [Hämta konfigurationer för elektronisk rapportering från Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [Lokaliseringskrav – Skapa en GER-konfiguration](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a>Landspecifika resurser för momsrapporter
Momsrapporten för varje land måste uppfylla kraven i landets lagstiftning. Det finns fördefinierade allmänna modeller och format för momsrapporter för de länder som anges i tabellen nedan.


| Land        | Ytterligare information                                                          |
|----------------|---------------------------------------------------------------------------------|
| Österrike        | [Detaljerad momsinformation för Österrike](emea-aut-vat-statement-details.md)         |
| Belgien        |                                                                                 |
| Tjeckien | [Momsutdrag för Tjeckien](emea-cze-vat-statement-details.md)   |
| Estland        | [Detaljerad momsinformation för Estland](emea-est-vat-statement-details.md) |
| Finland        | [Momsrapport för Finland](emea-fin-sales-tax-payment-report-finland.md)          |
| Tyskland        | [Momsdeklaration för Tyskland](emea-de-vat-declaration.md)                       |
| Italien          | [Detaljerad momsinformation för Italien](emea-ita-vat-statements-details.md)            |
| Lettland         | [Detaljerad momsinformation för Lettland](emea-lva-vat-statement-details.md)           |
| Litauen      | [Detaljerad momsinformation för Litauen](emea-ltu-vat-statement-details.md)         |
| Nederländerna    | [Momsdeklaration för Nederländerna](emea-nl-vat-declaration.md)           |
| Sverige         | [Momsrapport för Sverige](emea-swe-sales-tax-payment-report-sweden.md)          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
