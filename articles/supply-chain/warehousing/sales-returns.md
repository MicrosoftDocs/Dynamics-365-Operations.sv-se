---
title: Försäljningsreturer
description: Det här avsnittet innehåller information om processen för returorder. Det innehåller information om kundreturer och deras effekt på kostnadsredovisning och lagerbehållningskvantiteter.
author: omulvad
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnTable, ReturnTableListPagePreviewPane, ReturnTableReferences, SalesReturnExpiredOrdersPart, SalesReturnFindOrderFormPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d460cab24ca73d43a0f055c5f65791968841e472
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835520"
---
# <a name="sales-returns"></a>Försäljningsreturer

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om processen för returorder. Det innehåller information om kundreturer och deras effekt på kostnadsredovisning och lagerbehållningskvantiteter.

Kunder kan returnera artiklar av olika skäl. Till exempel kan en artikel ha fel eller den uppfyller inte kundens förväntningar. Processen startar när en kund utfärdar en begäran att returnera en artikel. När en kunds begäran har tagits emot skapas en returorder.

## <a name="return-order-process"></a>Returorderprocess
Följande bild ger en översikt över returorderprocessen.  

[![Returorderprocess](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Det finns två typer av returorder: fysisk retur och endast kreditering.

-   **Fysisk retur** – returordern auktoriserar fysiska returer av produkterna.
-   **Endast kreditering** – returordern auktoriserar en kundkredit men kräver inte att kunden ska returnera produkterna fysiskt.

### <a name="physical-return-order-process"></a>Orderprocess för fysisk retur

1.  **Skapa en returorder.** Dokumentera formellt auktoriseringen för kunden att returnera alla felaktiga eller oönskade produkter. Returordern kräver inte att företaget godkänner returnerade produkter eller ger kunden en kredit. Om returen har godkänts auktoriserar du att en ersättningsartikel skickas innan den felaktiga artikeln har returnerats.
2.  **Anländer till lagret för inspektion.** Slutför en inledande inspektion och verifiering mot returorderdokumentet. Returordern stöder också karantän för de returnerade artiklarna för ytterligare inspektion och kvalitetskontroll.
3.  **Bestäm disposition.** Avsluta inspektionsprocessen och bestäm vad som ska göras med de returnerade produkterna. Som en del av detta steg bestämmer du om du vill kreditera kunden, avvisa produktreturen eller godkänna produktreturen, kassera produkten och sedan skicka en ersättningsprodukt till kunden.
4.  **Skapa följesedel.** Skapa en följesedel och genomför det dispositionsbeslut som du angav i steg 3. Slutför de logistika processerna.
5.  **Skapa en faktura.** Stäng returordern.

### <a name="credit-only-process"></a>Process för Endast kreditering

1.  **Skapa en returorder.** Dokumentera formellt auktoriseringen för kunden att få en kredit utan att returnera de felaktiga eller oönskade produkterna. Dispositionskoden **Endast kreditering** godkänner beslutet att kreditera kunden utan fysisk retur.
2.  **Skapa en faktura.** Skapa kreditfakturan och stäng sedan returordern.

## <a name="return-material-authorization"></a>RMA-nummer (Return Materials Authorization)
Bearbetning av RMA-nummer (Return Materials Authorization) bygger på funktioner för försäljningsorder. En RMA registreras som en returorder som skaps som en försäljningsorder och kan ha en annan försäljningsorder kopplad till den som kallas en ersättningsorder. Båda försäljningsorder länkar till det ursprungliga RMA-numret.

-   **Returorder** – om du vill registrera en RMA skapar du en returorder som är en försäljningsorder som har den tilldelade typen **Returorder.** De ändringar som du gör i RMA-informationen uppdateras automatiskt i försäljningsordern. Tills returordern har statusen **Öppen** visas den inte i listan över försäljningsorder. Du använder RMA för att hantera införsel och inleverans av returnerade artiklar, samt att godkänna en dispositionsåtgärden för Eendast kreditering (se avsnitt **Ddispositionskoder och dispositionsåtgärder**). Alla andra uppföljningsprocesser måste hanteras i försäljningsordern.
-   **Ersättningsorder** – när en ersättningsorder måste levereras till kunden kan RMA innehålla en andra kopplad försäljningsorder. Du kan manuellt skapa en ersättningsorder för RMA för stöd för omedelbar leverans. Alternativt kan ersättningsordern skapas automatiskt efter att införsel, inspektion och inleverans slutförs för RMA radartikeln med en dispositionskod som indikerar ersättning. Ersättningsordern fungerar på samma sätt som när den är kopplad till en försäljningsorder. Du kan exempelvis använda den till att konfigurera en anpassad produkt som ersättningsartikeln, skapa en produktionsorder för att reparera en returnerad artikel, skapa en inköpsorder för direktleveranser för att skicka ersättningen från en leverantör eller ge stöd till andra ändamål.

## <a name="create-a-return-order"></a>Skapa en returorder
Returorderprocessen startar när en kund kontaktar organisationen för att returnera en felaktig eller oönskad produkt och/eller som ska krediteras. När organisationen har accepterat returen kan returen dokumenteras av en returorder. Returordern blir fokuspunkt för den interna bearbetningen av den returnerade produkten. Följande bild visar proceduren för att skapa en returorder.  

[![Proceduren för att skapa en returorder](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Skapa en ny returorderrubrik.

Informationen i tabellen nedan måste inkluderas när du skapar en returorder.

| Fält              | beskrivning                                              | Kommentarer                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kund-ID   | En referens till kundens tabell                       | Du måste ange ett befintligt kundkonto.                                                                                                                                                                                                                                                                                                  |
| Leveransadress   | Adressen som artikeln returneras till                 | Organisationens adress används som standard. Om ett specifikt lagerställe har valts i rubriken, ändras leveransadress till lagerställets leveransadress. Du kan ändra den här adressen på sidan **Returorderdetaljer**.                                                                                                  |
| Plats/lagerställe     | Platsen eller lagerstället som tar emot den returnerade produkten | Leveransadressen för returordern bestäms utifrån leveransadressen för platsen eller lagerstället.                                                                                                                                                                                                                                 |
| RMA-nummer         | Det ID som har tilldelats returorden              | RMA-numret används som en alternativ nyckel under hela returorderprocessen. RMA-numret som tilldelas baseras på den RMA-nummersekvens som ställdes in på sidan **Parametrar för kundreskontra**.                                                                                                                              |
| Deadline           | Det senaste datumet då en artikel kan returneras.               | Standardvärdet beräknas från dagens datum plus giltighetsperioden. Om en retur är giltigt i endast 90 dagar från det datum då returordern skapas och returordern skapades den 1 maj är värdet i fältet exempelvis **30 juli**. Giltighetsperioden är inställd på sidan **Parametrar för kundreskontra**. |
| Returorsakskod | Kundorsaken för retur av produkten          | Orsakskoden markeras i listan med användardefinierade orsakskoder. Du kan uppdatera det här fältet när som helst.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Skapa returorder

När du har slutfört returrubriken kan du skapa returrader med någon av följande metoder:

-   Ange manuellt artikelinformation, kvantitet och annan information för varje returraden.
-   Skapa en returrad med hjälp av funktionen **Sök efter försäljningsorder**. Vi rekommenderar att du använder den här funktionen när du skapar en returorder. Funktionen **Söka efter försäljningsorder** upprättar en referens från returraden till den fakturerade försäljningsorderraden och hämtar radinformation som t.ex artikelnummer, kvantitet, pris, rabatt och kostnadsvärden från försäljningsraden. Referensen hjälper till att garantera att produkten när den returneras till företaget har samma styckkostnad som den såldes till. Referensen kontrollerar även att returorder inte skapas för en kvantitet som överstiger den kvantitet som har såldes på fakturan.

>Obs! Returrader som har en referens till en försäljningsorder hanteras som korrigeringar till eller återföringar av försäljningen. Mer information finns i avsnittet ”Bokför i redovisningen" senare i det här avsnittet.

### <a name="charges"></a>Debiteringar

Avgifter kan läggas till returordern genom en eller flera av följande metoder:

-   Du kan manuellt lägga till avgifter till returorderrubriken, returorderraden eller båda.
-   Avgifterkan läggas till automatiskt till returorderrubriken som en funktion av returorsakskoden.
-   Avgifter kan läggas till automatiskt till returorderraden baserat på radens dispositionskod.

Avgifter läggs till automatiskt efter att en returorsakskod eller dispositionskod kopplas till raden. Om orsakskoden ändras senare kommer den befintliga avgiftsposten inte att tas bort, utan en ny avgift läggs automatiskt till, baserat på den nya orsakskoden. När du lägger till avgifter till returorderraderna blir avgifterna som beräknas som en procentandel av raden eller ordervärdet negativt om raden eller radordern är negativ, såvida inte procentandelen också är ett negativt tal. En avgift som har ett negativt värde motsvarar en kredit till kunden.

### <a name="return-reason-codes"></a>Returorsakskoder

Genom att använda orsakskoder för returer, kan du göra det lättare att analysera returmönster. Orsakskoder innehåller information om varför en kund vill returnera artiklar. Vissa organisationer har flera orsakskoder. Dessa organisationer kan gruppera orsakskoderna till orsakskodgrupper för att få en bättre översikt och för ackumulerad rapportering.

### <a name="disposition-codes-and-disposition-actions"></a>Dispositionskoder och dispositionsåtgärder

Ett viktigt steg i returorderprocessen är att tilldela en dispositionskod till returorderraden som en del av införselregistreringen. Dispositionskoden anger följande information:

-   **De finansiella konsekvenserna** – ska kunden krediteras de returnerade artiklarna och ska eventuella avgifter läggas till på returorderraden?
-   **Dispositionskoder för den returnerade artikeln** – ska artikeln läggas tillbaka på lagret, ska den kasseras eller ska den returneras till kunden?
-   **Överföringen av den returnerade artikeln** – ska en ersättningsartikel utfärdas till kunden?

Förutom att avgöra hur returvarorna avyttras kan dispositionskoder medföra att avgifter ska tillämpas på returraden. De kan också användas för att gruppera returer för statistisk analys. Dispositionskoder definieras som en del av inställningarna för returorder. Men varje dispositionskod måste referera till en av de inbyggda dispositionsåtgärderna. I följande register finns de inbyggda dispositionskoderna och deras åtgärder. **Viktigt:** om en artikel inte ska returneras, men kunden ska fortfarande krediteras tilldelar du dispositionskoden **Endast kreditering** till returraden.

<table>
<thead>
<tr class="header">
<th>Dispositionskod</th>
<th>Finansiella konsekvenser</th>
<th>Konsekvenser för logistik</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Endast kreditering</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Förlust från kassering av artikeln bokförs i redovisningen.</li>
</ul></td>
<td>Artikeln ska inte returneras. Den här dispositionsåtgärden används i följande fall:
<ul>
<li>Det finns tillräckligt med förtroende mellan parterna.</li>
<li>Kostnaden för att returnera den felaktiga artikeln är mycket hög.</li>
<li>Artiklarna kan inte gå tillbaka till lagret. På grund av andra villkor krävs inte en fysisk retur.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kredit</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Lagervärdet ökas med kostnaden för den returnerade artikeln.</li>
</ul></td>
<td>Artikeln returneras och läggs tillbaka i lagret.</td>
</tr>
<tr class="odd">
<td>Ersätt och kreditera</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Lagervärdet ökas med kostnaden för den returnerade artikeln.</li>
<li>En särskild försäljningsorder för en ersättning skapas och hanteras separat.</li>
</ul></td>
<td>Artikeln returneras och läggs tillbaka i lagret.</td>
</tr>
<tr class="even">
<td>Ersätt och kassera</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Förlust från kassering av artikeln bokförs i redovisningen.</li>
<li>En särskild försäljningsorder för en ersättning skapas och hanteras separat.</li>
</ul></td>
<td>Artikeln returneras och kasseras.</td>
</tr>
<tr class="odd">
<td>Returnera till kund</td>
<td>Ingen, förutom eventuella avgifter eller kostnader.</td>
<td>Artikeln returneras men skickas tillbaka till kunden efter inspektion. Den här dispositionsåtgärden kan användas om artikeln har skadats avsiktligt eller om garantin har annullerats.</td>
</tr>
<tr class="even">
<td>Kassation</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Förlust från kassering av artikeln bokförs i redovisningen.</li>
</ul></td>
<td>Artikeln returneras eller kasseras.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Införsel till lagret för inspektion
Innan du fysiskt kan ta emot returnerade artiklar i lagret genom att bokföra en följesedel, måste artiklarna genomgå införselregistrering och en valfri inspektion. Följande bild ger en översikt över införselprocessen. Avsnitten som följer beskriver varje steg som visas i bilden.  

[![Införselprocess](./media/salesreturn03.png)](./media/salesreturn03.png)  

Processen har flera varianter som inte tas upp i det här avsnittet. Här följer några exempel på sådana varianter.

-   Använd inte listan **Införselöversikt** om du vill skapa en införseljournal. Skapa i stället införseljournalen manuellt. Returorder kommer att ha **Försäljningsorder** som referens.
-   Om du använder lagerstyrning genererar du lastpallstransporter. Returraden måste ha statusvärdet **Infört** under lastpallstransport.
-   Registrera införsel av den returnerade artikeln direkt från en returorderrad med hjälp av funktion **Registrering**.

Under införselprocessen integreras returer i den allmänna processen för lagerställeinförsel. Inleveransprocessen ger också stöd för karantänorder för returnerade artiklar som måste genomgå en särskild kontroll.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identifiera produkter i listan Införselöversikt

Sidan **Införselöversikt** visar alla planerade inkommande införslar. 
>Obs! Införsel från returorder måste behandlas separat från andra typer av införseltransaktioner. När du har identifierat ett inkommande paket på sidan **Införselöversikt** (t.ex. med hjälp av det medföljande RMA-dokumentet) klickar du på **Starta införsel** i åtgärdsfönstret för att skapa och initiera en införseljournal som matchar införseln.

### <a name="edit-the-arrival-journal"></a>Redigera införseljournalen

Genom att ange alternativet **Karantänhantering** till **Ja** kan du skapa en karantänorder för returraden. Om en rad har skickats i karantän för inspektion, kan du inte ange en dispositionskod. 
 
Om du anger alternativet **Karantänhantering** till **Ja** i artikelns lagermodellgrupp kommer alternativet **Karantänhantering** på sidan **Journalrader** att markeras för införseljournalraden och kan inte ändras. Om raden skickas i karantän, måste du ange lämpligt karantänlagerställe. 

Om införselraden inte har skickats till inspektion måste införselansvarige på lagerstället ange dispositionskoden direkt på införseljournalraden och därefter bokföra införseljournalen. Om samma dispositionskod inte ska tilldelas till hela kvantiteten av returraden eller om hela kvantitetn på raden inte har inlevererats, måste du dela upp raden. När du delar upp en införseljournalrad delar du även upp returraden (**SalesLine**) och skapar ett nytt parti-ID. Du kan dela upp raden genom att minska kvantiteten av införseljournalraden. När journalen är bokförd skapas en ny returrad med statusen **Förväntade** för resterande kvantitet. Du kan också dela upp raden genom att klicka på **Funktioner** &gt; **Dela upp**.

### <a name="process-the-quarantine-order"></a>Bearbeta karantänordern

Om de returnerade produkterna skickas till inspektion på karantänlagerstället, slutförs eventuella ytterligare bearbetning i en karantänorder. En karantänorder skapas för varje införselraden som skickas till karantän. Dispositionskoden anger resultatet av inspektionsprocessen. 

Du kan dela upp en karantänorder på samma sätt som du kan dela upp införseljournalen. Om du delar upp karantänordern orsakar du en motsvarande delning av returraden. När dispositionskoden har angetts slutför du karantänordern genom att använda antingen funktionen **Slut** eller funktionen **Rapportera som färdig**. Om du väljer **Rapportera som färdig** skapas en ny införsel i det angivna lagerstället. Sedan kan du bearbeta denna införsel med hjälp av sidan **Införselöversikt**. 

Om införseln härstammar från en karantänorder kan du inte ändra dispositionskoden som tilldelas under inspektion. Om du slutför karantänordern med hjälp av funktionen **Slut** kommer partiet att registreras automatiskt. Ibland kan en artikel skickas tillbaka från karantän till avdelningen för Leverans och inleverans. Exempelvis kanske karantäninspektören inte vet var du ska placera artikeln i lagret. I detta fall måste motsvarande följesedel uppdateras på rätt sätt och hanteras med dispositionskoden som anges på grund av karantänen. 

Bekräftelsebrev kan skickas till kunden när returraden registreras. Rapporten **Returbekräftelse** liknar returorderdokumentet. Rapporten **Returbekräftelse** är inte journalförd eller på annat sätt registrerad i systemet och det är inte ett obligatoriskt steg i returorderprocessen.

## <a name="replace-a-product"></a>Ersätta en produkt
Det finns två metoder för hantering av produktersättning:

-   **Direkt ersättning** – Ersätta en produkt innan den returnerade produkten tas emot av kunden.
-   **Ersättning av dispositionskoden** – skapa automatiskt en ny ersättningsorderrad.

### <a name="up-front-replacement"></a>Direkt ersättning

I direkt ersättning ska ersättningsartikeln levereras till kunden innan artikeln returneras. Den här metoden är användbar om artikeln till exempel är en maskindel som inte kan tas bort om det inte finns en reservdel som ersätter den eller om du bara vill att kunden ska ha ersättningsprodukten så snart som möjligt. Direkt ersättning är en oberoende försäljningsorder. Rubrikinformationen initieras från kunden och radinformationen initieras från returordern. Du kan bearbeta, redigera och ta bort ersättningsordern oberoende av returordern. När du raderar en ersättningsorder får du ett meddelande att ordern skapades som en ersättningsorder. Följande bild visar processen för direkt ersättning.  

![Process för direkt ersättning](./media/SalesReturn04.png)

Returordern innehåller en referens till ersättningsordern. Om en direkt ersättningsorder har skapats för en returorder innan den felaktiga artikeln returneras kan inte välja dispositionskoder för ersättning efter att felaktiga artiklar har returnerats.

### <a name="replacement-by-disposition-code"></a>Ersättning genom dispositionskod

Om du levererar en ersättningsartikel till kunden och använder dispositionsåtgärden **Ersätt och kassera** eller **Ersätt och kreditera** på returordern, använder du processen som visas i följande bild.  

![Ersättningsprocess när en dispositionskod används](./media/SalesReturn05.png)

Ersättningsartikeln levereras med hjälp av en oberoende försäljningsorder, ersättningsförsäljningsordern. Den här försäljningsordern skapas när packsedeln för returordern skapas. Orderrubriken använder information från kunden som refereras till i returorderrubriken. Radinformationen hämtas från informationen som registreras på sidan **Ersättningsartikel**. Sidan **Ersättningsartikel** måste fyllas i för rader som har dispositionsåtgärder som börjar med ordet "Ersätt". Emellertid valideras eller begrämsas varken kvantiteten eller ersättningsartikelns identitet. Det här beteendet gör det möjligt för ärenden där kunden vill ha samma artikel, men i en annan konfiguration eller storlek samt ärenden där kunderna vill ha en helt annan artikel. Som standard anges en identisk artikel på sidan **Ersättningsartikel**. Men du kan välja en annan artikel förutsatt att funktionen har ställts in. 

>Obs! Du kan redigera och ta bort ersättningsförsäljningsordern när den har skapats.

## <a name="generate-a-packing-slip"></a>Skapa en följesedel
Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den order som artiklarna tillhör. Liksom fakturauppdateringsprocessen är uppdateringen av den ekonomiska transaktionen, uppdateringen av följesedeln den fysiska uppdateringen av lagerposten. Med andra ord genomför den här processen ändringar i lagret. Vid returer implementeras stegen som tilldelas dispositionsåtgärden under uppdateringen av följesedeln. När du genererar följesedeln inträffar följande händelser:

-   På lagerstället används standardprocessen för att utföra en fysisk inleverans. Redovisningsbokföring genereras om lagermodellgruppen (**Bokför fysiskt lager**) och parametrar för kundreskontra (**Bokför följesedel i redovisningen**) anges korrekt.
-   Artiklar som har markerats med en dispositionsåtgärd som innehåller ordet "kassation" och lagerbrist bokförs i redovisningen.
-   Artiklar som har markerats med dispositionsåtgärden **Returnera till kund** inlevereras och levereras till kunden. Dessa artiklar har ingen nettoeffekt på lagret.
-   En ersättningsförsäljningsorder skapas. Denna försäljningsorder baseras på informationen på sidan **Ersättningsartikel**.

Du kan endast generera följesedeln för rader som har returstatusen **Registrerade** och endast för hela kvantiteten på returraden. Om flera rader på returordern har statusen **Registrerad** kan du generera följesedeln för en delmängd av rader genom att ta bort de andra raderna från sidan **Bokför följesedel**. 

Delvisa returer definieras i termer av returorderrader, inte i termer av returorderleveranser. Om du därför inlevererar hela kvantiteten som anges på en returorderrad men du får inte får något inlevererat från de andra raderna på returordern anses leveransen inte vara en delleverans. Om en returorderrad kräver att 10 enheter av en artikel ska returneras, men du du bara får fyra inlevererade enheter är leveransen en delleverans. Om inte alla förväntade returnerade artiklar har införts, kan du lägga leveransen åt sidan och vänta in resten av den returnerade kvantiteten. Alternativt kan du registrera och bokföra delkvantiteten. Som en del av processen för att bokföra följesedlar kan du koppla följesedelns referensnummer från kundens leveransdokument till orderraderna. Denna koppling är valfri och är endast för referens. Den skapar inga transaktionsuppdateringar. 

Generellt sett kan du hoppa över följesedelprocessen och gå direkt till fakturering. I så fall slutförs stegen som du skulle ha utfört under genereringen av följesedeln vid fakturering.

## <a name="generate-an-invoice"></a>Generera en faktura
Även om sidan **Returorder** innehåller den information och de åtgärder som krävs för att kunna hantera returorderns speciella logistiska spekter måste du använda sidab **Försäljningsorder** för att slutföra faktureringsprocessen. Organisationen kan sedan fakturera returorder och försäljningsorder samtidigt och samma person som kan genomföra faktureringsprocessen efter behov. Om du vill visa returordern från sidan **Försäljningsorder** klickar du på länken för försäljningsordernumret för att öppna den kopplade försäljningsordern. Returordern finns också på sidan **Alla försäljningsorder**. Returorder är försäljningsorder som har ordertypen **Returnerad order**.

### <a name="credit-correction"></a>Kreditkorrigering

Kontrollera att alla övriga avgifter är korrekta som en del av faktureringsprocessen. För att redovisningsbokföringar ska bli korrigeringar (Storno) bör du använda alternativet **Kreditera korrigering** på fliken **Övriga** på sidan **Bokföring av faktura** när du bokför fakturan/kreditfakturan. 
>Obs! Som standard aktiveras alternativet **Kreditkorrigering** om alternativet **Kreditfaktura som korrigering** på sidan **Parametrar för kundreskontra** har aktiverats. Vi rekommenderar dock att du inte bokför returer med Storno.

## <a name="create-intercompany-return-orders"></a>Skapa koncerninterna returorder
Returorder kan slutföras mellan två företag inom din organisation. Följande scenarier stöds:

-   Enkla koncerninterna returer mellan två företag som deltar i en koncernintern relation
-   En koncernintern kedja som upprättas när en kundreturorder skapas i det säljande företaget
-   En koncernintern kedja som upprättas när en leverantörsreturorder skapas i det inköpande företaget
-   Direktleverans returnerar mellan en extern kund och två företag som deltar i en koncernintern relation

### <a name="setup"></a>Inställningar

Följande bild visar de basinställningar som krävs för två företag att delta i en koncernintern relation och dra nytta av koncernintern handel.  

![Basinställningar](./media/SalesReturn06.png)

I följande scenario är CompBuy det inköpande företaget och CompSell är det säljande företaget. Vanligtvis levererar det säljande företaget varor till det inköpande företaget eller, vid direktleveransscenarier direkt till slutkunden. I CompBuy definieras leverantören IC\_CompSell som en koncernintern slutpunkt som är associerad med företaget CompSell. Samtidigt definieras kunden i CompSell, IC\_CompSell som en koncernintern slutpunkt som är associerad med företaget CompBuy. Lämplig åtgärdspolicyinformation och värdemappningar måste definieras i båda företagen. I scenariot direktleverans skapas en koncernintern returorder som också är en koncernintern försäljningsorder i det säljande företaget. RMA-numret för den koncerninterna returordern kan plockas från RMA-nummerserien i CompSell eller så kan den kopieras från RMA-numret som har tilldelats till den ursprungliga returordern i CompBuy. RMA-nummerinställningarna i åtgärdspolicyn **Inköpsrekvisition** avgör dessa åtgärder. Om RMA-numret synkroniseras bör du planera att minska risken för en konflikt av nummersammanstötningar om de två företagen använder samma nummerserie.

### <a name="simple-intercompany-returns"></a>Enkla koncerninterna returer

Scenariot innebär två företag i samma organisation, vilket visas i följande illustration.  

![Enkel koncernintern retur](./media/SalesReturn07.png)

Orderkedjan kan upprättas när en leverantörs returorder skapas i det inköpande företaget eller en kundreturorder skapas i det säljande företaget. Motsvarande order skapas i det andra företaget och ser till att rubrik- och radinformationen på leverantörsreturordern reflekterar inställningarna för kundens returorder. Returordern som har upprättats kan inkludera eller utesluta referensen (**Sök efter försäljningsorder**) till en befintlig kundfaktura. Följesedlar och fakturor för de två order kan behandlas separat. Du behöver inte skapa en följesedel för returordern för leverantören innan du genererar följesedeln för returordern.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Direktleverans returnerar mellan tre parter

Det här scenariot kan fastställas om föregående försäljning av typen **Direktleverans** har slutförts och om en faktura mot kunden finns i företaget som samverkar med kunden. I följande bild har företaget CompBuy tidigare sålt och fakturerat produkter till kunden externt. Produkterna har levererats direkt från företagets CompSell via en koncernintern orderkedja.  

![Direktleverans returnerar mellan tre parter](./media/SalesReturn08.png)

Om kunden Extern vill returnera produkterna, skapas en returorder (RMA02) för kunden i företaget CompBuy. Om du vill skapa den koncerninterna kedjan måste returordern markeras för direktleverans. När du använder funktionen **Sök efter försäljningsorder** för att plocka kundfakturan till retur kommer en koncernintern orderkedja som består av följande dokument att upprättas:

-   **Ursprunglig returorder:** RMA02 (företaget CompBuy)
-   **Inköpsorder:** PO02 (företag CompBuy)
-   **Koncernintern returorder:** RMA\_00032 (företaget CompSell)

När du har skapat den koncerninterna kedjan för direktleverans måste all fysisk hantering och bearbetning a returer infalla i sammanhanget för den koncerninterna returordern RMA\_00032 i företaget CompSell. Produkterna kan inte tas emot i företaget CompBuy. När en dispositionskod har tilldelats den koncerninterna returordern kan den synkroniseras med den ursprungliga returordern för att tillåta rätt fakturering av den ursprungliga ordern.

## <a name="post-to-the-ledger"></a>Bokför i redovisningen
Redovisningsbokföringar som genereras när returordern faktureras påverkas av några viktiga inställningar och parametrar:

-   **Retursjälvkostnad** – för andra lagermodeller än **Standardkostnad**, avgör parametern **Retursjälvkostnad** kostnaden för artikeln när den har godtagits tillbaka till lagret eller kasserats. Om du vill beräkna en korrekt värdering av lagret är det viktigt att du anger parametern **Retursjälvkostnad** på rätt sätt. Om du använder funktionen **Sök efter försäljningsorder** för att skapa en returorderrad som har en referens till en kundfaktura, är värdet **Retursjälvkostnad** lika med självkostnaden för artikeln som säljs. Annars hämtas värdet självkostnad från artikelinställningen eller anges manuellt.
-   **Kreditkorrigering/Storno** – Parametern **Kreditkorrigering** på sidan **Bokföring av faktura** avgör om transaktionerna ska vara registrerade som positiva poster (DR/k) eller som korrigerande negativa poster.

I exemplen nedan representeras retursjälvkostnaden av **Lagerkostnadspris**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Exempel 1: Returordern refererar inte till en kundfaktura

Returordern refererar inte till en kundfaktura. Den returnerade artikeln krediteras. Parametern **Kreditkorrigering** markeras inte när returorderfakturan eller kreditfakturan genereras.  

![Returordern refererar inte till en kundfaktura](./media/SalesReturn09.png)  

>Obs! Artikelns huvudpris används som standardvärde för parametern **Retursjälvkostnad**. Standardpriset skiljer sig från självkostnaden vid tidpunkten för lagerutleveransen. Därför är implikationen att en förlust på 3 har uppkommit. Dessutom innehåller inte returordern rabatten som gavs till kunden på försäljningsordern. Därför uppstår en alltför stor kredit.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Exempel 2: Kreditkorrigering markeras för returordern

Exempel 2 är samma som exempel 1, men parametern **Kreditkorrigering** parametern väljs när returorderfakturan genereras.  

![Returordern där kreditkorrigering markeras  ](./media/SalesReturn10.png)  

>Obs! Redovisningsbokföringar anges som negativa korrigeringar.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Exempel 3: Returorderraden skapas med hjälp av funktionen Sök efter försäljningsorder

I det här exemplet skapas returorderraden med hjälp av funktionen **Sök efter försäljningsorder**. Parametern **Kreditkorrigering** inte är markerad när fakturan skapas.  

![Returorderraden skapas med hjälp av funktionen Sök efter försäljningsorder  ](./media/SalesReturn11.png)  

>[Obs!] **Rabatt** och **Retursjälvkostnad** är korrekt inställda. Därför uppstår en exakt återföring av kundfakturan.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]