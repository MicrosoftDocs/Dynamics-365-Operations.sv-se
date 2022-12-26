---
title: Vanliga frågor och svar om aktiviteter för årsbokslut
description: Artikeln innehåller frågor som kan uppkomma när du stänger ett år och svar som kan hjälpa till med aktiviteter vid årsbokslut.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853053"
---
# <a name="year-end-activities-faq"></a>Vanliga frågor och svar om aktiviteter för årsbokslut 

[!include [banner](../includes/banner.md)]

Artikeln innehåller frågor som kan uppkomma när du stänger ett år och svar som kan hjälpa till med aktiviteter vid årsbokslut. Informationen i artikeln rör sig framförallt om frågor kring aktiviteter vid årsbokslut i redovisning och leverantörsreskontra.

## <a name="general-ledger-year-end-enhancements"></a>Förbättringar av årsbokslut i redovisning

Microsoft Dynamics 365 Finance version 10.0.20 innehåller en förbättring av årsbokslut. Den här förbättringen aktiveras som standard från version 10.0.25 och är obligatorisk i version 10.0.29. Om din organisation använder en version tidigare än 10.0.25 rekommenderar vi att du aktiverar funktionen innan du påbörjar årsbokslutet. Innan du kan använda funktionen måste den aktiveras i ditt system. Administratörer kan använda arbetsytan **Funktionshantering** för att kontrollera funktionens status och aktivera den vid behov. Funktionen visas på följande sätt:

- **Modul:** Redovisning
- **Funktionsnamn:** Förbättringar av redovisning vid bokslut

Inställningar av mallar för stängning vid årsslut har flyttats till en ny inställningssida, **Inställning av mallar för årsbokslut**. Den befintliga sidan för årsbokslut ändras till att likna sidan **Omräkning i utländsk valuta för redovisning**, där en lista visas varje gång årsbokslut körs eller återförs. På sidan visas ingen historisk information om årsbokslut som gjordes innan funktionen aktiverades. En redovisningschef kan initiera årsbokslut från den nya sidan.

För att återföra årsbokslut väljer du det senaste räkenskapsåret för korrekt juridisk person och väljer **Återför årsbokslut**. Återföringen raderar redovisningsposterna för det föregående årsbokslutet och kör inte årsbokslutet på nytt automatiskt. Om du aktiverar funktionen **Förbättringar av redovisning vid bokslut** efter att du har gjort klart ett årsbokslut, och du vill återföra historiska resultat för årsbokslut, ska du köra det historiska årsbokslutet igen efter att du ha aktiverat redovisningsparametern **Ta bort befintliga årsbokslutsposter när året stängs igen**.

Du kan köra årsbokslutet på nytt genom att starta om processen för räkenskapsåret och den juridiska personen. Processen fortsätter använda parameterinställningen för Redovisning för att avgöra om den nya körningen av årsbokslut gäller enbart nya eller ändrade transaktioner, eller köra processen för alla transaktioner på nytt och helt återföra det tidigare bokslutet.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Redovisning: Funktionen Förbättringar av redovisning vid bokslut har aktiverats. Varför kan jag inte visa mina föregående årsbokslut i historikavsnittet på sidan Årsbokslut?

Innan funktionen **Förbättringar av redovisning vid bokslut** har aktiverats spåras datumet och tiden då den senaste bokslutsprocessen kördes. Den spårar inte historik för varje gång som årsbokslutet genomförs. Informationen för varje bokslutskörning kan därför inte visas. När funktionen har inaktiverats underhålls information om efterföljande bokslutsprocess. Verifikationer från alla bokslutsprocesser, även de som körts innan funktionen aktiverades, kan visas på sidan **Verifikationstransaktioner**. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Redovisning: Årsbokslutsprocessen misslyckas på grund av följande fel: "Årsbokslutet kan inte köras eftersom en eller flera redovisningstransaktioner som har bokförts under det räkenskapsår som du stänger kvittades mot en redovisningstransaktion under ett annat räkenskapsår." Vad betyder det här felet?

Eftersom funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** har aktiverats exkluderas endast kvittade redovisningstransaktioner från det räkenskapsår som stängs från den ingående balansen. Det här gör att debet och kredit inte är i balans. Mer information finns i [Medvetenhet mellan redovisningskvittning och årsbokslut](awareness-between-ledger-settlement-year-end-close.md).

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Redovisning: Återföringen av årsbokslutsprocessen misslyckas på grund av följande fel: "Årsbokslutet för 2022-01-01 kan inte återföras eftersom ingående balanstransaktioner har redovisningskvittats under räkenskapsåret 2023-01-01." Vad betyder det här felet?

Eftersom funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** tillåts inte återföringar av årsbokslutsprocesser om ingående balanstransaktioner har kvittats under det nya räkenskapsåret. Återför redovisningskvittningen under det nya räkenskapsåret 2023 innan du återför årsbokslutet för den 1 januari 2022. Alternativt kan du stänga året för den 1 januari 2022 på nytt, men bara för nya justeringsposter. Om du bara vill stänga året för justeringar ska du inaktivera redovisningsparametern **Radera befintliga årsbokslutsposter när du stänger året igen**.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Redovisning: Varför bearbetar inte automatiseringen av redovisningskvittningar december månads redovisningskvittningstransaktioner?

Funktionen **Automatisera redovisningskvittningar** automatiserar transaktioner som är daterade från den första dagen på räkenskapsåret till det aktuella datumet då förekomsten körs. För räkenskapsår som slutar den 31 december kanske du måste justera körningsdatumet för din förekomst för att säkerställa att den körs i december. Till exempel kan automatisering vara konfigurerat till att köras den första dagen i varje månad. Den här automatiseringen körs den 1 december 2022 och är planerad att köras den 1 januari 2023. Vi rekommenderar att du ändrar förekomsten för den 1 januari 2023 så att den i stället körs den 31 december 2022. Den här ändringen ser till att transaktioner som är daterade 2 till 31 december tas med i automatiska kvittningar.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Redovisning: Vad är skillnaden mellan åtgärden Återför årsbokslut och parametern Radera befintliga årsbokslutsposter när du stänger året igen för årsbokslut?

Det kan förekomma sammanblandningar mellan åtgärden **Återför årsbokslut** och parametern **Radera befintliga årsbokslutsposter när du stänger året igen** i Redovisning (**Redovisning \> Redovisningsinställning \> Redovisningsparametrar**).

Välj åtgärden **Återför årsbokslut** i när du kör årsbokslutet för att på så sätt ta bort alla poster för utgående och ingående balans, som om årsbokslutet aldrig hade körts. I detta fall tas verifikationerna bort. Årsbokslutet körs inte igen automatiskt. Välj åtgärden **Kör årsbokslut**.

Parametern **Radera befintliga årsbokslutsposter när du stänger året igen** i Redovisning används bara när du kör (inte återför) årsbokslutet. Om parametern är inställd på **Ja** tas alla poster för utgående och ingående balans bort och årsbokslutet körs igen. Det här alternativet används när en organisation vill att alla transaktioner, inklusive justeringar sedan senaste årsbokslut, ska bokföras i en enda redovisningspost för poster för utgående och ingående balans. Om parametern ställs in på **Nej** finns alla poster för utgående och ingående balans kvar. De tas inte bort. I stället skapas en ny post för utgående och ingående balans enbart för de ändrade eller nya transaktionerna som inte har bokförts sedan räkenskapsårets senaste årsbokslut.

> [!NOTE]
> Posten för utgående balans skapas för det år som stängs. Detta inträffar bara om parametern **Skapa UB-transaktioner under överföring** i redovisningen är inställd på **Ja**. Posten för ingående balans skapas alltid eftersom detta är den ingående balansen för nästa år.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Redovisning: Vad är skillnaden mellan alternativen "Stäng alla" och "Stäng enstaka" i avsnittet Överför vinst och förlustdimension för årsbokslutsprocessen?

**Stäng alla** har den ekonomiska dimensionens ursprungliga värden från bokförda transaktioner och använder dem för att skapa ingående balanser för balanserad vinst eller förlust. Separata ingående balanser för balanserad vinst eller förlust skapas för varje unik kombination av värden för ekonomiska dimensioner. Om **Stäng enstaka** är markerat kommer alla transaktioner som bokförs med den ekonomiska dimensionen sammanfattas i en balanserade vinstmedel ingående balans för det dimensionsvärde som angetts i fältet efter **Stäng enstaka**. 

Anta att alla transaktioner för räkenskapsåret har bokförts med kontostrukturen för huvudkontot – avdelning. I Avdelning ekonomiska dimensionen på mallen, **Stäng enstaka** är markerad och värdet 100 anges som dimension. Om den totala intäkten för alla transaktioner som bokförts till avdelningar 200, 300 och 400 är 100,000 USD skapas en ingående balans för Balanserade vinstmedel – 100. Om du väljer **Stäng enstaka** och lämnar värdet för ekonomisk dimension tomt kommer alla transaktioner bokföras till balanserade vinstmedel med det dimensionsvärdet tomt.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Redovisning: När jag väljer alternativet "Stäng enstaka" i avsnittet Överför vinst och förlustdimension för årsbokslutsprocessen, kommer min detaljerade transaktionsinformation gå förlorad?

Alternativen **Stäng alla** och **Stäng enstaka** används för att ange vilka ekonomiska dimensioner för transaktioner som bokförs på vinst- och förlustkonton och som ska överföras till huvudkontot för balanserade vinstmedel. Den historiska, detaljerade bokföringen till vinst- och förlustkontona påverkas inte och förblir detaljerad. Alternativet påverkar vilken detaljnivå som överförs till kontona för balanserade vinstmedel som en ingående balans under det nya året. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Redovisning: Årsbokslutsprocessen misslyckas eftersom rapporteringsvalutan för året inte balanserar. Vad betyder detta?

Detta fel kan uppstå efter att du har aktiverat funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** (funktionen Medvetenhet). När funktionen är aktiverad inkluderas inte längre redovisningstransaktioner som har kvittats i den ingående balansen för nästa räkenskapsår när redovisningsåret stängs. Om redovisningstransaktioner som kvittas exkluderas, kan det bli problem för kunder vid årsbokslutet om redovisningen definieras med en rapporteringsvaluta.   
Redovisningskvittning utförs endast för redovisningsvalutan.  När redovisningstransaktioner kvittas säkerställer valideringen bara att debet i redovisningsvalutan är lika med kredit i redovisningsvalutan. Beloppen i rapporteringsvalutan för dessa redovisningstransaktioner valideras inte och debet kanske inte är lika med kredit.  Dessutom beräknar och bokför inte redovisningskvittning automatiskt en vinst/förlust i rapporteringsvalutan.  På grund av dessa begränsningar måste en vinst/förlust-transaktion finnas i rapporteringsvalutan när redovisningskvittning genomförs.  Om vinst/förlust inte inkluderas i redovisningskvittningen leder årsbokslutet till ett meddelande om att saldot inte kan balanseras.  Mer information finns i [Funktionen Medvetenhet mellan redovisningskvittning och rapporteringsvalutan är inte i balans](reporting-currency-yec.md).

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Redovisning: Vad kan ändras för att förbättra prestandan för årsslutsprocessen?

Du kan göra ett flera ändringar för att förbättra prestandan vid årsbokslutet. Vi rekommenderar att du utvärderar de föreslagna ändringarna så att du kan fastställa om dessa passar för din organisation.

### <a name="optimize-year-end-close-service"></a>Optimering av tjänsten för årsbokslut

Med tjänsten **Optimering av årsbokslut** kan Microsoft Dynamics 365 Finance-kunder utföra sina årsbokslut snabbare genom att flytta tung bokslutsbearbetning till en mikrotjänst. Den tid som sparas genom ett effektivt årsbokslut innebär att varje Finance-team kan reagera i tid på de justeringar som behövs och färdigställa de ekonomiska rapporterna. Genom att behandla årsbokslutet på en mikrotjänst frigörs värdefulla resurser. Behandlingen minimerar belastningen på SQL Server och ger kunderna möjlighet att genomföra årsbokslutet snabbare.

Tjänsten **Optimering av årsbokslut** är tillgänglig i version 10.0.31, så de flesta kunder kan använda den nya tjänsten för 2022 års bokslut. Tjänsten har dessutom bakåtporterats till versionerna 10.0.30 och 10.0.29. Mer information finns i [Optimering av årsbokslut](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Dimensionsuppsättningar

När du kör årsbokslutet återskapas varje dimensionsuppsättningssaldo. Detta har direkt inverkan på prestandan. En del organisationer skapar onödigt många dimensionsuppsättningar, eftersom de bara används vid en viss tidpunkt eller kanske bara vid något enda tillfälle. På grund av dessa onödiga dimensionsuppsättningar återskapas fortfarande vid årsbokslutet, vilket gör att processen tar längre tid. Ägna lite tid att utvärdera dimensionsuppsättningarna och ta bort dem som inte behövs.

De onödiga dimensionsuppsättningarna påverkar också batchjobbet **BudgetDimensionFocusInitializeBalance** (**Redovisning \> Kontoplan \> Dimensioner \> Ekonomiska dimensionsuppsättningar**).

[![Ekonomiska dimensionsuppsättningar.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Konfiguration av mall för årsbokslut

Med mallen för årsbokslut kan organisationer välja nivån på ekonomiska dimensioner som ska underhållas när resultatsaldon ska överföras till balanserade vinstmedel. Med dessa inställningarna kan en organisation underhålla de detaljerade ekonomiska dimensionerna (**Stäng alla**) när saldona överförs till balanserade vinstmedel eller välja att summera beloppen till ett enda dimensionsvärde (**Stäng enstaka**). Detta kan definieras för varje ekonomisk dimension. Mer information om de här inställningarna finns i artikeln [Årsbokslut](year-end-close.md).

Vi rekommenderar att du utvärderar organisationens behov och, om det går, stänga så många dimensioner som möjligt med årsslutsalternativet **Stäng enstaka** för att förbättra prestandan. Om du gör stängningen med ett enskilt dimensionsvärde (vilket även kan vara ett tomt värde) beräknar systemet färre detaljer när saldon för kontoposter för balanserade vinstmedel ska beräknas.

### <a name="degenerate-dimensions"></a>Degenerera dimensioner

En dimension som degenereras innebär liten till ingen återanvändning av sig själv eller i kombination med andra dimensioner. Det finns två typer av degenererade dimensioner. Första typen är en dimension som är enskilt degenererad. Vanligtvis visas den här typen av degenererad dimension endast på en enda transaktion eller på små uppsättningar transaktioner. Den andra typen är en dimension som degenereras i kombination med en eller flera andra dimensioner som visar samma potential baserat på de möjliga permutationer som kan genereras. En degenererad dimension kan ha stor påverkan på årsbokslutsprocessen. För att minimera prestandaproblem definierar du alla degenererade dimensioner som **Stäng enstaka** vid inställning för årsbokslut, enligt beskrivning i föregående avsnitt.

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Leverantörsreskontra: Vilka ändringar har gjorts som stöd för 1099-rapport vid årsslut för 2022?

#### <a name="update-to-all-1099-forms"></a>Uppdatera till alla 1099-formulär

Följande ändringar har gjorts i alla 1099-formulär för taxeringsåret 2022:

- År 2021 var året fast på 1099-formulär. Från och med 2022 fylls året i av rapporten.

#### <a name="1099-misc"></a>1099-MISC

Följande uppdateringar har gjorts i formulär 1099-MISC för taxeringsåret 2022:

- Ruta 13: Anger nu arkiveringskravet för Foreign Account Tax Compliance Act (FATCA).
- Ruta 14: Används nu för att rapportera de överskjutande betalningarna av avgångsvederlag.
- Ruta 15: Används nu för att rapportera betalningar enligt planer för icke-kvalificerad försenad kompensation (NQDC).
- Ruta 16: Används nu för att rapportera undandragen delstatsskatt.
- Ruta 17: Används nu för att rapportera betalarens delstatsnummer.
- Ruta 18: Används nu för att rapportera delstatsinkomsten.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Leverantörsreskontra: 1099 – Hur ändrar jag 1099-rutan och värdena för en leverantör som inte spårade 1099-information under året?

Använd funktionen **Uppdatera 1099** för att gå igenom tidigare betalade fakturatransaktioner för att tilldela 1099-data korrekt enligt inställningarna på fliken **1099-skatt** på sidan **Leverantör**. Om du vill använda funktionen **Uppdatera 1099** går du till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer**, väljer en leverantör och väljer sedan **Uppdatera 1099** på fliken **Leverantör** i åtgärdsfönstret.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>Kan jag köra Uppdatera 1099-funktionen för alla leverantörer samtidigt?

Du kan använda sidan **Uppdatera 1099-information för flera leverantörer** om du vill uppdatera 1099-rutan för en leverantörspost, och för att uppdatera transaktioner med informationen från 1099-rutan. Du öppnar den här sidan genom att gå till **Leverantörsreskontra \> Periodisk uppgift \> 1099-skatt**. För att kunna öppna sidan måste du vara tilldelad säkerhetsprivilegiet **Uppdatera rutan 1099 och transaktioner för flera leverantörer**.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Leverantörsreskontra: 1099 – "Omberäkna befintliga 1099-belopp" kontra "Uppdatera alla" i verktyget Uppdatera 1099

Kryssrutan **Omberäkna befintliga 1099-belopp** återställer 1099-beloppet till de totala betalda värdena, när de används tillsammans med kryssrutan **Uppdatera alla**.

[![Skatt 1099-transaktioner: Innan uppdateringsrutinen körs.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Kryssrutan **Omberäkning av befintliga 1099-belopp** fungerar bara om det finns delvärden för 1099 på fakturan eller om fakturan ändrades i formuläret 1099-skatt. Anta att du har en faktura med värdet 1 000,00 USD, men användaren anger manuellt ett 1099-belopp på fakturan på 500,00 USD.

[![Skatt 1099-transaktioner: Markera både Uppdatera alla och Omberäkna befintliga 1099-belopp.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Om den här fakturan betalas blir 500,00 USD det betalade 1099-beloppet. Om du utför omberäkningsrutinen ändras 1099-beloppet till 1 000,00 USD, vilket är den summa som betalades.

[![Skatt 1099-transaktioner: Efter att 1099-rutinen har körts.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Leverantörsreskontra: 1099 – Skapa 1099-transaktioner manuellt

En organisation kanske måste skapa 1099-transaktioner manuellt som inte är kopplade till en faktura. Du kan lägga till manuella 1099-transaktioner genom att gå **Leverantörsreskontra \> Periodiska uppgifter \> 1099-skatt \> Leverantörskvittning för 1099-transaktioner**. Välj knappen **Manuella 1099-transaktioner**.

Manuellt skapade 1099-transaktioner uppdateras inte med processen **Uppdatera alla** eller processen **Omberäkna befintliga 1099-belopp** i verktyget **Uppdatera 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Leverantörsreskontra: 1099 – Har Dynamics 365 Finance stöd för 1096-formuläret?

Dynamics 365 Finance skriver inte ut formuläret 1096 Annual Summary and Transmittal of US Information Returns.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Leverantörsreskontra: 1099 – Finns det några nya funktioner som stöder 1099-rapportering för den offentliga sektorn?

En ny funktion för den offentliga sektorn, **Uppdatera 1099-information efter huvudkonto**, har lagts till och du kan aktivera den i arbetsytan för **funktionshantering**. Med hjälp av den här funktionen kan du associera 1099-värdena för en leverantör med huvudkontot i redovisningsfördelningen, i stället för standardkontot för leverantörsposten.

Mer information finns i [Ange leverantörer för 1099-rapportering](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
