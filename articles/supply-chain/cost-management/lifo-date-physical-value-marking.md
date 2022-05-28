---
title: LIFO-datum med fysiskt värde och markering
description: Sist in, först ut-datum (LIFO-datum) är en lagermodell baserad på LIFO-principen. Utleveranser från lagret kvittas mot de senaste inleveranserna till lagret, baserat på datumet för lagertransaktionen. Genom att använda LIFO-datum kvittas utleveransen mot alla eventuella inleveranser som sker efter datum för utleveransen, detta om det inte finns någon inleverans före utleveransen. Flera utleveranser på samma datum kan kvittas i ordningen senaste utleverans - senaste inleverans.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51592
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ca344e6ca81814e787046f6ece97625d035346d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671462"
---
# <a name="lifo-date-with-physical-value-and-marking"></a>LIFO-datum med fysiskt värde och markering

[!include [banner](../includes/banner.md)]

Sist in, först ut-datum (LIFO-datum) är en lagerstyrnings- och värderingsmetod där det lager som producerats eller förvärvats senast säljs, används eller avyttras först. Under lagerstängningsprocessen i Microsoft Dynamics 365 Supply Chain Management skapar systemet kvittningar där den senaste inleveransen matchas mot den första utleveransen för respektive angivet datum - det äldsta datumet först, och så vidare. När du använder lagermodellen sist in, först ut (LIFO-datum) och det inte finns någon inleverans före utleveransen kvittas utleveransen mot alla eventuella inleveranser som sker efter utleveransen. Kvittning och matchningsprincipen baseras på lagertransaktionerens ekonomiska datum. När det finns flera utleveranser på samma datum kvittas dessa i ordningen senaste utleverans - senaste inleverans. En preliminär bedömning av kvittningar och justeringar kan utföras genom att lageromberäkningsprocessen körs.

Du kan åsidosätta LIFO-datumprincipen genom att markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans. En periodisk lagerstängning krävs när du använder lagermodellen med LIFO-datum för att skapa kvittningar och justera värdet på utleveranser enligt LIFO-principen. Till dess att du kör lagerstängningsprocessen värderas uttransaktionen till löpande medelvärde när de fysiska och ekonomiska uppdateringarna genomförs. Om du inte använder markering beräknas det löpande medelvärdet när den fysiska eller ekonomiska uppdateringen utförs.

Du rekommenderas att göra en periodisk lagerstängning när du använder lagermodellen med LIFO-datum.

I följande exempel visas effekten av att använda LIFO-datum i tre konfigurationer:

- LIFO-datum utan alternativet **Inkludera fysiskt värde**
- LIFO-datum med alternativet **Inkludera fysiskt värde**
- LIFO-datum med markering

## <a name="lifo-date-without-the-include-physical-value-option"></a>LIFO-datum utan alternativet Inkludera fysiskt värde

I det här exemplet markeras inte artikelmodellgruppen till att inkludera fysiskt värde. Illustrationen som följer visar dessa transaktioner:

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 23,00 USD kronor vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner)
- 7\. Lagerstängningen utförs. Baserat på LIFO-datummetoden kvittas den första ekonomiskt uppdaterade utleveransen mot den sista ekonomiskt uppdaterade inleveransen, med början första datum, osv. I det här exemplet skapas en kvittning mellan 3b och 2b. En justering 6,00 USD till 3b och den slutliga kostnaden blir 22,00 USD.

I illustrationen visas effekten av lagermodellen med LIFO-datum när alternativet **Inkludera fysiskt värde** inte används.

![LIFO-datum utan alternativet Inkludera fysiskt värde.](media/lifo-date-without-include-physical-value.png)

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

## <a name="lifo-date-with-the-include-physical-value-option"></a>LIFO-datum med alternativet Inkludera fysiskt värde

Om kryssrutan **Inkludera fysiskt värde** markeras för en artikel på sidan **Artikelmodellgrupp** använder systemet både fysiska och ekonomiska inleveranstransaktioner vid beräkning av löpande genomsnittlig självkostnad. Där det går görs också justeringar av den fysiskt uppdaterade inleveranstransaktionen. Om kryssrutan **Inkludera fysiskt värde** avmarkeras skapar lagerstängningen med lagermodellen med LIFO-datum kvittningar enbart för transaktioner som är ekonomiskt uppdaterade.

I det här exemplet markeras artikelmodellgruppen till att inkludera fysiskt värde. 

Illustrationen som följer visar dessa transaktioner:

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
- 7\. Lagerstängningen utförs. Baserat på LIFO-datummetoden kvittas den första ekonomiskt uppdaterade utleveransen mot den sista ekonomiskt uppdaterade inleveransen för respektive datum, med början första datum, osv. I det här exemplet skapas en kvittning mellan 2b och 3b. En justering 6,00 USD till 3b och den slutliga kostnaden blir 22,00 USD. Dessutom kommer transaktion 6a att justeras till inleveranstransaktionskostnaden för 5b. Systemet kvittar inte dessa transaktioner eftersom inleveransen uppdateras fysiskt men inte ekonomiskt. I stället bokförs bara en 6,33 USD den fysiska utleveranstransaktionen och den resulterande justerade kostnaden 30,00 USD.

I illustrationen visas effekten av lagermodellen LIFO på serien med transaktioner, när alternativet **Inkludera fysiskt värde** används.

![LIFO-datum med alternativet Inkludera fysiskt värde.](media/lifo-date-with-include-physical-value.png)

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

## <a name="lifo-date-with-marking"></a>LIFO-datum med markering

Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs. Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för den här artikeln för att kunna tillgodose kundens krav.

Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor (KSV), för den här försäljningsorderfakturan. När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. Om detta försäljningsorderdokument länkas till inköpsordern innan följesedeln eller fakturan bokförs, blir kostnaden för sålda varor 1200,00 kronor i stället för den aktuella löpande genomsnittliga kostnaden för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan markeringen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden.

Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra.

Du kan markera en utleveranstransaktion till en inleverans innan en transaktion bokförs. Du kan göra den här markeringen från en försäljningsorderrad på sidan **Försäljningsorderinformation** genom att välja **Lager \> Markering** på snabbflikarna **Försäljningsorderrader**. Du kan visa de öppna inleveranstransaktionerna på sidan **Markering**.

Du kan också markera ett problem transaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal.

Illustrationen som följer visar dessa transaktioner:

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3c. Lagrets ekonomiska utleverans för 3b markeras till lagrets ekonomiska utleverans för 1b.
- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 23,00 USD kronor vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner)
- 7\. Lagerstängningen utförs. Baserat på markeringsprincipen som använder LIFO-datummetoden kvittas de markerade transaktionerna mot varandra. I det här exemplet kvittas 3b mot 1b och en justering för -6,00 USD bokförs på 3b för att få värdet 10,00 USD. I det här exemplet görs inga ytterligare kvittningar eftersom stängningen bara skapar kvittningar för finansiellt uppdaterade transaktioner.

I illustrationen visas effekten av LIFO-datumlagermodellen när markering mellan inleveranser och utleveranser används. 

![LIFO-datum med markering.](media/lifo-date-with-marking.png)

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
- Kvittningar och markeringar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
