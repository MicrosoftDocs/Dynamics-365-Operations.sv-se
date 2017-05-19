---
title: Organisera rapportdelar i rapportdesignern
description: "När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna. Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ca6d02d41be67447719819e27fbcf3f615eced63
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="organize-report-components-in-report-designer"></a>Organisera rapportdelar i rapportdesignern

[!include[banner](../includes/banner.md)]


När du har utformat byggblock och skapat rapporter är det praktiskt att ordna objekten så att de blir lättare att hitta för användarna. Den här artikeln innehåller en beskrivning av hur du organiserar befintliga rapporter, byggblock och objekt i rapportdesignern.

Du kan ändra namn på mappar, rapporter, byggblock och andra objekt i rapportdesignern för att organisera dina filer. Beroende på vilken typ av objekt du byter namn på måste du kanske uppdatera associationer till det objektet.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Ändra namn på en mapp eller byggsten i Report Designer
I Report Designer kan du ändra namn på mappar, rapportdefinitioner, raddefinitioner, kolumndefinitioner och rapportträddefinitioner. **Obs!** Om du byter namn på ett byggblock måste du uppdatera alla rapportdefinitioner som använder byggblocket. I annat fall kan ingen ny rapport skapas.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Ändra namn på en mapp eller byggsten i Report Designer

1.  I Report Designer, använd navigeringsrutan för att hitta mappen eller objektet du vill byta namn på.
2.  Högerklicka på mappen eller objekt och klicka sedan på **Ändra namn**. Fältet **Namn** i navigeringsfönstret blir tillgängligt.
3.  Skriv in ett nytt namn och tryck sedan på Retur.
4.  Om byggblocket är en raddefinition, kolumndefinition eller rapportträdsdefinition måste du uppdatera andra byggblock som är kopplade till objektet. Högerklicka på byggblocket du bytte namn i steg 3, välj **Associationer** och välj sedan ett alternativ i listan om du vill uppdatera det.
5.  Upprepa steg 4 tills alla tillhörande artiklar uppdateras.

## <a name="create-and-manage-report-groups"></a>Skapa och hantera grupper
Du kan gruppera rapportdefinitioner för att generera flera rapporter samtidigt. För att skapa, ändra, ta bort och skapa rapportgrupper måste du ha rollen designer eller administratör. Användare med rollen generator kan skapa rapportgrupper och även ändra rapportdefinitioners inställningar för rapportgrupper.

### <a name="create-a-report-group"></a>Skapa en rapportgrupp

1.  Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2.  På menyn **Arkiv** klickar du på **Ny** &gt; **Rapportgruppsdefinition** för att öppna en ny rapportgrupp i visningsfönstret. Du kan även klicka på knappen **Rapportgrupp** ![Rapportgrupp](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Rapportgrupp") i verktygsfältet.
3.  Klicka på **Rapportgrupp** fliken. Om du vill åsidosätta informationen om enskilda rapportdefinitioner för generering av rapporten väljer du **Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner** kryssrutan. Företagets namn, detaljnivå, preliminär inställning och datuminformation fylls i automatiskt, men du kan fortfarande göra uppdateringar.
4.  Välj kryssrutan **Inkludera alla rapporteringsvalutor** om du vill skapa fler rapporter som visar vilken valuta som används i rapporten. Du kan komma åt flera vyer genom att klicka på knappen **Valuta** i Web Viewer när du visar rapporten.
5.  I fältet **Rapporter i grupp** klickar du på **Lägg till** för att välja rapporter som ska ingå i rapportgruppen. Om du vill välja flera rapporter i dialogrutan **Lägg till** kan du hålla ned Ctrl-tangenten samtidigt som du markerar rapporter. När du är klar med att välja rapporter klickar du på **OK**.
6.  Klicka på **Arkiv** &gt; **Spara** för att spara den nya rapportgruppen.

### <a name="modify-a-report-group"></a>Ändra en rapportgrupp

1.  Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2.  Dubbelklicka på rapportgruppen att modifiera.
3.  Klicka på fliken **Rapportgrupp** och utför valfria ändringar.
4.  På menyn **Arkiv** klickar du på **Spara** för att spara den ändrade rapportgruppen. Du kan också klicka på knappen **Spara** ![Spara](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Spara") i verktygsfältet.

**Obs!** Om du har schemalagda rapporter som genereras vid inställda intervall kan du åsidosätta dessa inställningar och generera en rapport direkt.

### <a name="generate-a-report-group-report"></a>Genererar en rapportgruppsrapport

1.  Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2.  Öppna rapportgruppen att generera.
3.  Klicka på knappen **Skapa rapport** ![Skapa rapport](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Skapa rapport") för att skapa rapporter.

### <a name="delete-a-report-group"></a>Ta bort en rapportgrupp

1.  Öppna Report Designer och klicka på **Rapportgrupper** i navigeringsfönstret.
2.  Högerklicka på rapportgruppen och välj sedan **Ta bort** för att ta bort.
3.  När ett bekräftelsemeddelande visas klickar du på **Ja**.

## <a name="report-group-tab-controls"></a>Flikkontroller för Rapportgrupp
I följande tabell hittar du beskrivningar av kontrollerna på fliken **Rapportgrupp**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kontroll</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Åsidosätt företaget, detaljer och datuminställningar från enskilda rapportdefinitioner</td>
<td>Markera den här kryssrutan för att åsidosätta individuella rapportdefinitioner av rapporter i denna rapport för generering av dessa rapporter.</td>
</tr>
<tr class="even">
<td>Företagets namn</td>
<td>Välj företag att använda för rapporter.</td>
</tr>
<tr class="odd">
<td>Detaljnivå</td>
<td>Ange vilken detaljnivå rapporten ska innehålla.
<ul>
<li><strong>Finansiella</strong> – en hög nivå sammanfattande rapport. Du kan inte detaljgranska till konton och dimensioner, förutom i dem som det finns konton och dimensioner tillagda för i rapportträdet.</li>
<li><strong>Ekonomisk &amp; Konto</strong> − En rapport som innehåller en sammanfattning på hög nivå och kontodetaljer.</li>
<li><strong>Ekonomisk, Konto &amp; Transaktion</strong> − En rapport som innehåller en sammanfattning på hög nivå och transaktionsdetaljer.</li>
</ul></td>
</tr>
<tr class="even">
<td>Preliminära</td>
<td>Ange vilka typer av aktiviteter rapporterna ska innehålla.
<ul>
<li><strong>Endast bokförd aktivitet</strong> – Omfattar endast transaktioner och saldon som har bokförs i dina ekonomiska data.</li>
<li><strong>Bokförd och okonterad aktivitet</strong> – Omfattar alla transaktioner och saldon som registreras och bokförs i dina ekonomiska data.</li>
<li><strong>Endast okonterad aktivitet</strong> – Omfattar endast transaktioner som registrerats, men som ännu inte har bokförts i dina ekonomiska data.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Inkluderar alla rapporteringsvalutor</td>
<td>Om ytterligare rapporteringsvalutor som är konfigurerade i ditt Microsoft Dynamics ERP-system kommer att visas här. Välj den här kryssrutan om du vill ha skapa fler rapporter i de valutor som anges. De kan sedan visas i Web Viewer om du klickar på knappen <strong>Valuta</strong> och väljer en valuta.</td>
</tr>
<tr class="even">
<td>Datuminformation sparas inte med rapportdefinition</td>
<td><ul>
<li>Basperiod</li>
<li>Basår</li>
<li>Period</li>
</ul>
Endast standardbasperiodinställningar sparas tillsammans med rapportdefinitionen.</td>
</tr>
<tr class="odd">
<td>Datuminformation sparas med rapportdefinition</td>
<td><ul>
<li>Rapportdatum</li>
<li>Standardbasperioden</li>
</ul></td>
</tr>
<tr class="even">
<td>Rapporter i grupp</td>
<td>Lägg till, ta bort och ordna om rapporter i rapporten.
<ul>
<li>För att lägga till rapportdefinitioner i rapporten grupp, dubbelklicka på rapportgrupp för att öppna den och klicka sedan på <strong>Lägg till</strong>. Välj de rapporter som ska ingå i rapportgrupp, och klicka sedan på <strong>OK</strong>.</li>
<li>För att ta bort en rapport från rapportgrupp, välj den och klicka sedan på <strong>Ta bort</strong>.</li>
<li>Om du vill ändra i vilken ordning rapporterna skapas, välj en rapport i listan och sedan klicka på <strong>Flytta upp</strong> eller <strong>Flytta ned</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Se även
--------

[Ekonomisk rapportering](financial-reporting-intro.md)




