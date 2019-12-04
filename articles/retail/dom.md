---
title: Fördelad orderhantering (DOM)
description: I detta avsnitt beskrivs funktionen fördelad orderhantering (DOM) i Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 10d894bb65031741a5ec8365f7f8db76b58ab334
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693122"
---
# <a name="distributed-order-management-dom"></a>Fördelad orderhantering (DOM)

[!include [banner](includes/banner.md)]

I detaljhandelns nya paradigm försöker återförsäljarna erbjuda personligt kundengagemang, upplevelser i flera kanaler och friktionsfria möten. Eftersom det finns så många alternativ shoppar konsumenterna där de upplever sig behandlas bäst. I många fall är priserna och produkterna inte längre viktigast för konsumenternas beslut.

Återförsäljare som vill förbättra kundupplevelsen måste ha insyn i sitt lager i realtid, i samtliga kanaler. En enda, holistisk överblick över hela lagret kan optimera uppfyllelse, allokering och distribution av order. Därför börjar det bli allt viktigare för återförsäljare att välja och börja använda ett system för fördelad orderhantering (DOM).

DOM optimerar orderuppfyllelsen i ett komplext nätverk som består av system och processer. Hanteringen är beroende av en gemensam, global inblick i lagret i hela organisationen om det ska gå att hantera order på ett smart så att de uppfylls korrekt och billigare. Genom att göra återförsäljarens leveranskedja mer effektiv hjälper DOM återförsäljaren att bli bättre på att tillgodose kundens förväntningar.

Följande illustration visar livscykeln för en försäljningsorder i ett DOM-system.

![Livscykel för försäljningsorder i samband med DOM](./media/flow.png "Livscykel för försäljningsorder i samband med DOM")

## <a name="set-up-dom"></a>Ställ in DOM

1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
2. Expandera noden **Retail** på fliken **Konfigurationsnycklar** och markera kryssrutan **Fördelad orderhantering**.
3. Öppna **Retail \> Fördelad orderhantering \> Inställningar \> DOM-parametrar**.
4. Ange följande värden på fliken **Allmänt**:

    - **Aktivera fördelad orderhantering** – Välj inställningen **Ja**.
    - **Bekräfta att Bing-kartor används för DOM** – Välj inställningen **Ja**.

        > [!NOTE]
        > Du kan välja **Ja** endast om alternativet **Aktivera Bing Maps** på fliken **Bing Maps** på sidan **Gemensamma butiksparametrar** (**Butik \> Administrationsinställning \> Parametrar \> Gemensamma butiksparametrar**) också har värdet **Ja**, och om en giltig nyckel anges i fältet **Bing Maps-nyckel**.

    - **Kvarhållandeperiod i dagar** – Ange hur länge uppfyllelseplanerna som DOM-körningar genererar behålls i systemet. Batchjobbet **Inställning av borttagningsjobb för DOM-uppfyllelsedata** raderar alla uppfyllelseplaner som är äldre än antalet dagar som anges här.
    - **Avvisningsperiod (i dagar)** – Anger hur lång tid som måste gå innan en avvisad orderrad får tilldelas samma plats.

5. Ange följande värden på fliken **Problemlösare**:

    - **Maximalt antal automatiska uppfyllelseförsök** – Ange hur många gånger DOM-motorn försöker koppla en orderrad till en plats. Om DOM-motorn inte kan koppla en orderrad till en plats på det uppgivna antalet försök flaggas orderraden som ett undantag. Motorn hoppar sedan över den raden framöver tills statusen återställs manuellt.
    - **Radie för lokal butiksregion** – Ange ett värde. Detta fält bestämmer hur platser grupperas och anses vara desamma vad avstånd beträffar. Om du t.ex. väljer **100** anses alla butiker och distributionscenter inom en radie av 100 miles från uppfyllelseadressen vara likvärdig i fråga om avstånd.
    - **Problemlösartyp** – Välj ett värde. Två typer av problemlösare medföljer Retail: **Produktionsproblemlösare** och **Förenklad problemlösare**. **Produktionsproblemlösare** måste väljas för alla maskiner som kör DOM (dvs. alla servrar som ingår i DOMBatch-gruppen). Produktionsproblemlösare kräver en särskild licensnyckel som normalt licensieras och används i produktionsmiljö. I andra miljöer måste denna licensnyckel börja användas manuellt. Använd licensnyckeln manuellt på detta sätt:

        1. Öppna biblioteket Gemensamma tillgångar i Microsoft Dynamics Lifecycle Services, välj **Modell** som tillgångstyp och ladda ned filen **DOM-licens**.
        2. Starta Microsoft Internet Information Services-hanteraren (IIS), högerklicka på **AOSServices webbplats** och välj **Utforska**. Utforskaren öppnas i **\<AOS Service root\>\\webroot**. Anteckna sökvägen till \<AOS Service root\>, eftersom den anges i nästa steg.
        3. Kopiera konfigurationsfilen i katalogen **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        4. Gå till Retail Headquarters-klienten och öppna sidan **DOM-parametrar**. Välj **Produktionsproblemlösare** i fältet **Problemlösartyp** på fliken **Problemlösare** och bekräfta att inga felmeddelanden visas.

        > [!NOTE]
        > Den förenklade problemlösaren medföljer så att återförsäljare ska kunna testa DOM-funktionen utan att behöva använda den särskilda licensen. Den förenklade problemlösaren bör inte användas i produktionsmiljö.
        >
        > Även om den förenklade problemlösaren ger tillgång till samma funktioner som Produktionsproblemlösaren är den begränsad i fråga om prestanda (antalet order och orderrader som går att hantera under en körning) och konvergens av resultaten (en orderbatch kanske inte ger det bästa resultatet i vissa scenarier).
     
6. Återgå till **Butik \> Fördelad orderhantering \> Inställningar \> DOM-parametrar**.
7. Tilldela de olika DOM-enheterna de nödvändiga nummerserierna på fliken **Nummerserier**.

    > [!NOTE]
    > Innan någon nummerserie kan tilldelas enheterna måste de anges på sidan **Nummerserier** (**Organisationsadministration \> Nummerserier \> Nummerserier**).

8. Med DOM-funktionen går det att ange olika typer av DOM-regler och organisationen kan konfigurera flera regler beroende på vilka krav verksamheten ställer. DOM-regler går att ange för en grupp med platser eller enskilda platser och för en viss produktkategori, produkt eller variant. Så här skapar du grupperingen av platser som måste användas för DOM-reglerna:

    1. Öppna **Butik \> Kanalinställningar \> Uppfyllelsegrupper**.
    2. Välj **Ny** och ange ett nytt namn på och en beskrivning för den nya gruppen.
    3. Välj **Spara**.
    4. Välj **Lägg till rad** om du vill lägga till endast en plats i gruppen. Om du väljer **Lägg till rader** kan du lägga till flera platser.

9. Definiera regler i **Butik \> Fördelad orderhantering \> Inställningar \> Hantera regler**. Följande DOM-regler stöds nu:

    - **Regel för minimilager** – Med denna regeltyp kan organisationen sätta av en viss mängd av en produkt för andra ändamål än orderuppfyllande. Organisationen kanske inte vill att DOM ska kunna välja hela lagret som finns i en butik för att uppfylla en order. Den kanske vill reservera en viss mängd produkter för kunder som kommer in i butiken. När denna regeltyp används går det att definiera minimilagret som ska behållas för en produktkategori, en enskild produkt eller en produktvariant per plats eller platsgrupper.
    - **Prioritetsregel för uppfyllelseplats** – Med denna regeltyp kan organisationen ange en hierarki med platser och fastställa prioritetsordningen som DOM-motorn tar hänsyn till när den försöker hitta uppfyllelseplatser för specifika produkter. Det giltiga prioritetsintervallet är 1 till 10, där 1 är högsta prioritet och 10 är lägsta prioritet. Platser med högre prioritet beaktas före platser med lägre prioritet. Om regeln definieras som en fast begränsning kopplas order endast till platser för vilka prioriteter har angetts.
    - **Regel för partiell order** – Med denna regel kan organisationen ange om en order eller orderrader får uppfyllas partiellt. Följande parametrar är tillgängliga:

        - **Uppfyll partiella order?** – Om detta alternativ har värdet **Ja** får DOM uppfylla bara en del av kvantiteten på en orderrad. Denna partiella uppfyllelse uppnås genom att orderraden delas.
        - **Uppfyll partiella rader?** – Om detta alternativ har värdet **Ja** får DOM uppfylla en partiell kvantitet på orderrader. Denna partiella uppfyllelse uppnås genom att orderraden delas.
        - **Uppfyll order från enbart en plats?** – Om detta alternativ har värdet **Ja** ser DOM till att alla rader på ordern uppfylls från samma plats.


        I följande tabell förklaras beteendet när en kombination av dessa parametrar har angetts.

        |      | Uppfyll partiella order | Uppfyll partiella rader | Uppfyll order från enbart en plats | Beskrivning |
        |------|------------------------|-----------------------|--------------------------------------|-------------|
        | 1    | Ja                    | Ja                   | Ja                                  | Ett par rader i ordern kan uppfyllas och enskilda rader kan uppfyllas partiellt, men alla rader måste komma från samma plats i en instans av DOM-körningen. (Denna kombination stöds inte för närvarande.) |
        | 2    | Ja                    | Nej                    | Ja                                  | Ett par rader i ordern kan uppfyllas men enskilda rader kan inte uppfyllas partiellt, och alla uppfyllda rader måste komma från samma plats i en instans av DOM-körningen. (Denna kombination stöds inte för närvarande.) |
        | 3    | Ja                    | Ja                   | Nej                                   | Ett par rader i ordern kan uppfyllas men enskilda rader kan inte uppfyllas partiellt, och varje rad kan uppfyllas från mer än en plats i en instans av DOM-körningen. |
        | 4\*  | Nej                     | Inte aktuellt        | Nej                                   | Alla orderrader måste uppfyllas, enskilda rader kan inte uppfyllas partiellt och varje orderrad kan uppfyllas från olika platser. |
        | 5\*  | Nej                     | Inte aktuellt        | Ja                                  | Alla orderrader måste uppfyllas, enskilda rader kan inte uppfyllas partiellt och alla orderrader kan levereras endast från en plats. |
        | 6\*  | Nej                     | Inte aktuellt        | Nej                                   | Denna kombination fungerar som kombination 4, eftersom **Uppfyll partiella rader** inte kan ha värdet **Ja** när **Uppfyll partiella order** har värdet **Nej**. |
        | 7\*  | Nej                     | Inte aktuellt        | Ja                                  | Denna kombination fungerar som kombination 5, eftersom **Uppfyll partiella rader** inte kan vara **Ja** när **Uppfyll partiella order** är **Nej**. |
        | 8    | Ja                    | Nej                    | Nej                                   | Ett par rader i ordern kan uppfyllas men enskilda rader kan inte uppfyllas partiellt, och de olika orderraderna kan uppfyllas från mer än en plats i en instans av DOM-körningen. |
        | 9\*  | Nej                     | Inte aktuellt        | Ja                                  | Alla orderrader måste uppfyllas och de får bara göra det från en plats. |

        \* Om **Uppfyll partiella order** har värdet **Nej** anses **Uppfyll partiella rader** alltid ha värdet **Nej**, oavsett av vilket värde det faktiskt har.

> [!NOTE]
> I Retail version 10.0.5 har parametern **Uppfyll order från enbart en plats** ändrats till **Maximalt antal uppfyllelseplatser**. I stället för att låta en användare konfigurera om order kan uppfyllas från enbart en plats eller från så många platser som möjligt, kan användarna nu ange om uppfyllelse kan ske från en bestämd uppsättning platser (upp till 5) eller från så många platser som möjligt. Detta ger mer flexibilitet när det gäller antalet platser som ordern kan uppfyllas från.

   - **Platsregel för offline-uppfyllelse** – Med denna regel kan organisationen ange att en plats eller en grupp med platser är offline eller inte tillgänglig för DOM, så att order inte kan tilldelas till dessa platser för uppfyllelse.
    - **Regel för högsta antal avvisningar** – Med denna regel kan organisationen ange ett tröskelvärde för avvisningar. När tröskelvärdet har nåtts märker DOM-processorn en order eller orderrad som ett undantag och utesluter den från ytterligare behandling.

        När orderrader har tilldelats en plats kan platsen avvisa en tilldelad orderrad eftersom den kanske inte kan uppfylla den raden av någon anledning. Avvisade rader märks som undantag och återförs till poolen för bearbetning i nästa körning. Under nästa körning försöker DOM tilldela en annan plats den avvisade raden. Den nya platsen kan också avvisa den tilldelade orderraden. Denna tilldelnings- och avvisningscykel kan löpa flera varv. När antalet avvisningar når upp till det angivna tröskelvärdet märker DOM orderraden som ett permanent undantag och plockar inte raden för tilldelning igen. DOM tar bara upp orderraden för tilldelningen igen om en användare återställer dess status manuellt.

   - **Regel för längsta avstånd** – Med denna regel kan organisationen ange det maximala avstånd som en plats eller grupp med platser får finnas på för att uppfylla ordern. Om överlappande maximala avståndsregler har angetts för en plats använder DOM det minsta maximala avstånd som har angetts för den platsen.
    - **Regel för maximalt antal order** – Med denna regel kan organisationen ange det maximala antalet order som en plats eller grupp med platser kan bearbeta under en dag. Om det maximala antalet order har tilldelats en plats under en dag tilldelar DOM inte fler order dit under resten av dagen.

   Här följer några gemensamma attribut som går att ange för de föregående regeltyperna:

   - **Startdatum** och **Slutdatum** – Varje regel kan fås att gälla mellan vissa datum med hjälp av dessa fält.
   - **Inaktiverad** – Bara de regler som har värdet **Nej** i detta fält tas med i en DOM-körning.
   - **Fast begränsning** – Det går att ange en regel som en fast begränsning eller inte. Varje DOM-körning genomlöper två iterationer. Under det första varvet behandlas varje regel som en regel med fast begränsning, oavsett fältinställningen. Med andra ord tillämpas alla regler. Det enda undantaget är regeln **Platsprioritet**. Under den andra iterationen tas regler som inte hade angetts som fasta begränsningsregler bort, och order eller orderrader som inte hade tilldelats platser när alla reglerna hade tillämpats tilldelas platser.

10. Uppfyllelseprofiler används för att gruppera ett antal regler, juridiska personer, ursprung till försäljningsorder och leveranssätt. Varje DOM-körning gäller en specifik uppfyllelseprofil. På så sätt kan organisationen ange och köra vissa regler för ett antal juridiska personer på order med specifika försäljningsorderursprung och leveranssätt. Om olika regler måste köras för olika typer av försäljningsorderursprung eller leveranssätt kan uppfyllelseprofiler alltså definieras enligt detta. Så här ställs uppfyllelseprofiler in:  

    1. Öppna **Butik \> Fördelad orderhantering \> Inställningar \> Uppfyllelseprofiler**.
    2. Välj **Ny**.
    3. Ange värden i fälten **Profil** och **Beskrivning**.
    4. Ange värdet på alternativet **Tillämpa resultat automatiskt**. Om du väljer **Ja** tillämpas resultaten från DOM-körningen för profilen automatiskt på försäljningsorderraderna. Om du väljer **Nej** går resultaten endast att se i uppfyllelseplanen. De används inte på försäljningsorderraderna.
    5. Om du vill att DOM-profilen ska köras för order med samtliga försäljningsorderursprung – till och med order där försäljningsorderursprunget är odefinierat – ska alternativet **Bearbeta order med tomt försäljningsursprung** ha värdet **Ja**. Om du vill köra profilen endast för vissa försäljningsorderursprung går de att definiera på sidan **Försäljningsursprung**. Detta förklaras senare.
    6. Välj **Lägg till** på snabbfliken **Juridiska personer** och välj sedan en juridisk person.
    7. Välj **Lägg till** på snabbfliken **Regler** och välj sedan den regel som ska länkas till profilen.
    8. Upprepa de föregående två stegen tills alla regler som ska vara med är kopplade till profilen.
    9. Välj **Spara**.
    10. Välj **Leveranssätt** på fliken **Inställningar** i åtgärdsfönstret.
    11. Välj **Nytt** på sidan **Leveranssätt**.
    12. Välj den juridiska personen i fältet **Företag**. Listan med företag är begränsad till de juridiska personerna som lades till tidigare.
    13. Ange leveranssättet som ska kopplas till denna profil i fältet **Leveranssätt**. Ett leveranssätt går inte att koppla till flera aktiva profiler.
    14. Upprepa de föregående två stegen tills alla leveranssätt som ska vara med är kopplade till profilen.
    15. Stäng sidan **Leveranssätt**.
    16. Välj **Försäljningsorderursprung** på fliken **Inställningar** i åtgärdsfönstret.
    17. Välj **Nytt** på sidan **Försäljningsursprung**.
    18. Välj den juridiska personen i fältet **Företag**. Listan med företag är begränsad till de juridiska personerna som lades till tidigare.
    19. Ange försäljningsursprunget som ska kopplas till denna profil i fältet **Försäljningsursprung**. Ett försäljningsursprung går inte att koppla till flera aktiva profiler.
    20. Upprepa de föregående två stegen tills alla försäljningsursprung som ska vara med är kopplade till profilen.
    21. Stäng sidan **Försäljningsursprung**.
    22. Ge alternativet **Aktivera profil** värdet **Ja**. Ett varningsmeddelande visas om det finns några fel i inställningarna.

## <a name="dom-processing"></a>DOM-bearbetning

DOM körs bara i batchjobb. Gör på följande vis för att konfigurera batchjobbet för DOM-körningar.

1. Öppna **Butik \> Fördelad orderhantering \> Batchbearbetning \> Inställning för DOM-bearbetarjobb**.
1. Välj en profil som DOM måste köras för i fältet **Uppfyllelseprofil** på snabbfliken **Parametrar**.
1. Välj en konfigurerad batchgrupp i fältet **Batchgrupp** på snabbfliken **Kör i bakgrunden**.
1. Ange batchjobbets namn i fältet **Uppgiftsbeskrivning**.
1. Välj **Upprepning** och ange hur ofta batchjobbet ska upprepas.
1. Välj **OK**.

Vid bearbetningen beaktar DOM ordern och orderraderna enligt beskrivningen här:

- Orderrader som uppfyller kriterierna för försäljningsorderursprung, leveranssätt och juridisk person enligt inställningen i DOM-profilen och som dessutom uppfyller något av dessa kriterier:

    - De skapas från butikskanaler.
    - De har aldrig kopplats av DOM.
    - De har kopplats av DOM tidigare men märkts som undantag och är under det maximala tröskelvärdet för försök.
    - Leveranssättet är inte upphämtning eller elektronisk leverans.
    - De är inte märkta för leverans.
    - De är inte manuellt exkluderade.

- Order som inte är spärrade

När DOM har tillämpat reglerna, lagerbegränsningarna och optimeringarna väljer DOM platsen som är närmast kundens leveransadress.

![Villkor för försäljningsorder](./media/ordercriteria.png "Villkor för försäljningsorder")

## <a name="results-of-dom-runs"></a>Resultat av DOM-körningar

Om uppfyllelseprofilen är inställd på **Tillämpa automatiskt** tillämpas resultaten av körningen automatiskt på försäljningsorderraderna. Uppfyllelseplanen går att se separat. Men om uppfyllelseprofilen inte är inställd på **Tillämpa automatiskt** går resultatet av körningen bara att se från uppfyllelseplanvyn. 

Gör på följande vis om du vill se alla uppfyllelseplaner som genereras.

1. Öppna **Butik \> Fördelad orderhantering \> Fördelad orderhantering**.
2. Välj rutan **Uppfyllelseplaner** på arbetsytan **Fördelad orderhantering**.
3. Välj id:t för den aktuella orderuppfyllelseplanen för att visa uppfyllelseplanen.

    Orderinformationsavsnittet i uppfyllelseplanen visar de ursprungliga försäljningsorderraderna som ingick i körningen. Förutom de vanliga försäljningsorderradsfälten innehåller orderinformationsavsnittet även följande tre DOM-relaterade fält:

    - **Uppfyllelsetyp** – Detta fält visar om försäljningsorderraden är helt kopplad, partiellt kopplad eller inte kopplad alls till en plats.
    - **Dela** – Detta fält visar om en försäljningsorderrad har delats och kopplats till olika platser.
    - **Antal uppfyllelseplatser** – Detta fält visar hur många uppfyllelserader som skapades för en försäljningsorderrad (baserat på antalet platser som den ursprungliga försäljningsorderraden har kopplats till).

    Avsnittet med information om orderuppfyllelsen visar tilldelningen av de ursprungliga försäljningsorderraderna till olika platser tillsammans med kvantiteter.

## <a name="order-line-actions-and-statuses"></a>Åtgärder och statusar för orderrader

Nedan beskrivs inställningarna på orderraden. Öppna orderraden från **Retail \> Kunder \> Alla försäljningsorder**.
- Om du ger alternativet **Exkludera från DOM-bearbetning** på fliken **Allmänt** för försäljningsorderraden värdet **Ja** exkluderas orderraden från DOM-bearbetning.
- Fältet **DOM-status** på fliken **Allmänt** för försäljningsorderraden kan ges något av dessa värden:

    - **Ingen** – Orderraden har aldrig kopplats.
    - **Slutfört** – Orderraden har kunnat kopplats och tilldelat en plats.
    - **Undantag** – Orderraden har kopplats men kan inte tilldelas en plats. Det finns flera undertyper till undantag som går att visa från DOM-arbetsytan:

        - **Ingen tillgänglig kvantitet** – Det finns inget på lager att tilldela ordern på dessa platser.
        - **Högsta antal avvisningar** – Orderraden har nått det högsta tröskelvärdet för avvisningar.
        - **Dataändringskonflikt** – Försäljningsorderraden har ändrats sedan ordern kopplades. Därför kan uppfyllelseplanen inte tillämpas på ordern.
        - **Orderradsspecifikt undantag** – Orderraden har flera undantag.

- När försäljningsordern registreras kan DOM köras interaktivt. När en orderrad matas in kan man efter att ha angett produkt och kvantitet välja **Uppdatera rad** och sedan – under **DOM** – välja **Föreslå uppfyllelseplats**. Då visas en lista med platser som kan uppfylla kvantiteten på orderraden. Listan bygger på DOM-regler. Listan är sorterad efter avstånd. Välj en plats för att ange den relevanta platsen och lagerstället på försäljningsorderraden. Om detta ska fungera måste det finnas en befintlig, aktiv uppfyllelseprofil som matchar försäljningsradens försäljningsursprung och leveransläge.
- Visa DOM-körningsloggarna för en försäljningsorderrad genom att välja **Försäljningsorderrad** och sedan – under **DOM** – välja **Visa DOM-loggar**. DOM-loggarna innehåller alla händelser och loggar som genererades av DOM-körningen. Loggarna kan hjälpa dig att förstå varför en viss plats tilldelades orderraden och vilka regler och begränsningar som ansågs ingå i tilldelningen. På fliken **Hantera** är DOM-loggarna också tillgängliga på försäljningsorderrubrikens nivå.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Kör ett rensningsjobb för DOM-uppfyllelseplaner

När DOM-bearbetningen körs skapas uppfyllelseplaner. Med tiden blir det många uppfyllelseplaner i systemet. Du kan hantera antalet uppfyllelseplaner som systemet behåller genom att konfigurera ett batchjobb som raderar äldre uppfyllelseplaner utifrån värdet **Kvarhållandeperiod i dagar**.

1. Öppna **Butik \> Fördelad orderhantering \> Batchbearbetning \> Inställning av borttagningsjobb för DOM-uppfyllelsedata**. 
1. Välj en konfigurerad batchgrupp i fältet **Batchgrupp**.
1. Välj **Upprepning** och ange hur ofta batchjobbet ska upprepas.
1. Välj **OK**.

## <a name="more-information"></a>Mer information

Här är några saker att tänka på när du använder DOM-funktionen:

- Nu granskar DOM bara order som skapas från butikskanaler. Försäljningsorder identifieras som butiksförsäljningsorder när alternativet **Butiksförsäljning** har värdet **Ja**.
- Microsoft har inte testat DOM med avancerade lagerstyrningsfunktioner. Kunder och partner måste noga bedöma om DOM är kompatibelt med den avancerade lagerstyrningskapacitet och processerna som är relevanta för dem.
- DOM är bara tillgängligt i molnversionen av Retail. Det stöds inte i lokala installationer.
