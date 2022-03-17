---
title: Viktat genomsnitt med fysiskt värde och markering
description: Viktat medelvärde är en lagermodell som baseras på principen om viktat medelvärde, där utleveranser från lagret värderas till medelvärdet av de artiklar som inlevereras till lagret under lagerstängningsperioden, plus all lagerbehållning från föregående period.
author: AndersGirke
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c124716b70be837573506a738ef2034397f2bda
ms.sourcegitcommit: addae271ddfc5a8b0721c23337f69916153db4cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/21/2022
ms.locfileid: "8330236"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Viktat genomsnitt med fysiskt värde och markering

[!include [banner](../includes/banner.md)]

Viktat medelvärde är en lagermodell som baseras på ett medelvärde som är ett resultat av multipliceringen av respektive komponent (artikeltransaktion) med en faktor (självkostnad) som återspeglar dess vikt (kvantitet). Ett annat sätt att säga detta på är att viktat medelvärde är en lagermodell som tilldelar kostnaden för ärendetransaktioner baserat på medelvärdet av allt lager som mottagits under perioden, plus eventuell lagerbehållning från föregående period.

När du kör en lagerstängning med lagermodellen för viktat medelvärde kan du skapa en kvittning på två sätt. Vanligtvis kvittas alla inleveranser mot en virtuell utleverans som innehåller den totala inlevererade kvantiteten och det totala inlevererade värdet. Denna virtuella utleverans har en motsvarande virtuell inleverans mot vilken utleveranser kvittas. På så sätt får alla utleveranser samma genomsnittskostnad. Den virtuella utleveransen och inleveransen kan ses som en virtuell överföring, en så kallad *överföring av viktat medelvärde vid lagerstängning*. Denna kvittningsmetod kallas för *viktat medelvärde vid summerad kvittning*. Om det endast finns en inleverans kan alla utleveranser kvittas mot den och ingen virtuell överföring skapas. Denna kvittningsmetod kallas för *direkt kvittning*. Allt lager som finns kvar efter lagerstängningen värderas till det viktade medelvärdet från den föregående perioden och inkluderas i beräkningen av det viktade medelvärdet under nästa period.

Du kan åsidosätta den viktade genomsnittsprincipen genom att markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans. En periodisk lagerstängning krävs när du använder lagermodellen för viktat medelvärde för att skapa kvittningar och justera värdet på utleveranser enligt principen om viktat gneomsnitt. Till dess att du kör lagerstängningsprocessen värderas uttransaktionen till löpande medelvärde när de fysiska och ekonomiska uppdateringarna genomförs. Om du inte använder markering beräknas det löpande medelvärdet när den fysiska eller ekonomiska uppdateringen utförs.

Metoden med viktat medelvärdeligt datum för stängning av lager beräknas med följande formel:

- Viktat medelvärde = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = transaktionens kvantitet  
P = transaktionstyp

Kvittningar är lagerstängningstransaktioner som justerar utleveranser till rätt viktat medelvärde vid stängningsdatumet. I följande exempel visas effekten av att använda viktat medelvärde med fem olika konfigurationer:

- Viktad medelvärde med direkt kvittning utan alternativet **Inkludera fysiskt värde**
- Viktat medelvärde med summerad kvittning utan alternativet **Inkludera fysiskt värde**
- Viktad medelvärde med direkt kvittning med alternativet **Inkludera fysiskt värde**
- Viktad medelvärde med summerad kvittning med alternativet **Inkludera fysiskt värde**
- Viktat medelvärde med länkning

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Viktat medelvärde med direkt kvittning utan Inkludera fysiskt värde

Den direkta kvittningsprincipen skapar kvittningar direkt mellan in- och utleveranser utan att ytterligare lagertransaktioner skapas. Systemet använder denna direkta kvittningsprincip i följande situationer:

- En inleverans och en eller flera utleveranser har bokförts under perioden.
- Enbart utleveranser har bokförts under perioden och lagret innehåller artikelbehållning från en tidigare stängning.

I det här exemplet avmarkeras kryssrutan **Inkludera fysiskt värde** i **artikelmodellgruppen** för den frisläppta produkten. Illustrationen som följer visar dessa transaktioner:

- 1a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 20,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 10,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 10,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 4a. Lagrets fysiska utleverans för kvantiteten 1 till en kostnad på 10,00 USD vardera (löpande medelvärde för ekonomiskt bokförda transaktioner).
- 4b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 10,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 5a. Lagrets fysiska utleverans för kvantiteten 1 till en kostnad på 10,00 USD vardera (löpande medelvärde för ekonomiskt bokförda transaktioner).
- 6\. Lagerstängningen utförs. Baserat på metoden för viktat medelvärde använder systemet den direkta kvittningsmetoden, detta eftersom bara en inleverans uppdateras ekonomiskt under perioden. I det här exemplet skapas en kvittning mellan 1b och 3b, och ytterligare en mellan 1b och 4b. Ingen justering görs eftersom det löpande medelvärdet är detsamma som det viktade medelvärdet.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den direkta kvittningsprincipen utan alternativet **Inkludera fysiskt värde**.

![Kvittning av viktat medeldatum utan Inkludera fysiskt värde.](media/weighted-average-direct-settlement-without-include-physical-value.png)

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Varje datum i diagrammet är åtskilda av en tunn svart lodrät linje. Datumet anges längst ned i diagrammet.
- Lagerstängningar visas som en röd lodrät streckad linje.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Viktat medelvärde med summerad kvittning utan alternativet Inkludera fysiskt värde

När det finns flera kvitton under en period använder det viktade medelvärdet principen om sammanfattad kvittning, där alla kvitton inom en stängningsperiod sammanfattas till en transaktion kallad *Viktat medelvärde för stängning av lager*. Alla inleveranser för den perioden kvittas mot utleveransen för den nya lageröverföringstransaktionen. Alla utleveranser för perioden kvittas mot inleveransen för den nya lagertransaktionen. Om lagerbehållning finns efter lagerstängningen inkluderas lagerbehållningen i den nya lagertransaktionen för det viktade genomsnittet av lagerstängningstransaktionerna.

Följande transaktioner visas på bilden som följer:

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 23,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 7\. Lagerstängningen utförs.
- 7a. Den ekonomiska utleveranstransaktionen för viktat medelvärde för stängning av lager skapas för att summera kvittningen av alla ekonomiska lagerinleveranser.
  - Transaktion 1b kvittas för kvantiteten 1 med ett kvitterat belopp på 10,00 USD.
  - Transaktion 2b kvittas för kvantiteten 1 med ett kvitterat belopp på 22,00 USD.
  - Transaktion 5b kvittas för kvantiteten 1 med ett kvitterat belopp på 30,00 USD.
  - Transaktion 7a. skapas för kvantiteten 3 med ett kvitterat belopp på 62,00 USD. Denna transaktion motbokar summan av de tre inleveranstransaktionerna som uppdateras ekonomiskt under perioden.
- 7b. Ekonomisk inleverans för viktat medelvärde för stängning av lagerskapas som en motbokning till ekonomiskt bokförda problem.
  - Transaktion 3b kvittas för kvantiteten 1 med ett kvitterat belopp på 20,67 USD. Denna transaktion justeras med 4,67 USD för att få det ursprungliga värdet 16,00 USD till 20,67, vilket är det viktade medelvärdet för ekonomiskt bokförda transaktioner för perioden.
  - Transaktion 7b. skapas för kvantiteten 1 med ett kvitterat belopp på 20,67 USD som motbokning till 3b. Denna transaktion motbokar summan av den inleveranstransaktion som uppdateras ekonomiskt under perioden.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den summerade kvittningsprincipen utan alternativet **Inkludera fysiskt värde**.

![Summerad kvittning av viktat medeldatum utan Inkludera fysiskt värde.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Varje datum i diagrammet är åtskilda av en tunn svart lodrät linje. Datumet anges längst ned i diagrammet.
- Lagerstängningar visas som en röd lodrät streckad linje.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Viktad medelvärde med direkt kvittning med alternativet Inkludera fysiskt värde

Parametern **Inkludera fysiskt värde** fungerar på ett annat sätt med lagermodellen för viktat medelvärde än i tidigare versioner av produkten. När du väljer alternativet **Inkludera fysiskt värde** för en artikel i formuläret **Artikelmodellgrupp** använder systemet fysiska uppdaterade inleveranser för att beräkna uppskattad självkostnad eller löpande genomsnittlig självkostnad. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet.

Följande transaktioner visas på bilden som följer:

- 1a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 20,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 4a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD per styck (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 4b. Lagrets ekonomiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD per styck (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 5a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD per styck (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 6\. Lagerstängningen utförs. Baserat på metoden för viktat medelvärde använder systemet den direkta kvittningsmetoden, detta eftersom bara en inleverans uppdateras ekonomiskt under perioden. I det här exemplet skapas en kvittning mellan 1b och 3b, och ytterligare en mellan 1b och 4b. Transaktion 3b och 4b justeras med -5,00 USD kronor för att få värdet till 10,00 USD.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den direkta kvittningsprincipen med alternativet **Inkludera fysiskt värde**.

![Viktat medeldatum med Inkludera fysiskt värde.](media/weighted-average-direct-settlement-with-include-physical-value.png)

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Varje datum i diagrammet är åtskilda av en tunn svart lodrät linje. Datumet anges längst ned i diagrammet.
- Lagerstängningar visas som en röd lodrät streckad linje.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Viktad medelvärde med summerad kvittning med alternativet Inkludera fysiskt värde

Parametern **Inkludera fysiskt värde** fungerar på ett annat sätt med viktat medelvärde än i tidigare versioner. Markera kryssrutan **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupp**. Sedan använder systemet fysiskt uppdaterade inleveranser vid beräkning av den uppskattade självkostnaden, eller det löpande medelvärdet. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet. Vi rekommenderar en månadsvis lagerstängning när du använder lagermodellen för viktat medelvärde. I detta exempel på viktat medelvärde med summerad kvittning markeras lagermodellgruppen till att inkludera fysiskt värde.

Följande transaktioner visas på bilden som följer:

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 16,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till självkostnaden 16,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 23,67 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 7\. Lagerstängningen utförs.
- 7a. Den ekonomiska utleveranstransaktionen för viktat medelvärde för stängning av lager skapas för att summera kvittningen av alla ekonomiska lagerinleveranser.
  - Transaktion 1b kvittas för kvantiteten 1 med ett kvitterat belopp på 10,00 USD.
  - Transaktion 2b kvittas för kvantiteten 1 med ett kvitterat belopp på 22,00 USD.
  - Transaktion 5b kvittas för kvantiteten 1 med ett kvitterat belopp på 30,00 USD.
  - Transaktion 7a. skapas för kvantiteten 3 med ett kvitterat belopp på 62,00 USD.  
- 7b. Ekonomisk inleverans för viktat medelvärde för stängning av lager skapas som en motbokning till ekonomiska transaktioner gällande avslutade problem.
  - Transaktion 3b kvittas för kvantiteten 1 med ett kvitterat belopp på 20,67 USD. Denna transaktion justeras med 4,67 USD för att få det ursprungliga värdet 16,00 USD till 20,67, vilket är det viktade medelvärdet för ekonomiskt bokförda transaktioner för perioden.
  - Transaktion 7b. skapas för kvantiteten 1 med ett kvitterat belopp på 20,67 USD som motbokning till 3b.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den summerade kvittningsprincipen utan alternativet **Inkludera fysiskt värde**.

![Summerad kvittning av viktat medeldatum med Inkludera fysiskt värde.](media/weighted-average-summarized-settlement-with-include-physical-value.png)

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Varje datum i diagrammet är åtskilda av en tunn svart lodrät linje. Datumet anges längst ned i diagrammet.
- Lagerstängningar visas som en röd lodrät streckad linje.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-with-marking"></a>Viktat medelvärde med länkning

Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs.

Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom detta är en snabborder måste du betala mer för denna artikel för att kunna tillgodose kundens begäran. Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor, för den här försäljningsorderfakturan.

När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. T.ex. markeras försäljningsorderdokumentet för inköpsordern, innan följesedeln eller fakturan bokförs. Kostnaden för sålda varor kommer då att bli 120,00 kronor i stället för den aktuella löpande genomsnittlig kostnad för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan länkningen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden.

Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra.

En inleveranstransaktion markeras för en utleveranstransaktion. I detta fall ignoreras den definierade värderingsmetoden för artikelns artikelmodellgrupp och systemet kvittar dessa transaktioner mot varandra.

Du kan markera en utleveranstransaktion till en inleverans innan en transaktion bokförs. Du kan göra detta från en försäljningsorderrad på sidan **Försäljningsorderdetaljer**. De öppna inleveranstransaktionerna visas på sidan **Markering**.

Du kan markera ett problem transaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal.

Följande transaktioner visas på bilden som följer:

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3c. Lagrets ekonomiska utleverans för 3b markeras till lagrets ekonomiska utleverans för 2b.
- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 23,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 7\. Lagerstängningen utförs. Baserat på markeringsprincipen som använder metoden för viktat medelvärde kvittas de markerade transaktionerna mot varandra. I det här exemplet kvittas 3b mot 2b och en justering för 6,00 USD bokförs på 3b för att få värdet 22,00 USD. I det här exemplet görs inga ytterligare kvittningar eftersom stängningen bara skapar kvittningar för finansiellt uppdaterade transaktioner.

I bilden nedan visas hur den här serien med transaktioner påverkas om du väljer lagermodellen för viktat medelvärde med markering.

![Viktat medelvärde med Markering.](media/weighted-average-with-marking.png)

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Varje datum i diagrammet är åtskilda av en tunn svart lodrät linje. Datumet anges längst ned i diagrammet.
- Lagerstängningar visas som en röd lodrät streckad linje.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
