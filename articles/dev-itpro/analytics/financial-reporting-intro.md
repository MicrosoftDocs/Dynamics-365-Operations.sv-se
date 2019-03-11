---
title: Ekonomisk rapportering
description: Ekonomisk rapportering för Finance and Operations kan användas av finans- och affärsmän för att skapa, underhålla, distribuera och visa bokslut. Den går utanför traditionella rapporteringsbegränsningar för att hjälpa dig att skapa olika typer av rapporter på ett effektivt sätt.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ae2087cf142fc2670bda3c542b336f12978178a6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "323788"
---
# <a name="financial-reporting"></a>Ekonomisk rapportering

[!include [banner](../includes/banner.md)]

Ekonomisk rapportering för Finance and Operations kan användas av finans- och affärsmän för att skapa, underhålla, distribuera och visa bokslut. Den går utanför traditionella rapporteringsbegränsningar för att hjälpa dig att skapa olika typer av rapporter på ett effektivt sätt.

Ekonomisk rapportering innehåller stöd för dimension. Därför är kontosegment eller dimensioner tillgängliga direkt. Det krävs inga ytterligare verktyg eller konfigurationssteg.

## <a name="financial-reporting-setup"></a>Inställning av ekonomisk rapportering
Sidan **Inställningar för Financial reporting** innehåller en lista över alla ekonomiska dimensioner i systemet. **Redovisning** \> **Redovisningsinställningar** \> **Inställningar för Financial reporting**.

Sidan **Inställningar för Financial reporting** har två avsnitt som avgör vilka data du rapportera om i Financial reporting:

- **Fliken Dimensioner** - Eftersom olika företag använder olika dimensioner och kontostrukturer går det inte att bestämma i vilken ordning användarna vill visa alla ekonomiska dimensioner i rapporter. Den här sidan låter dig ange i vilken ordning du vill att ekonomiska dimensioner ska visas när du skapar och visar en rapport i Financial reporting.
- **Fliken Attribut** låter dig välja om du vill kunna använda **Leverantörer** och **Kunder** som attribut för filtrering och rapportutformning. Rapportering om leverantörer och kunder är bara av vikt om du inte anger flera olika leverantörer eller kunder i en enda verifikation vid bokföring av transaktioner. Val av leveranörer och/eller kunder tillför ytterligare tid till integrationen.

## <a name="financial-reporting-components"></a>Komponenter för ekonomisk rapportering
Följande komponenter för ekonomisk rapportering gör det lättare att skapa, visa och tidsplanera rapporter.

| Komponent        | Funktioner | Ytterligare information |
|------------------|-----------|------------------------|
| Report Designer  | Skapa rapportbyggnadsblock som kan kombineras för att definiera och skapa en rapport. Rapportguiden leder mindre erfarna användare genom designprocessen. Avancerade användare kan skapa nya rapportbyggnadsblock eller ändra befintliga byggnadsblock så att de uppfyller deras krav. | |
| Rapportscheman | Tidsplanera en enstaka rapport eller en rapportgrupp så att den skapas regelbundet. | [Skapa ekonomisk rapport](generate-financial-report.md) |

## <a name="features"></a>Funktioner
<table>
<thead>
<tr>
<th>Funktion</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Rapportdesignflexibilitet</td>
<td>Report Designer har följande rapporteringsalternativ när du designar en rapport:
<ul>
<li>Spara dimensionskombinationer och återanvänd dimensioner för flera rapporter.</li>
<li>Kontrollera hur dimensionbeskrivningar formateras och visas.</li>
<li>Identifiera konton eller dimensioner som har utelämnats från rapportbyggnadsblock.</li>
<li>Formatera rubrik för rullande prognoser.</li>
</ul>
</td>
</tr>
<tr>
<td>Samarbete för ekonomisk rapport</td>
<td>Följande funktioner hjälper dig att hantera generering och fördelning av rapporter:
<ul>
<li>Tidsplanera rapporter så att de skapas automatiskt varje dag, varje vecka, varje månad eller varje år.</li>
<li>Exportera till skrivskyddat XPS-format, som ger en bättre dokumentsäkerhet via digitala signaturer.</li>
<li>Exportera ett Microsoft Excel-kalkylblad</li>
<li>Om du vill dela rapporter kan du skapa e-postmeddelanden som innehåller länkar till rapporterna.</li>
</ul>
</td>
</tr>
<tr>
<td>Visning av interaktiv rapportering</td>
<td>Med interaktiva funktioner kan du utföra följande uppgifter:
<ul>
<li>Ändra rapportdatumet för den rapport du visar.</li>
<li>Ändra valutan för den rapport du visar.</li>
<li>Visa rapporten i en sammanfattningsvy och en detaljerad vy.</li>
<li>Lägg till dimensionsfilter för att begränsa rapportens innehåll till en viss dimension eller kombination av dimensioner.</li>
<li>Lägg till attributfilter för att begränsa rapportens innehåll till ett visst attribut eller kombination av attribut.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ytterligare resurser
[Skapa en ekonomisk rapport](generate-financial-report.md)
