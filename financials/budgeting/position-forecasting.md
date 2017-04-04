---
title: Befattningsprognos
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 1bc458d58834be1e2e9b602619f76424b3bb449b
ms.lasthandoff: 03/31/2017


---

# <a name="position-forecasting"></a>Befattningsprognos



Utgifter relateradr till att kompensera för arbetare är ofta en stor del av ett företags kostnader. Med befattningsprognoser kan du planera dessa utgifter och inkludera dem i planeringen av budgetar.

## <a name="position-forecasting-in-budget-planning"></a>Befattningsprognos i budgetplanering

[![Grafiska upp](./media/graphic-top.png)](./media/graphic-top.png) 

Position prognoser använder tre huvudkomponenterna för korrekt budgetbelopp för utgifter för befattningen. Beloppen kan sedan tas med på en budgetplan för budgetberäkningar. 

Den primära komponenten är **prognostisera befattning**, som representerar alla kostnadsdata som hör till en viss befattning. Du kan skapa flera versioner av en prognosbefattning genom att tilldela ett annat budgetplanscenario till varje version. Flera versioner tillåts för iterativ budgetering och gör att du kan jämföra ”vad händer om"-situationer. Varje prognosbefattning har en motsvarande befattning i Personal.

Ett **budgetkostnadselement** är en inställningskomponent som representerar en specifik kostnad som är kopplad till en befattning, till exempel grundlön, arbetsgivarbetald sjukförsäkring, mobiltelefobidrag, osv. Ett budgetkostnadselement omfattar huvudkontot som används för kostnaden och alternativ för beräkning. Varje budgetkostnadselement kan tilldelas till flera prognosbefattningar. 

En **kompensationsgrupp** är en valfri inställningskomponent som används för att tillämpa en uppsättning budgetkostnadselement och löneberäkningar på befattningar som har liknande lönegenskaper. En kompensationsgrupp kan innehålla ett kompensationsrutnät med kostnader. När gruppen tilldelas en prognosbefattning, kan en nivå och ett steg i rutnätet tilldela prognosbefattningens inkomster. Uppsättningen av kostnadselement läggs till automatiskt.

### <a name="position-forecasting-processes"></a>Befattningsprognosprocesser

[![graphic1b](./media/graphic1b.png)](./media/graphic1b.png) 

I en typisk process position prognoser skapar du först installationskomponenterna (kostnadselement budget och kompensation grupper). Prognosbefattningar genereras sedan, baserat på befintliga befattningar. Du kan sedan göra justeringar. Du kan till exempel lägga till eller avsluta befattningar, ändra ändra lönesatser och förmånskostnader och lägga till löneökningar. Du kan skapa flera versioner av en prognosbefattning för att underlätta jämmförelser mellan olika budgetscenarier. Därefter kan du inkludera budgettransaktioner i prognosbefattningsplaner och sammanföra i kostnaderna från prognosbefattningarna, som den här planen.

Du kan skapa ytterligare prognosbefattningsversioner, som budgetplaner revideras. Dessa nya versioner innehåller bas för revideringarna.

## <a name="position-forecasting-setup"></a>Befattningsprognosinställning
[![graphic2](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Budgetkostnadselement

Är kostnader för budget för definiering kostnadsdetaljer en prognos för befattningen. Dessa uppgifter omfattar den typ av kostnader, hur kostnaden beräknas, och om kostnaden fördelas till flera data, när prognosbefattningen ingår i en budgetrapport plan. 

Specifika här fältet definierar beteendet för det budgeterade kostnader elementet. Varje element budgeterade kostnader tilldelas en kostnadsredovisning av **Tjäna**typen för budget **Förmån****Skatter**, eller **Annat**. Budgetkostnadstyperna är främst avsedd för att beräkna summor. **Prognosbefattningsåsidosättning** värdet anger om belopp på elementet kan ändras på prognosbefattningen. **Allokeringsmetod** Fältet används när en prognos, befattning anges till en budgetrapport plan. Du kan dela upp kostnadsbeloppet till separata budgettransaktioner planrader, som har olika datum, på ett månatligt som sker kvartalsvis, vecka eller som inträffar varannan vecka kvartal. Genom att välja ett startdatum, kostnaden som du tilldelar ett enskilt belopp på startdatumet som anges på prognosbefattningen. 

Beräkningen av budgeterade kostnader elementets kostnadsbelopp använder giltighetsdatum för att aktivera samma kostnadsredovisning det element som ska användas i olika perioder. En enskild huvudkonto tilldelas i varje period, tillsammans med en procentsats eller ett årligt belopp som anger kostnadsbeloppet. Ett element budgeterade kostnader kan använda en procentsats för kostnadsredovisning andra element eller ett årligt belopp, men inte båda. Du kan även ange en årlig gräns. 

Om det bli elementet baseras på en procentsats, måste du ange de budgeterade kostnader de element som används som grund för beräkningen.

**Example** 

Jodis organisation tillhandahåller en utbildning justering med 5 procent av en medarbetares grundlön. Jodi vill skapa ett element budgeterade kostnader för denna kostnadsredovisning. Hon skapar ett nytt element budgeterade kostnader och tilldelar **Förmån** budgeten kostnadsredovisning typ.

Jodi inte vill att chefer ska ändra beloppet av förmånen. Därför markerar hon **Tillåt aktivering inte ändringar** i **Prognostisera befattningåsidosätt** fältet. Organisationen vill att den här kostnad ska fördelas jämnt till varje månad. Därför ska Jodi **Kvartalsvis** i **Allokeringsmetod** fältet. 

Därefter lägger till anger anger Jodi en beräkningsrad kostnader, datum och en huvudkonto och procent **5.00** . Hennes organisation har ett lock av $5,000 per år för den här förmån. Därför skapar Jodi det belopp som den årliga gränsen. 

Slutligen lägger till Jodi alla kostnader för att tjäna som används för grundlön som beräkningsbaser. Hennes budgeterade kostnader element är nu går det att användas.

### <a name="compensation-groups"></a>Kompensationsgrupper

kompensationsgrupper kan användas för att gruppprognosbefattningen som har liknande kompensationattribut. De kan också användas för att definiera en prognos befattnings resultat och årliga ökningar och tilldela en uppsättning att för Vanliga budgeten. 

En grundläggande funktionerna för kompensationsgrupper är att tilldela en uppsättning kostnader för budgeten till en prognos befattning. Därför kan användas för att kompensationsgrupper lägger till allmänna kostnader, till exempel förmånplaner och moms. En chef, som skapar en prognos befattning, måste inte vara kostnadsredovisning alla element som måste läggas till. I stället de kostnader kan läggas till element, när kompensationsgruppen har valts. Elementen läggas till kompensationsgruppen som ställs in på fliken **Kostnadsredovisning element för budget** . 

kompensationsgrupper kan också bestämma förtjänsttakterna en prognos för befattningen. Du ställer in en grupp för att använda antingen en timlön kvartal eller en årslönbas för att beräkna prognosbefattningresultat. På **Kompensationtaktregister** fliken bestämmer en kompensationsrutnät resultatet av kostnader som anges till en prognos befattning som baseras på en nivå och tilldelat steg. Dessa raster kan baseras på befintliga kompensationsrutnät i Personal. Du kan också skapa nya kompensationsrutnät för budgettransaktioner planering. 

De giltiga data och förfallodatum på kompensationtaktregistren kan du ändra kostnader för det datum. Den här funktionen är praktiskt, när en enhet köpslå har förhandlat för en styrelseövergripande ökning i mitten av en budgetrapport cykel. I detta fall ändra förfallodatumet för den befintliga tabellen till dagen före ändring av och lägga till en ny tabell som börjar med det nya datumet. När du skapar en ny tabell, klickar du på **Skapa nytt kompensationsrutnät från ett befintligt rutnät**, kan du välja en befintlig tabell från Personal. I taktregistret, som skapas, **Massändra** kan väljaren du kan tillämpa en procentsats, eller alla det plana beloppet ökning eller minskning till att utvärdera i rutnätet. 

**Öka tidsplan** och **Datum för ökning** fält på kompensationsgruppen, används när du måste skapa lönökningar, eftersom befattningar går från ett steg i nästa. En årlig lönökning är typiskt ett scenario. Ökningtidsplanen bestämmer om befattningens jubileumsdatum, eller ett enskilt vanligtvis datumet används för stegökningen. Ökningtidsplanen gäller för alla prognosbefattningar i kompensationsgruppen. 

Det kostnader för elementet förtjänsten, som valts på kompensationsgruppen, används, när du skapar resultat för prognosbefattningarna i gruppen, inklusive deras grundlön och eventuella kliver taget. **Kompensation fasta plan** Fältet kompensationsgruppen länkar till en fast kompensationsplan i Personal. Den länk kan tilldela en arbetares information om fast kompensation till en prognos befattning och kan därför göra budgettransaktioner planera exakt. Kom ihåg att strukturen för kompensationsrutnätet (nivåerna och stegen) för kompensationsgruppen bör matcha strukturen för fasta kompensationsplanen. I annat fall kan systemet inte korrekt och länka kompensationsgruppen fasta kompensationsplanen.

## <a name="creating-forecast-positions"></a>Skapa prognosbefattningar
[![graphic3](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Skapa befattningar en befintlig prognos för befattningar

Du kan skapa prognosbefattningar för den mest exakta budgetplanering, genom att använda information från befintliga positioner i Microsoft Dynamics 365 för transaktioner, oavsett om befattningen är för närvarande fylld eller ofylld. 

**Lägga till befintliga befattningar** Funktionen visas alla befattningar för en organisation. Genom att** Fr o m** ange datum, kan du ändra listan med befattningar, så att den innehåller befattningarna som hittats vid ett datum i det förflutna, eller mer allmän, i framtiden (till exempel, början på nästa budgettransaktioner cykeln). Välj en budgetrapport planeringsprocess och budgetering planscenariot, valda befattningar i listan och klicka på om **OK** du vill skapa prognosbefattningar för de valda befattningar. Observera att du kan bara skapa en förväntad befattning för varje befintlig position i en budgetrapport och planeringsprocess situationer. Du kan dock skapa ytterligare versioner, genom att tilldela olika budgettransaktioner planscenarion. 

Om kostnader för budget har tilldelats till befattningen i Personal, tilldelas använder de här kostnadsredovisning element även för prognosbefattningen och standardinställningbeloppen. **Tilldelad arbetare** Fältet på prognosbefattningen anges till namnet på arbetare som hör till befattningen, om en anställd tilldelas. Det här fältet är ett enskilt textfält. Ingen direkt länk skapas. 

Om ett element budgeterade kostnader, markeras tilldelas det årliga avskrivningsbeloppet för fast kompensation till prognosbefattningen, genom att använda kostnadsredovisning det valda elementet, förutsatt att den tilldelade arbetare har en fast kompensationsplan. Om arbetare inte har en fast kompplan, eller om ingen anställd har tilldelats, används standardinställningbeloppet budgeten för kostnadsredovisning elementet. 

När **Tilldela en grupp kompensation** väljaren anges till **Ja**, om arbetare, som hör till befattningen, har en fast kompensationsplan som är kopplad till en grupp (kompensation som tidigare beskrivits), nivå, och steget från arbetare tilldelas prognosbefattningen, tillsammans med kompensationsgruppen. Det kostnader för elementet resultatbudgeten från kompensationsgruppen läggas till prognosbefattningen, och kostnaden på den nivå och steget från kompensationsgruppen används. 

Inställningen av **Tilldela en grupp kompensation** väljaren åsidosätter **Budgetering den kostnadskalkylerade elementtilldelningen** inställningen. De två inställningarna kan användas samtidigt. 

[![graphic4](./media/graphic4.png)](./media/graphic4.png) 

Ett annat alternativ är att tilldela en årsdag. Välj datum (modifierat startdatum, arbetarestartdatum, anställningstartdatum eller tjänsteålderdatum) från den tilldelade arbetare anges Nästa som prognosbefattningens jubileumsdatum och används för information, och när lönökningar genereras.

### <a name="creating-new-forecast-positions"></a>Skapa nya prognosbefattningar

Du kan skapa nya sätt prognosplanering befattningar på två sätt: genom att kopiera en befintlig prognosmodell befattning och genom att skapa en ny prognosbefattning helt. 

När en prognos, befattning har valt **Kopiera den valda prognosbefattningen** att skapa en ny prognosbefattning som har ett prognos för stat. **Föreslaget** Det det prognostiserade befattningen har samma alla data som prognosbefattningen, som använder, utom den tilldelade arbetare och eventuella anteckningar på de budgeterade kostnader elementen. Observera att en motsvarande ny befattning skapas också i Personal. Den befattning har en beskrivning av **Skapat av prognos**. 

Du kan också skapa en ny prognosbefattning helt. Markera ett befintligt jobb, och även välja det budgeterade och budgetering planscenariot planeringsprocessen. Du kan sedan lägga till andra uppgifter som du vill lägga till. En gång till skapas en ny befattning i personal samtidigt.

## <a name="working-with-forecast-positions"></a>Arbeta med prognosbefattningar
[![graphic5](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Flera versioner av en prognosbefattning

Du kan ändra prognosbefattningar antingen att tillämpa och ändringar för budgetjournalen cykeln eller till modellen föreslagna ändringar. En är ofta du vill skapa en jämföra som anges i prognosbefattningar, skapa kopior av de prognosbefattningar och sedan använda kopiorna för modellering andra uppsättningar med ändringar. Kopiorna tilldelas till ett annat budgettransaktioner planscenario, men tills minst ändringar görs, annars är identiska med prognosbefattningarna de att kopieras. Originalen och kopiorna delar samma positionen i Personal. 

**Kopiera till scenariot**-funktionen innehåller den här funktionen. Observera att varje personalresursbefattning kan bara ha en förväntad position i varje budget planscenario.

### <a name="modifying-forecast-positions"></a>Ändra prognosbefattningar

Ändringar som görs för att beräkna befattningar begränsas till de prognosbefattningar. Ändringarna påverkar inte befattningposterna i Personal. De flesta ändringar begränsas också till prognosbefattningen som redigeras. Med andra ord budgeterar ändringarna är specifika för det budgeterade och planeringsprocessen planscenariot som betalas ut. Undantagen är ändringar av fält som delas mellan processer för befattningen och situationer. Dessa fält innehåller fält på fliken **Allmänt** och fliken **Ekonomisk dimension**. När dessa fält ändras, gäller de nya värden till för planering budget för befattningen i alla scenarierna. Därför dessa fält kan du snabbt uppdatera alla versioner.

#### <a name="budget-cost-elements"></a>Budgetkostnadselement

Ger kostnader för budget i huvudmenyn informationen för budgettransaktioner planer: budgetbeloppet och huvudkontot. Budgetbeloppet är det belopp som skickas till den här planen, när en prognos befattning är inkluderade i en plan. Budgetbeloppet beräknas och kan inte ändras direkt. Denna kvantitet är antingen årligt belopp eller en procentsats för beräkning av årligt beloppets baselementen (som definierats i inställningarna för kostnadsredovisning budgeten elementet). Beloppet faktorer sedan efter antal dagar i elementets datumintervall (startdatum till slutdatumet) och även av värdet ( **Heltid motsvarighet** FTE )för prognosbefattningen. 

Om till exempel en budgetrapport kostnadsredovisning beräknas från elementrad Januari 1, 2017, till juni 30, 2017, som har ett årligt belopp på 100,000 och ett av FTE-värde, som × **0.50** = 24,794.52 för 100,000 × 181 dagar (÷ 365 dagar). 

De budgeterade kostnader elementraderna måste räknas om när FTE-värdet, ändras på prognosbefattningen. Raderna måste också beräknas om, aktiveringen när datum, eller avyttringsdatum ändras. Ändringar av dessa data kan orsaka en uppdatering av budgettransaktioner kostnadsredovisning elementets start - och slutdatum, som måste ligga inom prognosbefattningens data. När omberäkningen krävs, **Beräkna om** blir knappen tillgängliga, och ”kräver ett beräknings" meddelande visas. Omberäkningen krävs, även om du lägger till eller ta bort en budget - element.

**Example** 

Organisationen har tagit med två alternativ för att minska kostnaden för en revisor position. En väljare ska fylla i befattningdelen av sätt genom året. Övrig väljaren är att ändra befattningen till halvtid för hela året. Golvspiken har skapat en prognos befattning för den befintliga revisorbefattningen i ett scenario jämföra. Han kopierar den här baslinjeprognosbefattning till scenario A, Lista avyttringsdatumet maj till 31 och omberäkna. Golvspiken kopierar till baslinjeprognosbefattningen scenariot B, ändras till FTE-värdet och omberäkna **0.50**. Golvspiken har nu tre versioner, som vart och ett har kostnad summor, som stämmer överens med hans väljare.

#### <a name="assigning-a-compensation-group"></a>Tilldela en kompensationsgrupp

När du tilldelar en grupp kompensation först till en prognos befattning, anges kostnader till de element som standardinställningbudgeten från kompensationsgruppen. Om kostnadsredovisning element redan tilldelats prognosbefattningen, förblir den kostnadskalkylerade element. Om en grupp kompensation redan har tilldelats och är ändrad, tas ersättas de befintliga budgettransaktioner kostnadsredovisning elementen bort och uppsättning av från kompensationsgruppen. 

När du väljer en kompensationsnivå och ett steg, anges i en kostnadsredovisning för resultatbudget (enligt definitionen i kompensationsgruppen). Det årliga belopp beräknas genom att använda takten i den valda nivån och steget och den årliga timmar i kompensationsgruppen (eller, för årslön Den genererade lönen, hela beloppet i till nästa steg). En gång till faktorer det här beloppet av kostnader elementradens datumintervall och prognosbefattningens värdet för FTE.

#### <a name="generating-increases"></a>Generera ökningar

Årliga manuellt (ett per kalenderår) kan skapas automatiskt för prognosbefattningar som har steg-baserad en tilldelad kompensationsgrupp. Klicka **Generera manuellt** om du lägger till ett element för kostnadsredovisning resultatbudget vid nästa högsta steg. Startdatumet för den kostnadskalkylerade elementet för den nya resultatbudgeten är det schemalagda ökningdatumet som visas på prognosbefattningen. Datumet anges i kompensationsgruppen på ett av två sätt. Om kompensationsgruppens schemat för ökning anges till, **Vanligt datum**anges på datumet för ökning kompensationsgruppen. Om ökningtidsplanen anges till, används **Jubileumsdatum**jubileumsdatumfältet på prognosbefattningen, och det budgeterade cykeln levererar året. Om det finns flera kalenderår i en budgetrapport cykel, läggas till flera taget. 

Slutdatum för den kostnadskalkylerade elementet för den aktuella resultatbudgeten uppdateras med dagen före ökningdatumet. Omberäkningprocessen används automatiskt när taget, genereras. Därför måste du omberäkna inte manuellt. 

Om du klickar **Generera manuellt** på en annan gång, lägger till processen körs igen men inte fler poster. Endast en ökning per kalenderår skapas.

#### <a name="changes-from-other-pages"></a>Ändringar från andra sidor

Uppdateringar av prognosbefattningar kan också komma från andra områden, till exempel budgeten kostnadsredovisning elementet och sidorna för kompensation gruppinställningar. Du kan också ändra prognosbefattningar, genom massupdatering. 

Det finns två alternativ på den **Budget kostnadsfaktorn** installationssida: **förse befattningar** och **uppdatera befattningar**. **Lägg till befattningar**-alternativet lägger till budgetkostnadselementet till markerade prognosbefattningar. Om element redan har tilldelats en prognosbefattning kommer den prognosbefattningen hoppas över. **Uppdatera befattningar**-alternativet använder de aktuella värden (huvudkontot, procentvärde, årligt belopp, och så vidare) till de valda prognosbefattningarna. 

Varje process har en liknande sida där du kan välja prognosbefattningar. **Lägga till befattningar** På den här sidan visas alla prognosbefattningar som är tillgängliga för urval, medan sidan **Uppdatera befattningar** visas endast de prognosbefattningar som redan har den tilldelade budgeterade kostnader elementet. (Därför den **uppdatera befattningar** sidan kan du ta reda på vilka prognosbehov befattningar redan kostnadsfaktorn kopplade.) Du kan flytta prognosbefattningar från en övre rutnätet till ett lägre rutnät för att inkludera dem i uppdateringen. 

Observera att **Ändringsdata** funktionen ändras direkt på **Kostnadsberäkning** fliken budgettransaktioner kostnadsredovisning elementets start - och slutdatum på prognosbefattningarna. Inga valväljare är tillgängliga. 

På **kompensationsgrupp** sidan **Uppdateringbefattningtakter** använder funktionen de aktuella takterna för kompensation taktregistret till prognosbefattningar som tilldelats gruppen. Takterna uppdateras, och rader för merkostnadelement läggas till för alla nya taktregisterrader (baserat på datum.) Om uppdateras de budgeterade kostnader element och ökningdata inte. Du kan välja vilka budgetjournalen planeringsprocessen och budgeterade planscenariot som ska uppdateras. Därför kan du uppdatera ett scenario men lämna andra situationer oförändrade för jämförelse. 

Genom att markera prognostiserade befattningar och klicka **Massuppdatering**sedan på kan du lägga till eller ändra mer än en förväntad befattning på samma tid. Flera alternativ är tillgängliga. En väljare på **Ekonomiska dimensioner** fliken varierar lite från andra är relaterade och för att budgetera kostnader element. Du kan lägga till kostnadsredovisningen för budget, genom att **Budgetstandardvärden** ange väljaren till **Ja**. Om inga budgeterade kostnader element är markerad, men **Budgetstandardvärden** anges till **Ja**kostnadsredovisningen, budgeterar alla element som tilldelats för närvarande tas bort. 

Omberäkningprocessen används automatiskt i en prognosbefattning som har ändrats.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Komma prognostiserade med befattningar till budget planer

[![graphic6](./media/graphic6-1024x327.png)](./media/graphic6.png)

Skapa och ändra prognosbefattningar syftar läggas till budgetplaner, så att inkludera budgetplaner mest exakta budgetbeloppen. Det finns två sätt att lägga till befattningar prognostiserade budgetering planer. Du kan använda antingen en utvecklingsprocess eller en valprocess på den här planen.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Generera budgetplansrader från prognosbefattningar

**Generera budgetjournalen planen från prognosbefattningar** Funktionen skapar eller uppdateringbudgetplaner, så att de har budgetbeloppen, och FTE räknar från prognosbefattningar. Budgetbeloppen från prognosbefattningen blir de här planradbeloppen och samlas in efter värden för ekonomisk dimension och giltighetsdatum. Under genereringen tilldelar källaprognosbefattningen till det budgeterade planraden. Om du vill visa befattningen kan du antingen lägga till prognosbefattningen som en rad i budgetjournalen planlayouten eller använda frågan. **Budgetplansrader** Ange väljaren till du vill hoppa över den**Inkludera positionen i budgettransaktioner planrad** arbetsuppgift **Nej**. 

Du kan välja ett här scenariot för plan FTE om du vill inkludera antalet heltidsanställda i den här planen. Du kan bara välja sådana situationer av kvantitettypen som ingår i layouten för målbudgetplanen. När du väljer, är ett FTE-scenario, måste du även ange en FTE-huvudkonto. Detta konto används för att skapa den kvantitet budget plan linjer. 

Den här planeringsprocessen och budgeten planscenariot, som väljs i källan, och processen scenariot avgör om planering för målscenariobudget. Eftersom dessa attribut tilldelas prognosbefattningar, måste de in synkroniseras med den här planen. Därför kan de inte redigeras på destinationen. 

Vad gäller andra utvecklingsprocesser, är tre väljare tillgängliga:

-   **Skapa en ny budgetplan** – Skapa en ny plan som har attributen, som väljs i **Mål** avsnittet.
-   **Återbetala det befintliga budgettransaktioner planscenariot** – Ta bort alla data i målbudgetplanen i det valda budgettransaktionen planscenariot och skapa nya rader som har de valda prognosbefattningdatan.
-   **Uppdatera det befintliga budgettransaktioner planscenariot och lägga till nya data** – Uppdateringbefintliga rader i målet planerar, som matchar källaraderna, och även lägger till nya rader för nya data. Matcha baseras på redovisningskontot, datum, budgetklass och andra värden, till exempel prognosbefattningen. Alla rader som har en position som stämmer överens med källan positionsnummer ersätts med nya rader från källan.

### <a name="selecting-forecast-positions"></a>Välja prognosbefattningar

Du kan också lägga till prognosbefattningbudgetbelopp direkt till en budgetrapport plan. Använd **Lägga till befattningar** funktionen över de här planraderna för att välja prognosbefattningarna du vill inkludera. 

De budgeterade planscenariona, som du kan välja, som är källan till scenarier, som är inkluderade i planens layout. En väljare på **Mål** fliken kan du ange att den FTE-scenariot, och huvudkontot är tillgängliga om du vill inkludera FTE-räkningar, men behöver inte anges. 

Den här valprocess uppför som väljaren **Uppdatera det befintliga budgettransaktioner planscenariot och lägga till nya data** för en utvecklingsprocess. All befintlig budgettransaktioner plan rader där prognosbefattningen läggas till tas bort och ersättas av nya rader baserat på den aktuella statusen för prognosbefattningen.

#### <a name="date-options"></a>Datumalternativ

För både utvecklingsprocessen och startdatumet valprocessen avgör på det budgeterade kostnader elementraden giltighetsdatum för motsvarande budgettransaktioner planraden. **Allokeringsmetod** Fältet på det budgeterade kostnader elementinställningarsidan anger allokeringsmetod:

-   **Start datum** Det – budgeterade kostnader elementets startdatumet som används det budgeterade planradens giltighetsdatum.
-   **Månatlig** Budgetbeloppet – fördelas jämnt på med antalet månader i datumintervallet för att producera vanligtvis ett månatligt belopp som tilldelas den första dagen i varje månad. Om den första perioden är en delvis månad, faktorer beloppet för den månaden av antal dagar som är den aktiva kostnaden i månaden, och resultatet tilldelas startdatum. Belopp för den senaste månaden är skillnaden mellan det totala budgetbeloppet och summan av alla ändra månad. Därför kan påverka avrundning beloppet för den sista månaden.
-   **Kvartalsvis** – Den här metoden är detsamma **Månatlig**som, men de beräkningar som görs tre-månad perioder.
-   **Varje vecka** – Logiken liknar av **Månatlig** logiken och **Kvartalsvis** metoder. Veckovisa budgetbeloppet – fördelas jämnt på med antalet veckor i datumintervallet för att producera vanligtvis ett veckovis belopp som tilldelas den första dagen i varje vecka. Om den första perioden är en delvis vecka, faktorer beloppet för den veckan av antal dagar som är den aktiva kostnaden i veckan, och resultatet tilldelas startdatum. Belopp för den senaste veckan är skillnaden mellan det totala budgetbeloppet och summan av alla andra veckor. Därför kan påverka avrundning beloppet för den sista veckan.
-   **Varannan vecka** – Den här metoden är detsamma **Veckovis**som, men de beräkningar som görs varannan vecka.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Ändra budgetplansraderna som har prognosbefattningar

Den här planradshowen källan för budgetbeloppen (prognosbefattningnumret )men inte är kopplad. Därför visas ändringar i prognosbefattningen inte i budgetjournalen planraden, och ändringar i budgetjournalen planraden visas i prognosbefattningen. Om du ändrar en prognos befattning och vill uppdateringarna ska inkluderas i en budgetrapport plan, måste du för att prognosbefattningen till planen igen. Kom ihåg att denna process tar bort alla rader där den prognosbefattning har tilldelats. Därför tas bort, de ändringar du har gjort till de rader. 

Om du vill se vilken budget planerar en prognos, befattning har inkluderats in, kan du generera **Prognosbefattningar med den här planen** rapporten. Alternativt på prognosbefattningen, kan du öppna faktaboxen **Associerade budgetplaner** om du vill visa planerna.


