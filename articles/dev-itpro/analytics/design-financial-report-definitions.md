---
title: "Rapportdefinitioner i designer för ekonomiska rapporter"
description: "Den här artikeln innehåller information om rapportdefinitioner. En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport. En rapportdefinition innehåller också alternativ och inställningar för att anpassa en rapport."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96090a3ae15294d98d6207c8eb4a1e58429ca9eb
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="report-definitions-in-financial-report-designer"></a>Rapportdefinitioner i designer för ekonomiska rapporter

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om rapportdefinitioner. En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport. En rapportdefinition innehåller också alternativ och inställningar för att anpassa en rapport. 

En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport. En rapportdefinition innehåller också alternativ och inställningar som du kan använda för att anpassa en rapport. När du har definierat raddefinitioner och kolumndefinitioner, måste du kombinera dem i en rapportdefinition. I det här läget definierar du också andra aspekter av definitioner, till exempel detaljnivå och rapportdatum. Du kan sedan spara och skapa en rapport. Ekonomist rapportering omfattar följande detaljnivåer:

-   Ekonomi
-   Ekonomisk och Konto
-   Ekonomisk, Konto och Transaktion

Beroende på hur data lagras i Microsoft Dynamics ERP-system kanske inte transaktionsdetaljer är tillgängliga i rapporter.

## <a name="create-a-report-definition"></a>Skapa en rapportdefinition
1.  I Report Designer i menyn **Fil** klickar du på **Nytt** och väljer sedan **Rapportdefinition**.
2.  Ange lämplig information i flikarna **Rapport**som krävs på **Utleverans och fördelning**, **Sidhuvud och sidfot**och **Inställningar**.

## <a name="contents-of-a-report-definition"></a>Innehåll i en rapportdefinition
I följande register finns beskrivningar av flikarna i en rapportdefinition och hur informationen används.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabb</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Rapport</td>
<td>Skapa en rapport, konfigurera en rapport eller ändra en befintlig rapport.</td>
</tr>
<tr class="even">
<td>Utleverans och fördelning</td>
<td>Ändra rappportens utleveranstyp och destination.</td>
</tr>
<tr class="odd">
<td>Huvud och sidfot</td>
<td>Definiera och formatera rapportens sidhuvud och sidfot. Du kan till exempel lägga till text eller bilder till sidhuvudet eller sidfoten. Ekonomisk rapportering stöder .bmp-, .jpg- och .png-filer för bilder. Du kan också lägga till autotextkoder om du vill infoga annan information som till exempel företagsnamn, rapportnamn eller sidnummer.</td>
</tr>
<tr class="even">
<td>Inställningar</td>
<td>Ange rapportdefinitioninställningar, till exempel följande inställningar:
<ul>
<li>Formatering och avrundningsbelopp</li>
<li>Formatdetaljrapporter</li>
<li>Formatrapporteringsträd</li>
<li>Skapa rapport över inleveransavvikelser</li>
<li>Ange valutakonvertering</li>
<li>Delsumma- och filterkontodetaljer</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Se även
--------

[Ekonomisk rapportering](financial-reporting-intro.md)




