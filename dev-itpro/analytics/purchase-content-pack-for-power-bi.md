---
title: "Inköp Utgiftsanalyser Power BI-innehåll"
description: "Det här avsnittet beskriver vad som ingår i inköpet spendera analys innehållet för Microsoft Power BI. Det förklaras hur du öppnar rapporter som ingår i paketet innehåll och ger information om datamodellen och enheter som används för att skapa innehåll pack."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Inköp Utgiftsanalyser Power BI-innehåll

Det här avsnittet beskriver vad som ingår i inköpet spendera analys innehållet för Microsoft Power BI. Det förklaras hur du öppnar rapporter som ingår i paketet innehåll och ger information om datamodellen och enheter som används för att skapa innehåll pack.

<a name="overview"></a>Översikt
--------

Köp tillbringar analys innehåll pack för Microsoft Power BI skapades när du köper ansvariga och chefer, som ansvarar för budgetar. Utformad för att hjälpa dem hålla ett öga på utgifter för inköp. Den använder transaktionsdata för inköp från Microsoft Dynamics 365 för operationer och innehåller både en aggregerad vy över hela företaget inköpsbelopp och en uppdelning av inköp utgifter per leverantör och produkt. Rapporter visa ändringar i purchase utgifter över tiden. De kan därför användas för chefer notifieringar om positiva och negativa utgifterna trender för enskilda leverantörer och produkter. Diagram visar inköp utgifter för olika anskaffningskategorier och leverantörsgrupper. Kategori och regionala chefer kan vara praktiskt att använda diagrammen för att identifiera ändringar i utgifter beteende. Content pack vi inköpshanterare och chefer, som ansvarar för budgetar analysera inköp utgifter på följande sätt:

-   Till dags dato köpa (leverantörsgrupp och enskilda leverantörer anskaffningskategori och enskilda produkter och leverantör)
-   År över år inköp byte (grupp och upphandling leverantörskategori)

## <a name="accessing-the-content-pack"></a>Åtkomst till content pack
Köp tillbringar innehåll pack har publicerats som en tillgång i Microsoft Dynamics Lifecycle Services (LCS) för genomförandet och kan nås från Microsoft Dynamics 365 för analys. Mer information om hur du ska öppna Power BI-rapporter finns i [Power BI innehåll från Microsoft och partner LCS](power-bi-content-microsoft-partners.md).

## <a name="metrics-that-are-included-in-the-content-pack"></a>Mått som ingår i paketet innehåll
Köp tillbringar analys innehållet inkluderar en rapport som består av en uppsättning mått. De här måtten är visualized som, brickor, t.ex. Nedan visas en översikt över de visuella effekterna i innehållet.

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
<th>Sida vid sida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Inköp per leverantör</td>
<td><ul>
<li>De 10 främsta leverantörerna per inköp (stapeldiagram)</li>
<li>Totalt inköp enligt leverantör gruppen / land / namn (cirkeldiagram)</li>
<li>Inköp per leverantör gruppen / land / namn (stapeldiagram)</li>
<li>Genomsnittlig inköp enligt leverantör gruppen / land / namn (stapeldiagram)</li>
</ul></td>
<td><ul>
<li>Totalt inköp</li>
<li>YOY inköp tillväxt</li>
<li>Totalt antal leverantörer</li>
<li>Totalt antal aktiva leverantörer</li>
</ul></td>
</tr>
<tr class="even">
<td>Inköp per produkt</td>
<td><ul>
<li>Inköp per anskaffningskategori / product name (stapeldiagram)</li>
<li>Totalt inköp per anskaffningskategori / product name (cirkeldiagram)</li>
<li>Topp 10-produkter per inköp (stapeldiagram)</li>
</ul></td>
<td><ul>
<li>Totalt antal produkter</li>
<li>Procentandel av totalt antal aktiva produkter av totalt antal produkter</li>
<li>Antal produkter redovisa inköp 80 %</li>
</ul></td>
</tr>
<tr class="odd">
<td>Inköp av perioden *</td>
<td><ul>
<li>Inköp per månad / dag (stapeldiagram)</li>
<li>Ackumulerade YOY Inköpsvarians (vattenfallet diagram)</li>
<li>Totala inköp YOY tillväxt (stapeldiagram)</li>
<li>Inköp-uttryck (matris)</li>
</ul></td>
<td><ul>
<li>YOY inköp tillväxt</li>
<li>YOY inköp growth %</li>
</ul></td>
</tr>
<tr class="even">
<td>Inköp efter leverantör</td>
<td><ul>
<li>Inköp sorterat efter ort</li>
<li>Inköp YOY growth %</li>
<li>Inköp per land</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Inköp utgifter analys per tid</td>
<td><ul>
<li>Inköp innevarande månad / dag (linjediagram)</li>
<li>Köpa innevarande året och föregående år (rad- och diagram)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Utgiftsanalyser inköp per leverantör</td>
<td><ul>
<li>Topp 10 leverantör inköp % av inköp (tratten)</li>
<li>De 10 främsta leverantörerna med ökad YOY utgiftsgräns</li>
<li>De 10 främsta leverantörerna med minskad YOY utgiftsgräns</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\*Inköp i år och förra året och tillväxt per anskaffningskategori

## <a name="data-model-and-entities"></a>Datamodell och enheter
Dynamics 365 för data som används för inköp av rapporten tillbringar innehållet för analys. Informationen visas som sammansatta mått som mellanlagras i arkivet entitet som är en Microsoft SQL-databas som är optimerad för analys. Mer information om enheten arkivet finns på [Power BI integration med Store enhet i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) blogginlägg. Sammansatta måtten i det här innehållet är del av sammansatta mått som var tillgängliga i kuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics 365 för operationer 2012 R3 inköp. För att förbereda kubens aggregerade mått i butiken enheten måste du göra dem kan. Mer information finns i proceduren för mellanlagring av sammansatta mått i enheten butiken i den [Power BI integration med Store enhet i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/) blogginlägg. Följande viktiga aggregerade mätningar är tillgängliga direkt från raderna fakturaentiteten och används som bas för innehållet.

| Enhet        | Sammansatta centrala nyckeltal | Datakälla för Dynamics 365 för operationer | Fält              | beskrivning                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Fakturarader | Inköp                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Belopp i redovisningsvaluta |

Följande tabell visar viktiga mått som beräknas i innehållet från fakturaentiteten rader.

| Mått               | Beräkning                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Inköp-innevarande år | Inköp innevarande år = SUMMA ('Fakturarader'\[inköp\])                                            |
| Köpa förra året    | Inköpsorder = förra året BERÄKNA (SUMMA ('Fakturarader'\[inköp\]), SAMEPERIODLASTYEAR (datum\[datum\])) |
| YOY inköp tillväxt   | Köpa YOY tillväxt = \[innevarande år köpa\] – \[köper förra året\]                            |

Följande används nycklar i content pack dimensionerna som filter för att dela upp sammansatta mått, så att du kan uppnå mer granularitet och analytiska djupare kunskaper.

| Enhet                 | Exempel på attribut                                |
|------------------------|-------------------------------------------------------|
| Leverantörer                | Leverantörsgrupper, leverantörer land eller regioner Leverantörsnamn |
| Produkter               | Produktnummer, produktnamn, grupper-objektnamn        |
| Anskaffningskategorier | Anskaffningskategorin anskaffning kategorinamn      |
| Juridiska personer         | Namn på juridisk person                                     |
| Datum                  | Datum år motbokning                                    |

Som standard visar innehållet data för det aktuella kalenderåret. Du kan dock ändra filtret i avsnittet filter för rapporten. Du kan också ändra filtret för företaget.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)



