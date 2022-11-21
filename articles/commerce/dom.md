---
title: Fördelad orderhantering (DOM)
description: Den här artikeln beskriver funktionen fördelad orderhantering (DOM) i Dynamics 365 Commerce.
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a18441c44869e0e95cf79e35045dd7eacca7e43d
ms.sourcegitcommit: 4f987aad3ff65fe021057ac9d7d6922fb74f980e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2022
ms.locfileid: "9764192"
---
# <a name="distributed-order-management-dom"></a>Fördelad orderhantering (DOM)

[!include [banner](includes/banner.md)]

Den här artikeln beskriver funktionen fördelad orderhantering (DOM) i Microsoft Dynamics 365 Commerce.

DOM är en flerkanalslösning för optimering av orderuppfyllelse som bidrar till att maximera orderuppfyllelsen i försörjningskedjan. DOM ser till att produkter levereras till dina kunder i rätt kvantitet, från rätt källa, vid rätt tidpunkt. DOM kan också hjälpa dig maximera vinsterna, minimera kostnaderna och uppfylla kraven på servicenivå.

DOM använder MIP (Mixed Integer Programming) och prediktiva analysmodeller för att utföra optimeringar för både batcher och enskilda order. Med den här funktionen kan handlare använda definierade regler för att balansera många motsägelsefulla orderuppfyllelsebehov. I ett modern leveransnätverk där produktuppfyllelsen kan komma från flera kanaler måste organisationerna snabbt anpassa sig efter orderändringar, problem med leverantörstillgänglighet och toppar i efterfrågan. DOM hjälper dig maximera orderuppfyllelsen och hitta rätt källor för produktleverans utifrån affärsbegränsningar och affärsmål, till exempel att minimera kostnaderna genom att uppfylla order från de närmaste källorna. DOM använder avståndet mellan källorna för produktuppfyllelse och leveransdestinationerna, kostnadsfaktorer som har definierats som optimeringsmål och regler som har definierats som begränsningar, till exempel lager vid uppfyllelsenoder för att optimera orderuppfyllelsen. Med DOM kan du definiera flera profiler som gör det möjligt för företag att köra olika optimeringsstrategier beroende på vilken typ av affärs- eller konsumentsegment som används. 

Följande illustration visar livscykeln för en försäljningsorder i ett DOM-system.

![Livscykel för försäljningsorder i samband med DOM.](./media/flow.png "Livscykel för försäljningsorder i samband med DOM")

## <a name="set-up-dom"></a>Ställ in DOM

1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
2. Expandera noden **Commerce** på fliken **Konfigurationsnycklar** och markera kryssrutan **Fördelad orderhantering**.
3. Öppna **Retail och Commerce \> Fördelad orderhantering \> Inställningar \> DOM-parametrar**.
4. Ange följande värden på fliken **Allmänt**:

    - **Aktivera fördelad orderhantering** – Välj inställningen **Ja**.
    - **Bekräfta att Bing-kartor används för DOM** – Välj inställningen **Ja**.

        > [!NOTE]
        > Du kan välja **Ja** endast om alternativet **Aktivera Bing-kartor** på fliken **Bing-kartor** på sidan **Gemensamma Commerce-parametrar** (**Retail och Commerce \> Administrationsinställning \> Parametrar \> Gemensamma Commerce-parametrar**) också har värdet **Ja**, och om en giltig nyckel anges i fältet **Nyckel till Bing-kartor**.
        >
        > Med portalen [utvecklingscenter för Bing-kartor](https://www.bingmapsportal.com/) kan du begränsa åtkomsten till dina API-nycklar för Bing-kartor till en uppsättning domäner som du anger. Med den här funktionen kan kunder definiera en strikt uppsättning referensvärden eller intervall med IP-adresser som nyckeln ska valideras mot. Förfrågningar som kommer från din lista över tillåtna domäner bearbetas normalt, medan förfrågningar från domäner utanför listan returnerar ett svar om nekad åtkomst. Det är valfritt att lägga till domänsäkerhet för din API-nyckel, och de nycklar som lämnas i befintligt skick fortsätter fungera. Listan över tillåtna domäner för en nyckel är oberoende av alla andra nycklar, vilket gör att du kan ha olika regler för varje nyckel. Distribuerad orderhantering har inte stöd för inställningar av egenskaper som refereras av domäner.

    - **Kvarhållandeperiod i dagar** – Ange hur länge uppfyllelseplanerna som DOM-körningar genererar behålls i systemet. Batchjobbet **Inställning av borttagningsjobb för DOM-uppfyllelsedata** raderar alla uppfyllelseplaner som är äldre än antalet dagar som anges här.
    - **Avvisningsperiod (i dagar)** – Anger hur lång tid som måste gå innan en avvisad orderrad får tilldelas samma plats.

5. Ange följande värden på fliken **Problemlösare**:

    - **Maximalt antal automatiska uppfyllelseförsök** – Ange hur många gånger DOM-motorn försöker koppla en orderrad till en plats. Om DOM-motorn inte kan koppla en orderrad till en plats på det uppgivna antalet försök flaggas orderraden som ett undantag. Motorn hoppar sedan över den raden framöver tills statusen återställs manuellt.
    - **Radie för lokal butiksregion** – Ange ett värde. Detta fält bestämmer hur platser grupperas och anses vara desamma vad avstånd beträffar. Om du t.ex. väljer **100** anses alla butiker och distributionscenter inom en radie av 100 miles från uppfyllelseadressen vara likvärdig i fråga om avstånd.
    - **Problemlösartyp** – välj ett värde. Två typer av problemlösare medföljer Commerce: **Produktionsproblemlösare** och **Förenklad problemlösare**. **Produktionsproblemlösare** måste väljas för alla maskiner som kör DOM (dvs. alla servrar som ingår i DOMBatch-gruppen). Produktionsproblemlösaren kräver en särskild licensnyckel som normalt licensieras och används i produktionsmiljö. I nyare Nivå 2+-miljöer är Produktionsproblemlösaren redan aktiverad. I andra miljöer måste denna licensnyckel distribueras manuellt. Använd licensnyckeln manuellt på detta sätt:

        1. Öppna biblioteket Gemensamma tillgångar i Microsoft Dynamics Lifecycle Services, välj **Modell** som tillgångstyp och ladda ned filen **DOM-licens**.
        1. Starta Microsoft Internet Information Services-hanteraren (IIS), högerklicka på **AOSServices webbplats** och välj **Utforska**. Utforskaren öppnas i **\<AOS service root\>\\webroot**. Anteckna sökvägen till \<AOS Service root\>, eftersom den anges i nästa steg.
        1. Kopiera konfigurationsfilen i katalogen **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Gå till Headquarters-klienten och öppna sidan **DOM-parametrar**. Välj **Produktionsproblemlösare** i fältet **Problemlösartyp** på fliken **Problemlösare** och bekräfta att inga felmeddelanden visas.

        > [!NOTE]
        > Den förenklade problemlösaren medföljer så att återförsäljare ska kunna testa DOM-funktionen utan att behöva använda den särskilda licensen. Den förenklade problemlösaren bör inte användas i produktionsmiljö.
        >
        > Produktionsproblemlösaren förbättrar prestandan (till exempel antalet order och orderrader som går att hantera under en körning) och konvergens av resultaten (eftersom en orderbatch kanske inte ger det bästa resultatet i vissa scenarier). Regeln för **Partiell order** kräver Produktionsproblemlösaren.

6. Gå tillbaka till **Butik och handel \> Fördelad orderhantering \> Inställningar \> DOM-parametrar**.
7. Tilldela de olika DOM-enheterna de nödvändiga nummerserierna på fliken **Nummerserier**.

    > [!NOTE]
    > Innan någon nummerserie kan tilldelas enheterna måste de anges på sidan **Nummerserier** (**Organisationsadministration \> Nummerserier \> Nummerserier**).

8. Med DOM-funktionen går det att ange olika typer av DOM-regler och organisationen kan konfigurera flera regler beroende på vilka krav verksamheten ställer. DOM-regler går att ange för en grupp med platser eller enskilda platser och för en viss produktkategori, produkt eller variant. Så här skapar du grupperingen av platser som måste användas för DOM-reglerna:

    1. Öppna **Retail och Commerce \> Kanalinställningar \> Uppfyllelsegrupper**.
    2. Välj **Ny** och ange ett nytt namn på och en beskrivning för den nya gruppen.
    3. Välj **Spara**.
    4. Välj **Lägg till rad** om du vill lägga till endast en plats i gruppen. Om du väljer **Lägg till rader** kan du lägga till flera platser.

    > [!NOTE]
    > I Commerce version 10.0.12 och högre måste **möjligheten att ange platser som Leverans- eller Upphämtning-aktiverade i Uppfyllelsegrupp** vara aktiverad på arbetsytan **Funktionshantering**.
    >
    > Funktionen lägger till nya konfigurationer på sidan **Uppfyllelsegrupp** så att du kan definiera om lagerstället kan användas för leverans, eller om kombinationen av lagerställe/butik kan användas för leverans, upphämtning eller både och. 
    >
    > Om du aktiverar funktionen uppdateras alternativen som är tillgängliga för val av plats när du skapar upphämtnings- eller leveransorder i kassan.
    >
    > Om du aktiverar funktionen resulterar det också i uppdaterade sidor i kassan när åtgärderna "leverera alla" eller "leverera valda" har valts.

9. Definiera regler i **Retail och Commerce \> Fördelad orderhantering \> Inställningar \> Hantera regler**. Följande DOM-regler stöds nu:

    - **Regel för minimilager** – Med denna regeltyp kan organisationen sätta av en viss mängd av en produkt för andra ändamål än orderuppfyllande. Organisationen kanske inte vill att DOM ska kunna välja hela lagret som finns i en butik för att uppfylla en order. Den kanske vill reservera en viss mängd produkter för kunder som kommer in i butiken. När denna regeltyp används går det att definiera minimilagret som ska behållas för en produktkategori, en enskild produkt eller en produktvariant per plats eller grupp med platser. Du kan också definiera minimilager genom att använda en kompletterande kategorihierarki. Om en produkt finns i flera kategorier får en kompletterande kategori högst betydelse för alla regler där du kan använda kategorier.
    - **Prioritetsregel för uppfyllelseplats** – Med denna regeltyp kan organisationen ange en hierarki med platser och fastställa prioritetsordningen som DOM-motorn tar hänsyn till när den försöker hitta uppfyllelseplatser för specifika produkter. Det giltiga prioritetsintervallet är 1 till 10, där 1 är högsta prioritet och 10 är lägsta prioritet. Platser med högre prioritet beaktas före platser med lägre prioritet. Om regeln definieras som en fast begränsning kopplas order endast till platser för vilka prioriteter har angetts. DOM prioriterar leveransorder helt och hållet från en plats. Om en hel order och dess rader inte är tillgängliga på en plats som har prioritet 1, försöker DOM uppfylla den från en plats som har prioritet 2.
    - **Regel för partiell order** – I Retail version 10.0.5 har parametern **Uppfyll order från enbart en plats** ändrats till **Maximalt antal uppfyllelseplatser**. Med den gamla parametern kunde användare konfigurera om ordern skulle uppfyllas från en enda plats eller från så många platser som möjligt. Med den nya parametern kan användarna ange om uppfyllelsen ska ske från en bestämd uppsättning med platser (högst fem) eller från så många platser som möjligt. För alla alternativ utom uppfyllelse från en enda plats delar DOM upp raden, eftersom orderbearbetningen sker per rad. Den här regeln fungerar bara med Produktionsproblemlösaren.
    - **Platsregel för offline-uppfyllelse** – Med denna regel kan organisationen ange att en plats eller en grupp med platser är offline eller inte tillgängliga för DOM, så att order inte kan tilldelas dessa platser för uppfyllelse.
    - **Regel för högsta antal avvisningar** – Med denna regel kan organisationen ange ett tröskelvärde för avvisningar. När tröskelvärdet har nåtts märker DOM-processorn en order eller orderrad som ett undantag och utesluter den från ytterligare behandling. För att säkerställa prestandan ser DOM inte på historiken över avvisanden. 

        När orderrader har tilldelats en plats kan platsen avvisa en tilldelad orderrad eftersom den kanske inte kan uppfylla den raden av någon anledning. Avvisade rader märks som undantag och återförs till poolen för bearbetning i nästa körning. Under nästa körning försöker DOM tilldela en annan plats den avvisade raden. Den nya platsen kan också avvisa den tilldelade orderraden. Denna tilldelnings- och avvisningscykel kan löpa flera varv. När antalet avvisningar når upp till det angivna tröskelvärdet märker DOM orderraden som ett permanent undantag och plockar inte raden för tilldelning igen. DOM tar bara upp orderraden för tilldelningen igen om en användare återställer dess status manuellt.

    - **Regel för längsta avstånd** – Med denna regel kan organisationen ange det maximala avstånd som en plats eller grupp med platser får finnas på för att uppfylla ordern. Om överlappande maximala avståndsregler har angetts för en plats använder DOM det minsta maximala avstånd som har angetts för den platsen.
    - **Regel för maximalt antal order** – Med denna regel kan organisationen ange det maximala antalet order som en plats eller grupp med platser kan bearbeta. Under optimeringsprocessen tar systemet hänsyn till order som inte har levererats från dessa platser. Den här kontrollen utförs för alla profiler. Om ett överlappande maximalt antal order har definierats för alla profiler för samma plats beaktar systemet därför det maximala antalet order som har definierats för alla profiler. 

    Här följer några gemensamma attribut som går att ange för de föregående regeltyperna:

    - **Startdatum** och **Slutdatum** – Du kan använda dessa fält för att göra så att reglerna gäller mellan vissa datum.
    - **Inaktiverad** – Bara de regler som har värdet **Nej** i detta fält tas med i en DOM-körning.
    - **Fast begränsning** – Det går att ange en regel som en fast begränsning eller inte. Varje DOM-körning genomlöper två iterationer. Under det första varvet behandlas varje regel som en regel med fast begränsning, oavsett fältinställningen. Med andra ord tillämpas alla regler. Det enda undantaget är regeln **Platsprioritet**. Under den andra iterationen tas regler som inte hade angetts som fasta begränsningsregler bort, och order eller orderrader som inte hade tilldelats platser när alla reglerna hade tillämpats tilldelas platser.

10. Uppfyllelseprofiler används för att gruppera ett antal regler, juridiska personer, ursprung till försäljningsorder och leveranssätt. Varje DOM-körning gäller en specifik uppfyllelseprofil. På så sätt kan organisationen ange och köra vissa regler för ett antal juridiska personer på order med specifika försäljningsorderursprung och leveranssätt. Om olika regler måste köras för olika typer av försäljningsorderursprung eller leveranssätt kan uppfyllelseprofiler alltså definieras enligt detta. Så här ställs uppfyllelseprofiler in:  

    1. Öppna **Retail och Commerce \> Fördelad orderhantering \> Inställningar \> Uppfyllelseprofiler**.
    2. Välj **Ny**.
    3. Ange värden i fälten **Profil** och **Beskrivning**.
    4. Ange värdet på alternativet **Tillämpa resultat automatiskt**. Om du väljer **Ja** tillämpas resultaten från DOM-körningen för profilen automatiskt på försäljningsorderraderna. Om du väljer **Nej** går resultaten endast att se i uppfyllelseplanen. De används inte på försäljningsorderraderna.
    5. Om du vill att DOM-profilen ska köras för order med samtliga försäljningsorderursprung – inklusive order där försäljningsorderursprunget är odefinierat – ska alternativet **Bearbeta order med tomt försäljningsursprung** ha värdet **Ja**. Om du vill köra profilen endast för vissa försäljningsorderursprung går de att definiera på sidan **Försäljningsursprung**. Detta förklaras senare.

        > [!NOTE]
        > I Commerce version 10.0.12 och senare måste funktionen **Möjlighet att ange uppfyllelsegrupp för en uppfyllelseprofil** vara aktiverad på arbetsytan **Funktionshantering**. Med hjälp av den här funktionen kan du ange en lista över lagerställen som DOM bör beakta när optimering körs med en uppfyllelseprofil. Om listan med lagerställen inte anges söker DOM i alla lagerställen i juridiska personer som har definierats i profilen.
        >
        > Den här funktionen lägger till en ny konfiguration på sidan **Uppfyllelseprofil** som kan associeras med en enskild uppfyllelsegrupp. 
        >
        > Om du väljer uppfyllelsegruppen körs DOM-reglerna för den uppfyllelseprofilen effektivt mot de "leverans"-lager som ingår i uppfyllelsegruppen. 
        > 
        > Om du vill använda den här funktionen effektivt måste du kontrollera att det finns en uppfyllelsegrupp som innehåller alla leveranslager och sedan associera den uppfyllelsegruppen med uppfyllelseprofilen.

    6. Välj **Lägg till** på snabbfliken **Juridiska personer** och välj sedan en juridisk person.
    7. Välj **Lägg till** på snabbfliken **Regler** och välj sedan den regel som ska länkas till profilen.
    8. Upprepa de föregående två stegen tills alla regler som ska vara med är kopplade till profilen.
    9. Välj **Spara**.
    10. Välj **Leveranssätt** på fliken **Inställningar** i åtgärdsrutan.
    11. Välj **Nytt** på sidan **Leveranssätt**.
    12. Välj den juridiska personen i fältet **Företag**. Listan med företag är begränsad till de juridiska personerna som lades till tidigare.
    13. Ange leveranssättet som ska kopplas till denna profil i fältet **Leveranssätt**. Ett leveranssätt går inte att koppla till flera aktiva profiler.
    14. Upprepa de föregående två stegen tills alla leveranssätt som ska vara med är kopplade till profilen.
    15. Stäng sidan **Leveranssätt**.
    16. Välj **Försäljningsorderursprung** på fliken **Inställningar** i åtgärdsrutan.
    17. Välj **Nytt** på sidan **Försäljningsursprung**.
    18. Välj den juridiska personen i fältet **Företag**. Listan med företag är begränsad till de juridiska personerna som lades till tidigare.
    19. Ange försäljningsursprunget som ska kopplas till denna profil i fältet **Försäljningsursprung**. Ett försäljningsursprung går inte att koppla till flera aktiva profiler.
    20. Upprepa de föregående två stegen tills alla försäljningsursprung som ska vara med är kopplade till profilen.
    21. Stäng sidan **Försäljningsursprung**.
    22. Ge alternativet **Aktivera profil** värdet **Ja**. Ett varningsmeddelande visas om det finns några fel i inställningarna.

## <a name="dom-processing"></a>DOM-bearbetning

DOM körs bara i batchjobb. Gör på följande vis för att konfigurera batchjobbet för DOM-körningar.

1. Öppna **Retail och Commerce \> Fördelad orderhantering \> Batchbearbetning \> Inställning för DOM-bearbetarjobb**.
1. Välj en profil som DOM måste köras för i fältet **Uppfyllelseprofil** på snabbfliken **Parametrar**.
1. Välj en konfigurerad batchgrupp i fältet **Batchgrupp** på snabbfliken **Kör i bakgrunden**.
1. Ange batchjobbets namn i fältet **Uppgiftsbeskrivning**.
1. Välj **Upprepning** och ange hur ofta batchjobbet ska upprepas.
1. Välj **OK**.

Vid bearbetningen beaktar DOM ordern och orderraderna enligt beskrivningen här:

- Orderrader som uppfyller kriterierna för försäljningsorderursprung, leveranssätt och juridisk person enligt inställningen i DOM-profilen och som dessutom uppfyller något av dessa kriterier:

    - De skapas från handelskanaler.
    - De har aldrig kopplats av DOM.
    - De har kopplats av DOM tidigare men märkts som undantag och är under det maximala tröskelvärdet för försök.
    - Leveranssättet är inte upphämtning eller elektronisk leverans.
    - De är inte märkta för leverans.
    - De är inte manuellt exkluderade.

- Order som inte är spärrade

När DOM har tillämpat reglerna, lagerbegränsningarna och optimeringarna väljer DOM platsen som är närmast kundens leveransadress. DOM konverterar adresser av typen **Leverans** till latitud- och longitudvärden. Sedan konverteras leveransadressen i försäljningsordern till latitud- och longitudvärden, och adressens latitud- och longitudvärden uppdateras för framtida användning. DOM använder Bing-kartor för att fastställa latitud- och longitudvärdena utifrån information om adress, ort och postnummer.

DOM använder API:et för Bing-kartor för att beräkna flyg- eller körsträcka, beroende på inställningarna. Därefter används den här informationen för att fastställa leveranskostnaden. Optimeringsmodellen prioriterar att hela ordern uppfylls från en enda plats. Även om en del av ordern finns tillgänglig på samma ort eller postnummer har modellen optimerats för att minska antalet leveranser. 

DOM söker efter tillgängligt lager genom att visa lagerbehållningen i lagerställe V2-entiteter. Under varje batchkörning delar DOM upp order i batcher beroende på parametervärdet **DOM-processor** för uppgifter som har definierats i profilen. Standardvärdet för parametern är **2 000**. Om exempelvis 10 000 orderrader har optimerats i en körning och parametern **DOM-processor** har standardvärdet **2 000**, skapar DOM fem batcher som bearbetas samtidigt. Sedan hämtas uppfyllelseplaner från optimeraren och används på raden. Om orderraden måste delas mellan två platser ser DOM till att priser och skatter fördelas på lämpligt sätt mellan raderna.

![Villkor för försäljningsorder.](./media/ordercriteria.png "Villkor för försäljningsorder")

## <a name="results-of-dom-runs"></a>Resultat av DOM-körningar

Om uppfyllelseprofilen är inställd på **Tillämpa automatiskt** tillämpas resultaten av körningen automatiskt på försäljningsorderraderna. Uppfyllelseplanen går att se separat. Men om uppfyllelseprofilen inte är inställd på **Tillämpa automatiskt** går resultatet av körningen bara att se från uppfyllelseplanvyn. 

Gör på följande vis om du vill se alla uppfyllelseplaner som genereras.

1. Öppna **Retail och Commerce \> Fördelad orderhantering \> Fördelad orderhantering**.
2. Välj rutan **Uppfyllelseplaner** på arbetsytan **Fördelad orderhantering**.
3. Välj id:t för den aktuella orderuppfyllelseplanen för att visa uppfyllelseplanen.

    Orderinformationsavsnittet i uppfyllelseplanen visar de ursprungliga försäljningsorderraderna som ingick i körningen. Förutom de vanliga försäljningsorderradsfälten innehåller orderinformationsavsnittet även följande tre DOM-relaterade fält:

    - **Uppfyllelsetyp** – Detta fält visar om försäljningsorderraden är helt kopplad, partiellt kopplad eller inte kopplad alls till en plats.
    - **Dela** – Detta fält visar om en försäljningsorderrad har delats och kopplats till olika platser.
    - **Antal uppfyllelseplatser** – Detta fält visar hur många uppfyllelserader som skapades för en försäljningsorderrad (baserat på antalet platser som den ursprungliga försäljningsorderraden har kopplats till).

    Avsnittet med information om orderuppfyllelsen visar tilldelningen av de ursprungliga försäljningsorderraderna till olika platser tillsammans med kvantiteter.

## <a name="order-line-actions-and-statuses"></a>Åtgärder och statusar för orderrader

Nedan beskrivs inställningarna på orderraden. Öppna orderraden från **Retail och Commerce \> Kunder \> Alla försäljningsorder**.

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

1. Öppna **Retail och Commerce \> Fördelad orderhantering \> Batchbearbetning \> Inställning av borttagningsjobb för DOM-uppfyllelsedata**. 
1. Välj en konfigurerad batchgrupp i fältet **Batchgrupp**.
1. Välj **Upprepning** och ange hur ofta batchjobbet ska upprepas.
1. Välj **OK**.

## <a name="more-information"></a>Mer information

Här är några saker att tänka på när du använder DOM-funktionen:

- För tillfället granskar DOM bara order som skapas från handelskanaler. Försäljningsorder identifieras som butiksförsäljningsorder när alternativet **Commerce-försäljning** har värdet **Ja**.
- Microsoft har inte testat DOM med funktioner för avancerad lagerstyrning. Därför måste kunder och partner noga bedöma om DOM är kompatibelt med de funktioner och processer för avancerad lagerstyrning som är relevanta för dem. Med avancerad lagerstyrning kan man använda konfigurerbara dimensioner, till exempel lagerstatus, som inte ger någon exakt uppfattning om tillgängligt lager. DOM har en utökningsbar metod för att ange tillgängligt lager för implementeringar som används för avancerad lagerstyrning. Den kan användas för att arbeta med anpassade värden för lagerstatus och andra dimensioner.

    Utökningsbarheten i DOM är begränsad eftersom optimeringen sker i den inbyggda MIP-modellen som tar hänsyn till optimeringen och dess begränsningar. Det finns redan flera utökningsbara punkter för att ställa in optimering av lager och efterbearbetning. DOM-profiler kan skilja sig åt när det gäller försäljningsursprung och leveranssätt. Försäljningsorderursprunget kan anges vid orderinmatningen, och olika optimeringsstrategier kan användas baserat på dessa värden. Med DOM kan anpassade jobb skapas som tar DOM-processoruppgiften som indata och gör det möjligt att skicka profilen som en parameter. Därmed kan en optimering köras efter en annan för olika affärsscenarier.

- DOM är bara tillgängligt i molnversionen av Commerce. Det stöds inte i lokala installationer.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
