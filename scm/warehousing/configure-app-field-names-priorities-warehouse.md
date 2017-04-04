---
title: "Konfigurera app fältnamn i Warehousing app"
description: "Det här avsnittet beskrivs hur du definierar och konfigurerar lagerstället app fältnamn och prioriteringarna i Dynamics 365 för operationer."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>Konfigurera app fältnamn i Warehousing app

Det här avsnittet beskrivs hur du definierar och konfigurerar lagerstället app fältnamn och prioriteringarna i Dynamics 365 för operationer. 

**Anmärkning:** detta avsnitt gäller funktioner i Lagerstyrning. Det gäller inte för funktioner i Lagerhantering. Dynamics 365 - för lagring är ett program som du kan använda för att utföra uppgifter på lagerstället. Du kan definiera och konfigurera de fältnamn som används i programmet, samt konfigurera prioriteten fältnamnen ska tilldelas. Det här avsnittet beskrivs hur du definierar och konfigurerar dessa lagerställe app fältnamn och prioriteringar och hur de används i Dynamics 365 för - lagring. Detaljerad information om hur du konfigurerar anslutningen till Dynamics 365 för - lagring, finns i kursen [installera och konfigurera Dynamics 365 för - lagring](install-configure-warehousing-app.md).

<a name="configure-warehouse-app-field-names"></a>Konfigurera lagerställe app fältnamn
===================================

När du använder Dynamics 365 för verksamhet – lagring på din mobila enhet kan du konfigurera hur metadata ska visas på enheten på den **lager app fältnamn** sida. Välj i ett nytt företag i Dynamics 365 för operationer **skapa standardinställningen** att generera alla fältnamn som används i lagerställe mobiltelefon arbetsflöden och därefter tilldela en prioriterad indataläge och inmatningstyp dem. När du har genererat alla fältnamn väljer du in följande alternativ.

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
<td>Det här alternativet anger om skanning fält eller en manuell inmatning inmatningsfält som ska visas för valda fältets namn. Detta är användbart för att skilja fälten beroende på om du använder streckkoder för fältet. <strong>Anmärkning:</strong> för fältnamn med önskade Inmatningsläge värdet <strong>skanning</strong>, ange information manuellt om streckkoden är skadad eller oläsbar.</td>
</tr>
<tr class="even">
<td>Inmatningstyp</td>
<td>Det här alternativet definierar vilken Indatatyp som ska användas för valda fältets namn. Det finns fyra alternativ:
<ul>
<li><strong>Val av</strong> - innehåller en lista över alternativ att välja mellan. Fältnamn med det här alternativet kan inte redigeras.</li>
<li><strong>Datum</strong> - fältnamn anges enligt datum visas ett datumformat med etiketten. På så vis lagerarbetare se i vilket format du bör ange datum. Fältnamn med det här alternativet kan inte redigeras.</li>
<li><strong>Alpha</strong> - Överför enhet tangentbordet ska användas när information anges manuellt i programmet. Erfarenheten tangentbord kan ändras beroende på vilken enhet som används.</li>
<li><strong>Numeriska</strong> - för att använda numeriska endast indata fältnamnen du väljer det här alternativet för att visa en anpassad numerisk knappsats med inmatningsfält i stället för tangentbordet för enheten.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Konfigurera lagerställe app fältet prioritet
======================================

I den **lager app fältet Prioritet** sidan inför fältnamn i olika prioriterade grupper. Detta gör det möjligt att bestämma vilken information som ska visas på sidan Huvuduppgiften när lagerarbetare utför åtgärder med programmet. Om du klickar på **skapa standardinställningen**, skapas en standarduppsättning prioriterade grupper. Det går att skapa så många prioritet som krävs, men endast tre grupper av prioritet visas på aktivitetssidan. När Dynamics 365 för operationer skickar metadata till programmet, kommer det att tilldela varje fält beroende på dess prioritet som en relativ prioritet och appen visas de första tre huvudmål grupper i metadata på sidan serviceuppgift. Resten av överskridande metadata visas på en informationssida med sekundär. Nedan visas ett exempel på en prioritet grupper.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppen prioritet</th>
<th>Tilldelade fält</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Prioriteten 10</td>
<td><ul>
<li>Artikel</li>
<li>Kvantitet</li>
<li>Enhet</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioriteten 20</td>
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

Exempelvis när lagerarbetare utför en aktivitet på en mobil enhet om metadata som ska visas i appen består av följande fält:

-   Artikel
-   Kvantitet
-   Enhet
-   Artikelbeskrivning
-   Storlek och plats

Baserat på lagerstället app fältet Prioritet ställts in i tabellen ovan, ska följande 3 rader med information visas på sidan uppgifter:

-   Rad 1: Artikel, kvantitet, enhet
-   Rad 2: Beskrivning av
-   Rad 3: storlek

Återstående metadata, till exempel plats, visas inte på sidan uppgifter men visas på en informationssida. Om du vill veta mer och visa exempel på användargränssnittet finns i blogginlägget [om Dynamics 365 för - lagring](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Se även
--------

[Installera och konfigurera Microsoft Dynamics 365 för operationer – lagring](install-configure-warehousing-app.md)


