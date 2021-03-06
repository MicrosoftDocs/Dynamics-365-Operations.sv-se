---
title: Massanställningsprojekt
description: Massanställningsprojekt låter personalresursspecialister skapa flera befattningar och anställa ett antal arbetare till dessa befattningar på ett effektivt sätt.
author: andreabichsel
ms.date: 06/20/2017
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
ms.openlocfilehash: b3d0747232ba4682afe4b28dc7d24ad2413448bb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052856"
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

Välj sidan **Massanställningsprojekt** och välj projektet "SummerInterns” och klicka sedan på sidan **Öppna projekt**. I den öppna massanställningsprojektet klickar du på **Skapa befattningar** och anger information om revisorbefattningen. Du kan ange att fem revisorbefattningar ska skapas med samma information för varje, och klicka sedan på OK. Upprepa den här processen för orderprocessor- och kassörbefattningarna.

När du har valt studenter att anställa till praktikbefattningarna, ska du ange varje students information i **Befattningsinformation** för befattningen som du anställer dem för. När du har angett alla befattningdetaljer väljer du befattning på sidan Massanställningsprojekt och klickar sedan på **Anställ**. En befattningspost skapas för varje befattning och en arbetarpost skapas och tilldelas korrekt befattning för varje person som du anställer.

## <a name="mass-hire-project-statuses"></a>Status för massanställningsprojekt

Ett massanställningsprojekt kan ha nedanstående statusvärden.

- Skapad
- Öppen
- Stängt

Klicka på sidan **Massanställningsprojekt**, klicka på **Öppna projekt** eller **Stäng projekt** för att ändra status för ett massanställningsprojekt. Vad du kan göra med ett projekt enligt dess status beskrivs i följande tabell.

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
<td>Du kan inte lägga till befattningar till projektet. Om du vill lägga till befattningar till massanställningsprojektet öppnar du projektet igen. Det här är status för slutförda projekt.
<blockquote>[!NOTE] För att du ska kunna stänga ett massanställningsprojekt måste alla befattningar ha status Skapad eller Stängd.</blockquote>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]