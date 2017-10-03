---
title: "LIFO-datum med fysiskt värde och markering"
description: "Sist in, först ut-datum (LIFO-datum) är en lagermodell baserat på LIFO-principen. Utleveranser från lagret kvittas mot de senaste inleveranserna till lagret, baserat på datumet för lagertransaktionen. Genom att använda LIFO-datum, om det inte finns någon inleverans före utleveransen, kvittas utleveransen mot alla eventuella inleveranser som sker efter utleveransen. Flera utleveranser på samma datum kan kvittas i ordningen senaste utleverans - senaste inleverans."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 96089fed3e8b522fb3a8646ffd87fadff8fe1f3e
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="lifo-date-with-physical-value-and-marking"></a>LIFO-datum med fysiskt värde och markering

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Sist in, först ut-datum (LIFO-datum) är en lagermodell baserat på LIFO-principen. Utleveranser från lagret kvittas mot de senaste inleveranserna till lagret, baserat på datumet för lagertransaktionen. Genom att använda LIFO-datum, om det inte finns någon inleverans före utleveransen, kvittas utleveransen mot alla eventuella inleveranser som sker efter utleveransen. Flera utleveranser på samma datum kan kvittas i ordningen senaste utleverans - senaste inleverans. 

När du använder lagermodellen sist in, först ut (LIFO-datum) används och det inte finns någon inleverans före utleveransen kvittas utleveransen mot alla eventuella inleveranser som sker efter utleveransen. Flera utleveranser på samma datum kan kvittas i ordningen senaste utleverans - senaste inleverans. När du använder LIFO-datum, behöver du inte använda LIFO-datumregeln. Istället kan du markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans. 

Du rekommenderas att göra en periodisk lagerstängning när du använder lagermodellen LIFO-datum. 

I följande exempel visas effekten av att använda LIFO-datum i tre konfigurationer:

-   LIFO-datum utan alternativet **Inkludera fysiskt värde**
-   LIFO-datum med alternativet**Inkludera fysiskt värde**
-   LIFO-datum med länkning

## <a name="lifo-date-without-the-include-physical-value-option"></a>LIFO-datum utan alternativet Inkludera fysiskt värde
I det här exemplet markeras inte artikelmodellgruppen till att inkludera fysiskt värde. Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 150,00 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   4b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 150,00 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   6. 7. Lagerstängningen utförs. Baserat på LIFO-datummetoden kvittas den sista ekonomiskt uppdaterade utleveransen mot den sista ekonomiskt uppdaterade inleveransen per datum. En justering på 100,00 kronor görs av utleveranstransaktionen. Dessa transaktioner kvittas mot varandra.

Det nya löpande medelvärdet för självkostnaden återspeglar medelvärdet för de ekonomiskt uppdaterade transaktionerna på 150,00 kronor. 

I illustrationen visas effekten av lagermodellen LIFO-data på serien med transaktioner, när alternativet **Inkludera fysiskt värde** inte används. ![LIFO-datum med Inkludera fysiskt värde](./media/lifodatewithoutincludephysicalvalue.gif) 

**Förklaringar till bilden**

-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom parentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde som inte är inom parentes anger att lagertransaktionen har bokförts finansiellt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="lifo-date-with-the-include-physical-value-option"></a>LIFO-datum med alternativet Inkludera fysiskt värde
Du kan markera kryssrutan **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupper**. I detta fall använder systemet både fysiska och ekonomiska inleveranstransaktioner vid beräkning av löpande genomsnittlig självkostnad. Där det går görs också justeringar av den fysiskt uppdaterade inleveranstransaktionen. Om kryssrutan **Inkludera fysiskt värde** avmarkeras skapar lagerstängningen med lagermodellen LIFO-datum kvittningar enbart för transaktioner som är ekonomiskt uppdaterade. 

I det här exemplet markeras artikelmodellgruppen till att inkludera fysiskt värde. 

Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 183,30 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   4b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 183,30 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   6. 7. Lagerstängningen utförs. Baserat på LIFO-datummetoden kvittas eller justeras den sista uppdaterade utleveransen mot den sista uppdaterade inleveransen per datum. Dessa transaktioner kvittas inte mot varandra eftersom den ekonomiska inleveranstransaktionen justeras mot en fysisk uppdateringstransaktion. I stället görs bara en justering på 66,70 kronor i utleveranstransaktionen.

Det nya löpande medelvärdet för självkostnaden återspeglar medelvärdet för de ekonomiskt uppdaterade transaktionerna på 200,00 kronor. 

I illustrationen visas effekten av lagermodellen LIFO på serien med transaktioner, när alternativet **Inkludera fysiskt värde** används. ![LIFO-datum med Inkludera fysiskt värde](./media/lifodatewithincludephysicalvalue.gif) 

**Förklaringar till bilden**

-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom parentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde som inte är inom parentes anger att lagertransaktionen har bokförts finansiellt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="lifo-date-with-marking"></a>LIFO-datum med länkning
Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs. 

Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för den här artikeln för att kunna tillgodose kundens krav. Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor (KSV), för den här försäljningsorderfakturan. 

När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. Om detta försäljningsorderdokument länkas till inköpsordern innan följesedeln eller fakturan bokförs, blir kostnaden för sålda varor 1200,00 kronor i stället för den aktuella löpande genomsnittliga kostnaden för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan markeringen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden. 

Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra. 

Om du till exempel har en inleveranstransaktion för en utleveranstransaktionen. I detta fall ignoreras den definierade värderingsmetoden för artikelns artikelmodellgrupp, systemet kvittar dessa transaktioner mot varandra. 

Du kan markera ett problem transaktion till en inleverans innan en transaktion bokförs. Du kan göra detta från en försäljningsorderrad på sidan **Försäljningsorderdetaljer**. Du kan visa de öppna inleveranstransaktionerna på sidan **Markering**. 

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
-   7. 7. Lagerstängningen utförs. Eftersom de ekonomiskt uppdaterade transaktionerna Först in, först ut (FIFO) länkas till en befintlig inleverans kvittas dessa transaktioner mot varandra och ingen justerings görs.

Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 275,00 kronor. 

I illustrationen visas effekten av lagermodellen LIFO på serien med transaktioner, när markering mellan inleveranser och utleveranser används. ![LIFO-datum med Markering](./media/lifodatewithmarking.gif) 

**Förklaringar till bilden**

-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom parentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde som inte är inom parentes anger att lagertransaktionen har bokförts finansiellt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.





