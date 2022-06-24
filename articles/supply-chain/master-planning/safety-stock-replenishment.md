---
title: Säkerhet för artiklar i lageruppfyllelse
description: I denna artikel beskrivs uppfyllandet av säkerhetslagret och hur du konfigurerar säkerhetslagerantalet för artiklar.
author: t-benebo
ms.date: 8/23/2021
ms.topic: article
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 70461ad1de94c984cb41e6b1d46af9e310a928d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887411"
---
# <a name="safety-stock-fulfillment-for-items"></a>Säkerhet för artiklar i lageruppfyllelse

[!include [banner](../includes/banner.md)]

Säkerhetslager anger en ytterligare kvantitet för en artikel i lagret för att minska risken för att artikeln är slut på lagret. Säkerhetslager används som ett buffertlager om försäljningsorder kommer in och leverantören inte kan leverera ytterligare artiklar för att uppfylla kundens begärda leveransdatum. När säkerhetslager används för att uppfylla en försäljningsorder, reduceras säkerhetslagret. Du kan använda huvudplanering för att automatiskt föra tillbaka lagret till säkerhetsnivån.

## <a name="set-up-safety-stock-levels-for-items"></a>Ställ in säkerhetslagernivåer för artiklar

Säkerhetslager ställs in som en del av artikeldisponering på sidan **Artikeldisponering** under **Frisläppta produkter \> Plan \> Disponering**.

Ange säkerhetslagernivån att underhålla för artikeln i fältet **Minimum**. Värdet uttrycks i lagerenheter. Om du lämnar fältet tomt är standardvärdet noll. Det här fältet är tillgängligt när du väljer **Period**, **Behov** eller **Min/Max** i listan **Disponeringskod**. De lagernivåbegränsningen gäller tillgängligt lager, vilket innebär att reservationer och märkning kan utlösa säkerhetslagerpåfyllnad innan den fysiska kvantiteten hamnar under den angivna miniminivån.

> [!NOTE]
> Du måste definiera alla övriga planerade disponeringsdimensioner innan du kan definiera fältet **Minimum**. Detta förhindrar att en ogiltig post används vid huvudplanering. Situationen skulle kunna uppstå om en dimensionsgrupp utökas med ytterligare en planerad disponeringsdimension för vilken de minsta och största lagerkvantiteterna ännu inte har angetts.

Använd minimumnycklar för att hantera säsongsvarianter i efterfrågan. Du kan till exempel minska minimilagernivån under lågsäsong och gradvis öka nivån under de övriga månaderna. Du skapar en minimumnyckel genom att gå till **Huvudplanering \> Inställningar \> Disponering \> Minimi-/maxinycklar**. Du anger en minimumnyckel för att justera säkerhetslagernivån efter säsongsvarianter i fältet **Minimumnyckel** på sidan **Artikeldisponering**.

## <a name="example-minimum-key"></a>Exempel: Minimumnyckel

Följande procedur är ett exempel som visar hur du konfigurerar en miniminyckel som tar upp ökad säsongsefterfrågan under våren och sommaren.

1. Gå till **Huvudplanering \> Inställningar \> Disponering \> Minimi-/maxinycklar**.
1. Välj **Ny** för att skapa en minimi-/maxinyckel.
1. Ange en identifierare för nyckeln i fältet **Minimum- eller maximumnyckel**. Ange ett namn för nyckeln i fältet **Namn**.
1. Ange alternativet **Använd giltighetsdatum** till *Ja* och lämna fältet **Giltighetsdatum** tomt för att göra nyckeln giltig från den första dagen i innevarande år.

    > [!NOTE]
    > Kombinationen av inställningarna **Använd giltighetsdatum** och **Giltighetsdatum** definierar det datum som nyckeln är giltig från.
    >
    > - När alternativet **Använd giltighetsdatum** är inställt på *Nej* gäller nyckeln från aktuellt datum eller systemdatum.
    > - När alternativet **Använd giltighetsdatum** har inställningen *Ja*, gäller nyckeln från det datum som definieras i fältet **Giltighetsdatum**.

1. I avsnittet **Perioder**, skapa 12 rader och ställ in följande värden för dem:

    - **Ändra** – Tilldela varje rad ett unikt nummer från 1 till 12. Det här fältet visar den stegvisa förändringen av tidsenheten som definieras i fältet **Enhet**.
    - **Enhet** – Välj *Månader* för varje rad.
    - **Från datum**, **Till datum** och **Månad** – Dessa fält ställs in automatiskt, baserat på inställningarna **Ändring** och **Enhet**. Månatliga perioder startar från den första dagen i innevarande år.
    - **Faktor** – Ange värdena som beskrivs i följande tabell. Det här fältet definierar den faktor som du ska multiplicera minimilagret med.

        | Rad (ändring) | Faktor | Resultat |
        |---|---|---|
        | 1–3 | 1 | Minimilagret baseras på inställningen för januari till mars på sidan **Artikeldisponering**. |
        | 4–5 | 2 | Minimilagret multipliceras med faktorn 2 för april till maj. |
        | 6–8 | 2.5 | Minimilagret multipliceras med faktorn 2,5 för juni till och med augusti. |
        | 9–12 | 1 | Minimilagret återgår till inställningen för september till och med december på sidan **Disponering**. |

    Inställningarna ska nu se ut ungefär som inställningarna i följande illustration.

    ![Minimi- eller maximinyckelperioder.](media/min-max-key-periods.png "Minimi- eller maximinyckelperioder")

> [!NOTE]
> Du kan också använda en guiden om du vill skapa en minimum-/maximumnyckel. På sidan **Minimi- eller maximumnycklar**, i åtgärdsrutan, välj **Guide** för att öppna guiden **Minimum-/maximumnycklar**. I guiden går du steg för steg genom processen för att skapa och konfigurera minimum-/maximumnyckeln.

Om disponeringskoden är *Min/max* kan du även ange maximal lagerkvantitet som du vill underhålla för en artikeln. Värdet uttrycks även i lagerenheter. Om förväntat tillgängligt lager faller under minimikvantiteten, genererar huvudplaneringen en planerad order för att uppfylla alla öppna behov först och ökar sedan det tillgängliga lagret till den angivna maximikvantiteten. Precis som du konfigurerar minimilagerkvantitet måste du definiera alla övriga planerade disponeringsdimensioner innan du kan konfigurera fältet **Maximum**.

## <a name="example-minmax-coverage-code"></a>Exempel: Min/max disponeringskod

Minimikvantiteten är 10 och maximikvantiteten är 15. Aktuella lagerbehållning är 4. Detta ger ett minimikvantitetskrav på 6. Eftersom maximikvantiteten är 15 är genererar huvudplaneringen en planerad order på 11 artiklar.

För artiklar med säsongsvarianter behöver du kanske ha olika maximinivåer. Om du vill göra det måste du definiera **Maximumnycklar** genom att gå till **Huvudplanering \> Inställningar \> Disponering \> Minimum-/maximumnycklar**. Fyll i fältet **Maximumnyckel** på idan **Artikeldisponering**. Du kan visa information om säkerhetslagernivåer, definierade med miniminycklarna på fliken **Min/max** på sidan **Artikeldisponering**. Du måste se till att minimi- och maximivärdena hålls synkroniserade under en viss period.

## <a name="safety-stock-fulfillment"></a>Säkerhetslageruppfyllelse

Parametern **Uppfyll minimum** gör det möjligt att välja datum eller tidsperiod under vilken lagernivån måste uppfylla kvantiteten som du angav i fältet **Minimum**. Det här fältet är tillgängligt när du väljer **Period**, **Behov** eller **Min/Max** i listan **Disponeringskod**.

Om **Miniminycklar** är används, välj kryssrutan **Minimiperioder** om du vill uppfylla minimilagernivån för alla de perioder som ställs in i minimumnyckeln. Om du avmarkerar kryssrutan är minimilagret endast uppfyllt för aktuell period.

Följande scenario visar hur denna parameter fungerar och vad som är skillnaderna mellan värdena.

> [!NOTE]
> För alla bilder i denna artikel representerar x-axeln lager, y-axeln representerar dagar, staplarna representerar lagernivån, pilarna representerar transaktioner, exempelvis försäljningsorderrader, inköpsorderrader eller planerade order.

[![Vanligt scenario för uppfyllelse av säkerhetslager.](media/Scenario1.png)](media/Scenario1.png)

Parametern **Uppfyll minimum** kan ha följande värden:

### <a name="todays-date"></a>Dagens datum

Den angivna minimikvantiteten är uppfylld på datumet då huvudplaneringen körs. Systemet försöker så snart som möjligt uppfylla säkerhetslagergränsen även om det kan vara orealistisk på grund av ledtiden.

[![Behov på dagens datum.](media/TodayReq.png)](media/TodayReq.png)

Planerad order P1 skapas för dagens datum i syfte att göra att tillgängligt lager överskrider säkerhetslagernivån på det datumet. Försäljningsorderraderna S1 till S3 fortsätter att minska lagernivån. Planerade order P2 till P4 genereras av huvudplaneringen så att lagernivån återförs till säkerhetsgränsen efter varje försäljningsorder.

När disponeringskoden **Krav** används skapas flera planerade order. Det är alltid en god idé att använda antingen **Period** eller **Min/Max** disposition för artiklar och material som efterfrågas ofta till att förpacka påfyllningen. Följande illustration visar ett exempel på disponeringskoden **Period**.

[![Period. Dagens datum.](media/TodayPeriod.png)](media/TodayPeriod.png)

Följande illustration visar ett exempel på disponeringskoden **Min/Max**.

[![Min/max. Dagens datum.](media/TodayMinMax.png)](media/TodayMinMax.png)

### <a name="todays-date--procurement-time"></a>Dagens datum + anskaffningstid

Den angivna minimikvantiteten är uppfylld på det datum då huvudplaneringen körs plus leverans- eller produktionstid. Den här tiden inkluderar eventuella säkerhetsmarginaler. Om artikeln har ett handelsavtal och kryssrutan **Sök efter handelsavtal** är markerad på sidan **Huvudplaneringsparametrar** tas leveranstiden från handelsavtalet inte med i beräkningen. Produktionstider tas från inställningarna för artikeldisponering eller från artikeln.

Det här uppfyllelseorderläget skapar planer med färre förseningar och färre planerade order, oavsett om disponeringsgruppen inställd på artikeln.

I följande bild visas resultatet av planen om disponeringskoden är **Krav** eller **Period**.

[![Krav eller Period. Dagens datum och ledtid.](media/TodayPLTReq.png)](media/TodayPLTReq.png)

I följande bild visas resultatet av planen om disponeringskoden är **Min/Max**.

[![Min/max. Dagens datum och ledtid.](media/TodayPLTMinMax.png)](media/TodayPLTMinMax.png)

### <a name="first-issue"></a>Första utleveransen

Den angivna minimikvantiteten är uppfylld på datumet när tillgängligt lager ligger under miniminivån, enligt följande bild. Även om det tillgängliga lagret understiger miniminivån på datumet då huvudplaneringen körs, försöker inte **Första utleveransen** att täcka det förrän nästa behov kommer in.

Följande illustration visar ett exempel på disponeringskoden **Krav**.

[![Planera en artikel med disponeringskoden Krav och uppfyllandet Första utleverans.](media/FirstIssueReq.png)](media/FirstIssueReq.png)

Följande illustration visar ett exempel på disponeringskoden **Period**.

[![Planera en artikel med disponeringskoden Period och uppfyllandet Första utleverans.](media/FirstIssuePeriod.png)](media/FirstIssuePeriod.png)

Följande illustration visar ett exempel på disponeringskoden **Min/Max**.

[![Planera en artikel med disponeringskoden MinMax och uppfyllandet Första utleverans.](media/FirstIssueMinMax.png)](media/FirstIssueMinMax.png)

Om tillgängligt lager redan ligger under säkerhetslagergränsen på datumet när huvudplaneringen körs, kommer **Dagens datum** och **Dagens datum + anskaffningstid** omedelbart att utlösa lagerpåfyllnaden. **Första utleveransen** väntar tills det finns en annan utleveranstransaktion, till exempel försäljningsorder och krav i strukturlisterad för artikeln och utlöser den påfyllnad vid tidpunkten för transaktionen.

På datumet när huvudplaneringen körs, om tillgängligt lager inte ligger under säkerhetslagergränsen, ger **Dagens datum** och **Första utleveransen** exakt samma resultat som visas i följande bild.

[![Inte under gräns.](media/ReqFirstIssue.png)](media/ReqFirstIssue.png)

På det datum då huvudplaneringen körs kommer, om tillgängligt lager inte underskrider gränsen för säkerhetslagret, **Dagens datum + anskaffningstid** att tillhandahålla följande resultat eftersom detta skjuter upp uppfyllandet tills slutet på anskaffningstiden.

![Uppfyllelsen senareläggs till slutet av anskaffningens ledtid.](media/ReqTodayLT.png)

### <a name="coverage-time-fence"></a>Tidsgräns för disponering

Den angivna minimikvantiteten är uppfylld inom den tidsperiod som är angiven i fältet **Tidsgräns för disponering**. Det här alternativet är användbart när huvudplanering inte tillåter att tillgängligt lager används till faktiska order, till exempel försäljningar eller överföringar, i försöket att hålla säkerhetsnivån. I en framtida version behövs det här lagerpåfyllnadsläget inte lägre och det här alternativet blir inaktuellt.

## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Planera säkerhetslageråteranskaffning för artiklar med först utgången, först ut (FEFO)

Vid varje tillfälle används lagerinleverans med senaste utgångsdatum för säkerhetslager så att den faktiska efterfrågan, till exempel försäljningsrader eller BOM-rader, uppfylls i ordningen FEFO (först utgången, först ut).

Visa hur detta fungerar genom att anta följande scenario.

[![FEFO-scenario.](media/FEFOScenario.png)](media/FEFOScenario.png)

När planeringen körs täcks den första försäljningsordern från befintlig lagerbehållning och en ytterligare inköpsorder för kvarvarande antal.

[![FEFO 1.](media/FEFO1.png)](media/FEFO1.png)

En planerad order skapas för att säkerställa att tillgängligt lager återställs till säkerhetsgränsen.

[![FEFO 2.](media/FEFO2.png)](media/FEFO2.png)

När den andra försäljningsordern planeras används föregående planerad order som täcker säkerhetslagret för denna kvantitet. Därför rullar säkerhetslagret kontinuerligt.

[![FEFO 3.](media/FEFO3.png)](media/FEFO3.png)

Slutligen skapas ytterligare en planerad order för att täcka säkerhetslagret.

[![FEFO 4.](media/FEFO4.png)](media/FEFO4.png)

Alla batcher upphör enligt detta och planerade order skapas för att fylla på säkerhetslagret när detta har förfallit.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Hur huvudplanering hanterar av säkerhetlagrets begränsningar

Säkerhetslager spåras i systemet som en kravtyp precis som försäljningsrader eller krav i strukturlistan. Du ser raden för lagersäkerhetskrav på sidan **Nettobehov** om du tar bort standardfiltret i kolumnen **Kravtyp**.

Fullgörande av transaktionen för säkerhetslagret aktier prioriteras ned om systemet fastställer att detta medför fördröjningar vid fullgörandet av verkliga behov såsom försäljningsrader, strukturlisterader, överföringsbehov eller efterfrågeprognosrader. I annat fall har kontroll att tillgängligt lager är högre än säkerhetslagerantalet samma prioritet som övriga efterfrågetyper. Detta säkerställer verkliga transaktioner utan förseningar och bidrar till att förhindra överpåfyllnad och tidig påfyllnad av säkerhetslagret.

Under huvudplaneringens täckningfas prioriteras lagerpåfyllnad av säkerhetslager inte längre ned. Lagerbehållning kan användas före alla andra typer av efterfrågan. Under fördröjningsberäkningen läggs ny logik till som överskrider fördröjda försäljningsrader, strukturlisteradbehov och alla andra behovstyper, för att fastställa om de kan levereras i tid, förutsatt att säkerhetslagret används. Om systemet identifierar att det kan minimera fördröjningar genom att använda säkerhetslagret, ersätter sedan försäljningsrader eller strukturlisterader den ursprungliga täckningen med säkerhetslagret och systemet utlöser lagerpåfyllnad för säkerhetslagret i stället.

Om planen eller artikeln inte har ställts in för försenad beräkning har säkerhetslagerbegränsningen samma prioritet som övrig efterfrågan. Detta innebär att en reserv av lagerbehållning och annat tillgängligt lager före andra typer av efterfrågan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Använd säkerhetslagerjournalen för att uppdatera minimumdisponering för artiklar](safety-stock-journal.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
