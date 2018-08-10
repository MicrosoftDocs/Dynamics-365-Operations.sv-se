---
title: "Säkerhet för artiklar i lageruppfyllelse"
description: "Här beskrivs uppfyllandet av säkerhetslagret och hur du ställer in säkerhetslagerantalet för artiklar."
author: roxanadiaconu
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: d6ecb346f7bfa54a4e16307f623c82acb3a86892
ms.contentlocale: sv-se
ms.lasthandoff: 12/14/2017

---

# <a name="safety-stock-fulfillment-for-items"></a>Säkerhet för artiklar i lageruppfyllelse

[!include [banner](../includes/banner.md)]

Säkerhetslager anger en ytterligare kvantitet för en artikel i lagret för att minska risken för att artikeln är slut på lagret. Säkerhetslager används som ett buffertlager om försäljningsorder kommer in och leverantören inte kan leverera ytterligare artiklar för att uppfylla kundens begärda leveransdatum. När säkerhetslager används för att uppfylla en försäljningsorder, reduceras säkerhetslagret. Du kan använda huvudplanering för att automatiskt föra tillbaka lagret till säkerhetsnivån.    

## <a name="set-up-safety-stock-levels-for-items"></a>Ställ in säkerhetslagernivåer för artiklar

Säkerhetslager ställs in som en del av artikeldisponering på sidan **Artikeldisponering** under **Frisläppta produkter** > **Plan** > **Disponering**.

Ange säkerhetslagernivån att underhålla för artikeln i fältet **Minimum**. Värdet uttrycks i lagerenheter. Om du lämnar fältet tomt är standardvärdet noll. Det här fältet är tillgängligt när du väljer **Period**, **Behov** eller **Min/Max** i listan **Disponeringskod**. De lagernivåbegränsningen gäller tillgängligt lager, vilket innebär att reservationer och märkning kan utlösa säkerhetslagerpåfyllnad innan den fysiska kvantiteten hamnar under den angivna miniminivån.

> [!NOTE]
> Du måste definiera alla övriga planerade disponeringsdimensioner innan du kan definiera fältet **Minimum**. Detta förhindrar att en ogiltig post används vid huvudplanering. Situationen skulle kunna uppstå om en dimensionsgrupp utökas med ytterligare en planerad disponeringsdimension för vilken de minsta och största lagerkvantiteterna ännu inte har angetts.

Använd minimumnycklar för att hantera säsongsvariationer i efterfrågan. Du kan till exempel minska minimilagernivån under lågsäsong och gradvis öka nivån under de övriga månaderna. Du skapar en minimumnyckel genom att gå till **Huvudplanering** > **Inställningar** > **Disponering** > **Minimi-/maximinycklar**. Du anger en minimumnyckel för att justera säkerhetslagernivån efter säsongsvariationer i fältet **Minimumnyckel** på sidan **Artikeldisponering**. 

## <a name="example-minimum-key"></a>Exempel: Minimumnyckel
Om du vill ställa in en minimumnyckel som tar hänsyn till ökad säsongsefterfrågan under vår- och sommarmånaderna går du till **Huvudplanering** > **Inställningar** > **Disponering** > **Minimi-/maximinycklar** och följ stegen.

1. Skapar 12 rader och tilldela ett nummer från 1 till 12 till raderna i fältet **Ändra**.
2. Välj **Månader** i fältet **Enhet**.
3. I fältet **Faktor** anges värdena som beskrivs i följande tabell.

|Rad|Ange det här värdet|Resultat|
|---|---|---|
|1–3|1|Minimilagret baseras på inställningen för januari till mars på sidan **Artikeldisponering**.|
|4-5|2|Minimilagret multipliceras med faktorn 2 för april till maj.|
|6-8|2,5|Minimilagret multipliceras med faktorn 2,5 för juni till och med augusti.|
|9-12|1|Minimilagret återgår till inställningen för september till och med december på sidan **Disponering**.|

Om disponeringskoden är **Min/max** kan du även ange **Maximal** lagerkvantitet som du vill underhålla för artikeln. Värdet uttrycks även i lagerenheter. Om förväntat tillgängligt lager faller under minimikvantiteten, genererar huvudplaneringen en planerad order för att uppfylla alla öppna behov först och ökar sedan det tillgängliga lagret till den angivna maximikvantiteten. Precis som du ställer in **Minimum** måste du definiera alla övriga planerade disponeringsdimensioner innan du kan definiera fältet **Maximum**.

## <a name="example-minmax-coverage-code"></a>Exempel: Min/max disponeringskod
Minimikvantiteten är 10 och maximikvantiteten är 15. Aktuella lagerbehållning är 4. Detta ger ett minimikvantitetskrav på 6. Eftersom maximikvantiteten är 15 är genererar huvudplaneringen en planerad order på 11 artiklar.

För artiklar med säsongsvariationer behöver du kanske ha olika maximinivåer. Om du vill göra det måste du definiera **Maximumnycklar** genom att gå till **Huvudplanering** > **Inställningar** > **Disposition** > **Minimi-/maximinycklar**. Fyll i fältet **Maximumnyckel** på idan **Artikeldisponering**. Du kan visa information om säkerhetslagernivåer, definierade med miniminycklarna på fliken **Min/max** på sidan **Artikeldisponering**. Du måste se till att minimi- och maximivärdena hålls synkroniserade under en viss period.

## <a name="safety-stock-fulfillment"></a>Säkerhetslageruppfyllelse 

Parametern **Uppfyll minimum** gör det möjligt att välja datum eller tidsperiod under vilken lagernivån måste uppfylla kvantiteten som du angav i fältet **Minimum**. Det här fältet är tillgängligt när du väljer **Period**, **Behov** eller **Min/Max** i listan **Disponeringskod**.

Om **Miniminycklar** är används, välj kryssrutan **Minimiperioder** om du vill uppfylla minimilagernivån för alla de perioder som ställs in i minimumnyckeln. Om du avmarkerar kryssrutan är minimilagret endast uppfyllt för aktuell period.

Följande scenario visar hur denna parameter fungerar och vad som är skillnaderna mellan värdena.

> [!NOTE]
> För alla bilder i det här avsnittet representerar x-axeln lager, y-axeln representerar dagar, staplarna representerar lagernivån, pilarna representerar transaktioner, exempelvis försäljningsorderrader, inköpsorderrader eller planerade order.

[![Vanligt scenario för uppfyllande av säkerhetslager](./media/Scenario1.png)](./media/Scenario1.png) Parametern **Uppfylla minimum** kan ha följande värden:
### <a name="todays-date"></a>Dagens datum 
Den angivna minimikvantiteten är uppfylld på datumet då huvudplaneringen körs. Systemet försöker så snart som möjligt uppfylla säkerhetslagergränsen trots att den kan vara orealistisk på grund av ledtiden. 
[![Krav på dagens datum](./media/TodayReq.png)](./media/TodayReq.png) Planerad order P1 skapas för dagens datum så att tillgängligt lager kommer över säkerhetslagernivån på det datumet. Försäljningsorderraderna S1 till S3 fortsätter att minska lagernivån. Planerade order P2 till P4 genereras av huvudplaneringen så att lagernivån återförs till säkerhetsgränsen efter varje försäljningsorder.
När disponeringskoden **Krav** används skapas flera planerade order. Det är alltid en god idé att använda antingen **Period** eller **Min/Max** disposition för artiklar och material som efterfrågas ofta till att förpacka påfyllningen. Följande illustration visar ett exempel på disponeringskoden **Period**.
[![Period. Dagens datum](./media/TodayPeriod.png)](./media/TodayPeriod.png) Följande illustration visar ett exempel på disponeringskoden **Min/Max**.
[![MinMax. Dagens datum](./media/TodayMinMax.png)](./media/TodayMinMax.png)
### <a name="todays-date--procurement-time"></a>Dagens datum + anskaffningstid 
Den angivna minimikvantiteten är uppfylld på det datum då huvudplaneringen körs plus leverans- eller produktionstid. Den här tiden inkluderar eventuella säkerhetsmarginaler. Om artikeln har ett handelsavtal och kryssrutan **Sök efter handelsavtal** är markerad på sidan **Huvudplaneringsparametrar** tas leveranstiden från handelsavtalet inte med i beräkningen. Produktionstider tas från inställningarna för artikeldisponering eller från artikeln.
Det här uppfyllelseorderläget skapar planer med färre förseningar och färre planerade order, oavsett disponeringsgruppen inställd på artikeln. I följande bild visas resultatet av planen om disponeringskoden är **Krav** eller **Period**.  
[![Krav. Period. Dagens datum och produktionstid](./media/TodayPLTReq.png)](./media/TodayPLTReq.png) Följande bild visar resultatet av planen om disponeringskoden är **Min/Max**.  
[![MinMax. Dagens datum och ledtid](./media/TodayPLTMinMax.png)](./media/TodayPLTMinMax.png)
### <a name="first-issue"></a>Första utleveransen 
Den angivna minimikvantiteten är uppfylld på datumet när tillgängligt lager ligger under miniminivån, enligt följande bild. Även om det tillgängliga lagret understiger miniminivån på datumet då huvudplaneringen körs, försöker inte **Första utleveransen** att täcka det förrän nästa behov kommer in.
Följande illustration visar ett exempel på disponeringskoden **Krav**.
[![Planera för en artikel med disponeringskoden **Krav** och uppfyllandet **Första utleveransen**](./media/FirstIssueReq.png)](./media/FirstIssueReq.png) Följande bild visar ett exempel på disponeringskoden **Period**.
[![Planera för en artikel med disponeringskoden **Period** och uppfyllandet **Första utleveransen**](./media/FirstIssuePeriod.png)](./media/FirstIssuePeriod.png) Följande bild visar ett exempel på disponeringskoden **Min/Max**.
[![Planera för en artikel med disponeringskoden **MinMax** och uppfyllandet **Första utleveransen**](./media/FirstIssueMinMax.png)](./media/FirstIssueMinMax.png) På datumet när huvudplaneringen körs, om tillgängligt lager redan ligger under säkerhetslagergränsen **Dagens datum** och **Dagens datum + anskaffningstid** utlöser omedelbart påfyllningen. **Första utleveransen** väntar tills det finns en annan utleveranstransaktion, till exempel försäljningsorder och krav i strukturlisterad för artikeln och utlöser den påfyllnad vid tidpunkten för transaktionen. Pådatumet när huvudplaneringen körs, om tillgängligt lager inte ligger under säkerhetslagergränsen, ger **Dagens datum** och **Första utleveransen** exakt samma resultat som visas i bilden nedan. 

[![NotUnderLimit](./media/ReqFirstIssue.png)](./media/ReqFirstIssue.png) På datumet när huvudplaneringen körs, om inte tillgängligt lager ligger under säkerhetslagergränsen, ger **Dagens datum + anskaffningstid** följande resultat eftersom den skjuter upp uppfyllande tills slutet på anskaffningstiden.
![Planera en artikel med disponeringskoden **Krav** och uppfyllandet **Första utleveransen**](./media/ReqTodayLT.png)
### <a name="coverage-time-fence"></a>Tidsgräns för disponering
Den angivna minimikvantiteten är uppfylld inom den tidsperiod som är angiven i fältet **Tidsgräns för disponering**. Det här alternativet är användbart när huvudplanering inte tillåter att tillgängligt lager används till faktiska order, till exempel försäljningar eller överföringar, i försöket att hålla säkerhetsnivån. I en framtida version behövs det här lagerpåfyllnadsläget inte lägre och det här alternativet blir inaktuellt.
## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Planera säkerhetslageråteranskaffning för artiklar med först utgången, först ut (FEFO)
Vid varje tillfälle används lagerinleverans med senaste utgångsdatum för säkerhetslager så att den faktiska efterfrågan, till exempel försäljningsrader eller BOM-rader, uppfylls i ordningen FEFO (först utgången, först ut).
Visa hur detta fungerar genom att anta följande scenario.
[![FEFOScenario](./media/FEFOScenario.png)](./media/FEFOScenario.png) När planeringen körs täcks den första försäljningsordern från befintlig lagerbehållning och en ytterligare inköpsorder för kvarvarande antal.
[![FEFO1](./media/FEFO1.png)](./media/FEFO1.png) En planerad order skapas för att säkerställa att tillgängligt lager är tillbaka på säkerhetsgränsen.
[![FEFO2](./media/FEFO2.png)](./media/FEFO2.png) När andra försäljningsordern planeras används föregående planerad order som täcker säkerhetslagret för denna kvantitet. Därför rullar säkerhetslagret kontinuerligt.
[![FEFO3](./media/FEFO3.png)](./media/FEFO3.png) Slutligen skapas en annan planerad order för att täcka säkerhetslagret.
[![FEFO4](./media/FEFO4.png)](./media/FEFO4.png) Alla batchar upphör därför och planerade order skapas för att fylla på säkerhetslagret när det har förfallit.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Hur huvudplanering hanterar av säkerhetlagrets begränsningar

Säkerhetslager spåras i systemet som en kravtyp precis som försäljningsrader eller krav i strukturlistan. Du ser raden för lagersäkerhetskrav på sidan **Nettobehov** om du tar bort standardfiltret i kolumnen **Kravtyp**.

Fullgörande av transaktionen för säkerhetslagret aktier prioriteras ned om systemet fastställer att detta medför fördröjningar vid fullgörandet av verkliga behov såsom försäljningsrader, strukturlisterader, överföringsbehov eller efterfrågeprognosrader. I annat fall har kontroll att tillgängligt lager är högre än säkerhetslagerantalet samma prioritet som övriga efterfrågetyper. Detta säkerställer verkliga transaktioner utan förseningar och bidrar till att förhindra överpåfyllnad och tidig påfyllnad av säkerhetslagret.

Under huvudplaneringens täckningfas prioriteras lagerpåfyllnad av säkerhetslager inte längre ned. Lagerbehållning kan användas före alla andra typer av efterfrågan. Under fördröjningsberäkningen läggs ny logik till som överskrider fördröjda försäljningsrader, strukturlisteradbehov och alla andra behovstyper, för att fastställa om de kan levereras i tid, förutsatt att säkerhetslagret används. Om systemet identifierar att det kan minimera fördröjningar genom att använda säkerhetslagret, ersätter sedan försäljningsrader eller strukturlisterader den ursprungliga täckningen med säkerhetslagret och systemet utlöser lagerpåfyllnad för säkerhetslagret i stället.

Om planen eller artikeln inte har ställts in för försenad beräkning har säkerhetslagerbegränsningen samma prioritet som övrig efterfrågan. Detta innebär att en reserv av lagerbehållning och annat tillgängligt lager före andra typer av efterfrågan.

