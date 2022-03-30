---
title: Viktat genomsnittsdatum med Inkludera fysiskt värde och länkning
description: Datum för viktat medelvärde är en lagermodell som bygger på principen om viktat medelvärde, där utleveranser från lagret värderas till medelvärdet av artiklarna som inlevereras till lagret för varje dag i lagerstängningsperioden.
author: AndersGirke
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cf2206863d891eceb9c65ff879da3f9f72032b1
ms.sourcegitcommit: fcded93fc6c27768a24a3d3dc5cc35e1b4eff22b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392011"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Viktat genomsnittsdatum med Inkludera fysiskt värde och länkning

[!include [banner](../includes/banner.md)]

*Viktat genomsnittsdatum* är en lagermodell som baseras på ett medelvärde beröknat genom att multiplicera respektive komponent (artikeltransaktion) med en faktor (självkostnad) som återspeglar dess vikt (kvantitet) för respektive datum under perioden. Med andra ord tilldelar denna lagermodell kostnaden för ärendetransaktioner baserat på medelvärdet av allt lager som tas emot under respektive dag, plus eventuell lagerbehållning från föregående dag.

När du kör en lagerstängning genom att använda lagermodellen för viktat medelvärde kan du skapa en kvittning med hjälp av två olika metoder. Vanligtvis kvittas alla inleveranser mot en virtuell utleverans som innehåller den totala inlevererade kvantiteten och det totala inlevererade värdet. Denna virtuella utleverans har en motsvarande virtuell inleverans mot vilken utleveranser kvittas. På så sätt får alla utleveranser samma genomsnittskostnad varje dag. Den virtuella utleveransen och den virtuella inleveransen kan betraktas som en virtuell överföring. Denna virtuella överföring kallas för *överföring av viktat medelvärde vid lagerstängning*. Denna kvittningsmetod kallas därför för *viktat medelvärde vid summerad kvittning*. Om det endast finns en inleverans kan alla utleveranser kvittas mot den, och ingen virtuell överföring skapas. Denna kvittningsmetod kallas för *direkt kvittning*. Allt lager som finns kvar efter lagerstängningen värderas till det viktade medelvärdet från den sista dagen under föregående period och inkluderas i beräkningen av det viktade datummedelvärdet under nästa period.

Du kan åsidosätta principen för viktat genomsnittsdatum genom att markera lagertransaktioner så att en specifik artikelinleverans kvittas mot en specifik utleverans. En periodisk lagerstängning krävs när du använder lagermodellen för viktat genomsnittsdatum för att skapa kvittningar och justera värdet på utleveranser enligt principen om viktat genomsnittsdatum. Fram tills dess att du kör lagerstängningsprocessen värderas utleveranstransaktioner till löpande medelvärde när de fysiska och ekonomiska uppdateringarna genomförs. Om du inte använder länkning beräknas det löpande medelvärdet när den fysiska eller ekonomiska uppdateringen utförs.

Metoden med viktat genomsnittsatum för kostnadsredovisning för lager beräknas med följande formel för respektive dag:

*Kostnad* = \[(*Q*<sub>*b*</sub> × *P*<sub>*b*</sub>) + &#x2211;<sub>*n*</sub>(*Q*<sub>*n*</sub> × *P*<sub>*n*</sub>)\] ÷ (*Q*<sub>*b*</sub> + &#x2211;<sub>*n*</sub>*Q*<sub>*n*</sub>)

- *Q* = transaktionens kvantitet
- *P* = transaktionspris

Med andra ord är den viktade genomsnittskostnaden lika med startkvantiteten gånger det första priset plus summan av varje inleveranskvantitet gånger inleveranspriset, allt dividerat med den första kvantiteten plus summan av inleveranskvantiteterna.

Under lagerstängningen utförs beräkningen dagligen under hela stängningsperioden.

> [!NOTE]
> Mer information om kvittningar finns i [Stängning av lager](inventory-close.md).

I följande exempel visas effekten av att använda viktat genomsnittsdatum med fem olika konfigurationer:

- Viktat genomsnittligt datum med direkt kvittning när alternativet **Inkludera fysiskt värde** inte används.
- Viktat genomsnittligt datum med summerad kvittning när **Inkludera fysiskt värde** inte används
- Viktat genomsnittligt datum med direkt kvittning när alternativet **Inkludera fysiskt värde** används.
- Viktat genomsnittligt datum med summerad kvittning när **Inkludera fysiskt värde** används
- Viktat genomsnittligt datum när länkning används

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Viktat genomsnittligt datum med direkt kvittning när alternativet Inkludera fysiskt värde inte används

Den direkta kvittningsprincipen skapar kvittningar direkt mellan in- och utleveranser utan att ytterligare lagertransaktioner skapas. Systemet använder denna direkta kvittningsprincip i följande situationer:

- En inleverans och en eller flera utleveranser har bokförts under perioden.
- Enbart utleveranser har bokförts under perioden och lagret innehåller artikelbehållning från en tidigare stängning.

I det här exemplet avmarkeras kryssrutan **Inkludera fysiskt värde** på sidan **artikelmodellgruppen** för den frisläppta produkten. Bilden som följer visar dessa transaktioner:

**Dag 1:**

- 1a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 20,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 10,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 10,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).

**Dag 2:**

- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 20,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).

**Dag 3:**

- 7\. Lagerstängningen utförs. Baserat på metoden för viktat genomsnittsdatum använder systemet den direkta kvittningsmetoden för 30 december (12/30), detta eftersom bara en inleverans uppdateras ekonomiskt 12/30. I det här exemplet skapas en kvittning mellan transaktionerna 1b och 3b. En justering på USD 10,00 görs för att få värdet för transaktion 3b att justeras till 20,00. Ingen justering eller kvittning görs den 31 december (31/12) eftersom det inte finns några ekonomiskt uppdaterade utleveranser den 31/12.

I bilden nedan visas hur den här serien med transaktioner påverkas när du använder lagermodellen för viktat medelvärde och den direkta kvittningsprincipen utan alternativet **Inkludera fysiskt värde**.

![Viktat genomsnittligt datum med direkt kvittning utan alternativet Inkludera fysiskt värde.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**Bildförklaringar:**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Datumen avgränsas av tunna, svarta lodräta rader. Datumen anges längst ned på bilden.
- Lagerstängningar visas som en röda, lodräta streckade linjer.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Viktat genomsnittligt datum med summerad kvittning när Inkludera fysiskt värde inte används

När det finns flera kvitton under en period använder det viktade genomsnittsdatumet principen om sammanfattad kvittning, där alla inleveranser under en och samma dag sammanfattas till en transaktion kallad *Viktat medelvärde för stängning av lager*. Alla inleveranser för dagen kvittas mot utleveransen för den nya lageröverföringstransaktionen. Alla utleveranser för dagen kvittas mot inleveransen för den nya lagertransaktionen. Om lagerbehållning finns efter lagerstängningen inkluderas lagerbehållningen i den nya lagertransaktionen för det viktade genomsnittet av lagerstängningstransaktionerna.

Bilden som följer visar dessa transaktioner:

**Dag 1:**

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).

**Dag 2:**

- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 23,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).

**Dag 3:**

- 7\. Lagerstängningen utförs.
- 7a. Den ekonomiska utleveranstransaktionen för viktat medelvärde för stängning av lager skapas för att summera kvittningen av alla ekonomiska lagerinleveranser.

    - Transaktion 1b kvittas för kvantiteten 1 med ett kvitterat belopp på 10,00 USD.
    - Transaktion 2b kvittas för kvantiteten 1 med ett kvitterat belopp på 22,00 USD.
    - Transaktion 7a skapas för kvantiteten 2 med ett kvitterat belopp på 32,00 USD. Denna transaktion motbokar summan av de två inleveranstransaktionerna som uppdateras ekonomiskt under perioden.

- 7b. Ekonomisk inleverans för viktat medelvärde för stängning av lager skapas som en motbokning för ekonomiskt bokförda utleveranser.

    - Transaktion 3b kvittas för kvantiteten 1 med ett kvitterat belopp på 16,00 USD. Denna transaktion justeras inte eftersom den utgör det viktade medelvärdet för ekonomiskt bokförda transaktioner den 1 december (12/1).
    - Transaktion 7b skapas för kvantiteten 2 med det ekonomiska beloppet USD 32,00 och ett kvittat belopp om 16,00 USD som motkonto mot transaktion 3b. Denna transaktion motbokar summan av den utleveranstransaktion som uppdateras ekonomiskt under perioden. Transaktionen förblir öppen eftersom det fortfarande finns en (1) behållning.

I bilden nedan visas hur den här serien med transaktioner påverkas när du väljer lagermodellen för viktat medelvärde med den summerade kvittningsprincipen, men utan alternativet **Inkludera fysiskt värde**.

![Viktat genomsnittligt datum med summerad kvittning utan alternativet Inkludera fysiskt värde.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**Bildförklaringar:**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Datumen avgränsas av tunna, svarta lodräta rader. Datumen anges längst ned på bilden.
- Lagerstängningar visas som en röda, lodräta streckade linjer.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Viktat genomsnittligt datum med direkt kvittning när alternativet Inkludera fysiskt värde används.

I produktens senaste version fungerar alternativet **Inkludera fysiskt värde** på ett annat sätt med lagermodellen för viktat genomsnittsdatum än i tidigare versioner. Närdu väljer kryssrutan **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupp** använder systemet fysiska uppdaterade inleveranser för att beräkna uppskattad självkostnad eller löpande genomsnittlig självkostnad. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet.

Bilden som följer visar dessa transaktioner:

**Dag 1:**

- 1a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 10 med en kostnad på 10,00 USD vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 10 med en kostnad på 20,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till självkostnaden 15,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).

**Dag 2:**

- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 21,25 USD per styck (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).

**Dag 3:**

- 7\. Lagerstängningen utförs. Baserat på metoden för viktat genomsnittsdatum använder systemet den direkta kvittningsmetoden för 30 december (12/30), detta eftersom bara en inleverans uppdateras ekonomiskt 12/30. I det här exemplet skapas en kvittning mellan transaktionerna 1b och 3b. Ingen justering görs av utleveransen den 30/12. Ingen justering eller kvittning görs heller den 31 december (31/12) eftersom det inte finns några ekonomiskt uppdaterade utleveranser den 31/12.

I bilden nedan visas hur den här serien med transaktioner påverkas när du använder lagermodellen för viktat medelvärde och den direkta kvittningsprincipen med alternativet **Inkludera fysiskt värde**.

![Viktat medelvärde med direkt kvittning samt med Inkludera fysiskt värde.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**Bildförklaringar:**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Datumen avgränsas av tunna, svarta lodräta rader. Datumen anges längst ned på bilden.
- Lagerstängningar visas som en röda, lodräta streckade linjer.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Viktat genomsnittligt datum med summerad kvittning när Inkludera fysiskt värde används

I produktens senaste version fungerar alternativet **Inkludera fysiskt värde** på ett annat sätt med genomsnitt än i tidigare versioner. När du väljer kryssrutan **Inkludera fysiskt värde** för en artikel på sidan **Artikelmodellgrupp** använder systemet fysiskt uppdaterade inleveranser för att beräkna uppskattad självkostnad eller löpande genomsnittlig självkostnad. Utleveranser bokförs utifrån denna uppskattade självkostnad under perioden. Vid lagerstängningen tas det bara hänsyn till ekonomiskt uppdaterade inleveranser i beräkningen av det viktade medelvärdet. Vi rekommenderar att du genomför en månadsvis lagerstängning när du använder lagermodellen för viktat medelvärde. I detta exempel på viktat genomsnittsdatum med summerad kvittning markeras lagermodellgruppen till att inkludera fysiskt värde.

Bilden som följer visar dessa transaktioner:

**Dag 1:**

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 16,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till självkostnaden 16,00 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).

**Dag 2:**

- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till självkostnaden 23,67 USD (löpande medelvärde för fysiskt och ekonomiskt bokförda transaktioner).

**Dag 3:**

- 7\. Lagerstängningen utförs.
- 7a. Den ekonomiska utleveranstransaktionen för viktat medelvärde för stängning av lager skapas för att summera kvittningen av alla ekonomiska lagerinleveranser.

    - Transaktion 1b kvittas för kvantiteten 1 med ett kvitterat belopp på 10,00 USD.
    - Transaktion 2b kvittas för kvantiteten 1 med ett kvitterat belopp på 22,00 USD.
    - Transaktion 7a skapas för kvantiteten 2 med ett kvitterat belopp på 32,00 USD. Denna transaktion motbokar summan av de två inleveranstransaktionerna som uppdateras ekonomiskt under perioden.

- 7b. Ekonomisk inleverans för viktat medelvärde för stängning av lager skapas som en motbokning för ekonomiskt bokförda utleveranser.

    - Transaktion 3b kvittas för kvantiteten 1 med ett kvitterat belopp på 16,00 USD. Denna transaktion justeras inte eftersom den utgör det viktade medelvärdet för ekonomiskt bokförda transaktioner den 1 december (12/1).
    - Transaktion 7b skapas för kvantiteten 2 med det ekonomiska beloppet USD 32,00 och ett kvittat belopp om 16,00 USD som motkonto mot transaktion 3b. Denna transaktion motbokar summan av den utleveranstransaktion som uppdateras ekonomiskt under perioden. Transaktionen förblir öppen eftersom det fortfarande finns en (1) behållning.

I bilden nedan visas hur den här serien transaktioner påverkas när du använder lagermodellen för viktat medelvärde och den sammanfattade kvittningsprincipen utan alternativet **Inkludera fysiskt värde**.

![Viktad medelvärde med summerad kvittning med alternativet Inkludera fysiskt värde.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**Bildförklaringar:**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Datumen avgränsas av tunna, svarta lodräta rader. Datumen anges längst ned på bilden.
- Lagerstängningar visas som en röda, lodräta streckade linjer.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

## <a name="weighted-average-date-when-marking-is-used"></a>Viktat genomsnittligt datum när länkning används

Märkning är en process som gör det möjligt att länka, eller markera, en utleveranstransaktion till en inleveranstransaktion. Länkning kan göras antingen före eller efter att en transaktion bokförs. Du kan använda länkning när du vill vara säker på den exakta kostnaden för lagret när transaktionen bokförs eller när lagerstängningen utförs.

Din kundtjänstavdelning har till exempel accepterat en snabborder från en viktig kund. Eftersom det är en snabborder måste du betala mer för denna artikel för att kunna tillgodose kundens begäran. Du måste vara säker på att kostnaden för den här lagerartikeln återspeglas i marginalen, eller kostnaderna för sålda varor (KSV), för den här försäljningsorderfakturan.

När inköpsordern bokförs inlevereras lagret till en kostnad på 120,00 USD. Om detta försäljningsorderdokument länkas till inköpsordern innan följesedeln eller fakturan bokförs, blir kostnaden för sålda varor (KSV) 120,00 USD istället för den aktuella löpande genomsnittliga kostnaden för artikeln. Om länkningen inträffar efter det att följesedeln eller fakturan för försäljningsorder bokförs,kommer kostnaden för sålda varor (KSV) att bokföras till den löpande genomsnittliga självkostnaden.

Innan lagerstängningen utförs kan dessa två transaktioner fortfarande länkas till varandra.

Om en inleveranstransaktion länkas till en utleveranstransaktion ignoreras den värderingsmetod som valts för artikelns modellgrupp, och systemet kvittar dessa transaktioner mot varandra.

Du kan markera en utleveranstransaktion till en inleverans innan en transaktion bokförs. Du kan utföra denna länkning från en försäljningsorderrad på sidan **Försäljningsorderdetaljer**. De öppna inleveranstransaktionerna visas på sidan **Länkning**.

Du kan också markera en utleveranstransaktion till en inleverans efter en transaktion bokförs. Du kan matcha eller markera en utleveranstransaktion för en öppen inleveranstransaktion för en inventerad artikel från en bokförd lagerjusteringsjournal.

Bilden som följer visar dessa transaktioner:

**Dag 1:**

- 1a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 1b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 100,00 kronor vardera.
- 2a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 200,00 kronor vardera.
- 2b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 22,00 USD vardera.
- 3a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3b. Lagrets ekonomiska utleverans för kvantiteten 1 till en självkostnad på 16,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).
- 3c. Lagrets ekonomiska utleverans för transaktion 3b markeras till lagrets ekonomiska utleverans för transaktion 2b.

**Dag 2:**

- 4a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 250,00 kronor vardera.
- 5a. Lagrets fysiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 5b. Lagrets ekonomiska inleverans för kvantiteten 1 med en kostnad på 300,00 kronor vardera.
- 6a. Lagrets fysiska utleverans för kvantiteten 1 till en självkostnad på 23,00 USD vardera (löpande medelvärde eller ekonomiskt bokförda transaktioner).

**Dag 3:**

- 7\. Lagerstängningen utförs. Baserat på länkningsprincipen som använder metoden för viktat medelvärde kvittas de markerade transaktionerna mot varandra. I det här exemplet kvittas transaktion 3b mot transaktion 2b och en justering på 6,00 USD bokförs på transaktion 3b för att få värdet 22,00 USD. I det här exemplet görs inga ytterligare kvittningar eftersom stängningen bara skapar kvittningar för finansiellt uppdaterade transaktioner.

I bilden nedan visas hur den här serien med transaktioner påverkas om du väljer lagermodell med viktat medelvärde och länkning.

![Viktat medelvärde med länkning.](media/weighted-average-date-with-marking.png)

**Bildförklaringar:**

- Lagertransaktioner visas som lodräta pilar.
- Fysiska transaktioner visas som kortare ljusgrå pilar.
- Ekonomiska transaktioner visas som längre svart pilar.
- Inleveranser till lagret visas som lodräta pilar ovanför axeln.
- Utleveranser från lagret visas som lodräta pilar under axeln.
- Varje ny inleverans- eller utleveranstransaktion betecknas av en ny etikett.
- Varje lodrät pil har en etikett med ett ordnings-ID, till exempel *1a*. Dessa ID:n anger ordningen på lagertransaktionsbokningarna utmed tidslinjen.
- Datumen avgränsas av tunna, svarta lodräta rader. Datumen anges längst ned på bilden.
- Lagerstängningar visas som en röda, lodräta streckade linjer.
- Kvittningar som utförs av en lagerstängning visas som prickade röda pilar som löper diagonalt från en inleverans till en utleverans.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
