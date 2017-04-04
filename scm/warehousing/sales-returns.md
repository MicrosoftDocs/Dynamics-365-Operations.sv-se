---
title: "Försäljningsreturer"
description: "Det här avsnittet innehåller information om processen för returorder. Den innehåller information om returer från kunder och deras effekt på lagerkvantiteter kostnadsredovisning och lagerbehållning."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Försäljningsreturer

Det här avsnittet innehåller information om processen för returorder. Den innehåller information om returer från kunder och deras effekt på lagerkvantiteter kostnadsredovisning och lagerbehållning.

Kunder kan returnera artiklar av olika skäl. Till exempel en artikel kan vara fel eller det uppfyller inte kundens förväntningar. Processen startar när en kund begär ska returnera en artikel. En returorder skapas i Microsoft Dynamics 365 för åtgärder när kundens begäran mottas.

## <a name="return-order-process"></a>Returordern
Bilden nedan ger en översikt över processen för returordern.  

[![salesreturns01](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Det finns två typer av returordern: fysisk tillbaka och endast kredit.

-   **RETUR fysiska** – returordern auktoriserar fysiska RETUR av produkterna.
-   **Kreditera endast** – returordern auktoriserar en kundkredit men inte kräver att kunden ska returnera produkterna fysiskt.

### <a name="physical-return-order-process"></a>Fysiska returordern.

1.  **Skapa en returorder.** Formellt dokument tillståndet för kunden ska returnera några oönskade eller felaktiga produkter. Returordern kräver inte att företaget Godkänn returnerade produkter eller en kredit för kunden. Om återlämnande har godtagits auktoriserar du en ersättningsartikel skickas före defekta artiklar som har returnerats.
2.  **Anländer till lagret för inspektion.** Slutföra en inledande kontroll och verifiering mot returordern. Returordern stöder också karantän för de returnerade artiklarna för ytterligare inspektion och kvalitetskontroll.
3.  **Bestäm hur.** Avsluta processen inspektion och bestämma vad som ska göras med de returnerade produkterna. Bestäm om du ska kreditera kunden Produktretur, avvisa eller acceptera produkt returnera, kassera produkten och skicka till kunden en ersättningsprodukt tillsammans med det här steget.
4.  **Skapa en följesedel.** Skapa en följesedel och genomför beslut dispositionskoder som du angav i steg 3. Slutför logistik processer.
5.  **Generera en faktura.** Stäng returordern.

### <a name="credit-only-process"></a>Bearbeta endast kredit

1.  **Skapa en returorder.** Formellt dokument tillståndet för kunden som ska få en kredit utan att returnera oönskade eller felaktiga produkter. Den **kreditera endast** dispositionskod tillåter beslutet att kreditera kunden utan fysisk RETUR.
2.  **Generera en faktura.** Generera kreditfakturan och stäng sedan returordern.

## <a name="return-material-authorization"></a>Return material authorization
Returnera Material returnummer (RMA) bearbetning bygger på funktionerna för försäljningsordern. En RMA registreras som en returorder som har skapats som en försäljningsorder och ha en annan försäljningsorder som är kopplad till den kallas en ersättningsorder. Både försäljningsorder länka till ursprungligt RMA-numret.

-   **Returorder** – om du vill registrera en RMA du skapar returordern, som är en försäljningsorder som har tilldelade typen **returneras ordern.** De ändringar som du gör i informationen RMA uppdateras automatiskt i försäljningsordern. Tills returordern har statusen **öppna**, visas inte i listan med försäljningsorder. Du använder RMA införsel och inleverans av returnerade artiklar ska hanteras, samt ge dispositionsåtgärden endast kredit (se avsnitt **dispositionskoder och hur åtgärder**). Uppföljning processer hanteras i försäljningsordern.
-   **Ersättningsorder** – när en ersättningsorder måste levereras till kunden, RMA kan innehålla andra berörda försäljningsordern. Du kan manuellt skapa en ersättningsorder för RMA för omedelbar leverans. Du kan också kan ersättningsordern skapas automatiskt när införsel, inspektion och inleveransen utförs för RMA radartikeln med en dispositionskod som visar byte. Ersättningsordern fungerar på samma sätt som är kopplad till en försäljningsorder. Du kan exempelvis använda den att konfigurera en anpassad produkt som ersättningsartikeln, skapa en produktionsorder för att reparera en returnerad artikel, skapa en inköpsorder för direktleveranser skicka ersättning från en leverantör eller stöd för andra ändamål.

## <a name="create-a-return-order"></a>Skapa en returorder
Returorderprocessen startar när en kund kontaktar organisationen returnerar en defekt eller oönskade produkt och/eller som ska krediteras. När organisationen har accepterat returen kan dokumenteras returen av en returorder. Returordern blir fokuspunkt interna bearbetningen av den returnerade produkten. Följande illustration visar proceduren för att skapa en returorder.  

[![Proceduren för att skapa en returorder](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Skapa en returorderhuvudet

Informationen i tabellen nedan måste inkluderas när du skapar en returorder.

| Fält              | beskrivning                                              | Kommentarer                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kund-ID   | En referens till tabellen Kunder                       | Du måste ange ett befintligt kundkonto.                                                                                                                                                                                                                                                                                                  |
| Leveransadress   | Adressen som artikeln returnerades till                 | Organisationens adress används som standard. Om ett specifikt lagerställe valts i huvudet, ändras leveransadress till leveransadressen för lagerstället. Du kan ändra den här adressen i den **returorderdetaljer** sida.                                                                                                  |
| Site, lagerställe     | Platsen eller lagerstället som tar emot den returnerade produkten | Leveransadressen för returordern bestäms utifrån leveransadressen på webbplatsen eller lagerställe.                                                                                                                                                                                                                                 |
| RMA-nummer         | ID som tilldelas till returordern              | RMA-numret används som en alternativ nyckel under hela detta förlopp returordern. RMA-numret som tilldelas utifrån RMA nummerserien som är inställd på den **parametrar för kundreskontra** sida.                                                                                                                              |
| Deadline           | Det senaste datum då en artikel kan returneras.               | Standardvärdet beräknas från dagens datum plus giltighetsperioden. Om en RETUR är giltigt endast 90 dagar från det datum då returordern skapas och returordern skapades den 1 maj värdet i fältet är exempelvis **30 juli**. Giltighetsperioden är inställd på den **parametrar för kundreskontra** sida. |
| Returorsakskod | Kundens orsaken returnerar produkten          | Orsakskoden markeras i listan med användardefinierade orsakskoder. Du kan använda detta fält när som helst.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Skapa returorderrader

När du har slutfört returnerade rubriken Skapa du returrader med någon av följande metoder:

-   Ange information om artikeln, kvantitet och annan information för varje returraden manuellt.
-   Skapa en returrad med hjälp av den **söka efter försäljningsorder** funktion. Vi rekommenderar att du använder den här funktionen när du skapar en returorder. Den **söka efter försäljningsorder** funktion upprättar en referens från returraden till fakturerade försäljningsorderraden och hämtar rad t.ex artikelnummer, kvantitet, pris, rabatt och kostnadsvärden från försäljningsraden. Referensen kan garantera att när produkten returneras till företaget, det har värderas till samma styckkostnad som den såldes vid. Referensen kontrollerar att returnerar order inte skapas för en kvantitet som överstiger den kvantitet som har sålts på fakturan.

**Anmärkning:** returrader som har en referens till en försäljningsorder ska hanteras som korrigeringar eller återföringar av försäljningen. Mer information finns i avsnittet "Post i redovisningen" senare i det här avsnittet.

### <a name="charges"></a>Debiteringar

Avgifter kan läggas till returordern genom ett eller flera av följande metoder:

-   Du kan manuellt lägga till tillägg returorderhuvudet, returorderraden eller båda.
-   Tillägg kan vara läggs automatiskt till returorderhuvudet som en funktion av returorsakskoden.
-   Tillägg kan läggas till returorderraden, baserat på dispositionskoden för raden automatiskt.

Tillägg läggs till automatiskt efter en returorsakskod eller dispositionskod är kopplade till raden. Om orsakskoden ändras senare, den befintliga posten med tillägget tas inte bort och bifoga ett nytt automatiskt, baserat på den nya orsakskoden. När du lägger till tillägg på orderraderna returnera bli avgifter som beräknas som en procentandel av värdet för raden eller order negativt om linjen eller raden ordern är negativ, såvida inte procentandelen är också ett negativt tal. En avgift som har ett negativt värde motsvarar en kredit till kunden.

### <a name="return-reason-codes"></a>Returorsakskoder

Genom att använda orsakskoder för returer, kan du göra det lättare att analysera returnera mönster. Orsakskoder innehåller information om varför en kund vill returnera artiklar. Vissa organisationer har flera orsakskoder. Dessa företag kan gruppera orsakskoderna till grupper med orsakskoder för att få en bättre översikt och för ackumulerat rapportering.

### <a name="disposition-codes-and-disposition-actions"></a>Dispositionskoder och hur åtgärder

Ett viktigt steg i processen returordern är att tilldela en dispositionskod till returorderraden under registrering anländer. Dispositionskoden anger följande information:

-   **De finansiella konsekvenserna** – kunden redovisas för de returnerade artiklarna och eventuella avgifter tillföras returorderraden?
-   **Dispositionskoder för den returnerade artikeln** – artikeln kan ska lägga till lager bör det kasseras eller den returneras till kunden?
-   **Överföringen av den returnerade artikeln** – en ersättningsartikel utfärdas till kunden?

Förutom avgöra hur returvarorna avyttras kan dispositionskoder medföra avgifter ska kopplas till returraden. De kan också användas för att gruppera returer för statistisk analys. Dispositionskoder definieras som en del av inställningarna för returorder. Men måste varje dispositionskod referera till en av de inbyggda dispositionskoder åtgärderna. Tabellen nedan innehåller inbyggda dispositionskoder och deras funktioner. **Viktigt:** om inte en artikel ska returneras, men redovisas fortfarande kunden, tilldela den **kreditera endast** dispositionskod till returraden.

<table>
<thead>
<tr class="header">
<th>Dispositionskod</th>
<th>Ekonomiska konsekvenser</th>
<th>Konsekvenser för logistik</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Endast kreditering</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Förlust från kassera artikeln bokförs i redovisningen.</li>
</ul></td>
<td>Artikeln ska inte returneras. Den här dispositionsåtgärden används i följande fall:
<ul>
<li>Det finns tillräckliga förtroende mellan parterna.</li>
<li>Kostnaden för att skicka tillbaka den defekta artiklar är mycket hög.</li>
<li>Objekten får inte tillbaka till lagret. På grund av andra villkor en fysisk RETUR behövs inte efter uppgraderingen.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kredit</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Lagervärdet ökas med kostnaden för den returnerade artikeln.</li>
</ul></td>
<td>Artikeln returneras och läggs till lagret.</td>
</tr>
<tr class="odd">
<td>Ersätt och kreditera</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Lagervärdet ökas med kostnaden för den returnerade artikeln.</li>
<li>En särskild försäljningsorder för en ersättning skapas och hanteras separat.</li>
</ul></td>
<td>Artikeln returneras och läggs till lagret.</td>
</tr>
<tr class="even">
<td>Ersätt och kassera</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Förlust från kassera artikeln bokförs i redovisningen.</li>
<li>En särskild försäljningsorder för en ersättning skapas och hanteras separat.</li>
</ul></td>
<td>Artikeln har returnerats och kasseras.</td>
</tr>
<tr class="odd">
<td>Returnera till kund</td>
<td>Ingen, förutom eventuella avgifter eller kostnader.</td>
<td>Artikeln returneras men skickas tillbaka till kunden efter slakt. Den här dispositionsåtgärden kan användas om artikeln har skadats avsiktligt eller om garantin har annullerats.</td>
</tr>
<tr class="even">
<td>Kassation</td>
<td><ul>
<li>Kunden krediteras försäljningspriset minus eventuella avgifter eller kostnader.</li>
<li>Förlust från kassera artikeln bokförs i redovisningen.</li>
</ul></td>
<td>Artikeln returneras eller kasseras.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Ankomst till lagerstället för inspektion
Innan du kan ta emot returnerade artiklar fysiskt i lagret genom att bokföra en följesedel, måste artiklarna genomgå införselregistrering och valfria inspektion. Bilden nedan ger en översikt över införselprocessen. I avsnitten som följer beskriver varje steg som visas i bilden.  

[![Inleveransprocess](./media/salesreturn03.png)](./media/salesreturn03.png)  

Processen har flera variationer som inte tas upp i det här avsnittet. Här följer några av dessa ändringar:

-   Använd inte den **Införselöversikt** listan om du vill skapa en införseljournal. I stället manuellt skapa införseljournalen. Order ska ha **försäljningsorder** som referens.
-   Om du använder lagerstyrning kan generera lastpallstransporter. Returraden måste ha statusvärdet för **infört** under lastpallstransport.
-   Registrera inleverans av returnerade artikeln direkt från en returorderrad kan med hjälp av den **registrering** funktion.

Returnerar under införsel är integrerade i den allmänna processen för införsel av lagerställe. Inleveransprocess också tillåter karantänorder för returnerade artiklar som måste genomgå en särskild undersökning.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identifiera produkter i listan för införsel – översikt

Den **Införselöversikt** sidan visas planerade inkommande införsel. **Anmärkning:** införsel från returorder behandlas separat från andra typer av transaktioner för införsel. När du har identifierat ett inkommande paket på den **Införselöversikt** sidan (t.ex, med hjälp av följedokumentet RMA) i åtgärdsfönstret genom att klicka på **starta införsel** att skapa och initiera en införseljournal som matchar skiftet.

### <a name="edit-the-arrival-journal"></a>Redigera införseljournalen

Genom att ange den **karantän management** att **Ja**, kan du skapa en karantänorder för returraden. Om en rad har skickats i karantän för inspektion, kan du inte ange en dispositionskod. **Obs!** om du anger den **karantän management** att **Ja** i artikelns lagermodellgrupp, den **karantän management** alternativet på den **journalrader** markeras för införseljournalraden och kan inte ändras. Om raden skickas i karantän, måste du ange lämpliga karantänlagerstället. Om införselraden har inte skickats för granskning, lagerställe införsel clerk anger dispositionskoden direkt på införseljournalraden och bokföra införseljournalen. Om samma dispositionskod inte ska tilldelas till hela kvantiteten av returraden eller om hela antalet på raden har inlevererats, måste du dela upp raden. När du delar en införseljournalraden också delas returraden (**SalesLine**) och skapa ett nytt parti-ID. Du kan dela upp raden genom att minska antalet införseljournalraden. När journalen är bokförd skapas en ny returrad med statusen **förväntade** för resten av antalet. Du kan också dela upp raden genom att klicka på **funktion**&gt;**dela**.

### <a name="process-the-quarantine-order"></a>Bearbeta karantänordern

Om de returnerade produkterna skickas på inspektion på karantänlagerstället, hanteras några andra processer i en karantänorder. En karantänorder skapas för varje införselraden skickas i karantän. Dispositionskoden anger resultatet av processen inspektion. Du kan dela upp en karantänorder på samma sätt som du kan dela införseljournalen. Om du delar upp karantänordern orsaka en motsvarande delning av returraden. Slutför karantänordern genom att skriva efter dispositionskoden anges den **slut** funktion eller **rapportera som färdig** funktion. Om du väljer **rapportera som färdig**, skapas en ny införsel i det bestämda lagret. Sedan kan du bearbeta denna införsel med hjälp av den **Införselöversikt** sida. Om ankomst som härstammar från en karantänorder, kan du inte ändra dispositionskoden som tilldelas under kontroll. Om du slutför karantänordern med hjälp av den **slut** funktion, partiet registreras automatiskt. Ibland kan en artikel skickas tillbaka från karantänen till skeppning och inleverans avdelning. Exempelvis kanske karantäninspektören inte vet var du ska placera artikeln i lagret. I detta fall måste motsvarande följesedel uppdateras på rätt sätt och hanteringen av dispositionskoden anges på grund av karantänen. Bekräftelsebrev kan skickas till kunden när returraden registreras. Den **returbekräftelse** rapporten liknar returordern. Den **returbekräftelse** rapporten inte är journalförda eller på annat sätt registrerade i systemet och det är inte ett obligatoriskt steg i processen för returordern.

## <a name="replace-a-product"></a>Ersätta en produkt
Det finns två metoder för hantering av Produktutbyte:

-   **Direkt ersättning** – Ersätt en produkt innan den returnerade produkten tas emot från kunden.
-   **Ersättning av dispositionskoden** – automatiskt skapa en ny orderrad byte.

### <a name="up-front-replacement"></a>Direkt ersättning

I direkt ersättning ska ersättningsartikeln levereras till kunden innan artikeln returneras. Den här metoden är användbar om artikeln är till exempel en maskindel inte kan tas bort om det finns en reservdel som ersätter eller om du bara vill att kunden ska ha ersättningsprodukten så snart som möjligt. Direkt ersättning är en oberoende försäljningsorder. Informationen i huvudet initieras från kunden och radinformationen initieras från returordern. Du kan bearbeta, redigera och ta bort ersättningsordern oberoende av returordern. När du raderar en ersättningsorder får meddelande du ett som ordern skapades som en ersättningsorder. Följande bild visar hur direkt ersättning.  

[![Direkt ersättning process](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

Returordern innehåller en referens till ersättningsorder. Om en order direkt ersättning har skapats för en returorder innan den defekta artiklar returneras kan välja du inte dispositionskoder för ersättning efter defekta artiklar som har returnerats.

### <a name="replacement-by-disposition-code"></a>Dispositionskod tillämpning

Om du levererar en ersättningsartikel till kunden och använder det **Ersätt och kassera** eller **Ersätt och kreditera** dispositionsåtgärden på returordern, använda som visas i följande bild.  

[![Byte-processen när en dispositionskod används](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

Ersättningsartikeln levereras med hjälp av en oberoende försäljningsorder försäljningsorder för ersättningsartiklar. Den här försäljningsordern skapas när packsedeln för returordern skapas. Orderrubriken använder information från kunden som refereras i returorderhuvudet. Radinformationen hämtas från informationen som registreras på den **ersättningsartikeln** sida. Den **ersättningsartikeln** sida måste fyllas i för rader som har dispositionskoder åtgärder som börjar med ordet "Ersätt". Dock varken kvantiteten identiteten för ersättningsartikeln valideras eller begränsad. Problemet gör det möjligt för fall där kunden vill ha samma objekt, men i en annan konfiguration eller storlek samt fall där kunderna vill ha ett helt annat objekt. Som standard anges en identisk artikel på de **ersättningsartikeln** sida. Men kan du välja ett annat objekt, förutsatt att funktionen har ställts in. **Anmärkning:** du kan redigera och ta bort försäljning ersättningsorder skapas.

## <a name="generate-a-packing-slip"></a>Skapa en följesedel
Innan returnerade artiklar kan föras in i lagret, måste du uppdatera följesedeln för den ordning som objekten tillhör. Liksom fakturauppdateringsprocessen är en uppdatering för den slutliga transaktionen, följesedeln den fysiska uppdateringen av lagerposten är. Med andra ord genomför proceduren ändras lagret. Steg som har kopplats till dispositionsåtgärden vid returer implementeras under följesedeln uppdateringen av följesedeln. När du genererar följesedeln inträffar följande händelser:

-   Standardprocessen för att utföra fysiska inleverans i distributionslagret. Redovisningsbokföringar genereras om lagret modell grupp (**Bokför fysiskt lager**) och parametrar för Kundreskontra (**Bokför följesedel i redovisningen**) anges korrekt.
-   Kasserade artiklar som har märkts med dispositionsåtgärden som innehåller ordet "kassation" och lagerbrist bokförs i redovisningen.
-   Artiklar som har märkts med den **returnera till kund** dispositionsåtgärden tas emot och levereras till kunden. Dessa artiklar påverkar inte net lager.
-   En ny försäljningsorder skapas. Denna försäljningsorder baseras på informationen i den **ersättningsartikeln** sida.

Du kan generera följesedeln bara för rader som har returnerade statusen **registrerade**, och endast för hela kvantiteten på returraden. Om flera rader på en returorder har den **registrerade** kan du generera följesedeln för en delmängd av rader genom att radera raderna från den **Bokför följesedel** sida. Partiell returnerar definieras i termer av returorderrader, inte när det gäller leveranser för returordern. Om du tar emot den fullständiga kvantiteten som anges på en returorderrad men du får inget från de andra raderna på returordern anses kan därför inte en delleverans leveransen. Om en returorderrad kräver att 10 enheter av en artikel ska returneras, men du får bara fyra enheter, dock leveransen en delleverans. Om du inte förväntade returnerade artiklar som har anlänt, kan du lägga leveransen åt sidan och vänta in resten av den returnerade kvantiteten. Alternativt kan du registrera och bokföra delkvantiteten. Du kan associera referensnumret från kundens leveransdokumenten med orderraderna som del av processen för bokföring av följesedlar. Denna koppling är valfria och används bara som referens. Det skapar inte några transaktionsuppdateringar. Generellt sett kan du hoppa över följesedelns följesedeln processen och gå direkt till fakturering. I så fall utförs på sätt som du skulle ha utfört under generering av följesedeln vid fakturering.

## <a name="generate-an-invoice"></a>Generera en faktura
Även om den **returorder** sidan som innehåller den information och de åtgärder som krävs för att kunna hantera de logistiska viktigt returordern, måste du använda de **försäljningsorder** Slutför faktureringsprocessen. Organisationen kan sedan fakturera returorder och försäljningsorder samtidigt och samma person som kan genomföra faktureringsprocessen efter behov. Så här visar du returordern från den **försäljningsorder** klickar du på länken för försäljningsordernummer att öppna den kopplade försäljningsordern. Returordern kan också finns på den **alla försäljningsorder** sida. Returnera order är order som har en ordertyp för **returneras order**.

### <a name="credit-correction"></a>Kreditkorrigering

Kontrollera att alla tillägg är korrekta med faktureringsprocessen. Så att redovisningsbokföringar blir korrigeringar (Storno) bör du använda de **kreditera korrigering** alternativet på den **andra** på fliken i den **bokföring av faktura** när du bokför fakturan/kreditfakturan. **Obs!** som standard den **korrigering kreditera** alternativet aktiveras om den **kreditfaktura som korrigering** alternativet på den **parametrar för kundreskontra** sida har aktiverats. Vi rekommenderar dock att du inte bokföra returnerar med Storno.

## <a name="create-intercompany-return-orders"></a>Skapa koncerninterna returorder
Returorder kan utföras mellan två företag inom din organisation. Följande scenarier stöds:

-   Enkel koncerninterna returer mellan två företag som deltar i en koncernintern relation
-   En koncernintern kedja som upprättas när en kund returorder skapas i det säljande företaget
-   En koncernintern kedja som upprättas när en leverantör returorder skapas i det inköpande företaget
-   Direktleverans försändelsen returnerar mellan två företag som deltar i en koncernintern relation och en extern kund

### <a name="setup"></a>Inställningar

Inställningen för minsta nedan som krävs för två företag att delta i en koncernintern relation och dra nytta av koncernintern handel.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

I följande scenario CompBuy är det inköpande företaget och CompSell är det säljande företaget. Vanligtvis levererar det säljande företaget varor till det inköpande företaget eller, vid direktleverans leveransen direkt till slutkunden. I CompBuy leverantörens Koncerninterna\_CompSell är definierad som en koncernintern slutpunkt som är associerade med CompSell. Samtidigt i CompSell kundens Koncerninterna\_CompBuy är definierad som en koncernintern slutpunkt som är associerade med CompBuy. Lämpliga åtgärder principinformationen och värdemappningarna måste definieras i båda företagen. I scenariot leverans en direktleverans skapas en koncernintern returorder som också är en koncernintern försäljningsorder skapas, i det säljande företaget. RMA-numret för den koncerninterna returordern kan plockas från nummerserien RMA i CompSell men den kan kopieras från RMA-numret som har tilldelats till den ursprungliga returordern i CompBuy. RMA nummer inställningarna på de **inköpsrekvisition** i CompBuy åtgärdspolicyn avgöra dessa åtgärder. Om synkroniseras RMA-numret, bör du planera minska risken för en konflikt nummer om de två företagen använder samma nummerserie.

### <a name="simple-intercompany-returns"></a>Enkel koncerninterna returer

Scenariot innebär två företag i samma organisation, vilket visas i följande illustration.  

[![Enkel koncernintern RETUR](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

Orderkedjan kan upprättas när en leverantör returorder skapas i det inköpande företaget eller en kund returorder skapas i det säljande företaget. Dynamics 365 för åtgärder som säkerställer att sidhuvud och radinformation för leverantören returnerar order motsvarar inställningarna på kunden returorder skapas motsvarande order i det andra företaget. Returordern har upprättats kan inkludera eller utesluta referensen (**söka efter försäljningsorder**) till en befintlig kundfaktura. Följesedlar och fakturor två order kan behandlas separat. Du behöver inte skapa en följesedel för returordern leverantör innan du genererar för returordern kundens följesedeln.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Direktleverans försändelsen returnerar mellan tre parter

Det här scenariot kan fastställas om föregående försäljning av den **direktleverans** typ har slutförts och om en faktura mot kunden finns i företaget som samverkar med kunden. I följande bild, har företaget CompBuy tidigare sålts och fakturerats produkter till Pågående externt. Produkterna har levererats direkt från företagets CompSell med en koncernintern orderkedja.  

[![Direktleverans försändelsen returnerar mellan tre parter](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Om Extern kunden vill returnera produkterna, skapas en returorder (RMA02) för kunden i företagets CompBuy. Om du vill skapa den koncerninterna kedjan returordern markeras för direktleverans. När du använder den **söka efter försäljningsorder** funktion att plocka kundfakturan ska returneras upprättas en koncernintern orderkedja består av följande dokument:

-   **Ursprunglig returorder:** RMA02 (CompBuy företag)
-   **Inköpsorder:** PO02 (CompBuy företag)
-   **Koncernintern returorder:** RMA\_00032 (företagets CompSell)

När du har skapat den koncerninterna kedjan direktleverans alla fysisk hantering och bearbetning av inge måste infalla i sammanhanget för den koncerninterna returordern RMA\_00032 i CompSell för företaget. Produkter som inte kan tas emot i företagets CompBuy. När en dispositionskod har skickats till koncerninterna returorder kan synkroniseras med den ursprungliga returordern att rätt faktureringen av den ursprungliga ordern.

## <a name="post-to-the-ledger"></a>Bokför i redovisningen
Redovisningsbokföringar som genereras när returordern faktureras påverkas av några viktiga inställningar och parametrar:

-   **Retursjälvkostnad** – för lagret modeller bortsett från **standardkostnad**, **Retursjälvkostnad** parametern avgör kostnaden för artikeln när det har godtagits tillbaka till lagret eller kasseras. Om du vill beräkna en korrekt värdering av lagret är det viktigt att du anger den **Retursjälvkostnad** parameter på rätt sätt. Om du använder den **söka efter försäljningsorder** du skapar en returorderrad som har en referens till en kundfaktura den **Retursjälvkostnad** värde är lika med självkostnaden för artikeln som säljs. Annars självkostnad värdet hämtas från inställningarna för artikeln eller anges manuellt.
-   **Kreditera korrigering Storno/** – den **korrigering kreditera** parameter på den **bokföring av faktura** sidan avgör om transaktionerna ska vara registrerade som positiva transaktioner (DR/k) eller korrigera, negativa poster.

I exemplen nedan retursjälvkostnaden representeras av **fakturarabatt självkostnad**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Exempel 1: Returordern inte referera en kundfaktura

En kundfaktura referera inte till returordern. Den returnerade artikeln krediteras. Den **korrigering kreditera** parameter inte är markerad när returorder, faktura eller kreditfaktura genereras.  

[![Returorder refererar inte till ett kund-invoic](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

**Anmärkning:** master artikelpriset används som standardvärde för den **Retursjälvkostnad** parameter. Standard pris skiljer sig från självkostnaden vid tidpunkten för lagerutleveransen. Därför är även en förlust 3 har uppkommit. Dessutom innehåller inte returordern rabatten som gavs till kunden på försäljningsordern. Därför uppstår en alltför stor kredit.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Exempel 2: Kreditkorrigering markeras för returorder

Exempel 2 är likadant som exempel 1, men **korrigering kreditera** parametern väljs när returorder fakturan genereras.  

[![Där kreditkorrigering väljs returorder](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

**Anmärkning:** ut redovisningsbokföringarna anges som negativ korrigeringar.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Exempel 3: Returorderraden skapas med hjälp av funktionen Sök efter försäljningsorder

I det här exemplet returorderraden skapas med hjälp av den **söka efter försäljningsorder** funktion. Den **korrigering kreditera** parameter inte är markerad när fakturan skapas.  

[![Returorderrad skapas med hjälp av Sök efter försäljningsorder](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

**Anmärkning:****rabatt** och **Retursjälvkostnad** är korrekt inställda. Därför uppstår en exakt återföring av den valda kundfakturan.


