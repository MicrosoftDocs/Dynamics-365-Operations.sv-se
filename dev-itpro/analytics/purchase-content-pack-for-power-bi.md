---
title: "Analys av inköpsutgift – Power BI-innehåll"
description: "Det här avsnittet beskriver vad som ingår i innehållspaketet Analys av inköpsutgift för Microsoft Power BI. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ad0ee95113d05710cccc1a5e9d215b38244c2047
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Analys av inköpsutgift – Power BI-innehåll

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver vad som ingår i innehållspaketet Analys av inköpsutgift för Microsoft Power BI. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

<a name="overview"></a>Översikt
--------

Innehållspaketet Analys av inköpsutgifter för Microsoft Power BI skapades för inköpsansvariga och chefer som ansvarar för budgetar. Det är utformat för att hjälpa dem hålla ett öga på utgifter för inköp. Det använder inköpstransaktionsdata från Microsoft Dynamics 365 for Operations och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt. Rapporter visar ändringar i inköpsutgifter över tiden. De kan därför användas för att notifiera chefer om positiva och negativa utgiftstrender för enskilda leverantörer och produkter. Diagram visar inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper. Kategori och regionala chefer kan finna det praktiskt att använda diagrammen för att identifiera ändringar i utgiftsbeteende. Innehållspaketet låter inköpsansvarig och inköpschefer som ansvarar för budgetar analysera inköpsutgifter på följande sätt:

-   Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)
-   Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)

## <a name="accessing-the-content-pack"></a>Åtkomst till innehållspaketet
Innehållspaket för analys av inköpsutgift publiceras som en implementeringstillgång i Microsoft Dynamics Lifecycle Services (LCS) och kan nås från Microsoft Dynamics 365 for Operations. Mer information om hur du når och öppnar Power BI-rapporter finns i [Power BI-innehåll i LCS från Microsoft och din partner](power-bi-content-microsoft-partners.md).
Anmärkning: KB 4011327 är ett krav för hans Power BI-innehåll. När du loggar in till Lifecycle Services får du åtkomst till KB här: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="metrics-that-are-included-in-the-content-pack"></a>Mått som ingår i innehållspaketet
Innehållspaketet för analys av inköpsutgift innehåller en rapport som består av en uppsättning mått. De här måtten visas som diagram, paneler och tabeller. Nedanstående tabell ger en översikt över de visualiseringar som används i innehållspaketet.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Rapportsida</th>
<th>Diagram</th>
<th>Paneler</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Inköp efter leverantör</td>
<td><ul>
<li>De 10 främsta leverantörerna per inköp (stapeldiagram)</li>
<li>Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)</li>
<li>Inköp per leverantörsgrupp / land / namn (stapeldiagram)</li>
<li>Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)</li>
</ul></td>
<td><ul>
<li>Totalt inköp</li>
<li>YOY inköpstillväxt</li>
<li>Totalt antal leverantörer</li>
<li>Totalt antal aktiva leverantörer</li>
</ul></td>
</tr>
<tr class="even">
<td>Inköp efter produkt</td>
<td><ul>
<li>Inköp per anskaffningskategori / produktnamn (stapeldiagram)</li>
<li>Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)</li>
<li>De 10 främsta produkterna efter inköp (stapeldiagram)</li>
</ul></td>
<td><ul>
<li>Totalt antal produkter</li>
<li>Totalt antal aktiva produkters procentuella andel av totalt antal produkter</li>
<li>Antal produkter som står för 80 % av inköp</li>
</ul></td>
</tr>
<tr class="odd">
<td>Inköp efter period*</td>
<td><ul>
<li>Inköp per månad / dag (stapeldiagram)</li>
<li>Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)</li>
<li>Totala YOY inköpstillväxt (stapeldiagram)</li>
<li>Anskaffningsutdrag (matris)</li>
</ul></td>
<td><ul>
<li>YOY inköpstillväxt</li>
<li>YOY inköpstillväxt %</li>
</ul></td>
</tr>
<tr class="even">
<td>Inköp per leverantörsplats</td>
<td><ul>
<li>Inköp per ort</li>
<li>Inköp YOY tillväxt %</li>
<li>Inköp per land</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analys av inköpsutgift per tid</td>
<td><ul>
<li>Inköp innevarande år per månad / dag (linjediagram)</li>
<li>Inköp innevarande år och föregående år (linje- och stapeldiagram)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analys av inköpsutgift per leverantör</td>
<td><ul>
<li>Topp 10 leverantörers inköp % av inköp (tratt)</li>
<li>Topp 10 leverantörer med ökad utgifts YOY</li>
<li>Topp 10 leverantörer med minskad utgifts YOY</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* Inköp detta och förra året och tillväxt per anskaffningskategori.

## <a name="data-model-and-entities"></a>Datamodell och enheter
Dynamics 365 for Operations-data används för rapporten i innehållspaketet för analys av inköpsutgift. Informationen visas som sammansatta mått som mellanlagras i enhetsarkivet, som är en Microsoft SQL-databas som är optimerad för analys. Mer information om enhetsbutiken finns i blogginlägget [Power BI-integration med enhetslagring i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i Purchase Cube i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3. För att förbereda kubens sammanlagda mått i enhetslagringen måste du göra dem driftfärdiga. Mer information finns i proceduren för mellanlagring av sammanlagda mått i enhetsbutiken i blogginlägget [Power BI-integration med enhetsbutik i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållspaketet.

| Enhet        | Sammanlagda huvudmått | Datakälla för Dynamics 365 for Operations | Fält              | beskrivning                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Fakturarader | Inköp                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Belopp i redovisningsvaluta |

Följande tabell visar viktiga mått som beräknas i innehållspaketet från fakturaradenheten.

| Mått               | Beräkning                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Inköp innevarande år | Inköp innevarande år = SUM('Fakturarader'\[Inköp\])                                            |
| Inköp i fjol    | Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\])) |
| YOY inköpstillväxt   | YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]                            |

Följande huvuddimensioner i innehållspaketet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och djupare analysinsikter.

| Enhet                 | Exempel på attribut                                |
|------------------------|-------------------------------------------------------|
| Leverantörer                | Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn |
| Produkter               | Produktnummer, produktnamn, artikelgruppsnamn        |
| Anskaffningskategorier | Anskaffningskategori, anskaffningskategorinamn      |
| Juridiska personer         | Namn på juridisk person                                     |
| Datum                  | Datum, Förskjutning för år                                    |

Som standard visar innehållspaketet data för det aktuella kalenderåret. Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet. Du kan också ändra filtret för företaget.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)





