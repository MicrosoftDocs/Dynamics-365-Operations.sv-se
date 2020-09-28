---
title: Ställ in roller i mallarna för uppdelad arbetsstruktur
description: Det här avsnittet innehåller information om hur du ställer in rollinformation i mallarna för uppdelad arbetsstruktur.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760666"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>Ställ in roller i mallarna för uppdelad arbetsstruktur

[!include [banner](../includes/banner.md)]

Projektledare kan ställa in mallar för uppdelad arbetsstruktur (WBS) de kan använda när de skapar en struktur för nya projekt. Projektledare kan lägga till roller när de skapar en mall. Använd följande procedur för att tilldela en roll till en strukturmall. 

1. Markera **Projekthantering och redovisning** > **Inställningar** > **Projekt** > **Uppdelade arbetsstrukturmallar**.
2. Markera **Information** för en vald strukturmall.
3. Välj en uppgift i listan och sedan, i **Roll**-fältet, välj en roll som ska tilldelas uppgiften.

## <a name="work-with-a-wbs"></a>Arbeta med en struktur

Du kan skapa en ny struktur, eller så kan du kopiera en struktur från en befintlig strukturmall. En projektledare kan enkelt hantera resurserna genom att tilldela roller till nya uppgifter på strukturen. Roller kan ersättas antingen efter det att en resurs har anskaffats eller efter det att en bekräftad resurs som ska arbeta med uppgiften identifierats. Denna flexibilitet låter projektledare utföra följande uppgifter:

- Identifiera det antal resurser som krävs för strukturarbetspaket.
- Uppskatta projektkostnader.
- Fastställa en preliminär budget.
- Beräkna aktivitetvaraktighet baserat på roller och resurser.
- Utveckla alla projektledningsplaner baserat på den tillgängliga projektinformationen.

Ytterligare alternativ har lagts till i strukturen för en bättre användning av resursplaneringsfunktionerna.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Alternativ</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Resurstilldelningar</td>
<td>Visa tilldelade resurser, datum, antalet timmar och bokningstyp för uppgifter på strukturen.</td>
</tr>
<tr class="even">
<td>Autogenerera team</td>
<td>Automatiskt lägg till planerade resurser genom att använda roller som associeras med en uppgift. Finance föreslår automatiskt planerade resurser genom att använda beslutsanalys för flera kriterier baserat på roller. När rollerna och insatsen (timmar) har angetts för uppgifterna i en struktur, samt efter det att strukturen har frisläppts, markerar du <strong>Autogenerera team</strong>. Det begärda antalet planerade resurser läggs till i strukturen och på fliken <strong>Projekt och tidsplanering av team</strong>.</td>
</tr>
<tr class="odd">
<td>Resurs (listruta)</td>
<td>På sidan <strong>Starta resurstilldelning</strong> kan du välja resurser att preliminär- eller fastboka utifrån den angivna varaktigheten. Du kan justera vyinställningarna om du vill visa och ange längden för resursaktiviteter. Du kan välja och tilldela resurser på nivån för arbetspaketet genom att använda följande alternativ:
<ul>
<li><strong>Godkänn</strong> – Bekräfta ändringarna för resursen som har tilldelats en uppgift.</li>
<li><strong>Avbryt</strong> – Avbryt ändringarna för resursen som har tilldelats en uppgift.</li>
<li><strong>Tilldela automatiskt</strong> – En tillgänglig bemannad resurs med en matchande roll väljs automatiskt och tilldelas till den valda uppgiften.</li>
</ul></td>
</tr>
</tbody>
</table>

1. På sidan **Alla projekt** markerar du projektet **XYZ-uppgradering fas 2**.
2. Markera **Plan** > **Aktiviteter** > **Uppdelad arbetsstruktur**.
3. Markera **Nytt** för att lägga till följande aktiviteter för första nivån i strukturen:

    - Påbörjande
    - Planering
    - Kör
    - Övervakning och kontroll
    - Stäng

4. Ange datum och arbete (timmar) enligt följande illustration.

    [![Ange datum och arbete](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Välj uppgiftsraden **Initierande** och sedan, i fältet **Roll**, välj **Senior projektledare**.
6. Markera **Publicera**.
7. På samma rad, i fältet **Resurs**, markerar du **Daniel Goldschmidt** och sedan **Godkänn**.
8. Välj **Planering**-uppgiftsraden och sedan, i fältet **Roll**, välj **Affärsanalytiker**.
9. Markera **Publicera** och sedan **Autogenerera team**.
10. Markera **Ja** i meddelanderutan som visas.
11. I fältet **Resurs**, kontrollera att värdet är **Affärsanalytiker 1**.
12. För resursen **Affärsanalytiker 1**, öppna sökningen och markera **Starta resurstilldelning**. Markera sedan en medarbetare för uppgiften.
13. Markera **Preliminär tilldelning** &gt; **Total kapacitet**.

    > [!NOTE] 
    > Du får ingen varning om att den angivna resursen nu är 2, detta eftersom antalet resurser förblir 1.

14. På sidan **Uppdelad arbetsstruktur** validerar resurstilldelningen för strukturen och väljer sedan **Spara**.
