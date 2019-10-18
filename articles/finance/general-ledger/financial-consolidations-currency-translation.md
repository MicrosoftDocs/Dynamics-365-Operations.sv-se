---
title: Ekonomisk konsolidering och valutaregistrering – översikt
description: Det här avsnittet beskriver online ekonomiska konsolideringar och valutaöversättningar i redovisning.
author: aprilolson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 7b6b3cced92920ef5a253ca15793f26f244475fa
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186611"
---
# <a name="financial-consolidations-and-currency-translation-overview"></a>Ekonomisk konsolidering och valutaregistrering – översikt

[!include [banner](../includes/banner.md)]

Det här avsnittet hjälper dig genom metoden som både Microsoft Dynamics 365 Finance och ekonomisk rapportering använder för konsolideringar. Det beskriver scenarier som omfattar rapportering med flera företag, aggregering, eliminering och minoritetsintresse. Här förklaras också hur du ska hantera vissa situationer, till exempel scenarier där juridiska personer har olika räkenskapsperioder eller olika kontoplaner.

Det här avsnittet är avsett för användare och funktionella konsulter och antar att läsare har en förståelse för Finance och ekonomisk rapportering. Grundinställningen omfattas inte.

> [!NOTE]
> Termen *juridisk person* används i Finance och termen *företag* används i ekonomiska rapporter. Båda dessa termer används i detta avsnitt: För detta avsnitt är deras innebörd dock densamma.

## <a name="audience"></a>Målgrupp
Det här avsnittet är avsett ekonomi- och redovisningsanvändare och programkonsulter som vill använda Finance and Operations och ekonomisk rapportering för att konsolidera flera företag och flera valutor.

## <a name="approach"></a>Metod
Finance använder en separat juridisk person för att behandla en konsolidering. Det gör att konsolidering av enskilda instanser, men ger även möjlighet att hämta data från andra källor. Konsolideringsprocessen måste köras varje gång ändringar görs i källans juridiska person.

Ekonomisk rapportering kan konsolidera flera företag vid rapportgenerering. Även om data lagras på ett datatorg är den versionshanterad och kan exporteras, varje källföretag är ägare och behållare av data. Rapporten kan köras när som helst, till och med varje minut (till exempel). Det finns många ytterligare fördelar, till exempel möjligheten att gå ner till alla företag och dimensioner.

Användare kan använda konsolidera online, ekonomisk rapportering, eller en kombination. Deras val beror på deras företags behov och inställningarna för deras revisorer.

## <a name="consolidations"></a>Konsolideringar
Modulen **konsolideringar** innehåller alternativ för att konsolidera flera juridiska personer under konsolideringsprocessen och för att importera eller exportera ett företags saldo. Du kan också ställa in elimineringar och bokföra elimineringsjournaler.

## <a name="benefits-of-using-consolidate-online"></a>Fördelar med att använda konsolidera online
Kunder som använder modulen **konsolideringar** får olika fördelar:

- **Djup av data** – du kan skapa konsoliderade rapporter som sammanför faktiska och budgetdata både på kontonivå och dimensionsnivå.
- **Dynamiska konsolideringar** – konsolideringar kan bearbetas flera gånger.
- **Granska funktionerna** – dimensioner och konton hanteras för analys och granskning och saldon skapas efter datum.
- **Valutakonvertering** – du kan ställa in intervall för konto och tariffer att konvertera från källföretagets redovisningsvaluta till konsolideringsföretagets redovisningsvaluta.
- **Bearbeta elimineringar i ett konsoliderat eller elimineringsföretag** – du kan bearbeta och bokföra elimineringar som en enskild process under konsolideringen. Du kan också köra ett förslag separat.

## <a name="supported-consolidation-scenarios"></a>Konsolideringsscenarier som stöds
Nedan följer några konsolideringsscenarier som Konsolidera online stöder:

- Konsolideringar på en nivå över juridiska personer
- Konsolideringar som involverar elimineringar
- Minoritetsintresse (i det här scenariot måste manuell beräkning och post i företaget användas.)
- Flera kontoplaner över juridiska personer
- Olika räkenskapskalendrar över flera juridiska personer
- Konsolideringar som involverar flera rapportvalutor

## <a name="legal-entity-setup"></a>Inställning av juridisk person
Innan du bearbetar en konsolidering måste du ställa in den juridiska personen. Du kan köra konsolideringen så många gånger som du behöver och alla data som ska konverteras från källföretagets redovisningsvaluta till den valuta som har definierats för konsolideringsföretaget. Därför, för följande organisationsstruktur, om du först måste konvertera alla amerikanska företag till amerikanska dollar (USD) och sedan till euro (EUR), valutan för det överordnade företaget, måstedu ah ha minst två konsolideringsföretag.

![Organisationsstruktur](./media/organizational-structure.png "Organisationsstruktur")

I den föregående organisationsstrukturen måste du ha en juridisk person för nordamerikanska konsolideringen eftersom konsolideringar alltid konsoliderar från källföretagets redovisningsvaluta till konsolideringsföretagets valuta. I exemplet, om alla företag ingår i en enda konsolidering, ska det mexikanska dotterbolaget konvertera från Mexikanska pesos (MXN) till euro, inte från MXN till USD till EUR.

När du skapar en juridisk person kan du ange om företaget används för både konsolideringsprocessen och elimineringsprocessen eller för endast en av dessa processer. I följande exempel används företaget för båda processerna. Observera att du inte kan bokföra dagboksjournaler i ett konsolideringsföretag, men du kan bokföra dem i ett elimineringsföretag. Därför kan du behöva ett separat elimineringsföretag.

![Juridisk person som används för både konsolidering och eliminering](./media/sep-elimination-company.png "Juridisk person som används för både konsolidering och eliminering")

## <a name="main-accounts-and-consolidation-account-groups"></a>Huvudkonton och konsolideringskontogrupper
Ett val som du måste göra är hur du vill konsolidera din kontoplan. Under konsolideringsprocessen finns det tre alternativ för konsolidering av huvudkonto.

Det första alternativet är att använda huvudkonton från källföretag. I det här fallet konsolideras alla konton från alla företag. Till exempel om Kontanter är konto 100000 i USMF-företaget och konto 1100 i DEMF-företaget inkluderar konsolideringsföretaget båda kontona. Varje konto har sitt respektive saldo.

Det andra alternativet är att ange ett standardkonto för konsolideringen på sidan **huvudkonton**. Kontot mappas sedan till konsolideringskontot. Det här alternativet kan vara användbart när du har olika kontoplaner eller måste mappa till ett diagram som definieras av huvudkontoret.

![Standardkonsolideringskonto anges på sidan Huvudkonton](./media/main-accounts.png "Standardkonsolideringskonto anges på sidan Huvudkonton")

Det tredje alternativet är att använda konsolideringskontogrupper. Du kan definiera så många konsolideringskontogrupper som du behöver. Sedan på sidan **Ytterligare konsolideringskonton** kan du bara mappa huvudkontot från kontoplanen på det konto som du vill ha för den gruppen.

![Mappning på sidan Ytterligare konsolideringskonton](./media/additional-consolidation-accounts.png "Mappning på sidan Ytterligare konsolideringskonton")

## <a name="consolidating-online"></a>Onlinekonsolidering
Information om hur du anger information om onlinekonsolideringar finns i [konsolidera online](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Hantera konsolideringstransaktioner
Om du vill visa resultaten av konsolideringen har du flera alternativ:

- Skapa en ekonomisk rapport mot konsolideringsföretaget.
- Granska listsidan **Råbalans** i konsolideringsföretaget.
- I listan över konsolideringstransaktioner på sidan **konsolideringar** kan du visa saldon som har skapats efter datum för varje källföretag för varje period.

    ![Konsolideringstransaktioner på sidan Konsolideringar](./media/managing-consolidation-transactions.png "Konsolideringstransaktioner på sidan Konsolideringar")

Om du vill köra konsolideringen igen, kan du bara behandla konsolideringen. Alternativt kan du först markera **ta bort transaktionerna** på sidan **konsolideringar**.

## <a name="consolidate-with-import"></a>Konsolidera med import
Konsolidera med importeringsfunktionalitet fungerar på samma sätt som funktionen Konsolidera online. När du väljer de juridiska personerna ska du bläddra från källfilen som innehåller data.

## <a name="export-company-balances"></a>Exportera företagsbalanser
Funktionen Exportera företagsbalanser fungerar på samma sätt som funktionen Konsolidera online. När du väljer de juridiska personerna, anger du en sökväg för utdata.

## <a name="elimination-rules"></a>Elimineringsregler
Du måste skapa en elimineringsregel för att kunna eliminera koncerninterna transaktioner. Alternativt kan du göra en manuell elimineringspost i ett företag som har tilldelats ett elimineringsföretag. Om du skapar en elimineringsregel har du två alternativ för elimineringsmetoden: **Nettoändring** och **Fast**.

### <a name="set-up-elimination-rules"></a>Ställ in elimineringsregler
När du ställer in elimineringsregler i Finance kan du skapa en ekonomisk dimension som särskilt används för eliminering. De flesta kunder kallar denna ekonomiska dimension för **Handelspartner** eller något liknande. Om du inte vill använda en ekonomisk dimension, se då till att ha huvudkonton som endast används för koncerninterna transaktioner.

Du hittar inställningar för elimineringar i området **Inställningar** i modulen **Konsolideringar**. När du anger en beskrivning för regeln måste du välja det företag som elimineringsjournalen ska bokföra till. Företaget som du väljer bör ha **Använd för ekonomisk elimineringsprocess** markerat i inställningarna för juridisk enhet.

Du kan ange det datum då elimineringsregeln träder i kraft och det datum då den förfaller enligt behov. Du måste ange **Aktiv** som **Ja** om du vill att elimineringsregeln ska vara tillgänglig i förslagsprocessen för eliminering. Välj ett journalnamn som har typen **Eliminering**.

![Grundläggande egenskaper för en elimineringsregel](./media/ledger-elimination-rule-journal.png "Grundläggande egenskaper för en elimineringsregel")

Du kan definiera de faktiska bearbetningsreglerna genom att klicka på **Rader** efter att du har angett grundläggande egenskaper. Det finns två olika alternativ för elimineringar: du kan eliminera nettoändringsbeloppet eller att definiera ett fast belopp.

Välj källkontona. Du kan använda asterisk (\*) som jokertecken. Till exempel, **1\*** väljer alla konton som startar med en **1** som datakälla för allokeringen.

När du har valt dina källkonton, använd fältet **Kontospecifikation** för att ange kontot som används från destinationsföretaget. Välj **Källa** om du vill använda samma huvudkonto som angetts i källkontot. Om du väljer **Användardefinierad** måste du ange ett destinationskonto.

![Sidan Elimineringsregelrad för redovisning](./media/ledger-elimination-rule-line.png "Sidan Elimineringsregelrad för redovisning")

Fältet **Dimensionsspecifikation** fungerar som fältet **kontospecifikation**. Välj **Källa** för att använda samma dimensioner i destinationsföretaget som i källföretaget. Om du väljer **Användardefinierad** måste du ange dimensioner för destinationsföretaget genom att välja **Måldimensioner**. Välj sedan källdimensioner och ekonomiska dimensioner, samt de värden som används som källa för eliminering.

### <a name="process-elimination-transactions"></a>Bearbeta elimineringstransaktioner
Det finns två sätt att bearbeta elimineringstransaktioner. Transaktionen kan behandlas under Konsolidera online-processen, eller du kan skapa en elimineringsjournal och köra elimineringsförslagsprocessen. Det här avsnittet fokuserar på det andra alternativet.

I ett företag som definierats som ett elimineringsföretag, välj **Elimineringsjournal** i modulen **Konsolideringar**. Klicka på **Rader** när du har valt journalnamn. Om du vill köra förslaget, välj **förslag**\>**Elimineringsförslag**.

Välj det företag som utgör grunden för den konsoliderade datan, och välj sedan den regel som du vill bearbeta. Ange start- och slutdatumen för att definiera det datumintervall som söks igenom för elimineringsbelopp. Fältet **GL-bokföringsdatum** anger det datum som används för att bokföra journalen i redovisningen. När du klickar på **OK** kan du granska belopp och bokföra journalen.

> [!NOTE]
> Elimineringsjournalen visar beloppen för kontovärden i valutan för de ursprungliga transaktionerna, inte i redovisningsvalutan. När du granskar beloppen i elimineringsjournalen kanske problemet verkar förvirrande.

Mer information och exempel finns i [Elimineringsregler](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>Valutaomvärdering i ett konsolideringsföretag
När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas. När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen. Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon. Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum.

Läs mer om valutaomvärdering i ett konsolideringsföretag i [Valutaomvärdering i ett konsolideringsföretag](currency-revaluation-consolidation-company.md).

För mer information om hur valutaomvärdering fungerar i modulen **redovisning** finns i [Omräkning i utländsk valuta för redovisning](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>Ytterligare information
- Alla bokföringsskikt konsolideras när konsolideringen ska utföras.
- Elimineringsjournaler kan bara bokföras till det aktuella lagret.
- Endast aktiva saldon konsolideras. Om du därför vill visa ingående balans, måste du fortfarande köra ett årsbokslut i konsolideringsföretaget.
- Du kan bokföra en dagboksjournal i ett elimineringsföretag, men inte i ett konsolideringsföretag.

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>Fördelar med att använda ekonomisk rapportering för ekonomisk konsolidering och valutaomräkning eller att komplettera Konsolidera online för konsoliderad rapportering
Kunder som använder ekonomisk rapportering för ekonomisk konsolidering och valutaomräkning eller att komplettera Konsolidera online för konsoliderad rapportering får olika fördelar:

- **Djup av data** – du kan skapa konsoliderade rapporter som sammanför faktiska och budgetdata både på kontonivå och dimensionsnivå. För Finance omfattar informationen data från både budgetkontroll och budgetplanering.
- **Dynamiska konsolideringar** – konsolideringar kan göras när som helst och på alla nivåer i organisationshierarkin.
- **Kompletta granskningsfunktioner** – Alla dimensioner, konton och transaktionsinformation hanteras för analys och granskning. Dessutom ger ekonomisk rapportering fullständig återgång till den ursprungliga transaktionen i någon av de juridiska personerna som konsolideras.
- **Strömlinjeformad valutaomräkning** – efter minimal installation i Finance kan du konvertera alla ekonomiska rapporter till all rapporteringsvaluta som har ställts in. Dessutom kan du skapa och tilldela namn till ett obegränsat antal rapporteringsvalutor.
- **Bokför elimineringarna vid källan** – du kan skapa och skriva ut en rapport för att kontrollera elimineringstransaktioner. Därefter kan du bokföra alla nya elimineringar som koncerninterna standardtransaktioner. Du kan också använda en juridisk person för eliminering för alla transaktioner som inte ska ingå i juridiska personer.

## <a name="supported-consolidation-scenarios"></a>Konsolideringsscenarier som stöds
Nedan följer några konsolideringsscenarier som Ekonomisk rapportering stöder:

- Konsolideringar på en nivå och flera nivåer över juridiska personer
- Konsolideringar som använder organisationsstrukturer som skapas från juridiska personer
- Konsolideringar som involverar elimineringar
- Minoritetsintresse
- Flera kontoplaner över juridiska personer
- Olika räkenskapskalendrar över flera juridiska personer
- Konsolideringar som involverar flera rapportvalutor
- Konsolideringar av affärsenhet

## <a name="generating-consolidated-financial-statements"></a>Generera konsoliderade bokslut
För information om scenarier där du kan skapa konsoliderade bokslut, se [skapa konsoliderade bokslut](./generating-consolidated-financial-statements.md).
