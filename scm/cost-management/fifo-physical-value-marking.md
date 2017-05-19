---
title: "FIFO med fysiskt värde och markering"
description: "Först in, först ut (FIFO) är en lagermodell där de första (äldsta) inleveranserna utlevereras först. Ekonomiskt uppdaterade utleveranser från lagret kvittas mot de första ekonomiskt uppdaterade inleveranserna i lagret baserat på lagertransaktionens ekonomiska datum."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 54682
ms.assetid: dc0e2855-83a0-41a7-a398-3c7852597d1a
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b0be852bde33e8dfc82ceb42dd98be10537f318d
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="fifo-with-physical-value-and-marking"></a>FIFO med fysiskt värde och markering

[!include[banner](../includes/banner.md)]


Först in, först ut (FIFO) är en lagermodell där de första (äldsta) inleveranserna utlevereras först. Ekonomiskt uppdaterade utleveranser från lagret kvittas mot de första ekonomiskt uppdaterade inleveranserna i lagret baserat på lagertransaktionens ekonomiska datum. 

När du använder FIFO, behöver du inte använda FIFO-regeln. Istället kan du markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans. Du rekommenderas att göra en periodisk lagerstängning när du använder lagermodellen FIFO. I följande exempel visas effekten av att använda FIFO i tre konfigurationer:

-   FIFO utan alternativet **Inkludera fysiskt värde**
-   FIFO med alternativet **Inkludera fysiskt värde**
-   FIFO med länkning

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO utan alternativet Inkludera fysiskt värde
I det här exemplet markeras inte artikelmodellgruppen till att inkludera fysiskt värde. Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 2 med en kostnad på 10,00 USD vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 2 med en kostnad på 10,00 USD vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 200,00 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   5b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 200,00 kronor vardera (löpande medelvärde eller ekonomiskt uppdaterade transaktioner).
-   6. 7. Lagerstängningen utförs. Baserat på FIFO-metoden kvittas den första ekonomiskt uppdaterade utleveransen mot den första ekonomiskt uppdaterade inleveransen. En justering på 100,00 kronor görs av utleveranstransaktionen.

Det nya löpande medelvärdet för självkostnaden återspeglar medelvärdet för de ekonomiskt uppdaterade transaktionerna. I illustrationen visas effekten av den FIFO-lagermodellen på serien med transaktioner, när alternativet **Inkludera fysiskt värde** inte används. ![FIFO utan Inkludera fysiskt värde](./media/fifowithoutincludephysicalvalue.gif) 

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

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO med alternativet Inkludera fysiskt värde
Om kryssrutan **Inkludera fysiskt värde** markeras för en artikel på sidan **Artikelmodellgrupp** använder systemet både fysiska och ekonomiska inleveranstransaktioner vid beräkning av löpande genomsnittlig självkostnad. Där det går görs också justeringar av den fysiskt uppdaterade inleveranstransaktionen. Om kryssrutan **Inkludera fysiskt värde** avmarkeras skapar lagerstängningen med FIFO-lagermodellen kvittningar enbart för transaktioner som är ekonomiskt uppdaterade. Illustrationen som följer visar dessa transaktioner:

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
-   7. 7. Lagerstängningen utförs. Baserat på FIFO-metoden kommer den första ekonomiska utleveranstransaktionen att justeras eller kvittas mot den första uppdaterade inleveransen, antingen ekonomisk eller fysisk.

Transaktion 5b kvittas mot inleveranstransaktion 1b. En negativ justering på 112,50 kronor görs på den här utleveranstransaktionen. Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 27,50 USD. I illustrationen visas effekten av den FIFO-lagermodellen på serien med transaktioner, när alternativet **Inkludera fysiskt värde** används. ![FIFO med Inkludera fysiskt värde](./media/fifowithincludephysicalvalue.gif) 

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

## <a name="fifo-with-marking"></a>FIFO med länkning
Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs. Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för den här artikeln för att kunna tillgodose kundens krav. Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor (KSV), för den här försäljningsorderfakturan. När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. Om detta försäljningsorderdokument länkas till inköpsordern innan följesedeln eller fakturan bokförs, blir kostnaden för sålda varor 1200,00 kronor i stället för den aktuella löpande genomsnittliga kostnaden för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan markeringen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden. Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra. När en inleveranstransaktion matchar en utleveranstransaktion ignoreras den definierade värderingsmetod för artikelmodellgruppen, och systemet kvittar dessa transaktioner mot varandra. Du kan markera ett problem transaktion till en inleverans innan en transaktion bokförs. Du kan göra detta från en försäljningsorderrad på sidan **Försäljningsorderdetaljer**. Du kan visa de öppna inleveranstransaktionerna på sidan **Markering**. Du kan också markera ett problem transaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal. Illustrationen som följer visar dessa transaktioner:

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

Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 27,50 USD. I illustrationen nedan visas hur den här serien med transaktioner påverkas av FIFO-lagermodellen när länkning mellan utleverans och inleverans används. ![FIFO med Markering](./media/fifowithmarking.gif) 

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





