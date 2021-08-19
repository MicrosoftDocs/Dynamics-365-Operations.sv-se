---
title: Vanliga frågor och svar om aktiviteter för årsavslut
description: Det här avsnittet har sammanställts för att underlätta aktiviteter för årsbokslut.
author: kweekley
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1b7606314b9cf7050a565822b5b9e23beb0cb4978b20e88596c5002d918cfcd9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725084"
---
# <a name="year-end-activities-faq"></a>Vanliga frågor och svar om aktiviteter för årsavslut 

[!include [banner](../includes/banner.md)]

Det här avsnittet har sammanställts för att underlätta aktiviteter för årsbokslut. Informationen i det här avsnittet är framförallt avsedd för frågor som rör aktiviteter för årsbokslut i redovisning och leverantörsreskontra.

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
Med mallen för årsbokslut kan organisationer välja nivån på ekonomiska dimensioner som ska underhållas när resultatsaldon ska överföras till balanserade vinstmedel. Med dessa inställningarna kan en organisation underhålla de detaljerade ekonomiska dimensionerna (**Stäng alla**) när saldona överförs till balanserade vinstmedel eller välja att summera beloppen till ett enda dimensionsvärde (**Stäng enstaka**). Detta kan definieras för varje ekonomisk dimension. Mer information om de här inställningarna finns i avsnittet [Årsbokslut](year-end-close.md).

Vi rekommenderar att du utvärderar organisationens behov och, om det går, stänga så många dimensioner som möjligt med årsslutsalternativet **Stäng enstaka** för att förbättra prestandan. Om du gör stängningen med ett enskilt dimensionsvärde (vilket även kan vara ett tomt värde) beräknar systemet färre detaljer när saldon för kontoposter för balanserade vinstmedel ska beräknas.

### <a name="10013-update-or-later"></a>Uppdateringen 10.0.13 eller senare
Om du har uppdaterat till version 10.0.13 eller senare sedan den senaste gången din organisation körde ett årsbokslut, kan den processen ta längre tid på grund av [implementeringen av HashV2-funktionen](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2). (Termen *hash* refererar till ett fält som beräknas från andra strängfält. API:et för att beräkna hash-GUID-värdet har uppdaterats för att förbättra säkerheten.) För att påskynda årsbokslutsprocessen rekommenderar vi att saldona för dimensionsuppsättningarna återskapas innan årsbokslutet körs. Om du redan har återskapat dimensionsuppsättningssaldona efter att ha uppdaterat till version 10.0.13, behöver du inte återskapa dem igen.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Redovisning – Vad gör Periodstängning – Årsbokslut?
 
[![Periodstängning, årsbokslut.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Prestandaförbättringar vid återskapande av ekonomiska dimensionsuppsättningar (ny funktion)
En ny funktion har lagts till i version 10.0.16 som förbättrar prestandan vid årsbokslut och konsolideringsprocessen. Funktionen kallas för Prestandaförbättringar vid återskapande av ekonomiska dimensionsuppsättningar. Med den här funktionen ändras sättet som dimensionsuppsättningar återskapas på, så att de bara återskapas för en relevant tidsram. I föregående versioner återskapades dimensionsuppsättningar för alla datum. Om du exempelvis stänger år 2020 kommer systemet bara att återskapa saldona för transaktioner under räkenskapsåret 2020. Om du kör konsolidering för datumintervallet 1 november 2020 till 30 november 2020, kommer systemet bara att återskapa saldona för det datumintervallet.

Eftersom den här funktionen betraktas som en stor ändring måste du aktivera den med hjälp av arbetsytan för **funktionshantering**.
 
[![Årsbokslut.](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Leverantörsreskontra: Vilka ändringar har gjorts som stöd för 1099-rapport vid årsslut för 2020?

Två nya regelfunktioner har lagts till för 1099-årsslut 2020. Den första funktionen, **Tillämpa ändringar på 1099-NEC- och 1099-MISC-formulär för 2020**, kom ut i mitten av året som en obligatorisk funktion. Dess syfte är att säkerställa att 1099-transaktionsdata för år 2020 kan spåras för det nya 1099-NEC-formuläret. Den här funktionen har lagt till de 1099-fält som behövs för att stödja de nya 1099-NEC-fälten och uppdaterade 1099-MISC-fälten. Den här uppdateringen uppgraderade även leverantörspostdata för informationen i 1099-rutan. 

Den andra regelfunktionen, **1099-utdrag uppdaterade för 2020 års skattelagar**, innehåller följande ändringar.

- 1099-OID – IRS har konverterat formuläret för kontinuerlig användning.
   - Rapporteringsårets tredje och fjärde siffra måste fyllas i när det skrivs ut. Använd **Rapporteringsår**-fältens tredje och fjärde siffror från **Utskriftsalternativ för 1099-skatt**. 

- 1099-NEC – Ett nytt formulär för 2020. Detta registrerar kompensation för icke-anställda. 

-   1099-MISC – På grund av att formulär 1099-NEC skapats har IRS reviderat formulär 1099-MISC och ordnat om rutnumren för att rapportera vissa inkomster.
Förändringar i intäktsrapporteringen och formulärets rutnummer visas nedan.
   - Betalaren har gjort direktförsäljning 5 000 USD eller mer (kryssruta) i ruta 7.
   - Försäkringsintäkter rapporteras i ruta 9.
   - Bruttointäkter till advokat rapporteras i ruta 10.
   - Avsnitt 409A-periodiseringar rapporteras i ruta 12.
   - Ej kvalificerad uppskjuten kompensationsinkomst rapporteras i ruta 14.
   - Rutorna 15, 16 och 17 rapporterar dragen delstatsskatt, delstats-ID-nummer samt belopp för inkomst som intjänats i delstaten.

- Inga ändringar av 1099-DIV eller 1099-INT under 2020.

- E-formulär – Formatet har ändrats för att passa med det nya NEC-formuläret, och MISC-rutan har ändrats enligt beskrivningen ovan. Specifik information om kraven på e-formulär finns [IRS-publikation 1220](https://www.irs.gov/pub/irs-pdf/p1220.pdf).

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Leverantörsreskontra: 1099 – Hur ändrar jag 1099-rutan och värdena för en leverantör som inte spårade 1099-information under året?
Använd funktionen Uppdatera 1099 (**Leverantörsreskontra > Leverantörer > Alla leverantörer > Välj en leverantör > fliken Leverantör i menyfliksområdet > Uppdatera 1099**) för att gå igenom tidigare betalade fakturatransaktioner för att tilldela 1099-data korrekt enligt inställningarna på fliken **1099-skatt** på sidan **Leverantör**.

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Kan jag köra Uppdatera 1099 för alla leverantörer samtidigt?
Nej. Rutinen Uppdatera 1099 utförs mot en enda leverantör åt gången. Om din organisation behöver denna funktion kan du rösta på förslaget med namnet [Batchprocess för uppdatering av leverantörens 1099-data](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8).

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Leverantörsreskontra: 1099 – "Omberäkna befintliga 1099-belopp" kontra "Uppdatera alla" i verktyget Uppdatera 1099.
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
