---
title: Vanliga frågor och svar om aktiviteter för årsbokslut
description: Artikeln innehåller frågor som kan uppkomma när du stänger ett år och svar som kan hjälpa till med aktiviteter vid årsbokslut.
author: moaamer
ms.date: 11/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a75d1e3e68837a437b2369ba369b0063e015b12
ms.sourcegitcommit: 78cbb125f20a33df38bda0546203b8f837cbcd93
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2022
ms.locfileid: "9751970"
---
# <a name="year-end-activities-faq"></a>Vanliga frågor och svar om aktiviteter för årsbokslut 

[!include [banner](../includes/banner.md)]

Artikeln innehåller frågor som kan uppkomma när du stänger ett år och svar som kan hjälpa till med aktiviteter vid årsbokslut. Informationen i artikeln rör sig framförallt om frågor kring aktiviteter vid årsbokslut i redovisning och leverantörsreskontra.

## <a name="general-ledger-year-end-enhancements"></a>Förbättringar av årsslut i redovisning 
Version 10.0.20 innehåller en förbättring av årsbokslut som aktiveras som standard när du börjar med version 10.0.25. Om din organisation använder en version tidigare än 10.0.25 rekommenderar vi att du aktiverar funktionen innan du påbörjar stängningen för årsbokslut. Innan du kan använda funktionen måste den aktiveras i ditt system. Administratörer kan använda arbetsytan Funktionshantering för att kontrollera funktionens status och aktivera den vid behov. Funktionen visas på följande sätt:

 - Modul: Redovisning
 - Funktionsnamn: Förbättringar av redovisning vid bokslut

Inställningar av mallar för stängning vid årsslut har flyttats till en ny inställningssida, **Inställning av mallar för årsbokslut**. Den befintliga sidan för årsbokslut ändras liknande Omräkning i utländsk valuta för redovisning, där en lista visas varje gång årsbokslut körs eller återförs. En redovisningschef kan initiera årsbokslut från den nya sidan. 

För att återföra årsbokslut väljer du det senaste räkenskapsåret för korrekt juridisk person och väljer knappen **Återför årsbokslut**. Återföringen raderar redovisningsposterna för det föregående årsbokslutet och kör inte årsbokslutet på nytt automatiskt. 

Du kan köra årsbokslutet på nytt genom att starta om processen för räkenskapsåret och den juridiska personen. Processen fortsätter använda parameterinställningen för Redovisning för att avgöra om den nya körningen av årsbokslut gäller enbart nya eller ändrade transaktioner eller helt återför det tidigare bokslutet och kör processen för alla transaktioner på nytt.  

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Redovisning: Hur vet jag att vi utför årsbokslutet och inte ångrar årsbokslutet?
Vi har sett organisationer försöka utföra årsbokslutet men i stället ångrade årsbokslutet. Om årsbokslutet slutförs mycket snabbt eller om årsbokslutet inte skapar några poser för ingående balans, ska du kontrollera inställningen **Ångra föregående slut** i **Årsbokslut** (**Redovisning > Periodstängning > Årsbokslut > Kör årsbokslut**). 

[![Köra årsbokslut kontra ångra årsbokslut.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Om alternativet **Ångra föregående slut** anges till **Ja** återförs föregående årsbokslut. När du ångrar tas alla poster för utgående och ingående balans bort, som om årsbokslutet aldrig hade körts. Verifikationerna tas bort. Årsbokslutet körs inte igen automatiskt. Du måste starta processen igen och nu ändra **Ångra föregående slut** till **Nej**. 

> [!NOTE]
> Posten för utgående balans kan eventuellt skapas för det år som stängs. Detta inträffar bara om redovisningsparametern **Skapa UB-transaktioner under överföring** är inställd på **Ja**. Posten för ingående balans skapas alltid eftersom detta är den ingående balansen för nästa år.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Redovisning: Vad är skillnaden mellan redovisningsparametrarna Ångra och Ta bort för årsbokslutet?
Det kan uppstå förvirring gällande skillnaderna mellan parametern **Ångra föregående slut**, som finns i dialogrutan **Årsbokslut**, och parametern **Radera UB-transaktioner vid överföring** i redovisningen (**Redovisning > Periodstängning > Årsbokslut > Kör årsbokslut**).  

[![Skillnaden mellan redovisningsparametrarna Ångra och Ta bort för årsbokslut.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Välj **Ångra föregående slut** i den nedrullningsbara menyn i dialogrutan när du kör årsbokslutet för att på så sätt ta bort alla poster för utgående och ingående balans, som om årsbokslutet aldrig hade körts. Verifikationerna tas bort. Årsbokslutet körs inte igen automatiskt. Om du vill köra årsbokslutet måste du sätta i gång den här processen igen, men denna gång ska du ändra **Ångra föregående slut** till **Nej** (**Redovisning > Redovisningsinställningar > Redovisningsparametrar**). 

[![Inställningen Redovisningsparametrar.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

Parametern **Radera UB-transaktioner vid överföring** i redovisningen används bara när du kör (inte ångrar) årsbokslutet (alternativet **Ångra föregåendes slut** anges till **Nej**). Om den här parametern är inställd på **Ja** tas alla poster för utgående och ingående balans bort och årsbokslutet körs igen. Den här processen används när organisationen vill att alla transaktioner, inklusive justeringar sedan senaste årsbokslut, ska bokföras i en enda redovisningspost för poster för utgående och ingående balans. 

Om det här alternativet ställs in på **Nej** finns alla poster för utgående och ingående balans kvar. De tas inte bort. I stället skapas en ny post för utgående och ingående balans enbart för de ändrade eller nya transaktionerna som bokförts sedan räkenskapsårets senaste årsbokslut.  

> [!NOTE]
> Posten för utgående balans skapas för det år som stängs. Detta inträffar bara om parametern **Skapa UB-transaktioner under överföring** i redovisningen är inställd på **Ja**. Posten för ingående balans skapas alltid eftersom detta är den ingående balansen för nästa år. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Redovisning: Vad kan ändras för att förbättra prestandan för årsslutsprocessen? 
Du kan göra ett antal ändringar för att förbättra prestandan vid årsbokslutet. Vi rekommenderar att du utvärderar de föreslagna ändringarna så att du kan överväga om ändringen passar för din organisation.  

### <a name="dimension-sets"></a>Dimensionsuppsättningar
När du kör årsbokslutet återskapas saldot för varje dimensionsuppsättning, vilket har en direkt inverkan på prestandan. En del organisationer skapar onödigt många dimensionsuppsättningar, eftersom de bara används vid en viss tidpunkt eller kanske bara vid något enda tillfälle.  Dessa onödiga dimensionsuppsättningar återskapas fortfarande vid årsbokslutet, vilket gör att processen tar längre tid. Ägna lite tid att utvärdera dimensionsuppsättningarna och ta bort dem som inte behövs.

De onödiga dimensionsuppsättningarna påverkar också batchjobbet **BudgetDimensionFocusInitializeBalance** (**Redovisning > Kontoplan > Dimensioner > Ekonomiska dimensionsuppsättningar**).

[![Ekonomiska dimensionsuppsättningar.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Konfiguration av mall för årsbokslut
Med mallen för årsbokslut kan organisationer välja nivån på ekonomiska dimensioner som ska underhållas när resultatsaldon ska överföras till balanserade vinstmedel. Med dessa inställningarna kan en organisation underhålla de detaljerade ekonomiska dimensionerna (**Stäng alla**) när saldona överförs till balanserade vinstmedel eller välja att summera beloppen till ett enda dimensionsvärde (**Stäng enstaka**). Detta kan definieras för varje ekonomisk dimension. Mer information om de här inställningarna finns i artikeln [Årsbokslut](year-end-close.md).

Vi rekommenderar att du utvärderar organisationens behov och, om det går, stänga så många dimensioner som möjligt med årsslutsalternativet **Stäng enstaka** för att förbättra prestandan. Om du gör stängningen med ett enskilt dimensionsvärde (vilket även kan vara ett tomt värde) beräknar systemet färre detaljer när saldon för kontoposter för balanserade vinstmedel ska beräknas.

## <a name="degenerate-dimensions"></a>Degenerera dimensioner

En dimension som degenereras innebär liten till ingen återanvändning av sig själv eller i kombination med andra dimensioner. Det finns två typer av degenererade dimensioner. Första typen är en dimension som är enskilt degenererad. Vanligtvis visas den här typen av degenererad dimension endast på en enda transaktion eller på små uppsättningar transaktioner. Den andra typen är en dimension som degenereras i kombination med en eller flera andra dimensioner som visar samma potential baserat på de möjliga permutationer som kan genereras. En degenererad dimension kan ha stor påverkan på årsbokslutsprocessen. För att minimera prestandaproblem definierar du alla degenererade dimensioner som **Stäng enstaka** vid inställning för årsbokslut, enligt beskrivning i föregående avsnitt.

## <a name="general-ledger-what-does-the-period-close-year-end-close-do"></a>Redovisning: Vad gör periodstängning vid årsbokslut?
 
[![Periodstängning, årsbokslut.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets"></a>Prestandaförbättringar för ombyggnad av uppsättningar med ekonomiska dimensioner
En ny funktion som lades till i version 10.0.16 som förbättrar prestanda vid årsbokslut och konsolideringsprocesser. Funktionen kallas för Prestandaförbättringar vid återskapande av ekonomiska dimensionsuppsättningar. Med den här funktionen ändras sättet som dimensionsuppsättningar återskapas på, så att de bara återskapas för en relevant tidsram. I föregående versioner återskapades dimensionsuppsättningar för alla datum. Om du exempelvis stänger år 2020 kommer systemet bara att återskapa saldona för transaktioner under räkenskapsåret 2020. Om du kör konsolidering för datumintervallet 1 november 2020 till 30 november 2020, kommer systemet bara att återskapa saldon för det datumintervallet.

Innan du kan använda funktionen måste den aktiveras i ditt system. Administratörer kan använda arbetsytan Funktionshantering för att kontrollera funktionens status och aktivera den vid behov. Funktionen visas på följande sätt:
 
- Modul: Redovisning
- Funktionens namn: Prestandaförbättringar vid återskapande av ekonomiska dimensionsuppsättningar

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2021"></a>Leverantörsreskontra: Vilka ändringar har gjorts som stöd för 1099-rapport vid årsslut för 2021?

Under 2021 har formulären DIV, NEC och MISC ändrats något och några ytterligare rutor har lagts till.

#### <a name="div-new-box2e-2f"></a>DIV: ny ruta 2e, 2f
 
- Ruta 2e. Visar den andel av beloppet i ruta 1a som är avsnitt 897 för vinst kopplad till disposition av intressen i amerikanska fasta tillgångar (USRPI).  
- Ruta 2f. Visar den andel av beloppet i ruta 2a som är avsnitt 897 för vinst kopplad till disposition av USRPI. Observera att rutorna 2e och 2f endast gäller för utländska personer och enheter vars inkomst behåller sin karaktär när de förs över eller fördelas till, dess direkta eller indirekta utländska ägare eller förmånstagare. Det behandlas i allmänhet som direkt kopplat till en verksamhet eller ett företag i USA. Se instruktionerna för din momsretur. 
 
#### <a name="nec-new-box-2"></a>NEC: ny ruta 2 
 
Om ruta 2 är markerad ska du rapportera konsumtionsvaror för totalt 5 000 USD eller mer som har sålts till dig för återförsäljning, som försäljningsuppdrag, som insatt provision eller på annan grund. I allmänhet ska du rapportera alla intäkter från försäljning av dessa produkter i Schedule C (formulär 1040). 
 
Samtidigt har formulärstorleken på NEC ändrats. Vid utskrift finns det tre formulär per sida. 
 
#### <a name="misc-new-box-11"></a>MISC: ny ruta 11 
 
Ruta 11 visar det belopp som betalats för inköp av fisk för vidareförsäljning av någon person som är delaktig i verksamhet eller företag som fångar fisk. Se instruktionerna för din momsretur för att rapportera denna intäkt. 
 
#### <a name="electronic-filing"></a>E-formulär 
Mer information om e-formulär finns i [Information om krav på e-formulär](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

Uppdatera formatspecifikationer och postlayouter för 2021 års e-rapport 
- Avsnitt 2 Utfärdarens ”A”-post. 
- Beloppskoder – Ökad längd till 18 för fältposition 28–45. 
 
#### <a name="sec-2-issuer-a-record-for-reporting-payments-on-form-1099-div"></a>Avsnitt 2 Utfärdarens ”A”-post, för att rapportera betalningar på formulär 1099-DIV: 
- Beloppstyp – Lagt till avsnitt 897 Ordinarie utdelningar och lagt till beloppskod H. 
- Beloppstyp – Lagt till avsnitt 897 Kapitalvinster och lagt till beloppskod J. 
 
#### <a name="sec-3-payee-b-record"></a>Avsnitt 3 Betalarens "B"-post 
- Allmänna informationsposter – Uppdaterat tredje punkten från 16 till 18 fält för Betalningsbelopp. 
- Fältrubrik för betalning H – Uppdaterat fältrubrik, längd och allmän fältbeskrivning för fältposition 247–258. 
- Fältrubrik för betalning J – Uppdaterat fältrubrik, längd och allmän fältbeskrivning för fältposition 259–270. 
- Uppdaterat tomt fält till fältposition 271-286. 
- Uppdaterat indikator för främmande land till fältposition 287. 
- Uppdaterat namnradsfält för första betalare till fältposition 288-327. 
- Uppdaterat namnradsfält för andra betalare till fältposition 328-367. 
- Postlayoutpositioner, formulär 1099-MISC – Raderat fältposition 548 och fältrubrik FATCA-formulär kravindikator. 
- Postlayoutpositioner, formulär 1099-NEC – Uppdaterat 545–546 till tomt, uppdaterat fält 547 till direktförsäljningsindikator, längd, beskrivning och anteckningar, uppdaterat fält 548–722 till tomt. 
 
#### <a name="sec-4-end-of-issuer-c-record"></a>Avsnitt 4 Slut på utfärdarens ”C”-post 
- Fältrubrik för betalning H – Uppdaterat fältrubrik, längd och allmän fältbeskrivning för fältposition 304–321. 
- Fältrubrik för betalning J – Uppdaterat fältrubrik, längd och allmän fältbeskrivning för fältposition 322–339. 
- Fältrubrik 340-499 – Uppdaterat längd till 160. 
 
#### <a name="sec-5-state-totals-k-record"></a>Avsnitt 5 Delstatssumma "K"-post 
- Fältrubrik för betalning H – Uppdaterat fältrubrik, längd och allmän fältbeskrivning för fältposition 304–321. 
- Fältrubrik för betalning J – Uppdaterat fältrubrik, längd och allmän fältbeskrivning för fältposition 322–339. 
- Fältrubrik 340-499 – Uppdaterat längd till 160.  

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Leverantörsreskontra: 1099 – Hur ändrar jag 1099-rutan och värdena för en leverantör som inte spårade 1099-information under året?
Använd funktionen Uppdatera 1099 (**Leverantörsreskontra > Leverantörer > Alla leverantörer > Välj en leverantör > fliken Leverantör i menyfliksområdet > Uppdatera 1099**) för att gå igenom tidigare betalade fakturatransaktioner för att tilldela 1099-data korrekt enligt inställningarna på fliken **1099-skatt** på sidan **Leverantör**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Kan jag köra Uppdatera 1099 för alla leverantörer samtidigt?
Nej. Rutinen Uppdatera 1099 utförs mot en enda leverantör åt gången. Om din organisation behöver denna funktion kan du rösta på förslaget med namnet [Batchprocess för uppdatering av leverantörens 1099-data](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Leverantörsreskontra: 1099 – "Omberäkna befintliga 1099-belopp" kontra "Uppdatera alla" i verktyget Uppdatera 1099
Kryssrutan **Omberäkna befintliga 1099-belopp** återställer 1099-beloppet till de totala betalda värdena, när de används tillsammans med kryssrutan **Uppdatera alla**. 

[![Skatt 1099-transaktioner: Innan uppdateringsrutinen körs.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Kryssrutan **Omberäkning av befintliga 1099-belopp** fungerar bara när det finns delvärden för 1099 på fakturan eller om den ändrades i formuläret 1099-skatt. Anta att du har en faktura med värdet 1 000,00 USD, men användaren skriver manuellt in ett 1099-belopp på fakturan på 500,00 USD.

[![Skatt 1099-transaktioner: Markera både Uppdatera alla och Omberäkna befintliga 1099-belopp.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Om detta betalas blir 500,00 USD det betalade 1099-beloppet. Om du utför omberäkningsrutinen ändrar systemet 1099-beloppet till 1 000,00 USD, vilket är den summa som betalades.

[![Skatt 1099-transaktioner: Efter att 1099-rutinen har körts.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Leverantörsreskontra: 1099 – Skapa 1099-transaktioner manuellt
En organisation kanske måste skapa 1099-transaktioner manuellt som inte är kopplade till en faktura. Du kan lägga till manuella 1099-transaktioner genom att gå **Leverantörsreskontra > Periodiska uppgifter > 1099-skatt > Leverantörskvittning för 1099-transaktioner**. Välj knappen **Manuella 1099-transaktioner**. 

Manuellt skapade 1099-transaktioner uppdateras inte med processen **Uppdatera alla** eller processen **Omberäkna befintliga 1099-belopp** i verktyget **Uppdatera 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Leverantörsreskontra: 1099 – Har Dynamics 365 Finance stöd för 1096-formuläret? 

Dynamics 365 Finance skriver inte ut formuläret 1096 Annual Summary and Transmittal of US Information Returns.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Leverantörsreskontra: 1099 – Finns det några nya funktioner som stöder 1099-rapportering för den offentliga sektorn? 
En ny funktion för den offentliga sektorn, **Uppdatera 1099-information efter huvudkonto**, har lagts till och du kan aktivera den i arbetsytan för **funktionshantering**. Med hjälp av den här funktionen kan du associera 1099-värdena för en leverantör med huvudkontot i redovisningsfördelningen, i stället för standardkontot för leverantörsposten.

Mer information finns i [Ange leverantörer för 1099-rapportering](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
