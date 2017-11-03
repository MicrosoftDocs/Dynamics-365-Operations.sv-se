---
title: "Rapportdefinitioner i designer för ekonomiska rapporter"
description: "En raddefinition är en rapportkomponent eller byggblock som anger innehållet på varje rad i en ekonomisk rapport. En raddefinition kan kombineras med kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner för att skapa en byggblocksgrupp som kan användas av flera företag."
author: aprilolson
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
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 06a75889e62cbba6e47a8543cf663868df5ae2e3
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="row-definitions-in-financial-report-designer"></a>Rapportdefinitioner i designer för ekonomiska rapporter

[!include[banner](../includes/banner.md)]


En raddefinition är en rapportkomponent eller byggblock som anger innehållet på varje rad i en ekonomisk rapport. En raddefinition kan kombineras med kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner för att skapa en byggblocksgrupp som kan användas av flera företag.

<a name="create-a-row-definition"></a>Skapa en raddefinition
-----------------------

1.  Klicka på **Raddefinitioner** i navigeringsfönstret i Report Designer.
2.  Gå till menyn **Fil** och klicka först på **Ny** och sedan på **Raddefinition**. Mer information om innehållet i varje cell finns på [Ändra definitionscell](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Öppna en raddefinition
1.  Klicka på **Raddefinitioner** i navigeringsfönstret i Report Designer.
2.  Dubbelklicka på namnet på raddefinitionen som du vill öppna.
3.  Om du vill visa alla byggblock som är associerade med raddefinitionen, högerklicka på raddefinitionen och välj sedan **Associationer**.

## <a name="contents-of-a-row-definition"></a> Innehåll i en raddefinition
En raddefinition kan innehålla upp till 20 000 rader för ekonomiska dimensioner och kan innehålla följande information:

-   Beskrivande text som tillför något till rapporten genom att skapa avsnittsrubriker, rader och mellanslag såsom **Kontant** eller **Total intäkt**
-   Länkar till ekonomiska data, vilket kan inkludera dimensionsvärden i Microsoft Dynamics 365 for Finance and Operations **Obs!** Du kan ställa in en raddefinition för att hämta data från systemet för ekonomiska dimensioner varje gång rapporten genereras.
-   Radsummor och formler som baseras på kopplade ekonomiska data.

Vanligtvis innehåller alla raddefinition innehåller en av följande typer av information:

-   Referenser till systemet för ekonomiska dimensioner
-   Summor eller beräkningar som är baserade på data
-   Formatering

Det finns två metoder för att lägga till information i en raddefinition:

-   Ange information om raden manuellt i en ny raddefinition. Mer information finns i [Ändra raddefinitionceller](modify-row-definition-cells-financial-reporting.md).
-   Använd rapportdesigner för att hämta radinformation direkt från de ekonomiska dimensionerna. Mer information hittar du i avsnittet "Relaterade formler/rader/enheter" i [Modifiera raddefinitionsceller](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a> Lägg till dimensioner i en raddefinition
En dimension är en skärningspunkt av data och värden. Du kan gruppera data och värden i rapportdesignern. Du kan sedan klassificera och analysera transaktioner mer ingående. Du kan använda dialogrutan **Infoga rader från dimensioner** om du vill lägga till flera rader i en raddefinition samtidigt. Dialogrutan visar en kolumn för varje dimension. I tabellen nedan beskrivs den typ av information som kan anges för varje dimension.

| Alternativ                | Beskrivning                                                                                                                                                                                                                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dimension             | Mönstret som identifierar den dimension du vill lägga till raddefinitionen. Detta mönster innehåller ett et-tecken (&) eller nummertecknet (\#) för varje position i dimensionerna. Rent allmänt bör du använda et-tecken för dimensionen Huvudkonto och siffertecken för alla andra dimensioner. |
| Dimensionsintervallets början | Dimensionens inledande värde som ska läggas till i raddefinitionen.                                                                                                                                                                                                                 |
| Dimensionsintervallets slut   | Det sista värdet för denna dimension för att lägga till raddefinitionen.                                                                                                                                                                                                                  |

Gör på följande sätt för att lägga till dimensioner i en raddefinition:

1.  Öppna Rapport Designer, klicka på **Raddefinitioner** och öppna sedan den raddefinition som ska modifieras.
2.  Klicka på menyn **Redigera** och klicka på **Infoga rapportenheter från dimensioner**.
3.  I dialogrutan **Infoga rader från Dimensioner**, på raden **Dimensioner**, väljer du cellen för dimensionen som ska överföras till raddefinitionen och klickar sedan på **Alla &&&**.
4.  Om du vill begränsa raddimensionen till ett specifikt intervall av dimensionsvärdena anger du startdimensionsvärdet i cellen **Dimensionsintervallstart** och skriv sedan in det avslutande dimensionsvärdet i cellen **Dimensionsintervallslut**. Om du vill inkludera alla värden för den valda dimensionen lämnar du dessa celler tomma. **Obs!** Jokertecken (\* eller ?) i dimensionsområden kan inte returnera alla resultat som du vill ha på grund av hur ERP-databasen sorterar data.
5.  Välj radkod för det första dimensionsvärdet i fältet **Startradskod** för att lägga till raddefinitionen.
6.  Ange avståndet mellan efterföljande radkoder i fältet **Öka varje rad med**. Om den första radkoden är 100 och stegvärdet är 30 har de nya raderna koderna 100, 130, 160, 190 och 220. Använd ett stegvärde som ger tillräckligt med utrymme för att infoga nya rader för format och formel.
7.  Klicka på **OK**. En rad per valt dimensionsvärde läggs till i raddefinitionen.

## <a name="adjust-rounding-in-a-row-definition"></a> Justera avrundning i en raddefinition
Om du har en balansräkning där beloppen avrundas kan det hända att summorna inte balanseras. Det här problemet kan uppstå om du exempelvis använder alternativet avrundning i en balansräkningsrapport och om även rapportdefinitionen använder avrundning. Du kan använda alternativet **Avrundningsjusteringar** i raddefinitionen för att balansera beloppen i balansräkningarna. Du kan inaktivera avrundning eller ändra den på fliken **Inställningar** i rapportdefinitionen. Följande tabell visar hur beloppen avrundas. I den här tabellen skiljer sig summorna av raderna 100 och 200, när avrundning slås på.

| Radkod | Belopp utan avrundning | Belopp med avrundning till hela tusental |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| Summa    | 7,300                    | 8                                       |

Gör på följande sätt för att justera avrundningen i en balansräkning.

1.  I Rapportdesignern, klicka på **Raddefinitioner** och öppna raddefinitionen för att ändra.
2.  Klicka på **Avrundningsjustering** på **Redigera**-menyn.
3.  I dialogrutan **Avrundningsjusteringar** anger du följande värden:
    -   **Avrundningsjusteringar** – Radkoden för raden som ska justeras för att balansera balansräkningen.
    -   **Total tillgångsrad** – radkoden för raden i balansräkningen som innehåller de totala tillgångarna.
    -   **Totala skulder och eget kapital** – Radkoden för raden i balansräkningen som innehåller totala skulder och eget kapital.
    -   **Justeringsbeloppsgräns** – Den gräns som uttrycks som ett positivt heltal och som anger gränsen för automatiska justeringar. Detta belopp jämförs med absolutvärdet för den verkliga avrundningsdifferensen.

    **Obs!** Dessa radkoder måste vara länkade till dina ekonomiska data. Med andra ord måste raden ha ett dimensionsvärde i cellen **Länk till ekonomiska dimensioner**. Referera **inte** en beskrivning (**DESC**) beräknad (**CALC**), eller summerad rad (**TOT**).

Beloppen i din balansräkning balanseras nu jämt när avrundning är aktiverad. **Obs!** Justeringsgränsen används utifrån det alternativ för **Avrundningsnoggrannhet** som anges för rapportdefinitionen. Om du till exempel väljer att avrunda rapporten till tusental och anger **2** i rutan **Justeringsbeloppsgräns** visas ett varningsmeddelande när värdet som identifieras i **Avrundningsjusteringsrad** ökar eller minskar med mer än 2 000.

## <a name="format-row-and-column-text"></a>Formatrad och kolumntext
Du kan anpassa utseendet på dina rapporter genom att ändra teckensnitt och formatera texten. Följande avsnitt innehåller information om hur du formaterar utseendet på rader och kolumner i rapporter.

### <a name="manage-font-styles"></a>Hantera teckenstilar

Du kan skapa och ändra teckensnitt för din rapport. Du kan sedan tillämpa dessa teckensnitt i dokumentet eller på en viss rad eller kolumn i en rapport.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Skapa ett teckensnitt</td>
<td><ol>
<li>I Report Designer i menyn <strong>Format</strong>klickar du på <strong>Utföranden och formatering</strong>.</li>
<li>Klicka på <strong>Ny</strong> i dialogrutan <strong>Format och formatering</strong> och ange ett unikt namn på det nya formatet.</li>
<li>Välj teckensnitt och klicka sedan på <strong>OK</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Ändra en teckenstil</td>
<td><ol>
<li>I Report Designer i menyn <strong>Format</strong>klickar du på <strong>Utföranden och formatering</strong>.</li>
<li>Markera en stil du vill ändra i dialogrutan <strong>Format och formatering</strong> och klicka sedan på <strong>Ändra</strong>.</li>
<li>Välj teckensnitt och klicka sedan på <strong>OK</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Tillämpa ett teckensnitt</td>
<td><ol>
<li>Öppna Report Designer och välj definition, kolumndefinition, sidhuvud eller sidfot och välj där sedan en eller flera celler.</li>
<li>Välj en teckenstil från listan <strong>Formatmall</strong> i verktygsfältet.</li>
</ol></td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Formatradtext

Den formatering som anges i raddefinitionen åsidosätter all formatering som anges i kolumndefinitionen och i rapportdefinitionen. Du kan ändra textformatet genom att använda kontrollerna i verktygsfältet Formatering. Dessa kontroller är standardinställda Microsoft Windows-kontroller.

1.  Öppna raddefinitionen i Report Designer för att ändra den.
2.  Välj cellerna om du vill formatera. Håll ned CTRL-tangenten medan du väljer koderna om du vill välja mer än en cell.
3.  Klicka på verktygsfältsknappen av formatet som ska användas. Om du exempelvis vill göra ett indrag på en rad ska du välja raden och klicka sedan på **Öka indrag** ![Öka indrag](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Öka indrag") i verktygsfältet.

### <a name="adjust-columns-while-you-design-reports"></a>Justera kolumner medan du utformar rapporter

För att göra det enklare att se kolumnerna som du arbetar med i raddefinitionen kan du justera bredden på en kolumn och dölja (minimera) eller visa kolumner i vyfönstret. Ändringarna påverkar enbart kolumnernas utseende på skärmen. De påverkar inte kolumnformateringen i rapporter.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Ändra bredden på en kolumn i vyfönstret

1.  Öppna raddefinitionen i Report Designer för att ändra den.
2.  På menyn **Format** väljer du **Kolumnbredd**.
3.  Ange ett värde i dialogrutan **Kolumnbredd** och klicka sedan på **OK**. Du kan även dra i den högra gränsen för kolumnrubrikcellen för att ändra kolumnens bredd.

### <a name="hide-columns-in-the-view-pane"></a>Dölj kolumner i vyfönstret

1.  Öppna raddefinitionen i Report Designer för att ändra den.
2.  Markera den kolumn eller de kolumner du vill minimera.
3.  Högerklicka och klicka sedan på **Dölj**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Visa alla dolda kolumner i vyfönstret

1.  Öppna raddefinitionen i Report Designer för att ändra den.
2.  Högerklicka på den dolda kolumnen du vill visa och klicka sedan på **Visa**.


<a name="see-also"></a>Se även
--------

[Ekonomisk rapportering](financial-reporting-intro.md)




