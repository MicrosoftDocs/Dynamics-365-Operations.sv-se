---
title: "Analys av inköpsutgift – Power BI-innehåll"
description: "Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet."
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: 07b6f433a8355d7f9ed6dce8e26f78d38a86a713
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a>Analys av inköpsutgift – Power BI-innehåll

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i Microsoft Power BI-innehållet **Inköps- och utgiftsanalys**. Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla ett öga på inköpsutgifter. Chefer kan analysera inköpsutgifter på följande sätt:

-   Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)
-   Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)

Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt. Rapporter visar ändringar i inköpsutgifter över tiden. Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter. Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper. Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehållet **Analys av inköpsutgift** visas på sidan **Analys av inköp och utgifter** (**Anskaffning och källa** > **Förfrågningar och rapporter** > **Analys av köpprestanda** > **Analys av inköp och utgifter**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mått som ingår i Power BI-innehållet
Power BI-innehållet **Inköps- och utgiftsanalys** innehåller en rapport som består av en uppsättning mått. De här måtten visas som diagram, paneler och tabeller. Nedanstående tabell ger en översikt över visualiseringarna.

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
Följande data används för att fylla i rapportsidorna i Power-Bi-innehållet **Inköps- och utgiftsanalys**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

De sammanlagda måtten i det här innehållet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3. För att förbereda kubens sammanlagda mått i enhetslagringen måste du göra dem driftfärdiga. Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Översikt över Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md). Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.

| Enhet        | Sammanlagda huvudmått | Datakälla                                 | Fält              | beskrivning                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Fakturarader | Inköp                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Belopp i redovisningsvalutan. |

Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.

| Mått               | Beräkning                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Inköp innevarande år | Inköp innevarande år = SUM('Fakturarader'\[Inköp\])                                            |
| Inköp i fjol    | Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\])) |
| YOY inköpstillväxt   | YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]                            |

Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.

| Enhet                 | Exempel på attribut                                |
|------------------------|-------------------------------------------------------|
| Leverantörer                | Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn |
| Produkter               | Produktnummer, produktnamn, artikelgruppsnamn        |
| Anskaffningskategorier | Anskaffningskategori, anskaffningskategorinamn      |
| Juridiska personer         | Namn på juridisk person                                     |
| Datum                  | Datum, Förskjutning för år                                    |

Som standard visar innehållet data för det aktuella kalenderåret. Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet. Du kan också ändra filtret för företaget.

