---
title: Spåra artiklar och råmaterial i lager, produktion och försäljning
description: I det här avsnittet beskrivs hur du kan använda artikelspårning för att identifiera var artiklar och råmaterial har använts, används eller ska användas i produktionen och försäljningsprocessen.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f45c39769b71832afe531db8a55097ede8a3c769
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562540"
---
# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Spåra artiklar och råmaterial i lager, produktion och försäljning

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kan använda artikelspårning för att identifiera var artiklar och råmaterial har använts, används eller ska användas i produktionen och försäljningsprocessen.

Artikelspårningsfunktionen är tillgänglig på **Artikelspårning** sidan. Följande avsnitt beskriver hur du kan använda artikelspårning och vilka alternativen och begränsningarna är.

## <a name="what-is-item-tracing"></a>Vad är artikelspårning?
Artikelspårning är ett Business Intelligence-verktyg (BI) som ger insyn i källan och destinationen för artiklar och råmaterial i leveranskedjan. Tillverkare kan spåra artiklar, råmaterial och ingredienser tillbaka till leverantören och vidarebefordra via produktion och försäljning av den färdiga produkten. Artikelspårning hjälper tillverkare att efterleva regelkrav, och hjälper även kvalitetstjänstemän och produktionschefer att analysera och vidta åtgärder som hanterar avvikelser i kvaliteten på produkter och material. Här av några exempel på sätten som tillverkare kan använda artikelspårning:

-   Identifiera mängden för en artikel eller ett råmaterial som finns i lager och var det lagras.
-   Fastställ hur mycket av artikeln eller råmaterial som har skickats, och till vilka kunder de har skickats till.
-   Identifiera alla planerade försändelser som innehåller artikeln eller råmaterialet.
-   Leta upp tillverkningsorder som använder artikeln eller råmaterialet, och som har planerats, pågår eller rapporterats som färdigt.
-   Ta reda på om artikeln eller råmaterialet har köpts in.
-   Utforska var en artikel eller ett råmaterial har förbrukats i produktionen av en annan artikel.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>Vad kan jag spåra, och finns det några begränsningar?
Du kan spåra historiska lagertransaktioner för artiklar och råmaterial som baseras på ett artikelnummer och en spårningsdimension, till exempel ett serienummer, ett batchnummer eller ett leverantörsbatchnummer. Du kan spåra en artikel eller ett råmaterial endast om det har en spårningsdimension tilldelad. Eftersom spårningen baseras på lagertransaktioner finns det vissa begränsningar vid spårning av artiklar. Det finns till exempel begränsningar som är relaterade till transaktioner för projekt, anläggningstillgångar och butiker. Samprodukter visas i spårningsdetaljerna, men biprodukter inkluderas inte. Spårning inkluderar alla lagerställetransaktioner från en plats till en annan. Därför kan användarna uppleva mängden information som överväldigande. Spårning visas för en juridisk person i taget. Det finns inga resurser mellan företagen i en koncernintern kontext. Du måste starta ett nytt spår för varje företag där en artikel inlevereras eller utfärdas.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>Vilka kriterier kan jag ange för en artikelspårning?
Villkoren som behövs för en artikelspårning är artikelnumret, en spårningsdimension (t.ex. ett batchnummer eller serienummer) samt riktningen. I följande tabell beskrivs de villkor som du kan använda i en artikelspårning.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fältgrupp</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Artikelnummer</td>
<td>Ange identifieringen för artikeln eller råmaterialet som du spårar.</td>
</tr>
<tr class="even">
<td>Produktdimensioner</td>
<td>Valfritt: Spåra särskilda aspekter av produktdefinitionen, till exempel en konfiguration, storlek, färg eller ett utförande.</td>
</tr>
<tr class="odd">
<td>Spåra dimensioner</td>
<td>Ange ett batchnummer, leverantörens batchnummer eller spårningsdimensionen för serienummer. När du använder batchnumret som ett kriterium visas leverantörsbatchnumret om du har samlat in denna information.</td>
</tr>
<tr class="even">
<td>Lagringsdimensioner</td>
<td>Valfritt: Spåra artiklar som har lagrats på en viss plats.</td>
</tr>
<tr class="odd">
<td>Period</td>
<td>Du kan även: Ange information för att begränsa spårning till en viss period. Spårdetaljerna visar bara dokument och transaktioner som har skapats mellan dessa datum.</td>
</tr>
<tr class="even">
<td>Framåt eller bakåt</td>
<td>Välj riktningen för spåret. Du kan spåra framåt eller bakåt:
<ul>
<li><strong>Bakåt</strong> – Spåra nedströms för att identifiera källan, tillgänglig kvantitet och eventuella produktionsorder som åtminstone delvis har rapporterats som slutförda.</li>
<li><strong>Framåt</strong> – Spåra uppströms för att identifiera målet. Du kan hitta försäljningsorder och vilka kunder som den spårade artikeln eller råmaterial minst delvis har skickats till.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>Vilken information ingår i spårningsdetaljerna?
Resultatet av en spårning visas i kronologisk ordning i trädet på snabbfliken **Detaljer** på sidan **Artikelspårning**. Ordningen varierar beroende på spårriktningen. Detaljerna inkluderar alla transaktioner från inköpet av artikeln från leverantören till försäljningen av artikeln till kunden. Spårresultat innehåller även interimprodukter som hör till artikeln eller spårningsdimensionen, som angetts i spårvillkoren. Toppnoden visar det antal artiklar, i lagerenheter, som återstår i lager baserat på de lagerdimensioner som registrerats i spårningskriterierna. **Obs!** Spårningsdetaljerna ger en ögonblicksbild av den information som fanns tillgänglig när spårningen genomfördes. Spårningsdetaljerna är inte uppdaterade om informationen ändrats efter att spårningen genomfördes.

## <a name="why-dont-some-nodes-contain-any-details"></a>Varför har inte en del noder alla detaljer?
För att minska mängden information i spårningsdetaljerna, innehåller bara noden för den första instansen av artikeln eller råmaterialet information. Om en vald nod inte innehåller detaljer kan du visa noden som innehåller detaljer genom att klicka på **Gå till spårad rad**. Du kan sedan återvända till noden som du lämnat genom att klicka på **Gå tillbaka**.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>Kan jag visa endast en viss typ av dokument? Kan jag till exempel visa endast tillverkningsorder, kunder eller leverantörer?
Ja, från spårningsdetaljerna du kan öppna listsidor som endast innehåller en viss typ av dokument eller transaktion. Du öppnar dessa sidor från **Spårning**-menyobjektet i åtgärdsfönstret, i grupperna **Artikel**. **Försäljning**, **Inköp**, **Produktion**och **Kvalitet**. Om du till exempel vill visa en lista med leverantörer i spårningsdetaljerna klickar du på **Spårning** &gt; **Inköp** &gt; **Leverantörer**. Listsidorna sammanfattar dokumenten eller transaktionerna från spårdetaljerna. Listsidorna **Pågående transaktioner**, **Väntande order** och **Försäljningsorder som inte har levererats** visar också annan information som inte inkluderas i spårdetaljerna. De visar alltid resultat för aktuellt datum, oavsett om ett datumintervall har angetts. I tabellen nedan beskrivs de ytterligare detaljer som dessa sidor kan innehålla.

| Listor                    | Beskrivning                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Försäljningsorder som inte har levererats | Visa försäljningsorderrader som inte har plockats, och därför inte visas i spårningsdetaljerna.                                                                                                                                                                                                                        |
| Väntande order           | Visa alla väntande tillverkningsorder för den spårade artikeln, oavsett spårningsdimensionerna som användes spårningskriterierna. Du kan också visa väntande tillverkningsorder där den spårade artikeln är en ingrediens, och inga registreringar har gjorts, och inga transaktioner har rapporterats som färdiga för ordern. |
| Pågående transaktioner     | Visa väntande lagertransaktioner för den spårade artikeln som innehåller de angivna spårningsdimensionerna eller en tom spårningsdimension. Du kan också visa väntande lagertransaktioner för artiklar och spårningsdimensionskombinationer eller ett blankstegs värde, i spårdetaljerna.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>Hur många nivåer kan jag spåra upp eller ned i en strukturlista eller formel?
Du kan spåra upp eller ned en nivå i en strukturlista eller en formel. Om till exempel du kör en spårning för råmaterial, kan du se den färdiga produkten och eventuella samprodukter. Om du däremot spårar en samprodukt inkluderar spårdetaljerna inte den färdiga produkten.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>Hur kan jag visa mer information om ett dokument eller en transaktion i spårdetaljerna?
På snabbfliken **Detaljer** kan du visa mer information om ett valt dokument eller en transaktion i spårningsdetaljerna på två sätt:

-   När du väljer en nod i spårdetaljerna på snabbfliken **Detaljer** visar de andra snabbflikarna på sidan information om dokumentet eller transaktionen i noden.
-   Öppna sidan med information för dokumentet i en vald nod genom att klicka på **Visa detaljer**. Om du till exempel väljer en nod som beskriver en produktionsorder och du klickar på **Visa detaljer** visas sidan **Produktionsorderdetaljer**.

Vissa snabbflikar ger dig åtkomst till ytterligare information om den valda noden. På snabbfliken **Avvikelser** kan du till exempel undersöka om det finns historik över avvikelser genom att klicka på **Förfrågningar**. På snabbfliken **Batch** kan du klicka på **Lista med behållning** om du vill visa mängden fysiskt lager som för tillfället är tillgängligt, och alla lagertransaktioner som gäller batchen.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>Kan jag köra mer än en spårning och sedan jämföra detaljerna?
När du har kört spårningen kan du använda följande alternativ på knappen **Spåra från nod** för att köra en ny spårning för transaktionen i den valda noden:

-   **Bakåt** eller **Framåt** – Starta en ny spårning för den valda noden och skriv över information om den aktuella spårningen.
-   **Ny bakåt** eller **Ny framåt** – Starta en ny spårning i ett nytt fönster och spara information om den aktuella spårningen.

Om du vill använda alternativen **Ny bakåt** eller **Ny framåt** måste du använda funktionen **Öppnar i ett nytt fönster** för att ett nytt spår ska visas i ett nytt fönster.

## <a name="can-i-save-the-trace-details"></a>Kan jag spara spårningsdetaljerna?
Du kan spara informationen på fliken <strong>Detaljer</strong> som en XML-fil genom att klicka på <strong>Exportera</strong> under åtgärden *<strong><em>Spårning</em></strong>* i åtgärdsfönstret. Förutom spårningsdetaljerna, XML-filen innehåller även spårningskriterier, överordnad nod och lagerbehållning. Möjligheten att spara information om en spårning är användbar, till exempel om du vill bekräfta informationen till en kvalitetsorder eller annan efterlevnadsdokumentation. Du kan ange där filen sparas. Markera alternativet <strong>Visa dokument</strong> om du vill visa filen direkt. <strong>Obs!</strong> Filen sparas alltid, även om du endast vill visa den. Som standard öppnas XML-filen i ett webbläsarfönster. Du kan dock högerklicka på filen, välja <strong>Öppna med</strong> och sedan välja programmet som ska användas för att visa innehållet.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>Kan jag beräkna saldo för en viss artikel eller ingrediens?
Du kan exportera informationen från de samlingssidor till Microsoft Excel. Öppna den aktuella sidan, klicka på **Öppna i Microsoft Office**-ikonen och välj sedan **Exportera till Microsoft Excel**. Den här funktionen är särskilt användbar när du vill beräkna ett klumpsaldo för en artikel eller ingrediens från sidan **Transaktioner**. På sidan **Sammanfattning av transaktioner** kan du filtrera på artikeln eller ingrediensen, och alternativt även på batchen, och sedan exportera informationen till Excel. I Excel kan du till exempel isolera lagerbehållningen, kvantiteten som sålts och den mängd som användes i produktionen.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>Kan jag se historik över problem med artiklar och råmaterial?
Spårningsdetaljerna innehåller information om kvalitetsorder och avvikelser som gäller råmaterial eller artikeln. Du kan visa en sammanfattning av kvalitetsorder och avvikelser genom att klicka på **Kvalitetsorder** eller **Avvikelser** i åtgärdsfönstret. **Obs!** Destruktiva kvalitetsorder kan visas mer än en gång i spårningsdetaljerna. När en destruktiv kvalitetsorder skapas för ett dokument, till exempel en inköpsorder, visas den för varje transaktion för dokumentet.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>Finns det några rapporteringsmöjligheter för artikelspårning?
Du kan generera rapporten **Levererade till kunder** när du vill identifiera mängden för den artikel eller råmaterial som har levererats och vilka kunder som den har skickats till. För en förfrågan, som gäller efterlevnad kan du generera rapporten för alla kunder. För en förfrågan som gäller kundservice kan du generera rapporten för en vald kund. Om produkten var ett råmaterial som användes i produktionen av en färdig artikel, inkluderas även den färdiga artikeln. **Obs!** Om du använder funktionerna för att ta bort eller arkivera försäljningsorder, inkluderar rapportresultaten också eventuella försäljningsorder som har tagits bort eller arkiverats.

## <a name="can-i-trace-coproducts-and-byproducts"></a>Kan jag spåra samprodukter och biprodukter?
Du kan spåra samprodukter, men du kan inte spåra en biprodukt eftersom spårningsdimensioner vanligtvis inte tilldelas till biprodukter. När du spårar en artikel omfattar spårningsdetaljerna alla relaterade samprodukter. En nod som innehåller en samprodukt inkluderar ordet ”samprodukt” i detaljerna. Du kan även visa information om en samprodukt genom att välja noden i spårningsdetaljerna och sedan klicka på snabbfliken **Produktion**.
