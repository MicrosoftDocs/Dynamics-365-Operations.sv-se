---
title: Sammanfoga lagerbatchar
description: Den här artikeln innehåller information om hur du konsoliderar två eller flera lagerbatchar till en sammanfogad batch.
author: pjacobse
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4c9443c6e659602ae09e4744396651186874ad3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008026"
---
# <a name="merge-inventory-batches"></a>Sammanfoga lagerbatchar

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om hur du konsoliderar två eller flera lagerbatchar till en sammanfogad batch.

När du sammanslår batchar kan beräkningar hjälpa dig att optimera egenskaperna och batchattribut för den sammanslagna batchen. När källbatcharna har valts kan den sammanfogade batchen granskas och ändras innan den bokförs. Du kan även överföra batchsammanfogningen till en lagerjournal för godkännande. Lagret kan sedan reserveras eller bokföras direkt från den aktuella lagerjournalen. När du bokför en sammanslagen batch, justeras lager för källbatcharna och den sammanslagna batchen.

## <a name="are-there-any-prerequisites"></a>Finns det några förutsättningar?
Ja finns ingen saker som du måste ställa in, innan du kan använda sammanfogningbatchverktygen. I följande tabell beskrivs förutsättningarna.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sida</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Journalnamn, Lager</td>
<td>Du måste skapa ett journalnamn av typen Strukturlista som används som standard när du bokför batch-sammanslagningar i lagerjournaler. Valfritt, men rekommenderas: Du kan ange att reservationer ska göras automatiskt när batchsammanfogningen överförs till lagerjournalen. Annars finns det en risk att en ändring görs i lagerbehållningen efter att batchsammanfogningsdetaljerna har ställts in och journalen har bokförts. Om du vill aktivera automatiska reservationer för journalnamnet väljer du <strong>Automatisk</strong> i fältet <strong><strong>Reservation</strong></strong>.</td>
</tr>
<tr class="even">
<td>Parametrar för hantering av lager och lagerstyrning</td>
<td>Du måste ange standardjournalnamnet som ska användas för lagerjournalen.</td>
</tr>
<tr class="odd">
<td>Frisläppta produkter</td>
<td>De rekommenderade inställningarna för artikeln är:
<ul>
<li>För att automatiskt generera batchnummer för sammanslagna batchar, måste du tilldela den frisläppta produkten till en batchnummergrupp. Du kan också ange en batch numret manuellt, när du skapar en sammanslagen batch, eller markerar ett befintligt batchnummer. Om du väljer ett befintligt batchnummer, måste du kontrollera att den valda batchen inte har inkluderats i en lagertransaktion.</li>
<li>Om du använder hållbarhetstid eller bäst före-datum för den frisläppta produkten, kommer datumen för en sammanslagen batch beräknas baserat på valet i fältet <strong>Databeräkning för batchsammanfogning.</strong> Följande alternativ är tillgängliga:
<ul>
<li><strong>Tidigast</strong> – Beräkningen baseras på det tidigaste datumet som angetts för en källbatch som väljs för batchsammanfogningen.</li>
<li><strong>Senast</strong> – Beräkningen baseras på det senaste datumet som angetts för en källbatch som väljs för batchsammanfogningen.</li>
<li><strong>Manuell</strong> – Ingen beräkning görs. Om ett datum är samma för alla källbatcher föreslås ett datum. Du kan ändra datumet. Om ett datum inte är samma för källbatcherna kan du ange datumet manuellt.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Batchnummergrupp</td>
<td>Valfritt: Om du vill generera ett batchnummer när du skapar en sammanslagen batch måste du tilldela en batchnummergrupp till den frisläppta produkten. I annat fall kan du ange ett batchnummer manuellt.</td>
</tr>
</tbody>
</table>

## <a name="when-might-i-want-to-merge-batches-of-inventory"></a>När kan jag vilja sammanslå batchar med lagret?
Här är några exempel på scenarier när det är praktiskt att sammanslå batchar:

-   Sammy går omkring på sitt lagerställe och upptäcker att det finns flera batchar med samma artikel som har låga kvantiteter. Han räknar med att få flera nya leveranser, och han inser att han kan frigöra lite golvutrymme genom att sammanslå de udda kvantiteterna till en ny batch.
-   Sammy tar emot lager och vill kombinera den nya batchen med en som han redan har tagit emot för att förbättra batchattributvärdet för den befintliga batchen. Därigenom skapar du en ny batch.

## <a name="can-i-merge-batches-across-sites-and-legal-entities"></a>Kan jag sammanslå batchar mellan webbplatser och juridiska personer?
Nej, du kan bara sammanslå batchar som har samma plats och lagerdimensioner för en juridisk person. Du kan dock ange en annan plats och lastpalls-ID för den sammanslagna batchen.

## <a name="can-i-merge-partial-quantities"></a>Kan jag sammanslå delvisa kvantiteter?
Nej, du kan endast sammanslå den fullständiga kvantiteten för batchar. Batchsammanfogningsfunktionen är avsedd som en lagerfunktion, inte en produktionsfunktion.

## <a name="what-if-the-batches-have-different-batch-attribute-values"></a>Vad händer om batcharna har olika batchattributvärden?
När du väljer källbatcharna som du vill kombinera i den sammanslagna batchen kommer Supply Chain Management att verifiera om egenskaper eller attributvärden är samma för alla batchar. När ett attributvärde är detsamma, föreslås ett värde för den sammanslagna batchen. Du kan ändra detta värde. Attributvärden som inte är desamma lämnas tomma för den sammanslagna batchen och du kan ange dessa värden manuellt. Om batchattributtypen för attributvärdet är ett heltal eller en del, och värdena inte är identiska för alla källbatcher, kommer värdet att beräknas med hjälp av en beräkning av viktat medelvärde. Det beräknade värdet avrundas uppåt eller nedåt till närmaste steg. Om värdet är tomt för en källbatch, är batchen och dess kvantitet inte med i beräkningen. **Exempel** I följande exempel visas en viktad genomsnittsberäkning för en sammanslagen batch. Två av källbatcherna har ett tomt värde för ett batchattributtyp som är ett heltal. Följande attribut tilldelas källbatcherna.

| Attribut | Minimum | Stegvis | Maximal |
|-----------|---------|-----------|---------|
| Grad     | 3       | 3         | 30      |

Källbatcharna har följande attributvärden för batchattributet **Grad**.

| Batch | Kvantitet | Attribut | Attributvärde |
|-------|----------|-----------|-----------------|
| B1    | 10       | Grad     | Tom           |
| B2    | 15       | Grad     | 15              |
| B3    | 20       | Grad     | 20              |
| B4    | 25       | Grad     | Tom           |
| B5    | 30       | Grad     | 25              |

När du lägger till dessa batchar som källbatchar kommer den sammanslagna batchen att tilldelas följande värden.

| Batch | Kvantitet | Attribut | Attributvärde |
|-------|----------|-----------|-----------------|
| B6    | 100      | Grad     | 21              |

Värdena och kvantiteterna för batcharna B1 och B4 tas inte med i beräkningen av det viktade medelvärdet. Därför beräknas värdet för den sammanslagna batchen på följande sätt.

| Värde | Kvantitet (vikt)                              | Relativ vikt | Relativ vikt × värde                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15    | 15                                             | 0.230769231     | 3.461538462                                                           |
| 20    | 20                                             | 0.307692308     | 6.153846154                                                           |
| 25    | 30                                             | 0.461538462     | 11.53846154                                                           |
|       | **Summa:** 65, vilket är summan av vikterna |                 | **Summa:** 21,5384615, vilket avrundas till 21 (den närmaste ökningen). |

## <a name="what-if-the-batches-have-different-batch-dates"></a>Vad händer om batcharna har olika batchdatum?
Om batcharna har olika batchdatum är några av datumen beräknade baserat på värdena i gruppen på **Batchdatum** på snabbfliken **Sammanfogad batch** på sidan **Batchsammanfogning**. Systemet beräknar värdena för fälten i gruppen **Batchdatum**. Dessa värden inkluderar tillverkningsdatum, utgångsdatum, datummärkning och bäst före-datum. Datumen beräknas utifrån inställningarna för artikeln i fältgruppen **Artikeldata** på sidan **Information om frisläppt produkt**. Du kan ändra värdena eller ange dem manuellt. För alla andra datum görs ingen beräkning. Samma princip används för batchattributvärden. Om ett datum är identiskt för alla källbatchar kommer detta datum föreslås för den sammanslagna batchen. Om datumet inte är identiskt för alla källbatchar är datumet tomt för den sammanslagna batchen och du kan ange det manuellt.

## <a name="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge"></a>Vad händer om dimensionerna är olika på batchar som jag vill sammanslå?
Produktdimensioner, spårningsdimensioner och lagringsdimensioner hanteras på följande sätt:

-   **Produktdimensioner** – Alla produktdimensioner för den valda artikeln måste vara samma. Du kan inte sammanslå batchar över produktdimensioner.
-   **Spåra dimensioner** – Ett nytt batchnummer skapas automatiskt om en batchnummergrupp anges för artikeln. Om en batchnummergrupp inte tilldelas till en artikel kan du välja en befintlig batch eller ange numret manuellt. Serienummer överförs från källbatchen till lagerjournalraderna för den sammanslagna batchen.
-   **Lagringsdimensioner** - Dimensioner för plats och lager måste vara desamma för alla källbatchar och den sammanslagna batchen. Du kan dock ange ny plats och lastpalls-ID för den sammanslagna batchen.

## <a name="how-does-posting-work"></a>Hur fungerar bokföring?
Bokföring fungerar på två sätt beroende på om du använder en godkännandeprocess för journaler. Du kan använda åtgärderna **Överför till journal** och **Bokför batchsammanfogningen** om du vill överföra batchsammanfogningen till en journal där den kan bekräftas och bokföras, eller så kan du bokföra batchsammanfogningen direkt. Huvudskillnaden mellan de två åtgärderna är att överföring till en journal inte bokför batchsammanfogningen. Båda åtgärderna gör att en ny batch skapas (om en befintlig batch inte är markerad), alla batchdetaljer och attributvärden uppdateras och att en lagerjournal skapas.

-   **Överför till journal** – Överför batchsammanfogningsinformationen till en ny lagerjournal. Om du har ställt in automatiska reservationer, reserveras kvantiteterna i källbatcherna. Information om batchsammanfogningen kan inte ändras. Om du vill ändra batchsammanfogningen måste du ta bort journalen. Journalen kan användas som en uppgift som en annan medarbetare måste utföra senare. En reservering av batchkvantiteten säkras till journalraden. Denna allokering låter en kvalitetsplanerare eller en lagerställechef skapa uppgifter för sina medarbetare.
-   **Bokför batchsammanfogningen** – Bokför batchsammanfogningen direkt. Den här åtgärden kan utföras efter att den fysiska sammanfogningen har inträffat.

Du kan godkänna lagerjournalen för batchsammanfogningen från listsidan **Alla batchsammanfogningar**. Klicka på **Journal** &gt; **Bokför**. När en journal är bokförd kan du inte ändra informationen i den sammanfogade batchen. När du har överfört en batchsammanfogning till en lagerjournal kan du bara ändra informationen om journalen har tagits bort.

## <a name="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal"></a>Varför visas inte faktisk/nominell vikt i lagerjournalen efter att jag slagit ihop en fångstviktartikel?
Du kan sammanslå batchar med fångstviktartiklar precis som alla andra artiklar. Dock visas information om faktisk/nominell vikt inte i lagerjournalen. Vi rekommenderar att du kontrollerar information om faktisk/nominell vikt innan du överför batchsammanfogningen till lagerjournalen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]