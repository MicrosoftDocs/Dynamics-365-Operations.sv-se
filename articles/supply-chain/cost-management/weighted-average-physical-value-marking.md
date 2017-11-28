---
title: "Viktat genomsnitt med fysiskt värde och markering"
description: "Viktat medelvärde är en lagermodell som baseras på principen om viktat medelvärde, där utleveranser från lagret värderas till medelvärdet av de artiklar som inlevereras till lagret under lagerstängningsperioden, plus all lagerbehållning från föregående period."
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 69876a9d1daec4e6980728527c784a5404239cc2
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="weighted-average-with-physical-value-and-marking"></a>Viktat genomsnitt med fysiskt värde och markering

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Viktat medelvärde är en lagermodell som baseras på principen om viktat medelvärde, där utleveranser från lagret värderas till medelvärdet av de artiklar som inlevereras till lagret under lagerstängningsperioden, plus all lagerbehållning från föregående period.

När du kör en lagerstängning kvittas alla inleveranser mot en virtuell utleverans som innehåller den totala inlevererade kvantiteten och det totala inlevererade värdet. Denna virtuella utleverans har en motsvarande virtuell inleverans mot vilken utleveranser kvittas. På så sätt får alla utleveranser samma genomsnittskostnad. Den virtuella utleveransen och inleveransen kan ses som en virtuell överföring, en så kallad ”överföring av viktat medelvärde vid lagerstängning".

Om det endast finns en inleverans kan alla utleveranser kvittas mot den och ingen virtuell överföring skapas. 

När du använder viktat medelvärde kan du välja om du vill markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans i stället för att följa regeln om viktat medelvärde. 

Vi rekommenderar månadsvis lagerstängning när du använder modellen med viktat medelvärde. 

Metoden med viktat genomsnittligt datum för stängning av lager beräknas med följande formel:
-   Viktat medelvärde = (Q1\*P1 + Q2\*P2 + Qn\*Pn) / (Q1 + Q2 + Qn)

Lagertransaktioner som lämnar lagerutleveranserna. Detta inkluderar försäljningsorder, lagerjournaler, och tillverkningsorder, som sker med en uppskattad självkostnad vid bokföringsdatumet. Denna uppskattade självkostnad kallas också för löpande medelvärde. Vid lagerstängningen analyserar systemet lagertransaktionerna för föregående och den aktuella perioden och fastställer vilken av följande stängningsprinciper som ska användas.
-   Direkt kvittning
-   Summerad kvittning

Kvittningar är lagerstängningstransaktioner som justerar utleveranser till rätt viktat medelvärde vid stängningsdatumet. I följande exempel visas effekten av att använda viktat medelvärde med fem olika konfigurationer:
-   Viktad medelvärde med direkt kvittning utan alternativet Inkludera fysiskt värde
-   Viktat medelvärde med summerad kvittning utan alternativet Inkludera fysiskt värde
-   Viktad medelvärde med direkt kvittning med alternativet Inkludera fysiskt värde
-   Viktad medelvärde med summerad kvittning med alternativet Inkludera fysiskt värde
-   Viktat medelvärde med länkning

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Viktat medelvärde med direkt kvittning utan Inkludera fysiskt värde
Den direkta kvittningsprincipen är densamma som används för viktat medelvärde i tidigare versioner. Systemet kvittar direkt mellan inleveranser och utleveranser. Systemet använder denna direkta kvittningsprincip i vissa särskilda situationer:
-   En inleverans och en eller flera utleveranser har bokförts under perioden.
-   Enbart utleveranser har bokförts under perioden och lagret innehåller artikelbehållning från en tidigare stängning.

I scenariot i följande avsnitt har en ekonomiskt uppdaterad inleverans och utleverans bokförts. Under lagerstängningen kvittar systemet inleveransen direkt mot utleveransen, och ingen justering av självkostnaden behövs för utleveransen. Följande transaktioner visas i bilden.
-   1a. Lagrets fysiska inleverans uppdateras med kvantiteten 5 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 5 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska utleverans uppdateras med kvantiteten 2 med en kostnad på 100,00 kronor vardera.
-   2b. Lagrets ekonomiska utleverans uppdateras med kvantiteten 2 med en kostnad på 100,00 kronor vardera.
-   3. Lagerstängningen utförs med den direkta kvittningsmetoden som kvittar lagrets ekonomiska inleverans mot lagrets ekonomiska utleverans.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den direkta kvittningsprincipen utan alternativet Inkludera fysiskt värde. 

![Direktkvittning av viktat medeldatum utan Inkludera fysiskt värde](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) 

**Förklaringar till bilden**
-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom hakparentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde utan hakparentes anger att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas med en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten Lagerstängning.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Viktat medelvärde med summerad kvittning utan alternativet Inkludera fysiskt värde
Viktat medelvärde kvittning baserat på principen att alla inleveranser inom en stängningsperiod summeras till en ny lageröverföringstransaktion som kallas Viktat medelvärde för stängning av lager. Alla inleveranser för den perioden kvittas mot utleveransen för den nya lageröverföringstransaktionen. Alla utleveranser för perioden kvittas mot inleveransen för den nya lageröverföringstransaktionen. Om lagerbehållningen är positiv efter lagerstängningen summeras den lagerbehållningen och värdet på lagret i den nya lageröverföringstransaktionen (utleverans). Om lagerbehållningen är negativ efter lagerstängningen är lagerbehållningen och värdet på lagret summan av enskilda utleveranser som inte har kvittats helt. I scenariot nedan har flera ekonomiskt uppdaterade inleveranser och en utleverans bokförts. 

Under lagerstängningen skapar och bokför systemet den summerade lageröverföringstransaktionen och kvittar alla inleveranser för perioden mot den summerade lageröverföringstransaktionen för utleverans. Alla utleveranser som har bokförts för perioden kvittas mot den summerade lageröverföringstransaktionen för utleverans. Det viktade medelvärdet beräknas till 150,00 kronor. Utleveransen bokfördes från början med en uppskattad självkostnad på 14,67 kronor. Därför skapas och bokförs en negativ justering på 0,33 av utleveransen. Vid lagerstängningsdatumet är lagerbehållningen tre stycken med värdet 450,00 kronor. 

Följande transaktioner visas i bilden nedan:
-   1a. Lagrets fysiska inleverans uppdateras med kvantiteten 2 med en kostnad på 110,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 2 med en kostnad på 140,00 kronor vardera.
-   2a. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 120,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 1 med en kostnad på 160,00 kronor vardera.
-   3a. Lagrets fysiska utleverans uppdateras med kvantiteten 1 med en kostnad på 146,70 kronor vardera (löpande medelvärde).
-   3b. Lagrets ekonomiska utleverans uppdateras med kvantiteten 1 med en kostnad på 146,70 kronor vardera (löpande medelvärde).
-   4a. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 140,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 1 med en kostnad på 160,00 kronor vardera.
-   5. 7. Lagerstängningen utförs.
-   6a. Den ekonomiska utleveranstransaktionen "Viktat medelvärde för stängning av lager” skapas för att summera kvittningen av alla ekonomiska lagerinleveranser.
-   6b. Den ekonomiska inleveranstransaktionen "Viktat medelvärde för stängning av lager” skapas som en motbokning till 5a.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den summerade kvittningsprincipen utan alternativet Inkludera fysiskt värde. 

![Summerad kvittning av viktat medeldatum utan Inkludera fysiskt värde](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Förklaringar till bilden**
-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom hakparentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde utan hakparentes anger att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas med en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten Lagerstängning.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.
-   Röda pilar illustrerar inleveranstransaktioner som kvittas mot utleveranstransaktioner som skapas i systemet.
-   Den gröna pilen visar motbokning av den systemgenererade inleveranstransaktionen som den ursprungliga bokförda utleveranstransaktionen kvittas mot.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Viktad medelvärde med direkt kvittning med alternativet Inkludera fysiskt värde
Parametern som omfattar fysiskt värde fungerar på ett annat sätt med lagermodellen för viktat medelvärde än i tidigare versioner av produkten. Markera kryssrutan Inkludera fysiskt värde för en artikel i formuläret Artikelmodellgrupper. Sedan använder systemet fysiskt uppdaterade inleveranser vid beräkning av den uppskattade självkostnaden, eller det löpande medelvärdet. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet. Vi rekommenderar en månadsvis lagerstängning när du använder lagermodellen för viktat medelvärde. I detta exempel på viktat medelvärde med direkt kvittning markeras artikelmodellgruppen till att inkludera fysiskt värde. 

Följande transaktioner visas i bilden nedan:
-   1a. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 110,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 150,00 kronor vardera.
-   3a. Lagrets fysiska inleverans uppdateras med en kvantitet på 1 med en kostnad på 125,00 kronor vardera (löpande genomsnittlig kostnad, eftersom det fysiska inleveransvärdet tas med i beräkningen).
-   3b. Lagrets ekonomiska inleverans uppdateras med en kvantitet på 1 med en kostnad på 125,00 kronor vardera (löpande genomsnittlig kostnad, eftersom det fysiska inleveransvärdet tas med i beräkningen).
-   4. 7. Lagerstängningen utförs. Under lagerstängningen bortser systemet från alla lagertransaktioner som bara har uppdaterats fysiskt. I stället används den direkta kvittningsprincipen eftersom det bara finns en ekonomisk inleverans. En justering på 25,00 kronor bokförs på lagertransaktionen som har utlevererats ekonomiskt vid lagerstängningsdatumet. Efter lagerstängningen är lagerbehållningen 1 med en löpande genomsnittlig självkostnad på 150,00 kronor.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den direkta kvittningsprincipen med alternativet Inkludera fysiskt värde. 

![Viktat medeldatum med Inkludera fysiskt värde](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) 

**Förklaringar till bilden**
-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom hakparentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde utan hakparentes anger att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas med en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten Lagerstängning.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Viktad medelvärde med summerad kvittning med alternativet Inkludera fysiskt värde
Parametern Inkludera fysiskt värde fungerar på ett annat sätt med viktat medelvärde än i tidigare versioner. Markera kryssrutan Inkludera fysiskt värde för en artikel på sidan Artikelmodellgrupp. Sedan använder systemet fysiskt uppdaterade inleveranser vid beräkning av den uppskattade självkostnaden, eller det löpande medelvärdet. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet. Vi rekommenderar en månadsvis lagerstängning när du använder lagermodellen för viktat medelvärde. I detta exempel på viktat medelvärde med summerad kvittning markeras lagermodellgruppen till att inkludera fysiskt värde. 

Följande transaktioner visas i bilden nedan:
-   1a. Lagrets fysiska inleverans uppdateras med kvantiteten 2 med en kostnad på 110,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 2 med en kostnad på 140,00 kronor vardera.
-   2. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   3a. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 120,00 kronor vardera.
-   3b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 1 med en kostnad på 160,00 kronor vardera.
-   4a. Lagrets fysiska inleverans uppdateras med en kvantitet på 1 med en kostnad på 135,00 kronor vardera (löpande genomsnittlig kostnad, eftersom det fysiska inleveransvärdet tas med i beräkningen).
-   4b. Lagrets ekonomiska inleverans uppdateras med en kvantitet på 1 med en kostnad på 135,00 kronor vardera (löpande genomsnittlig kostnad, eftersom det fysiska inleveransvärdet tas med i beräkningen).
-   5a. Lagrets fysiska inleverans uppdateras med kvantiteten 1 med en kostnad på 140,00 kronor vardera.
-   5b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 1 med en kostnad på 160,00 kronor vardera.
-   6. 7. Lagerstängningen utförs. Under lagerstängningen bortser systemet från alla lagertransaktioner som bara har uppdaterats fysiskt. Den summerade kvittningsprincipen används eftersom det bara finns en ekonomisk inleverans. En justering på 15,00 kronor bokförs på lagertransaktionen som har utlevererats ekonomiskt vid lagerstängningsdatumet. Efter lagerstängningen är lagerbehållningen 3 med en löpande genomsnittlig självkostnad på 150,00 kronor.
-   7a. Den ekonomiska utleveranstransaktionen "Viktat medelvärde för stängning av lager” skapas för att summera kvittningen av alla ekonomiska lagerinleveranser.
-   7b. Den ekonomiska inleveranstransaktionen "Viktat medelvärde för stängning av lager” skapas som en motbokning till 5a.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde och den summerade kvittningsprincipen utan alternativet Inkludera fysiskt värde. 

![Summerad kvittning av viktat medeldatum med Inkludera fysiskt värde](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) 

**Förklaringar till bilden**
-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom hakparentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde utan hakparentes anger att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas med en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel 1a. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten Lagerstängning.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.
-   Röda pilar illustrerar inleveranstransaktioner som kvittas mot utleveranstransaktioner som skapas i systemet.
-   Den gröna pilen visar motbokning av den systemgenererade inleveranstransaktionen som den ursprungliga bokförda utleveranstransaktionen kvittas mot.

## <a name="weighted-average-with-marking"></a>Viktat medelvärde med länkning
Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs. 

Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för den här artikeln för att kunna tillgodose kundens krav. Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor, för den här försäljningsorderfakturan. 

När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. T.ex. markeras försäljningsorderdokumentet för inköpsordern, innan följesedeln eller fakturan bokförs. Kostnaden för sålda varor kommer då att bli 120,00 kronor i stället för den aktuella löpande genomsnittlig kostnad för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan länkningen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden. 

Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra. 

En inleveranstransaktion markeras för en utleveranstransaktion. I detta fall markeras den definierade värderingsmetoden för artikelns artikelmodellgrupp och systemet kvittar dessa transaktioner mot varandra. 

Du kan markera ett problem transaktion till en inleverans innan en transaktion bokförs. Du kan göra detta från en försäljningsorderrad på sidan Försäljningsorderdetaljer. De öppna inleveranstransaktionerna visas på sidan Markering. 

Du kan markera ett problem transaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal. 

Följande transaktioner visas i bilden nedan:
-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
-   5a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor (löpande medelvärde för ekonomiskt och fysiskt uppdaterade transaktioner).
-   5b. Lagrets ekonomiska utleverans för kvantiteten 1 länkas till lagerinleveransen 2b innan transaktionen bokförs. Den här transaktionen bokförs till självkostnaden 200,00 kronor.
-   6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor vardera.
-   7. Lagerstängningen utförs. Eftersom de ekonomiskt uppdaterade transaktionerna länkas till en befintlig inleverans kvittas dessa transaktioner mot varandra och ingen justerings görs.

Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 275,00 kronor. 

I bilden nedan visas hur den här serien med transaktioner påverkas om du väljer lagermodellen för viktat medelvärde med markering. 

![Viktat medelvärde med Markering](./media/weightedaveragewithmarking.gif) 

**Förklaringar till bilden**
-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formatet Quantity@Unitprice.
-   Ett lagertransaktionsvärde inom hakparentes anger att lagertransaktionen har bokförts fysiskt i lagret.
-   Ett lagertransaktionsvärde utan hakparentes anger att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas med en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten Lagerstängning.
-   Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.






