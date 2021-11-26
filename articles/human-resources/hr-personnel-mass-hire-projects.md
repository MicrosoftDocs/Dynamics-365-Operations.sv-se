---
title: Massanställningsprojekt
description: Detta ämne beskriver massanställningsprojekt som låter personalresursspecialister skapa flera befattningar och anställa ett antal medarbetare till dessa befattningar på ett effektivt sätt.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e0a8bba2227136995542d08f4b3f1e9d6d48ad5
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728695"
---
# <a name="mass-hire-projects"></a>Massanställningsprojekt

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Massanställningsprojekt låter personalresursspecialister skapa flera befattningar och anställa ett antal arbetare till dessa befattningar på ett effektivt sätt.

## <a name="overview"></a>Översikt

Använd massanställningsprojekt när du anställer flera medarbetare på en gång, till exempel för säsongsarbete. Det kan vara praktiskt att skapa ett massanställningsprojekt, eftersom du kan skapa befattningposter, arbetarposter och arbetartilldelningar för befattningar samtidigt. När du skapar befattningar för ett massanställningsprojekt kan du ange följande information:

- Antalet positioner som ska skapas
- Arbetartypen av de människor som du vill anställa för befattningarna
- Avdelningen och det jobb som befattningarna kopplas till
- Heltid motsvarar befattningens värde

## <a name="example"></a>Exempel

På sommaren anställer du ofta 15-20 högskolestudenter på deltid för att fylla tillgängliga praktikplatser i ditt företag. I år vill du anställa fem revisorer, fem orderprocessorer och fem kassörer. I stället för att skapa varje befattningpost och arbetarposten separat, skapar du ett massanställningsprojektet som kallas ”SummerInterns”. Projektstart- och slutdatum korrelerar med start- och slutdatumen för befattningsvaraktighet för befattningarna som du skapar för massanställningsprojektet.

På sidan **Massanställningsprojekt** väljer du projektet **SummerInterns** och sedan **Öppna projekt**. I det öppna massanställningsprojektet klickar du på **Skapa befattningar** och anger sedan information om revisorbefattningen. Du kan ange att fem revisorbefattningar ska skapas och att samma information ska användas för dessa. Välj sedan **OK**. Upprepa den här processen för orderprocessor- och kassörbefattningarna.

När du har valt studenter att anställa till praktikbefattningarna ska du ange respektive students personliga information i befattningsinformationen för den befattning som du anställer dem för. När du har angett alla befattningsuppgifter väljer du befattningen på sidan **Massanställningsprojekt** och sedan på **Anställ**. En befattningspost skapas för respektive befattning, och en medarbetarpost skapas och tilldelas till korrekt befattning för respektive person som du anställer.

## <a name="mass-hire-project-statuses"></a>Status för massanställningsprojekt

Ett massanställningsprojekt kan ha nedanstående statusvärden.

- Har skapats
- Öppet
- Stängd

Klicka på sidan **Massanställningsprojekt** väljer du **Öppna projekt** eller **Stäng projekt** för att ändra status för ett massanställningsprojekt. Vad du kan göra med ett projekt enligt dess status beskrivs i följande tabell.

<table>
<thead>
<tr>
<th>Status</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Skapad</td>
<td>Du kan skapa och ändra information men inte skapa befattningar för projektet. Det här är standardstatus för nya projekt.</td>
</tr>
<tr>
<td>Öppen</td>
<td>Du kan ändra projektinformationen, skapa befattningar för massanställningsprojektet och anställa människor för befattningarna. Det här är status för aktiva projekt.</td>
</tr>
<tr>
<td>Stängt</td>
<td><p>Du kan inte lägga till befattningar till projektet. Om du vill lägga till befattningar till massanställningsprojektet öppnar du projektet igen. Det här är status för slutförda projekt.</p>
<p><strong>Obs!</strong> För att du ska kunna stänga ett massanställningsprojekt måste alla befattningar i projektet ha antingen statusen <b>Skapad</b> eller <b>Stängd</b>.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
