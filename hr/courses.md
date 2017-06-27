---
title: "Ställa in utbildningskurser"
description: "Personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om utbildningen som ges till arbetare."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 095f41c35641834a1ed8ac2527c7014826921376
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-training-courses"></a>Ställa in utbildningskurser

[!include[banner](includes/banner.md)]


Personalresursadministratörer och chefer kan använda kursfunktionerna för att underhålla information om utbildningen som ges till arbetare.

 <a name="set-up-prerequisites"></a> Konfigurera krav
---------------------

Följande information krävs och måste ställas in innan du skapar kurser.
-   **Kurstyper**

Följande information är valfri information som du kan ange för kurser. Om du vet att du ska ange denna information för kurser, ska du ställa in informationen, innan du skapar kursposter.
-   **Klassrumsgrupper**
-   **Kursgrupper**
-   **Kursplatser**
-   **Klassrum**
-   **Lärare**

## <a name="course-types"></a>Kurstyper
Du kan använda kurstyper för att kategorisera kurser enligt strukturen eller innehållet i kursen. Du kan skapa kurstyper på sidan **Kurstyper**. Du måste välja en kurstyp när du skapar en kurspost.

## <a name="course-setup-type"></a>Kursinställningstyp
Följande tabell listar de tre inställningstyperna för kurser. Inställningstyper bestämmer strukturen för kursen.

<table>
<thead>
<tr class="header">
<th>Inställningstyp</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Standard</strong></td>
<td>Välj den här typen för kurser som inte ska ha en daglig agenda. Detta är standardinställningen när du skapar en ny kurs.</td>
</tr>
<tr class="even">
<td><strong>Agenda</strong></td>
<td>Välj den här typen för att planera information om varje dag i en kurs som hålls över flera dagar.</td>
</tr>
<tr class="odd">
<td><strong>Agenda + session</strong></td>
<td>Välj den här typen för mer komplexa de kurser. Du kan till exempel dela in kursprogrammet i spårningar och sessioner.
<ul>
<li><strong>Spår</strong> – Spår är specifika ämnesområden för en kurs.</li>
<li><strong>Sessioner</strong> – Sessioner används för att dela upp spår och kan omfatta specifika processer eller tekniker som är relevanta för varje spår.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Kursuppgifter
Du kan utföra följande uppgifter för varje kurs.
-   Registrera deltagare
-   Ange en deadline för registreringen
-   Ange lägsta och högsta antal deltagare
-   Tilldela en plats och ett klassrum för kursen
-   Rekommendera hotell för kursdeltagare
-   Skapa en kursbeskrivning som du sedan kan annonsera på Självbetjäning för medarbetare

  >**Obs!** Du kan bara ta bort en kurs om ingen har registrerat sig för den. 
    
## <a name="course-statuses"></a>Kursstatus
Följande tabell listar möjliga kursstatusvärden och de åtgärder som du kan utföra när kursen har en viss status.

<table>
<thead>
<tr class="header">
<th>Status</th>
<th>Åtgärder</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Skapad</strong></td>
<td><ul>
<li>Ange och ändra kursinformation.</li>
<li>Ändra kursstatus till <strong>Öppen</strong> så att arbetare kan registrera sig för kursen.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Öppna</strong></td>
<td><ul>
<li>Registrera deltagare till kursen.</li>
<li>Ta bort deltagare från kursen.</li>
<li>Bekräfta deltagare för kursen.</li>
<li>Ändra kursens status till <strong>Stängd</strong> eller <strong>Inställd</strong>.</li>
<li>Planera enkäter för deltagare vilkas status är <strong>Bekräftad</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Stängt</strong></td>
<td>Du kan öppna kursen igen.</td>
</tr>
<tr class="even">
<td><strong>Avbrutna</strong></td>
<td>Du kan öppna kursen igen.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Kursdeltagare
Kursdeltagare är arbetare, sökanden eller kontaktpersoner som deltar i en utbildningskurs eller en händelse. Du kan bara registrera deltagare för öppna kurser. Det minsta och det högsta antalet deltagare som du kan registrera för en kurs definieras på snabbfliken **Allmänt** på sidan **Kurser**.

<a name="workflow"></a>Arbetsflöde
--------

Medarbetare som registrerar sig för en kurs via sidan **Självbetjäning för medarbetare** kan få sin registrering skickad via arbetsflödet för godkännande.  Ett arbetsflöde kan tilldelas till en kurs i snabbfliken **Allmänt** på sidan **Kurser**.






