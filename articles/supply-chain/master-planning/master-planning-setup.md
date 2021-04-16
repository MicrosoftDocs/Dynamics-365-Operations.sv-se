---
title: Ställ in huvudplanering
description: Det här ämnet beskriver olika viktiga strategier och parametrar som används för att ställa in huvudplaneringen.
author: t-benebo
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: fe7ff2ab877182dd3145e39574aa7229c48b6057
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833411"
---
# <a name="set-up-master-planning"></a>Ställ in huvudplanering

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver olika viktiga strategier och parametrar som används för att ställa in huvudplaneringen. Den innehåller en översikt över de typer av planer som används vid huvudplanering och förklarar vilken planeringsstrategi du ska använda, beroende på dina affärsbehov. Här beskrivs också de huvudsakliga parametrar som påverkar planen och förklarar hur dessa parametrar påverkar planerade order som föreslås.

## <a name="types-of-master-plans"></a>Typer av huvudplaner

Huvudplanering har två typer av planer: statiska och dynamiska. Varje typ har utformats för en annan användning. För bästa prestanda rekommenderar vi att du använder en lämplig plan för scenariot.

### <a name="static-plan"></a>Statisk plan

Den statiska planen förblir oförändrad, oavsett eventuella ändringar i tillgången och efter frågan, till nästa gång huvudplaneringen körs.

Den statiska planen används för att godkänna och bekräfta de order som föreslås. Det är en verksamhetsplan som olika anställda, till exempel en inköpare eller produktionsplanerare, kan använda för att basera sina beslut på och utföra sina dagliga uppgifter och aktiviteter.

Den statiska planen stöder också omgenerering. En helt ny optimerad plan beräknas varje gång huvudplaneringen körs och befintliga order som ännu inte har godkänts raderas.

### <a name="dynamic-plan"></a>Dynamisk plan

Den dynamiska planen börjar vanligtvis som en kopia av den statiska planen, men den kan uppdateras varje gång huvuddata ändras. Om data till exempel ändras skapas en ny försäljningsorder.

Den dynamiska planen används för ad hoc-planering. Den låter företaget övervaka ändringar av order och artikeltillgänglighet utan att ändra den statiska planen som andra använder i sina arbetsprocesser. Den används särskilt för CTP (capable to promise). Den dynamiska planen är standardplanen när nettobehov öppnas från ordersidor (t.ex. sidor för försäljningsorder, inköpsorder eller tillverkningsorder).

Den dynamiska planen använder nettoförändringen. Därför garanterar det snabbare att körningstid.

## <a name="strategies-for-using-master-plans"></a>Strategier för användning av huvudplaner

Du kan antingen använda en plan eller två planer i huvudplaneringen. Vilken strategi du använder beror på dina affärskrav.

### <a name="one-plan-strategy"></a>Strategi för en plan

För strategin med en plan använder du samma huvudplan för den statiska planen och den dynamiska planen. Denna strategi används för tillverka mot lager-scenarion, där du vanligtvis inte måste simulera en plan som uppfyller en order.

Strategin för en plan används vanligtvis i detaljhandels- och distributionsbranscher eller där leveransdatum för försäljning bekräftas baserat på servicenivåavtal (SLAs) eller produktionstider. För planen kan leveransdatumkontrollen användas utan CTP.

Om du måste göra en simulering kan planen köras igen för de artiklar som kräver simuleringen. De planerade order som skapas av ordersimuleringar är vanligtvis bekräftade.

### <a name="two-plan-strategy"></a>Strategi för två planer

För strategin med två planer använder du en statisk plan och en annan dynamisk plan. Strategin för två planer används vanligtvis för konfigurera enligt order-scenarier och tillverka enligt order-scenarier där du måste göra simuleringar av försäljningsorder och beräkna exakta leveransdatum för försäljningsorder, men beräkningarna får inte påverka vardagliga operationer. Simuleringarna görs alltid i den dynamiska planen. Strategin för två planer är till exempel användbar i bil- och OEM-industrin.

För strategin med två planer kan leveransdatumkontrollen användas med CTP. När CTP används, utlöser den automatiskt körningen i den dynamiska planen.

### <a name="setting-up-the-plans"></a>Ställa in planerna

Du kan skapa planer på sidan **huvudplaner** (**huvudplanering \> inställningar \> planer \> huvudplaner**).

Du kan ange vilka planer som ska användas för den statiska planen och den dynamiska planen genom att ställa in fälten **Aktuell statisk huvudplan** och **Aktuell dynamisk huvudplan** på sidan **Huvudplaneringsparametrar** (**Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**). Om du vill använda en strategi för en plan väljer du samma plan i fälten **Aktuell statisk huvudplan** och **Aktuell dynamisk huvudplan**.

## <a name="types-of-planning-methods"></a>Typer av planeringsmetoder

Tre beräkningsmetoder kan användas för att köra huvudplanering: regenerering och nettoförändring. Varje metod skapar en egen plan när den körs.

Planeringsmetoden anges i dialogrutan **huvudplaneringskörning**. Öppna den här dialogrutan genom att gå **Huvudplanering \> Huvudplanering \> Kör \> Huvudplanering**, eller välj **Kör** i arbetsytan **Huvudplanering**.

### <a name="regeneration"></a>Omgenerering

Planeringsmetoden för återskapande tar bort befintliga planerade order, såvida de inte bekräftas. Den genererar nya planerade order, baserat på alla krav. Återskapande är den enda planeringsmetod som är tillgänglig för statiska planer.

- Ändringar i utbudet beaktas. Ändringarna omfattar ändringar i prognosen.
- Den här metoden följer **periodens** täckningskod.
- Den här metoden stöder funktionen för ersättningsprodukter (PI).

### <a name="net-change"></a>Nettoändring

Metoden nettoförändringsplanering genererar planerade order för att täcka de behov som har skapats eller ändrats sedan den senaste huvudplaneringskörningen. Ändringar i leverans tas inte med när den här metoden körs. Systemet tar inte hänsyn till nya leveranser och tidigare skapade planerade order tas inte bort om de inte längre behövs. Metoden nettoförändringsplanering körs snabbare än omgenereringsmetod. Den är bara tillgänglig för dynamiska planer.

- Åtgärdsdatum och framtida uppgifter uppdateras för alla behov.
- Den här metoden följer inte **periodens** täckningskod.
- Den här metoden uppfyller inte prognosen även om den är vald i planen.
- Den här metoden stöder inte funktionen för ersättningsprodukter (PI).

### <a name="net-change-minimized"></a>Nettoändring minimerad

Den minimerade metoden nettoförändringsplanering genererar planerade order för att endast täcka de behov som har skapats eller ändrats sedan den senaste huvudtidsplaneringskörningen. För den här metoden uppdateras till skillnad från nettoförändringsmetoden, åtgärdsdatum och framtida datum bara nya eller ändrade krav. Den här planeringsmetoden är endast tillgänglig för dynamiska planer.

## <a name="types-of-scheduling-methods"></a>Typer av tidsplaneringsmetoder

För varje plan, på snabbfliken **allmänt** på sidan **huvudplaner** (**huvudplanering \> inställningar \> planer \> huvudplaner**), måste du välja den planeringsmetod som används för produktionbeställning. Du kan tidsplanera produktionen på grov- och finplaneringsnivå.

### <a name="operations-scheduling"></a>Grovplanering

Du kan använda grovplaneringen för att ange en allmän uppskattning av produktionsprocessen över en viss tid. Grovplanering bryter inte ned verksamheten för produktionsflödet till jobb. Mer information om grovplanering finns i [grovplanering](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Finplanering

Finplanering är en mer detaljerad planeringsmetod där varje operation delas in i sina individuella uppgifter eller jobb. Finplanering omfattar information om kapacitet. Den används som regel för att planera enskilda jobb för en omedelbar eller kortsiktig tidsram. Mer information om finplanering finns i [finplanering](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Frystidsgräns i dagar

För varje plan kan du välja hur långt i framtiden de olika behoven och andra överväganden måste beräknas i huvudplaneringen. Perioden kallas för en *tidsgräns*. För bästa prestanda vid huvudplanering rekommenderar vi att du justerar olika tidsgränser för att uppfylla dina affärskrav. För varje plan hittar du tidsgränsen på snabbfliken **Frystidsgräns i dagar** på sidan **huvudplaner** (**huvudplanering \> inställningar \> planer \> huvudplaner**).

> [!NOTE]
> Tidsgränser anger hur långt i framtiden som olika krav och andra överväganden beräknas av huvudplanering. De tidsgränser som har valts på den här sidan kommer att åsidosätta tidsgränsen som definierats i disponeringsgruppen. Detta innebär att ange ett tidsgränsalternativ till Ja och definition av dagar kommer att åsidosätta den tidsgräns som definierats i disponeringsgruppen. När du ställer in till Nej, kommer tidsgränsen att definieras i disponeringsgruppen. Slutligen, om du inte vill använda ett alternativ (till exempel om du inte vill använda åtgärdsmeddelanden), ställer du in det på **Ja** och anger sedan tidsgränsen till **0** (noll) dagar.

### <a name="coverage"></a>Disponering

Tidsgränsen för disponering representerar planeringsperioden eller hur långt upp efter frågan ska inkluderas. Med andra ord anger den planeringshorisonten.

Genom att ställa in alternativet **Disponering** till **Ja** kan du åsidosätta den tidsgräns för disponering som har definierats för artikeln under huvudplaneringen. I detta fall anger du nu antalet dagar som huvudplaneringens beräkning ska täcka behoven. Tidsgränsen för disponering beräknas framåt från dagens datum. Behov som ligger före dagens datum bearbetas alltid.

> [!NOTE]
> För bästa prestanda vid huvudplanering rekommenderar vi att du justerar olika tidsgränser för disponering till din planeringshorisont.

### <a name="freeze"></a>Frys

Frystidsgränsen representerar perioden då befintliga planerade order inte ändras när en ny huvudplan körs. Planerade order fryses och inga nya planerade order kommer att föreslås.

Genom att ställa in alternativet **Frysa** till **Ja** kan du åsidosätta den tidsgräns för frysning som har definierats för artikeln under huvudplaneringen. I detta fall anger du antalet dagar då du vill frysa planeringsaktiviteterna. Kom ihåg att under denna period genereras inga nya planerade order och befintliga planerade order kan inte ändras.

### <a name="firming"></a>Bekräftelse

Bekräftad tidsgräns anger den tidshorisont då planerade order automatiskt konverteras till produktions- och inköpsorder. Den här processen kallas även *automatisk bekräftelse av planerade order*.

Genom att ställa in alternativet **Bekräftelse** till **Ja** kan du åsidosätta den tidsgräns för bekräftelse som har definierats för artikeln under huvudplaneringen. I detta fall anger du antalet dagar då planerade inköps- och produktionsorder automatiskt bekräftas. Bekräftad tidsgräns beräknas framåt från datumet för huvudplaneringen. Automatisk bekräftelse av en planerad inköpsorder kan endast äga rum om artikel kopplades till en leverantör.

### <a name="forecast-plan"></a>Prognosplan

Tidsgränsen för prognosplan anger hur långt in i framtiden huvudplaneringen skapar planerade order för artiklar med prognostiserad efterfrågan.

Genom att ställa in alternativet **Prognosplan** till **Ja** kan du åsidosätta den tidsgräns för prognosplan som har definierats för artikeln under huvudplaneringen. I detta fall anger du det antal dagar då försäljningsprognosen från prognosplanen ska inkluderas i huvudplaneringen.

### <a name="capacity"></a>Kapacitet

Kapacitetstidsgränsen anger hur långt i framtiden som systemet tar hänsyn till resursens maximala kapacitet när order planeras. Med andra ord schemalägger planen produktionsordern med hjälp av produktionsflödet för artiklarna och tar hänsyn till produktionsflödets resurser och den maximala kapaciteten för varje resurs.

Genom att ställa in alternativet **Kapacitet** till **Ja** kan du åsidosätta den kapacitetstidsgräns som har definierats för artikeln under huvudplaneringen. I detta fall anger du antalet dagar då kapacitet för planerade tillverkningsorder ska planeras. I huvudplaneringen används artikelns aktiva produktionsflöde och tidsplaneringen görs bakåt från behovsdatum. Om behovsdatum för en planerad tillverkningsorder hamnar utanför kapacitetstidsgränsen bestäms produktionstiden med ledning av artikelns leveranstid. Kapacitetstidsgränsen beräknas framåt från dagens datum.

### <a name="action-message"></a>Åtgärdsmeddelande

Åtgärdsmeddelanden ger förslag på ändringar som kan göras av den befintliga leveransordern för att optimera leveransplaneringen. De kanske till exempel rekommenderar att du förflyttar eller skjuter upp order, eller att du ökar eller minskar orderantalet.

Genom att ställa in alternativet **Åtgärdsmeddelanden** till **Ja** kan du åsidosätta den åtgärdstidsgräns som har definierats för artikeln under huvudplaneringen. I detta fall anger du antalet dagar som huvudplaneringen ska generera åtgärdsmeddelanden för behov. Åtgärdstidsgränsen beräknas framåt från dagens datum.

Mer information om åtgärdsmeddelanden finns i [åtgärdsmeddelanden](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/action-messages).

> [!NOTE]
> Beräkningen av åtgärdsmeddelanden gör att en tid körs längre för huvudplaneringen. Om åtgärdsmeddelanden inte analyseras och tillämpas regelbundet (varje dag, vecka o.s.v.) bör du överväga att inaktivera beräkningen under huvudplaneringskörningen. Du inaktiverar beräkningen på sidan **huvudplaner**, ange **åtgärdstidsgräns** till **0** (noll) för huvudplanen som du kör. Kontrollera också att inställningen **åtgärdsmeddelande** är inaktiverad för alla disponeringsgrupper.

### <a name="calculated-delays"></a>Beräknade fördröjningar

Du kan ange hur långt i framtiden som eventuella fördröjningar i planerade order ska identifieras och rapporteras. På det här sättet kan du schemalägga möjliga (fördröjda) leveransdatum.

Om en planerad order inte kan uppfyllas för det begärda datumet, planeras den på det tidigaste uppfyllande datumet för en transaktion, baserat på produktionstider och material- och kapacitetstillgänglighet.

### <a name="approved-requisitions-time-fence"></a>Godkänd rekvisitionstidsgräns

Du kan ställa in huvudplaneringen för att skapa planerade order för rekvisitionbegäran. Ange alternativet **Inkludera rekvisitioner** till **Ja** på snabbfliken **allmänt** på sidan **huvudplaner**. När syftet med en godkänd rekvisition är lagerpåfyllnad, skapar huvudplaneringen automatiskt en motsvarande planerad order för att uppfylla den. Metoden lagerpåfyllnad bestäms av tillförselpolicyerna som har ställts in för artiklarna i organisationen. När en påfyllningsrekvisition har skapats och godkänts, krävs ingen ytterligare användareåtgärd.

Genom att ställa in alternativet **Godkänd rekvisitionstidsgräns** till **Ja** på snabbfliken **Tidsgräns i dagar** kan du åsidosätta den godkända tidsgränsen för rekvisitioner som har definierats för artikeln under huvudplanering. I detta fall anger du antal förflutna dagar under vilka förfrågan från godkända rekvisitioner som har Påfyllnadssyfte inkluderat i huvudplaneringen. Du kan till exempel ange, om bara ouppfylld, förfallen efterfrågan från godkända rekvisitioner som har skapats under de senaste 10 dagarna, ska betraktas som har planerats för.

### <a name="sequencing"></a>Ordningsföljd

Med hjälp av ordningsföljd kan planerade order ordnas baserat på ordningsföljden för de attribut som är kopplade till den färdiga produkten. Den används ofta för att förbereda tillverkningsorder för förpackning. Den kan till exempel användas för att packa lådor i en specifik sekvens, baserat på färg och storlek.

Genom att ställa in alternativet **ordningsföljd** till **Ja** kan du ange hur långt operationerna eller jobben ska ställas i ordning. Kom ihåg att ju längre tidsgränsen är, desto längre tid tar huvudplaneringen att köra.

### <a name="calculated-delays"></a>Beräknade fördröjningar

Fördröjningsalternativ hjälper till att garantera att beställningarna har möjliga planerade datum. Följande alternativ finns på snabbfliken **beräknade fördröjningar** på sidan **huvudplaner**:

- **Se till att de planerade orderna inte skapas före huvudplaneringens körningsdatum** – Ställ in det här alternativet till **Ja** för att garantera att order inte kan tidsplaneras för föregående datum.
- **Lägg till den beräknade fördröjningen för behovsdatumet** (under **Planerade inköpsorder**) – Ange det här alternativet till **Ja** för att lägga till den beräknade fördröjningen på behoven.
- **Lägg till den beräknade fördröjningen för behovsdatumet** (under **Planerade produktionsorder**) – Ange det här alternativet till **Ja** för att lägga till den beräknade fördröjningen på behoven.
- **Lägg till den beräknade fördröjningen för behovsdatumet** (under **Planerad överföring**) – Ange det här alternativet till **Ja** för att lägga till den beräknade fördröjningen på behoven.
- **Lägg till den beräknade fördröjningen för behovsdatumet** (under **Planerad kanban**) – Ange det här alternativet till **Ja** för att lägga till den beräknade fördröjningen på behoven.

När du ställer in alternativet **Lägg till den beräknade fördröjningen för behovsdatumet** till **Ja**  för att lägga till fördröjningar i behoven, tar systemet hänsyn till resursernas kapacitet och skapar genomförbara planerade order Vid omberäkningen av planerade orderdatum ökas körningstiden för huvudplaneringen. Om du inte behöver använda fördröjningar ställer du därför in alternativen på **nej**.

## <a name="positive-and-negative-days"></a>Positiva och negativa dagar

Positiva och negativa dagar påverkar hur huvudplanering föreslår planerade order och åtgärder. Positiva och negativa dagar anges i artikelns disponeringsgrupp. Du kan definiera de olika disponeringsgrupper och ange deras parametrar på sidan **disponeringsgrupper** (**huvudplanering \> inställning \> disponering \> disponeringsgrupper**).

### <a name="positive-days"></a>Positiva dagar

Positiva dagar anger hur långt i den framtida huvudplaneringen som det tas hänsyn till det aktuella lagret eller inleveransen för att uppfylla en framtida efterfrågan. Om till exempel de positiva dagarna är inställda på **100** kan det aktuella lagret användas för att uppfylla efterfrågan under de kommande 100 dagarna. Om det finns en order 150 dagar från det aktuella datumet kommer huvudplaneringen att skapa en planerad order för att tillfredsställa det behovet, även om lagerbehållningen för artikeln kan uppfylla ordern. För artiklar som flyttas snabbt som har en kort produktionstid kanske du inte vill använda lagerbehållningen för en order som ligger långt fram i tiden. I det här fallet är den aktuella lagerbehållningen snabbare, och fler order kan placeras i framtiden för att uppfylla en framtida efterfrågan i tid, vilket kan vara möjligt beroende på den korta produktionstiden för artikeln.

De positiva dagarna påverkar också åtgärdsmeddelandena. Du kan till exempel rekommendera att du ökar en planerad inköpsorder så att den inkluderar en efterfrågan som ligger inom antalet positiva dagar i framtiden. Om de positiva dagarna är inställda på **100** och om det finns efterfrågan på en artikel 30 dagar från det aktuella datumet skapas en planerad order för att tillfredsställa det behovet. Om det finns efterfrågan för samma artikel inom 90 dagar från det aktuella datumet, rekommenderar systemet att du ökar kvantiteten för ordern på 30 dagar från det aktuella datumet, så att ordern också täcker efterfrågan på 90 dagar. Om det däremot finns efterfrågan för artikeln om 150 dagar från det aktuella datumet, rekommenderar systemet inte att du ökar kvantiteten av ordern som redan har planerats. Istället skapas en ny planerad order.

Som regel anges de positiva dagarna som en siffra mellan den längsta produktionstiden för artiklarna och tidsgränsen för disponering. Vi rekommenderar att du tilldelar artiklar som regelbundet har upphandlats eller producerats till en disponeringsgrupp där de positiva dagarna är lika med artikelns produktionstid.

### <a name="negative-days"></a>Negativa dagar

Negativa dagar anger hur sena inleveranser av artiklar kommer att tillåtas. De representerar antalet dagar som du är villig att vänta innan du beställer ny påfyllnad när du har negativt lager eller inte har tillräckligt med lager. Negativa dagar svara på frågan, ska vi skapa en ny inköpsorder för artikeln, eller använda ett befintligt inköp, även om vi vet att artikeln kommer att vara sen?

Du har till exempel en försäljningsorder för en artikel som är 15 dagar från det aktuella datumet. Du har också en inköpsorder för samma artikel. Denna inköpsorder kommer att inlevereras om 20 dagar från det aktuella datumet. Vill du att en inköpsorder skapas för den försäljningsordern, eller vill du använda den befintliga ordern även om du inte kan slutföra försäljningsordern i tid? Om de negativa dagarna är inställda på mindre än **5** för att ange att artikeln kan försenas maximalt fem dagar, skapar systemet en ny planerad inköpsorder för att tillfredsställa försäljningsordern. Om de negativa dagarna är inställda på fler än **5**, använder systemet den befintliga ordern för artikeln.

De negativa dagarna påverkar även prestanda för huvudplaneringen. Om de negativa dagarna är inställda på ett högt antal genereras många åtgärdsmeddelanden.

Vi rekommenderar att du ställer in de negativa dagarna till ett tal som är mindre än produktionstiden för artikeln.

### <a name="dynamic-negative-days"></a>Dynamiska negativa dagar

Dynamiska negativa dagar tar hänsyn till artikelns produktionstid och de negativa dagar som du har angett. Systemet skapar en ny planerad inköpsorder baserat på tidsgränsen för negativa dagar som beräknas med hjälp av följande formel:

Produktionstid + negativa dagar + aktuellt datum – behovsdatum

Systemet använder bara de planerade leveransorder som finns inom denna tidsgräns och skapar en ny planerad order utanför den. Fördelen med dynamiska negativa dagar är att den enskilda produktens produktionstid kommer att inkluderas, för att återanvända befintliga order och undvika att skapa nya planerade order som kommer att bli längre än en senare dag, på grund av förseningar som orsakas av produktionstiden. 

Mer information finns i [negativa dagar och dynamiska negativa dagar](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]