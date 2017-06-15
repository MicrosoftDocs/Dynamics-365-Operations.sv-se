---
title: "Konfigurera programfältnamn i lagerstyrningsprogrammet"
description: "Det här avsnittet beskriver hur du definierar och konfigurerar fältnamnen i lagerställets program samt prioriteringar i Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: edcbf8a0921e0eb08d0f970e681c9d098b354c0b
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Konfigurera programfältnamn i lagerstyrningsprogrammet

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du definierar och konfigurerar fältnamnen i lagerställets program samt prioriteringar i Dynamics 365 for Operations. 

**Obs!** Denna artikel gäller funktioner i lagerstyrningshanteringen. Den gäller inte funktioner i lagerhanteringshanteringen. Dynamics 365 for Operations - Lagerstyrning är ett program som du kan använda för att utföra uppgifter på lagerstället. Du kan definiera och konfigurera de fältnamn som används i programmet, samt konfigurera prioriteringen bland de fältnamn som ska tilldelas. Det här avsnittet förklarar hur du definierar och konfigurerar fältnamn och prioriteringar i lagerställets program, samt hur dessa används i Dynamics 365 for Operations - Lagerstyrning. Detaljerad information om hur du konfigurerar anslutningen till Dynamics 365 för Operations - Lagerstyrning, finns i kursen [Installera och konfigurera Dynamics 365 for Operations - Lagerstyrning](install-configure-warehousing-app.md).

<a name="configure-warehouse-app-field-names"></a>Konfigurera fältnamn i lagerställets program
===================================

När du använder Dynamics 365 for Operations – Lagerstyrning på din mobila enhet kan du konfigurera hur metadata ska visas på enheten på sidan **Fältnamn i lagerställeprogram**. Välj **Skapa standardinställning** i ett nytt företag i Dynamics 365 for Operations för att skapa alla fältnamn som ska användas i lagerställets arbetsflöden för mobila enheter, och tilldela dem sedan ett föredraget inmatningsläge och en föredragen inmatningstyp. När du har genererat alla fältnamn väljer du in följande inmatningsalternativ.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Alternativ</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Prioriterat indataläge</td>
<td>Det här alternativet anger om ett skanningsfält eller ett fält för manuell inmatning bör visas för det valda fältnamnet. Detta är användbart för att skilja fälten åt, beroende på om du använder streckkoder för fältet. <strong>Obs!</strong> För fältnamn med önskat inmatningsläge angivet som <strong>Skanning</strong> kan du ange information manuellt om streckkoden är skadad eller oläsbar.</td>
</tr>
<tr class="even">
<td>Inmatningstyp</td>
<td>Det här alternativet definierar vilken inmatningstyp som ska användas för det valda fältnamnet. Det finns fyra alternativ:
<ul>
<li><strong>Val</strong> - Innehåller en lista över alternativ att välja mellan. Fältnamn med det här alternativet kan inte redigeras.</li>
<li><strong>Datum</strong> - Fältnamn som angetts som datum visar ett datumformat med etiketten. Detta hjälper lagerarbetare att se i vilket format datumet ska anges. Fältnamn med det här alternativet kan inte redigeras.</li>
<li><strong>Alpha</strong> - Om denna inställning används, används tangentbordet när information ska anges manuellt i programmet. Tangentbordsupplevelsen kan ändras beroende på vilken enhet som används.</li>
<li><strong>Numeriskt</strong> - För fältnamn som endast använder numerisk inmatning kan du använda detta alternativ för att visa en anpassad numerisk knappsats på inmatningsfältet istället för enhetens tangentbord.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Konfigurera prioriteringsordningen för lagerställets programfält
======================================

På sidan **Fältprioritet för lagerställeprogram** kan du ange fältnamn i olika prioriteringsgrupper. Detta gör det möjligt att bestämma vilken information som ska visas på huvuduppgiftssidan när lagerarbetare utför åtgärder med programmet. Om du klickar på **Skapa standardinställning** skapas en standarduppsättning prioriterade grupper. Det går att skapa så många prioriteringsgrupper som krävs, men endast tre prioriteringsgrupper visas på uppgiftssidan. När Dynamics 365 for Operations skickar metadata till programmet, kommer det att tilldela varje fält en relativ prioritet beroende på dess prioriteringsgrupp, och programmet kommer att visa de första tre prioriteringsgrupperna i metadatan på uppgiftssidan. Överflödig metadata visas på en ytterligare informationssida. Tabellen nedan visar ett exempel på fem prioriteringsgrupper.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prioriteringsgrupp</th>
<th>Tilldelade fält</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Prioritet 10</td>
<td><ul>
<li>Artikel</li>
<li>Kvantitet</li>
<li>Enhet</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioritet 20</td>
<td><ul>
<li>Klusterposition</li>
<li>Kluster</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioritet 30</td>
<td><ul>
<li>Artikelbeskrivning</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioritet 40</td>
<td><ul>
<li>Inställningar</li>
<li>Färg</li>
<li>Storlek</li>
<li>Stil</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioritet 50</td>
<td><ul>
<li>Plats</li>
<li>ID-nummer</li>
</ul></td>
</tr>
</tbody>
</table>

När en lagerarbetare exempelvis utför en aktivitet på en mobil enhet och metadatan som ska visas i programmet består av följande fält:

-   Artikel
-   Kvantitet
-   Enhet
-   Artikelbeskrivning
-   Storlek och plats

Baserat på fältprioriteringen i lagerställets program som anges i tabellen ovan, kommer följande 3 rader med information att visas på uppgiftssidan:

-   Rad 1: Artikel, Kvantitet, Måttenhet
-   Rad 2: Artikelbeskrivning
-   Rad 3: Storlek

Återstående metadata, till exempel plats, visas inte på uppgiftssidan men däremot på en informationssida. Om du vill veta mer och visa exempel på användargränssnittet, se blogginlägget [Vi presenterar Dynamics 365 for Operations - Lagerstyrning](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Se även
--------

[Installera och konfigurera Microsoft Dynamics 365 for Operations – Lagerstyrning](install-configure-warehousing-app.md)



