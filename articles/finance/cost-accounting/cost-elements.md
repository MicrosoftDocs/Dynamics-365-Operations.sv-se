---
title: Dimensioner för kostnadselement
description: Som en av kärnapelarna i kostnadsredovisning, används kostnadselementen för att kategorisera och spåra var kostnaderna flödar till.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e67ce047d08af6d34090ee4e1dc379dd16ecce07
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448101"
---
# <a name="cost-element-dimensions"></a>Dimensioner för kostnadselement

[!include [banner](../includes/banner.md)]

Som en av kärnapelarna i kostnadsredovisning, används kostnadselementen för att kategorisera och spåra var kostnaderna flödar till. 

Ett kostnadselement motsvarar en kostnadsrelevant artikel i kontoplanen. I princip kan det vara valfri typ av element på den lägsta nivån i en verksamhet som kostnader kan flöda till. Kostnadselement som ett begrepp sträcker sig från redovisningskonton till alla kostnadsrelevanta resurser. För närvarande stöder kostnadsredovisning huvudbokskonton.

## <a name="two-types-of-cost-elements"></a>Två typer av kostnadselement
Det finns två typer av kostnadselement: primära kostnadselement och sekundära kostnadselement. Följande tabell beskriver skillnaden mellan de två typerna.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Primära kostnadselement</strong></td>
<td><strong>Sekundära kostnadselement</strong></td>
</tr>
<tr class="even">
<td>De primära kostnadselementen representerar flödet av kostnader från ekonomisk redovisning till kostnadsredovisning. Kostnadselementstrukturen motsvarar resultaträkningsstrukturen i huvudboken, där ett kostnadselement kan motsvara en huvudkonto. Alla rubrikkontona kan inte nödvändigtvis representeras som kostnadselement beroende på företagets behov. Exempel på primära kostnadselement inkluderar:
<ul>
<li>Kostnader för sålda varor (KSV)</li>
<li>Indirekta materialkostnader</li>
<li>Personalkostnader</li>
<li>Energikostnader</li>
</ul></td>
<td>De sekundära kostnadselementen representerar flödet av kostnader internt eftersom dessa kostnader skapas och används bara i kostnadsredovisning. De används för att säkerställa att kostnadskällan kan spåras. Dessa kostnadelement används i kostnadsallokeringar och beräkningar av indirekta kostnader. Exempel på sekundära kostnadselement inkluderar:
<ul>
<li>Tillverkningskostnader</li>
<li>Tillverknings-, material- och marknadsföringsomkostnader</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Kostnadselement och+ dimensionsmedlemmar för kostnadselement.
Kostnadselement kallas *kostnadselementdimensioner*. De enskilda dimensionsvärdena kallas *dimensionsmedlemmar för kostnadselement*. Du kan till exempel ha en amerikansk kontoplanstruktur (COA) som utgör grunden för din lagstadgade rapportering. Detta COA används som kostnadselementdimension. Kontona som är primära kostnadselement, representeras som dimensionsmedlemmar för kostnadselement i kostnadsredovisning. Följande exempel visar en skärmdump av huvudkonton som kostnadselementdimensionen med dess faktiska huvudkonton som dimensionsmedlem för kostnadselement. 

[![Skärmbild av huvudkonton som dimension för kostnadselement](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>Importera dimensionsmedlemmar för kostnadselement via datakopplingar
För att underlätta inställningarna av dimensionsmedlemmar för kostnadselement i kostnadsredovisning kan du använda datakopplingar, som antingen är föruppbyggda eller personligt anpassade för att hämta de primära kostnadselementen från ett eller flera källsystem.

## <a name="implementation-considerations"></a>Implementeringöverväganden
Eftersom kostnadselement representerar den lägsta nivån i kostnadsdetaljer, ska du se till att alla kostnadselement som är nödvändiga för att göra chefs rapporteringen inkluderas när du implementerar kostnadselementstrukturen. Det kan vara en utmaning att hitta ett lämpligt antal kostnadselement för kostnadskontroll. Att ha tusentals kostnadselement kan göra det svårt att kontrollera varje kostnadselement. Alternativt kan du gruppera kostnadselement och hantera kostnadskontroll på en samlad nivå.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]