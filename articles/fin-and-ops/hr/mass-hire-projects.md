---
title: "Massanställningsprojekt"
description: "Massanställningsprojekt låter personalresursspecialister skapa flera befattningar och anställa ett antal arbetare till dessa befattningar på ett effektivt sätt."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMMassHireProject
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e98e6b3baf57302804d9171833f2b48b60355b22
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="mass-hire-projects"></a>Massanställningsprojekt

[!INCLUDE [banner](../includes/banner.md)]

Massanställningsprojekt låter personalresursspecialister skapa flera befattningar och anställa ett antal arbetare till dessa befattningar på ett effektivt sätt.

<a name="overview"></a>Översikt
--------

Använd massanställningsprojekt när du anställer flera medarbetare på en gång, till exempel för säsongsarbete. Det kan vara praktiskt att skapa ett massanställningsprojekt, eftersom du kan skapa befattningposter, arbetarposter och arbetartilldelningar för befattningar samtidigt. När du skapar befattningar för ett massanställningsprojekt kan du ange följande information:
-   Antalet positioner som ska skapas
-   Arbetartypen av de människor som du vill anställa för befattningarna
-   Avdelningen och det jobb som befattningarna kopplas till
-   Heltid motsvarar befattningens värde

## <a name="example"></a>Exempel
På sommaren anställer du ofta 15-20 högskolestudenter på deltid för att fylla tillgängliga praktikplatser i ditt företag. I år vill du anställa fem revisorer, fem orderprocessorer och fem kassörer. I stället för att skapa varje befattningpost och arbetarposten separat, skapar du ett massanställningsprojektet som kallas ”SummerInterns”. Projektstart- och slutdatum korrelerar med start- och slutdatumen för befattningsvaraktighet för befattningarna som du skapar för massanställningsprojektet. 

Välj sidan **Massanställningsprojekt** och välj projektet "SummerInterns” och klicka sedan på sidan **Öppna projekt**. I den öppna massanställningsprojektet klickar du på **Skapa befattningar** och anger information om revisorbefattningen. Du kan ange att fem revisorbefattningar ska skapas med samma information för varje, och klicka sedan på OK. Upprepa den här processen för orderprocessor- och kassörbefattningarna. 

När du har valt studenter att anställa till praktikbefattningarna, ska du ange varje students information i **Befattningsinformation** för befattningen som du anställer dem för. När du har angett alla befattningdetaljer väljer du befattning på sidan Massanställningsprojekt och klickar sedan på **Anställ**. En befattningspost skapas för varje befattning och en arbetarpost skapas och tilldelas korrekt befattning för varje person som du anställer.

## <a name="mass-hire-project-statuses"></a>Status för massanställningsprojekt
Ett massanställningsprojekt kan ha nedanstående statusvärden.
-   Skapad
-   Öppen
-   Stängt

Klicka på sidan **Massanställningsprojekt**, klicka på **Öppna projekt** eller **Stäng projekt** för att ändra status för ett massanställningsprojekt. Vad du kan göra med ett projekt enligt dess status beskrivs i följande tabell.

<table>
<thead>
<tr class="header">
<th>Status</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Skapad</td>
<td>Du kan skapa och ändra information men inte skapa befattningar för projektet. Det här är standardstatus för nya projekt.</td>
</tr>
<tr class="even">
<td>Öppen</td>
<td>Du kan ändra projektinformationen, skapa befattningar för massanställningsprojektet och anställa människor för befattningarna. Det här är status för aktiva projekt.</td>
</tr>
<tr class="odd">
<td>Stängt</td>
<td>Du kan inte lägga till befattningar till projektet. Om du vill lägga till befattningar till massanställningsprojektet öppnar du projektet igen. Det här är status för slutförda projekt.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Obs! </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>För att du ska kunna stänga ett massanställningsprojekt måste alla befattningar ha status Skapad eller Stängd.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
</tbody>
</table>








