---
title: "Datum för viktat medelvärde"
description: 
author: AndersGirke
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
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 95cc937a97596e4f6ce28636fb30b86e9b328220
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="weighted-average-date"></a>Datum för viktat medelvärde

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Viktat genomsnittligt datum är en lagermodell som baseras på principen om viktat medelvärde. För principen om viktat medelvärde värderas utleveranser från lagret till medelvärdet av artiklarna som inlevereras till lagret för varje enskild dag i lagerstängningsperioden. När du kör en lagerstängning genom att använda viktat genomsnittligt datum, kvittas alla dagliga inleveranser mot en virtuell utleverans. Den virtuella utleveransen innehåller den totala inlevererade kvantiteten och värdet för dagen. Den virtuella utleveransen har en motsvarande virtuell inleverans som utleveranserna kvittas mot. På så sätt får alla utleveranser samma genomsnittskostnad. Den virtuella utleveransen och inleveransen kan ses som en virtuell överföring, som kallas *viktat medelvärde för stängning av lager*. 

Om bara en inleverans har gjorts på eller före datumet, behöver du inte värdera medelvärdet av dessa. Eftersom alla utleveranser kvittas från den inleveransen, kommer den virtuella överföringen inte att skapas. Om bara utleveranser görs på datumet finns det heller inga inleveranser att värdera medelvärdet från, och den virtuella överföringen skapas inte heller i detta fall. När du använder viktat genomsnittligt datum kan du markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans. I det här fallet används inte regeln för viktat genomsnittligt datum. Vi rekommenderar en lagerstängning varje månad när du använder lagermodellen med datum för viktat medelvärde. 

Följande formel används för att beräkna viktat genomsnittligt datum för kostnadsredovisningsmetod. 

Viktat medelvärde = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q*n* × P*n*\]) ÷ (Q1 + Q2 + Q*n*) 

Under lagerstängningen utförs beräkningen dagligen under hela stängningsperioden vilket visas i följande bild. 

![Modell för daglig beräkning av viktat medeldatum](./media/weightedaveragedatedailycalculationmodel.gif) 

Lagertransaktioner som lämnar lagerinleveranserna, bland anat försäljningsorder, lagerjournaler, inköpskreditfakturor och tillverkningsorder, gör det med en uppskattad självkostnad vid bokföringsdatumet. Denna uppskattade självkostnad kallas också för löpande genomsnittlig självkostnad. På datumet för lagerstängningen analyserar systemet lagertransaktionerna för föregående perioder, föregående dagar och den aktuella dagen. Denna analys används för att avgöra vilken av följande stängningsprinciper som ska användas:

-   Direkt kvittning
-   Summerad kvittning

Kvittningar är lagerstängningstransaktioner som justerar utleveranser till rätt viktat medelvärde vid stängningsdatumet. 

**Obs!** Mer information om kvittning i Dynamics AX finns i artikeln om lagerstängning. I följande exempel visas effekten av att använda viktat medelvärde med fem olika konfigurationer:

-   Viktat genomsnittligt datum med direkt kvittning när alternativet **Inkludera fysiskt värde** inte används.
-   Viktat genomsnittligt datum med summerad kvittning när **Inkludera fysiskt värde** inte används
-   Viktat genomsnittligt datum med direkt kvittning när alternativet **Inkludera fysiskt värde** används.
-   Viktat genomsnittligt datum med summerad kvittning när **Inkludera fysiskt värde** används
-   Viktat genomsnittligt datum när markering används

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Viktat genomsnittligt datum med direkt kvittning när alternativet Inkludera fysiskt värde inte används
I den aktuella versionen används samma direkta kvittningsprincip som används i tidigare här versioner för viktat genomsnitt. Systemet kvittar direkt mellan inleveranser och utleveranser. Systemet använder denna direkta kvittningsprincip i särskilda situationer:

-   En inleverans och en eller flera utleveranser har bokförts under perioden.
-   Enbart utleveranser har bokförts under perioden och lagret innehåller artikelbehållning från en tidigare stängning.

I scenariot nedan har en ekonomiskt uppdaterad inleverans och utleverans bokförts. Under lagerstängningen kvittar systemet inleveransen direkt mot utleveransen, och ingen justering av självkostnaden behövs för utleveransen. 

Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans uppdateras med kvantiteten 5 med en kostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 5 med en kostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska utleverans uppdateras med kvantiteten 2 med en kostnad på 100,00 kronor vardera.
-   2b. Lagrets ekonomiska utleverans uppdateras med kvantiteten 2 med en kostnad på 100,00 kronor vardera.
-   3. Lagerstängningen utförs med den direkta kvittningsmetoden som kvittar lagrets ekonomiska inleverans mot lagrets ekonomiska utleverans.

![Viktat genomsnittligt datum med direkt kvittning utan alternativet Inkludera fysiskt värde](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) 

**Förklaring till bilden:**

-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formuläret *Kvantitet*@*Enhetspris*.
-   Om ett lagertransaktionsvärde är inom parentes anger det att lagertransaktionen har bokförts fysiskt i lagret.
-   Om ett lagertransaktionsvärde inte är inom parentes anger det att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
-   Kvittningar som utförs av en lagerstängning visas som streckade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Viktat genomsnittligt datum med summerad kvittning när Inkludera fysiskt värde inte används
Viktat genomsnitt baseras på principen att alla inleveranser i en stängningsperiod summeras till en ny lageröverföringstransaktion. Denna transaktion kallas *viktad genomsnittlig lagerstängning* Alla inleveranser för den dagen kvittas mot utleveransen för den nya lageröverföringstransaktionen. Alla utleveranser för dagen kvittas mot inleveransen för den nya lageröverföringstransaktionen. Om lagerbehållningen är positiv efter lagerstängningen summeras den lagerbehållningen och värdet på lagret i den nya lageröverföringstransaktionen (utleverans). Om lagerbehållningen är negativ efter lagerstängningen är lagerbehållningen och värdet på lagret summan av enskilda utleveranser som inte har kvittats helt. 

I scenariot nedan har flera ekonomiskt uppdaterade inleveranser och utleveranser bokförts under perioden. Under lagerstängningen utvärderar systemet varje dag för att fastställa hur varje dag ska behandlas i stängningen. 

Illustrationen som följer visar dessa transaktioner: 

**Dag 1:**

-   1a. Lagrets fysiska inleverans uppdateras med kvantiteten 3 med en kostnad på 150,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans uppdateras med kvantiteten 3 med en kostnad på 150,00 kronor vardera.
-   2a. Lagrets fysiska utleverans för kvantiteten 1 till en löpande genomsnittlig självkostnad på 150,00 kronor vardera.
-   2b. Lagrets ekonomiska utleverans för kvantiteten 1 till en löpande genomsnittlig självkostnad på 150,00 kronor vardera.

I systemet används direkt kvittning för dag 1. 

**Dag 2:**

-   3a. Lagrets fysiska utleverans för kvantiteten 1 till en löpande genomsnittlig självkostnad på 150,00 kronor vardera.
-   3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en löpande genomsnittlig självkostnad på 150,00 kronor vardera.

I systemet används direkt kvittning för dag 2. 

**Dag 3:**

-   4a. Lagrets fysiska utleverans för kvantiteten 1 till en löpande genomsnittlig självkostnad på 150,00 kronor vardera.
-   4b. Lagrets ekonomiska utleverans för kvantiteten 1 till en löpande genomsnittlig självkostnad på 150,00 kronor vardera.
-   5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 170,00 kronor vardera.
-   5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 170,00 kronor vardera.

Lagerstängningen utförs. Den direkta kvittningen måste användas eftersom det finns flera utleveranser under flera dagar.

-   7a. Den ekonomiska inleveranstransaktionen "Viktat medelvärde för stängning av lager” skapas för kvantiteten 2 till 320,00 kronor som summerar kvittningarna av alla ekonomiska lagerutleveranser fram till det datum som ännu inte har stängts.
-   7b. Den ekonomiska inleveranstransaktionen "Viktat medelvärde för stängning av lager” skapas som en motbokning till 7a.

Systemet skapar och bokför den summerade lageröverföringstransaktionen. Dessutom kvittar systemet alla inleveranser för dagen och lagerbehållningen för föregående dagar mot den summerade lageröverföringstransaktionen för utleverans. Alla utleveranser för dagen kvittas mot den summerade lageröverföringstransaktionen för utleverans. Den viktade genomsnittliga självkostnaden beräknas till 160,00 kronor. Utleveransen får en justering på 10,00 så att den viktade genomsnittskostnaden justeras. Den nya löpande genomsnittliga självkostnaden är 160,00. 

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde med den summerade kvittningsprincipen utan alternativet **Inkludera fysiskt värde**. 

![Viktat genomsnittligt datum med summerad kvittning utan alternativet Inkludera fysiskt värde](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Förklaring till bilden**

-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formuläret *Kvantitet*@*Enhetspris*.
-   Om ett lagertransaktionsvärde är inom parentes anger det att lagertransaktionen har bokförts fysiskt i lagret.
-   Om ett lagertransaktionsvärde inte är inom parentes anger det att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
-   Kvittningar som utförs av en lagerstängning visas som streckade röda pilar som löper diagonalt från en inleverans till en utleverans.
-   Fasta röda diagonala pilar visar inleveranstransaktioner som kvittas mot utleveranstransaktioner som skapas i systemet.
-   Den fasta gröna diagonala pilen visar motbokningen av den systemgenererade inleveranstransaktionen som den ursprungliga bokförda utleveranstransaktionen kvittas mot.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Viktat genomsnittligt datum med direkt kvittning när alternativet Inkludera fysiskt värde används.
I den aktuella versionen används samma direkta kvittningsprincip som används i tidigare här versioner för viktat genomsnitt. Systemet kvittar direkt mellan inleveranser och utleveranser. Systemet använder denna direkta kvittningsprincip i särskilda situationer:

-   En inleverans och en eller flera utleveranser har bokförts under perioden.
-   Enbart utleveranser har bokförts under perioden och lagret innehåller lagerbehållning från en tidigare stängning.

Om du väljer kryssrutan **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupp** använder systemet fysiska uppdaterade inleveranser för att beräkna uppskattad självkostnad eller löpande genomsnittlig självkostnad. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Viktat genomsnittligt datum med summerad kvittning när Inkludera fysiskt värde används
Om du väljer kryssrutan **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupp** använder systemet fysiska uppdaterade inleveranser för att beräkna uppskattad självkostnad eller löpande genomsnittlig självkostnad. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet. Viktat medelvärde vid kvittning baseras på principen att inleveranser inom en stängningsperiod summeras till en ny lageröverföringstransaktion som kallas *Viktat medelvärde för stängning av lager*. Alla inleveranser för den dagen kvittas mot utleveransen för den nya lageröverföringstransaktionen. Alla utleveranser för dagen kvittas mot inleveransen för den nya lageröverföringstransaktionen. Om lagerbehållningen är positiv efter lagerstängningen summeras den lagerbehållningen och värdet på lagret i den nya lageröverföringstransaktionen (utleverans). Om lagerbehållningen är negativ efter lagerstängningen är lagerbehållningen och värdet på lagret summan av enskilda utleveranser som inte har kvittats helt.

## <a name="weighted-average-date-when-marking-is-used"></a>Viktat genomsnittligt datum när markering används
Märkning är en process som gör det möjligt att länka en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs. 

Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för den här artikeln för att kunna tillgodose kundens krav. Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor, för den här försäljningsorderfakturan. När inköpsordern bokförs inlevereras lagret till en kostnad på 1200,000 kronor. Försäljningsorderdokumentet markeras för inköpsordern, innan följesedeln eller fakturan bokförs. Kostnaden för sålda varor kommer då att bli 120,00 kronor i stället för den aktuella löpande genomsnittlig kostnad för artikeln. Om försäljningsorderns följesedel eller fakturan bokförs innan länkningen görs, bokförs kostnaden för sålda varor till den löpande genomsnittliga självkostnaden. Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra. När en inleveranstransaktion är markerad på en utleveranstransaktion, ignoreras den definierade värderingsmetoden för artikelmodellgruppen. I stället kvittar systemet dessa transaktioner mot varandra. 

Du kan markera ett problem transaktion till en inleverans innan en transaktion bokförs. Du kan göra detta från en försäljningsorderrad på sidan **Försäljningsorderdetaljer**. Du kan visa de öppna inleveranstransaktionerna på sidan **Markering**. Du kan markera ett problem transaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal. Illustrationen som följer visar dessa transaktioner:

-   1a. Lagrets fysiska inleverans för kvantiteten 1 med en självkostnad på 100,00 kronor vardera.
-   1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en självkostnad på 100,00 kronor vardera.
-   2a. Lagrets fysiska inleverans för kvantiteten 1 med en självkostnad på 200,00 kronor vardera.
-   2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en självkostnad på 200,00 kronor vardera.
-   3a. Lagrets fysiska inleverans för kvantiteten 1 med en självkostnad på 250,00 kronor vardera.
-   4a. Lagrets fysiska inleverans för kvantiteten 1 med en självkostnad på 300,00 kronor vardera.
-   4b. Lagrets ekonomiska inleverans för kvantiteten 1 med en självkostnad på 300,00 kronor vardera.
-   5a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor (löpande medelvärde för ekonomiskt och fysiskt uppdaterade transaktioner).
-   5b. Lagrets ekonomiska utleverans för kvantiteten 1 länkas till lagerinleveransen 2b innan transaktionen bokförs. Den här transaktionen bokförs till självkostnaden 200,00 kronor.
-   6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 212,50 kronor.
-   7. 7. Lagerstängningen utförs. Eftersom de ekonomiskt uppdaterade transaktionerna länkas till en befintlig inleverans kvittas dessa transaktioner mot varandra och ingen justerings görs.

Den nya löpande genomsnittliga självkostnaden återspeglar genomsnittet av ekonomiskt och fysiskt uppdaterade transaktioner på 275,00 kronor. I bilden nedan visas hur den här serien med transaktioner påverkas om du väljer lagermodell med datum för viktat medelvärde och markering.

![Viktat genomsnittligt datum med markering](./media/weightedaveragedatewithmarking.gif) 

**Förklaring till bilden:**

-   Lagertransaktioner visas som lodräta pilar.
-   Inleveranser till lagret visas som lodräta pilar ovanför tidslinjen.
-   Utleveranser från lagret visas som lodräta pilar under tidslinjen.
-   Ovanför (eller under) respektive lodrät pil anges värdet på lagertransaktionen i formuläret *Kvantitet*@*Enhetspris*.
-   Om ett lagertransaktionsvärde är inom parentes anger det att lagertransaktionen har bokförts fysiskt i lagret.
-   Om ett lagertransaktionsvärde inte är inom parentes anger det att lagertransaktionen har bokförts ekonomiskt i lagret.
-   Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
-   Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
-   Lagerstängningar visas som en röd lodrät streckad linje och etiketten *Lagerstängning*.
-   Kvittningar som utförs av en lagerstängning visas som streckade röda pilar som löper diagonalt från en inleverans till en utleverans.





