---
title: Budgetplanering integration med andra moduler
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
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: d64f9228c538a08a2fc938bc6ff4ce11278b6fed
ms.openlocfilehash: 4b516e3460f58ef1c7f4a76357371eefde1bae49
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-integration-with-other-modules"></a>Budgetplanering integration med andra moduler



<a name="periodic-processes-for-generating-budget-plans"></a>Periodiska processer för att generera budget planer
----------------------------------------------

Budget planer kan skapas från följande resurser:

-   Huvudbokstransaktioner
-   Anläggningstillgångar
-   Prognospositioner
-   Projektprognoser
-   Prognoser om tillgång
-   Prognoser
-   Budgetregisterposter
-   Andra budget planer

De grundläggande elementen i den återkommande process är samma för alla processer. Flikar kan du ange källan till data, målet (budget) attribut, och alternativ för att köra processen i bakgrunden som ett bakgrundsjobb. I senare avsnitt i denna artikel beskriva saker som kanske inte är synliga i varje process.

### <a name="actions"></a>Åtgärder

För varje generation, tre åtgärder är tillgängliga:

-   **Skapa en ny budgetplan** skapar en ny plan som har de attribut som har markerats i formuläret ** mål ** avsnittet. Dessa attribut måste inte vara unikt. Därför två planer kan ha samma namn och andra värden.
-   **Byt ut den befintliga budgeten scenario** raderar alla data i målet budget i den valda budget plan scenario och skapar nya rader som använder den valda källdata.
-   **Uppdatera den befintliga budgeten scenario, och fästa nya data** uppdaterar befintliga rader i målplan som matchar källa rader och lägger till nya rader för nya uppgifter. Matchningen baseras på reskontra, datum, budget klass och diverse andra områden. Till exempel, när du genererar budget planer från prognos positioner, antalet är ett viktigt område. Alla rader som har en position som stämmer överens med källan positionsnummer ersätts med nya rader från källan.

### <a name="source"></a>Källa

För alla processer i **källa** på fliken kan du filtrera data med hjälp av den **Filter** knappen. Som standard läggs specifika fält i filtret för varje process. Till exempel, för att **generera budget plan från huvudboken** , **reskontra** och **viktigaste konto** kategorier finns tillgängliga och visas på sidan. Några fält som du lägger till filter är också läggas till sidan, tillsammans med några kriterier som du lägger till.

### <a name="target"></a>Mål

Det **historiska** alternativet på **fliken Mål** låter dig använda datum från källdata som giltighetsdatum i budgeten. Typiskt, det effektiva datumet måste vara inom planens budgetcykel. När du ställer in det **historiska** alternativet **Ja**, datum (år) källa används, så att du kan använda tidigare data som grund för jämförelsen. Du kan inte ändra historiska data i budgeten och planen är godkänd workflow-status. Men du kan återställa status om du måste andra scenarier i planen kräver förändringar.

Den **sammanlagda genom** fältet överst på sidan bestämmer också datum som används. Det här fältet summa belopp och eventuellt sätter datumet till den första dagen i räkenskapsåret eller fiskal period. 

Många av fälten på **fliken mål** blir redigerbart eller skrivskyddat, beroende på vilken åtgärd du väljer. När du ändrar från att skapa en ny budget planerar att uppdatera en befintlig plan, **Budget plan namn** blir otillgänglig och de fält som är relaterade till att välja en befintlig plan blir tillgängliga. Båda **mål** fliken och ** källa ** och den **redovisning** fält alltid är inte tillgängligt eftersom värdet bestäms av den valda budgetplaneringsprocessen. 

**Budgeten klass** låter dig ställa in budget plan rader som antingen utgiftstransaktioner inkomster eller transaktioner. Vanligen intäkt transaktioner är krediter till ett reskontrakonto och därför lagras som negativa belopp. Vanligen används dessa transaktioner visas även som negativa belopp i budgeten. Men genom att lägga budgeten klass som ett fält i planen layout kan du aktivera intäkt visas som positiva belopp.

### <a name="generation-rules"></a>Genereringsregler

Tre fält ger ytterligare funktioner: **Faktor**, **Minimum** och **Avrundning** **regel**. 

Värdet i **fältet Faktor** multipliceras med källa till beloppet i budgeten. Du kan sedan göra justeringar när du skapar budgeten linjer. Du kan till exempel ange **1.03** för en 3 procents ökning. Faktorn måste vara ett positivt tal. 

Den **minsta** fältet kan du ange gränsbeloppet för att skapa en budget. Om källan är mindre än detta antal, budgeten är inte skapas. Värdet **0,00** innebär att alla belopp men inte begränsa rader som positiva belopp. (Inget värde begränsar rader som positiva belopp. Negativa belopp är alltid inkluderade och avser oftast kredittransaktioner.)

**Avrundning regel** fältet kan du ange den precision i budgeten rader som skapas. Du kan avrunda beloppen till närmaste 1,00 10,00 100.00, och så vidare, valuta.

## <a name="notes-for-specific-processes"></a>Anvisningar för specifika processer
### <a name="generate-budget-plan-from-general-ledger"></a>Generera budgetplan från huvudbok

När du skapar en budget från huvudboken data måste du ange den **sammanlagda genom** fältet till **räkenskapsåret** om **historiska** alternativet är inställt på **Nej**. Perioder och datum i källan kan inte matcha perioderna i datumen i målet. Eftersom processen har inget tillförlitligt sätt att mappa dessa värden måste du begränsa processen till det första året. 

I mål, **Budget klass** är satt till antingen **kostnad** eller **intäkt**. Den här inställningen används för att välja**typ av Budget** attribut för rader som skapas när den huvudsakliga konto på en linje är inte av **intäkten** eller **kostnaden** .

### <a name="generate-budget-plan-from-fixed-assets"></a>Generera budgetplaner från anläggningstillgångar

**Skapa budget plan från anläggningsredovisning**har inget alternativ för sammanläggning av perioder eller dag. Det finns inga alternativ för konfigurering av planen som tidigare. Du kan använda proceduren periodiska transaktioner ska inkluderas planerade fasta tillgångar i budgeten planeringsprocessen.

### <a name="generate-budget-plan-from-forecast-positions"></a>Generera budgetplansrader från prognosbefattningar

**Skapa budget plan från prognos positioner** process tilldelar källa prognos position i budgeten. Du kan visa genom att lägga till den prognos som en rad i budgeten layout eller via **budgeten linjer** undersökning. Om du inte vill att prognosen att tilldelas budget plan linjer,**inkluderar position i budget alternativet linje** till **Nej**.

Rader i budgetplanen sammanställs efter redovisningskonto och befattning. Du kan dock exkludera positionsnumret, så att raderna som sammanställs per redovisningskonto bara. På **fliken mål** , **inkluderar position i budget** alternativ till **Nej**.

I **budgeten FTE scenario** kan du välja ett scenario ska inkludera antalet heltidstjänster (heltidsekvivalenter) i budgeten. Det här fältet är begränsat till kvantitet och typ scenarier som ingår i utformningen av mål budget plan. Om du väljer en FTE scenario, måste du även välja en FTE huvud konto. Detta konto används för att skapa den kvantitet budget plan linjer. 

Budgeten planering och budget plan scenario som väljs i källset målscenariot budget planeringsprocessen och scenario. Eftersom dessa attribut tilldelas prognos positioner, de måste överensstämma med budget. Därför är dessa attribut kan inte modifieras på målet.

### <a name="generate-budget-plan-from-project-forecasts"></a>Generera budgetplansrader från projektprognoser

**Skapa budget plan från projektet prognoser** , som **genererar budget plan från prognos positioner** , har ett alternativ för att inkludera projekt kvantiteter (timmar, kostnader och objekt) i en mängd scenario. De två process har också liknande filter för kolumner i budgeten layout. 

På **fliken källa** , tre alternativ i **Include-programsatsen** avsnitt avgöra vilken budget plan skapas. Dessa alternativ är desamma som de alternativ som är tillgängliga när du skapar budgeten registrera poster direkt från projektet prognoser. Ställ in **vinst och förlust** alternativet som **Ja** om du vill skapa rader för kostnader och för intäkterna. Ställ in **PIA** alternativet som **Ja** om du vill vill skapa produkter i arbete. Ställ in **lönefördelning** alternativet som **Ja** om du vill skapa rader för lönemotkonton för timtransaktioner. 

Det finns ingen **budget klass** , eftersom budgeten klass (**kostnad** eller **intäkt**) bestäms av källan. 

Du kan använda projektbudgetar som källa genom att välja den prognosmodell som innehåller projektets budget belopp. Kom ihåg att projektbudgetar skapa projektprognos posterna som de är godkända.

Välj endast kostnader eller intäkter för budgetrader, använd filter för att välja **Budgetuppdateringar: Beloppstyp = Kostnad**. Om du vill välja endast en typ av prognos, använd filter för att välja **Budget uppdateringar: Transaktionstyp = *xxx***. 

Endast en prognosmodell kan användas för att generera en budget scenario. Om du kör processen för en prognosmodell och sedan göra en uppdatering och försöka ange en annan modell, den första modellen kommer att skrivas över om samma projekt och reskontraförda konton. För att generera en budget scenario från mer än en prognosmodell, genererar olika budget plan scenarier och använda fördelningen alternativ till adderar dem tillsammans i ett annat scenario. 

**Skapa budget plan från projektet prognoser** tilldelar även källan projekt i budgeten.

### <a name="generate-budget-plan-from-supply-forecast"></a>Generera budgetplan från leveransprognos

Källa filteralternativ i **generera budget plan från prognos** processen var modellerad efter alternativ i **överföringen köpa budget redovisning** funktion, på grund av likheter mellan process och funktion.

### <a name="generate-budget-plan-from-demand-forecast"></a>Skapa budget plan från efterfrågan

För att **generera budget plan från demand forecast** process kan du ställa in **försäljningen för** alternativ till **Ja för** att generera inkomster i budgeten planerar in**livsmedel** till **Ja för** att skapa omkostnadsrader eller båda alternativen till **Ja**.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Generera budgetplan från budgetregisterposter

För att **generera budget plan från budget registrera poster** , källa måste du ange en variant, en budget och ett nummer. Med andra ord kan du skapa budget plan för endast en budget registret hos en tid. Du kan använda ytterligare poster i samma budget plan genom processen körs en gång för varje källa.

### <a name="generate-budget-plan-from-budget-plan"></a>Generera budgetplan från budgetplan

För att **generera budget plan från budgeten** , en extra uppsättning av alternativ på **fliken Mål** låter dig tilldela nya ekonomiska dimensioner. Om en ekonomisk dimension väljs, att värdet kommer att användas för alla budget-linjer. Därför kan du använda en budget som bas för andra planer, men kan också tilldela, exempelvis en annan avdelning eller ett kostnadsställe till nya budgetplaner.

## <a name="looking-back-from-the-budget-plan"></a>En återblick från budget plan
### <a name="budget-plans-by-dimension-set-inquiry"></a>Budget planer genom inställda måttet undersökning

**Budgeten planer genom inställda måttet** utredning innehåller flera alternativ som gör att du kan köra en fråga som hjälper dig att identifiera källan av budgeten. 

Markera en rad och klicka på **budgeten linjer** knappen för att köra **Budget plan linjer** fråga. Resultaten finnas filtered för dimension värdena för den valda raden. Därefter kan du tillämpa ytterligare parametrar. 

Använd den **prognos över utbudet** och **efterfrågan** knappar kör dessa frågor. I båda fallen fråga söker prognosrader som kunde ha skapat budgeten linjer. 

Ytterligare rapporter som finns tillgängliga inkluderar **prognosen positioner genom budgeten** . Detta betänkande är särskilt användbar när du vill bestämma huruvida en ställning har rätt att anslagen planer.

