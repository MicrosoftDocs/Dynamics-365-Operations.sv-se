---
title: Organisera rapportdelar i rapportdesignern
description: Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 29fdb6ac6b200956383386c42ccb7627314ea7a2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898723"
---
# <a name="organize-report-components-in-report-designer"></a>Organisera rapportdelar i rapportdesignern

[!include [banner](../includes/banner.md)]

När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna. Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.

Du kan ändra namn på mappar, rapporter, byggblock och andra objekt i rapportdesignern för att organisera dina filer. Beroende på vilken typ av objekt du byter namn på måste du kanske uppdatera associationer till det objektet.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Ändra namn på en mapp eller byggsten i Report Designer
I Report Designer kan du byta namn på mappar, rapportdefinitioner, raddefinitioner, kolumndefinitioner och rapportträdsdefinitioner.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Byta namn på en mapp eller ett byggblock i Report Designer

1. Använd navigeringsfönstret i Report Designer när du ska leta rätt på den mapp eller det objekt som du ska byta namn på.
2. Högerklicka på mappen eller objekt och klicka sedan på **Ändra namn**. Fältet **Namn** i navigeringsfönstret blir tillgängligt.
3. Skriv in ett nytt namn och tryck sedan på Enter.
4. Om byggblocket är en raddefinition, kolumndefinition eller rapportträdsdefinition måste du uppdatera andra byggblock som är kopplade till objektet. Högerklicka på byggblocket du bytte namn i steg 3, välj **Associationer** och välj sedan ett alternativ i listan om du vill uppdatera det.
5. Upprepa steg 4 tills alla tillhörande artiklar uppdateras.

## <a name="create-and-manage-report-groups"></a>Skapa och hantera grupper
Du kan gruppera rapportdefinitioner för att skapa flera rapporter samtidigt. För att skapa, ändra, ta bort och skapa rapportgrupper måste du ha rollen designer eller administratör. Användare med rollen generator kan skapa rapportgrupper och även ändra rapportdefinitioners inställningar för rapportgrupper.

### <a name="create-a-report-group"></a>Skapa en rapportgrupp

1. Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2. På menyn **Arkiv** klickar du på **Ny** &gt; **Rapportgruppsdefinition** för att öppna en ny rapportgrupp i visningsfönstret. Du kan även klicka på knappen **Rapportgrupp** ![Rapportgrupp.](media/report-group.gif "Rapportgrupp") i verktygsfältet.
3. Klicka på fliken **Rapportgrupp**. För att åsidosätta informationen om de enskilda rapportdefinitionerna genereringen av denna rapport väljer du kryssrutan **Åsidosätt företags-, informations- och datuminställningar från individuella rapportdefinitioner**. Företagets namn, detaljnivå, preliminär inställning och datuminformation fylls i automatiskt, men du kan fortfarande göra uppdateringar.
4. Välj kryssrutan **Inkludera alla rapporteringsvalutor** om du vill skapa fler rapporter som visar vilken valuta som används i rapporten. Du kan komma åt flera vyer genom att klicka på knappen **Valuta** i Web Viewer när du visar rapporten.
5. I fältet **Rapporter i grupp** klickar du på **Lägg till** för att välja rapporter som ska ingå i rapportgruppen. Om du vill välja flera rapporter i dialogrutan **Lägg till** kan du hålla ned Ctrl-tangenten samtidigt som du markerar rapporter. När du är klar med att välja rapporter klickar du på **OK**.
6. Klicka på **Arkiv** &gt; **Spara** för att spara den nya rapportgruppen.

### <a name="modify-a-report-group"></a>Ändra en rapportgrupp

1. Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2. Dubbelklicka på rapportgruppen att modifiera.
3. Klicka på fliken **Rapportgrupp** och utför valfria ändringar.
4. I menyn **Arkiv** klickar du på **Spara** för att spara den ändrade rapportgruppen. Du kan också klicka på knappen **Spara** ![Spara.](media/save.gif "Spara") i verktygsfältet.

> Om du har schemalagda rapporter som skapas vid inställda intervall kan du åsidosätta dessa inställningar och skapa en rapport direkt.

### <a name="generate-a-report-group-report"></a>Skapar en rapportgruppsrapport

1. Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2. Öppna rapportgruppen att skapa.
3. Klicka på knappen **Generera rapport** ![Generera rapport.](media/generate-report.gif "Generera rapport") för att generera rapporter.

### <a name="delete-a-report-group"></a>Ta bort en rapportgrupp

1. Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2. Högerklicka på rapportgruppen och välj sedan **Ta bort** för att ta bort.
3. När ett bekräftelsemeddelande visas klickar du på **Ja**.

## <a name="report-group-tab-controls"></a>Flikkontroller för Rapportgrupp
I följande tabell hittar du beskrivningar av kontrollerna på fliken **Rapportgrupp**.

<table>
<thead>
<tr>
<th>Kontroll</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner</td>
<td>Markera den här kryssrutan för att åsidosätta individuella rapportdefinitioner av rapporter i denna rapport för generering av dessa rapporter.</td>
</tr>
<tr>
<td>Företagets namn</td>
<td>Välj företag att använda för rapporter.</td>
</tr>
<tr>
<td>Detaljnivå</td>
<td>Ange vilken detaljnivå rapporten ska innehålla.
<ul>
<li><strong>Ekonomisk</strong> – En sammanfattningsrapport på hög nivå. Du kan inte detaljgranska till konton och dimensioner, förutom i dem som det finns konton och dimensioner tillagda för i rapportträdet.</li>
<li><strong>Ekonomisk &amp; Konto</strong> − En rapport som innehåller en sammanfattning på hög nivå och kontodetaljer.</li>
<li><strong>Ekonomisk, Konto &amp; Transaktion</strong> − En rapport som innehåller en sammanfattning på hög nivå och transaktionsdetaljer.</li>
</ul></td>
</tr>
<tr>
<td>Preliminära</td>
<td>Ange vilka typer av aktiviteter rapporterna ska innehålla.
<ul>
<li><strong>Endast bokförd aktivitet</strong> – Inkludera endast bokförda transaktioner och saldon i aktuella ekonomidata.</li>
<li><strong>Bokförd och icke bokförd aktivitet</strong> – Inkludera alla inmatade och bokförda transaktioner och saldon i aktuella ekonomidata.</li>
<li><strong>Endast icke bokförd aktivitet</strong> – Inkludera endast inmatade, men ännu ej bokförda, transaktioner i aktuella ekonomidata.</li>
</ul></td>
</tr>
<tr>
<td>Inkluderar alla rapporteringsvalutor</td>
<td>Om ytterligare rapporteringsvalutor som är konfigurerade i ditt Microsoft Dynamics ERP-system kommer att visas här. Välj den här kryssrutan om du vill ha skapa fler rapporter i de valutor som anges. Klicka på <strong>Valuta</strong> och välj en valuta om du vill visa rapporterna i Web Viewer.</td>
</tr>
<tr>
<td>Datuminformation sparas inte med rapportdefinition</td>
<td><ul>
<li>Basperiod</li>
<li>Basår</li>
<li>Period</li>
</ul>
Endast standardbasperiodinställningar sparas tillsammans med rapportdefinitionen.</td>
</tr>
<tr>
<td>Datuminformation sparas med rapportdefinition</td>
<td><ul>
<li>Rapportdatum</li>
<li>Standardbasperioden</li>
</ul></td>
</tr>
<tr>
<td>Rapporter i grupp</td>
<td>Lägg till, ta bort och ordna om rapporter i rapporten.
<ul>
<li>Om du vill lägga till rapportdefinitioner i rapportgruppen dubbelklickar du på rapportgruppen för att öppna den och klickar sedan på <strong>Lägg till</strong>. Välj de rapporter som du vill ta med i rapportgruppen och klicka på <strong>OK</strong>.</li>
<li>Om du vill ta bort en rapport från rapportgruppen väljer du den och klickar på <strong>Ta bort</strong>.</li>
<li>Om du vill ändra i vilken ordning rapporterna skapas, välj en rapport i listan och sedan klicka på <strong>Flytta upp</strong> eller <strong>Flytta ned</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ytterligare resurser

[Ekonomisk rapportering](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]