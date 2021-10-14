---
title: LIFO med fysiskt värde och markering
description: Sist in, först ut (LIFO) är en lagermodell där de senast (nyaste) anskaffade inleveranserna utlevereras först. Utleveranser från lagret kvittas mot de senaste inleveranserna till lagret, baserat på datumet för lagertransaktionen.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60ec1c1c24f05157b72a3ed57abe7dfaaa763093
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578546"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO med fysiskt värde och markering

[!include [banner](../includes/banner.md)]

Sist in, först ut (LIFO) är en lagermodell där de senast (nyaste) anskaffade inleveranserna utlevereras först. Utleveranser från lagret kvittas mot de senaste inleveranserna till lagret, baserat på datumet för lagertransaktionen. 

I lagermodellen Sist in, först ut (LIFO – Last in, first out) utlevereras de sista (senaste) inleveranserna först. Utleveranser från lagret kvittas mot de senaste inleveranserna till lagret, baserat på datumet för lagertransaktionen. När du använder LIFO, behöver du inte använda LIFO-regeln. I stället kan du markera lagertransaktioner så att en specifik artikelutleverans kvittas mot en specifik inleverans. Vi rekommenderar periodisk lagerstängning när du använder LIFO-modellen. 

I följande exempel visas effekten av att använda LIFO i tre konfigurationer:

-   LIFO utan alternativet **Inkludera fysiskt värde**
-   LIFO med alternativet **Inkludera fysiskt värde**
-   LIFO med markering

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO utan alternativet Inkludera fysiskt värde
I det här exemplet markeras inte artikelmodellgruppen till att inkludera fysiskt värde. Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 200,00 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   5b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 200,00 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   6. 7. Lagerstängningen utförs. Baserat på LIFO-metoden kvittas den sista ekonomiskt uppdaterade utleveransen mot den sista ekonomiskt uppdaterade inleveransen. En justering på 100,00 kronor görs av utleveranstransaktionen.

Det nya löpande medelvärdet för självkostnaden återspeglar medelvärdet för de ekonomiskt uppdaterade transaktionerna på 150,00 kronor. Följande illustration visar effekten av LIFO-lagermodellen på den här serien med transaktioner, när alternativet **Inkludera fysiskt värde** inte används. 

![LIFO utan Inkludera fysiskt värde.](./media/lifowithoutincludephysicalvalue.gif) 

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
- Utleveranser från lagret visas som lodräta pilar under tidslinjen.
- Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Kvantitet@Enhetspris.
- Ett lagertransaktionsvärde inom parentes anger att lagertransaktionen har bokförts fysiskt i lagret.
- Ett lagertransaktionsvärde som inte är inom parentes anger att lagertransaktionen har bokförts finansiellt i lagret.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO med alternativet Inkludera fysiskt värde
Om kryssrutan **Inkludera fysiskt värde** markeras för en artikel på sidan **Artikelmodellgrupper** använder systemet både fysiska och ekonomiska inleveranstransaktioner vid beräkning av löpande genomsnittlig självkostnad. Där det går görs också justeringar av den fysiskt uppdaterade inleveranstransaktionen. Om kryssrutan **Inkludera fysiskt värde** avmarkeras skapar lagerstängningen med LIFO-lagermodellen kvittningar enbart för transaktioner som är ekonomiskt uppdaterade. 

Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor vardera (löpande medelvärde för ekonomiskt och fysiskt uppdaterade transaktioner).
-   5b. Lagrets ekonomiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor vardera (löpande medelvärde för ekonomiskt och fysiskt uppdaterade transaktioner).
-   6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor vardera.
-   7. 7. Lagerstängningen utförs. Baserat på LIFO-metoden justeras eller kvittas den sista utleveranstransaktionen mot den sista uppdaterade inleveransen.

Transaktion 6a justeras mot inleveranstransaktion 4b. Systemet kvittar inte dessa transaktioner eftersom inleveransen uppdateras fysiskt men inte ekonomiskt. I stället bokförs en justering på 87,50 kronor på den fysiska utleveranstransaktionen. Transaktion 5b justeras efter den fysiska inleveranstransaktionen 3a. Systemet kvittar inte dessa transaktioner eftersom ingen av dem är ekonomiskt uppdaterad. I stället görs bara en justering på -37,50 kronor i utleveranstransaktionen. Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 20,00 USD. 

I illustrationen visas effekten av den LIFO-lagermodellen på serien med transaktioner, när alternativet **Inkludera fysiskt värde** används. 

![LIFO med Inkludera fysiskt värde.](./media/lifowithincludephysicalvalue.gif) 

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
- Utleveranser från lagret visas som lodräta pilar under tidslinjen.
- Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Kvantitet@Enhetspris.
- Ett lagertransaktionsvärde inom parentes anger att lagertransaktionen har bokförts fysiskt i lagret.
- Ett lagertransaktionsvärde som inte är inom parentes anger att lagertransaktionen har bokförts finansiellt i lagret.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="lifo-with-marking"></a>LIFO med markering
Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs. Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för den här artikeln för att kunna tillgodose kundens krav. 

Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor (KSV), för den här försäljningsorderfakturan. När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. Om detta försäljningsorderdokument länkas till inköpsordern innan följesedeln eller fakturan bokförs, blir kostnaden för sålda varor 1200,00 kronor i stället för den aktuella löpande genomsnittliga kostnaden för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan markeringen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden. 

Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra. 

Du kan markera en utleveranstransaktion till en inleverans innan en transaktion bokförs. Du kan göra detta från en försäljningsorderrad på sidan **Försäljningsorderdetaljer**. Du kan visa de öppna inleveranstransaktionerna på sidan **Markering**. 

Du kan också markera ett problem transaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal. 

Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor vardera (löpande medelvärde för ekonomiskt och fysiskt uppdaterade transaktioner).
-   5b. Lagrets ekonomiska utleverans för kvantiteten 1 länkas till lagerinleveransen 2b innan transaktionen bokförs. Den här transaktionen bokförs till självkostnaden 200,00 kronor vardera.
-   6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor vardera.
-   7. 7. Lagerstängningen utförs. Eftersom de ekonomiskt uppdaterade FIFO-transaktionerna länkas till en befintlig inleverans kvittas dessa transaktioner mot varandra och ingen justerings görs.

Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 27,50 USD. 

I illustrationen nedan visas hur den här serien med transaktioner påverkas av LIFO-lagermodellen när länkning mellan utleverans och inleverans används. 

![LIFO med markering.](./media/lifowithmarking.gif) 

**Förklaringar till bilden**

- Lagertransaktioner visas som lodräta pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
- Utleveranser från lagret visas som lodräta pilar under tidslinjen.
- Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Kvantitet@Enhetspris.
- Ett lagertransaktionsvärde inom parentes anger att lagertransaktionen har bokförts fysiskt i lagret.
- Ett lagertransaktionsvärde som inte är inom parentes anger att lagertransaktionen har bokförts finansiellt i lagret.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]