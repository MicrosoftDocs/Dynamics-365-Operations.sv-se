---
title: Kreditspärrar för försäljningsorder
description: I den här artikeln beskrivs inställningen av regler som används för att placera en försäljningsorder vid kreditspärr.
author: JodiChristiansen
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 44560425056ee1726f21a4279f36c2e718956814
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856840"
---
# <a name="credit-holds-for-sales-orders"></a>Kreditspärrar för försäljningsorder
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I den här artikeln beskrivs inställningen av regler som används för att placera en försäljningsorder vid kreditspärr. Spärrningsreglerna för kredithantering kan gälla för en enskild kund eller en grupp med kunder. Spärrningsregler definierar svar vid följande omständigheter:

1. Antal förfallna dagar
2. Kontostatus
3. Betalningsvillkor
4. Kreditgränsen har utgått
5. Förfallet belopp
6. Försäljningsorderbelopp
7. Del av tillgänglig kredit som används

Det finns dessutom två parametrar som kontrollerar ytterligare scenarier som blockerar en försäljningsorder:

1. Ändring i betalningsvillkoren
2. Ändra i kvittningsrabatterna

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Ställ in regler för spärrning och undantagsregler

När en kund initierar en försäljningstransaktion granskas informationen på försäljningsordern mot en uppsättning regler för spärrning som vägleder beslutet om huruvida kredit ska utökas till kunden och tillåta att försäljningen går framåt. Du kan även definiera undantag som åsidosätter spärrreglerna och tillåter att en försäljningsorder att bearbetas. Du kan ställa in spärrningsregler och undantagsregler på sidan **Kredithantering > Inställningar > Inställningar för kredithantering > Spärrningsregler**.

Från och med version 10.0.21 har spärrreglerna i kredithanteringen omreglerats på följande sätt för att ge mer flexibilitet:

- Utökningsbegäranden har aktiverats så att du kan skapa egna spärrregler.
- Kryssrutan **Frisläpp försäljningsorder** är nu tillgänglig för alla spärregler. Tidigare var det bara tillgängligt för spärregeln för försäljningsorder. När den här kryssrutan är markerad frisläpper undantagsregeln försäljningsordern utan att andra regler som kan spärra försäljningsorder övervägs. Den här kryssrutan är bara tillgänglig för typen **Undantagsregel**.

### <a name="days-overdue"></a>Dagar försenad

Öppna fliken **förfallna dagar** om spärregeln gäller för kunden med en eller flera fakturor som har förfallit ett visst antal dagar.
1. Välj det kundintervall som regeln **gäller för**.
   - Välj **register** om regeln gäller för en viss kund.
   - Välj **grupp** om regeln tillämpas på kundgruppsnivå. 
   - Välj **Alla** om regeln gäller alla kunder.
2. När du har angett intervallet måste du ange **kontot/gruppen** som ska användas i intervallet.
   - För området **tabell** tillhandahåller sökningen en lista med kunder som du kan välja mellan. 
   - Välj en **grupp** om regeln gäller för en kundkreditgrupp.
   - Välj **Alla** om regeln gäller alla kunder. 
3. Välj **riskgrupp** om du vill använda kriterier för att använda en spärr för kredithantering för kunder som är grupperade efter en gemensam uppsättning faktorer, t.ex. Dun- och Bradstreet-värdering, antalet år som de har arbetat, hur länge de har varit kunder och så vidare.  
4. Välj vilken typ av regel som du ställer in. Med alternativet **spärr** kan du skapa en regel som blockerar en order. Med alternativet **exkludera** skapas en regel som utesluter en annan regel från att blockera en order. 
5. Välj en **värdetyp**. Standardvärdet är ett fast antal dagar. Om du skapar ett undantag kan du ange ett fast antal dagar eller ett belopp istället. 
6. Ange det antal dagar som är **Förfallna** och som kan tillåtas för den valda spärrningsregeln innan en order placeras i kredithanteringsspärr för granskning. Antalet förfallna dagar motsvarar ett ytterligare antal respitdagar som har lagts till efter det förfallodatum som fakturan kan ha innan den anses ha förfallit. Om du har angett typen **värde** som ett belopp för ett undantag anger du ett belopp och en valuta för beloppet.

### <a name="account-status"></a>Kontostatus

Öppna fliken **kontostatus** om spärregeln gäller för en kund med den valda kontostatusen.
1. Välj vilken typ av regel som du ställer in.  **Spärr** kommer att skapa en regel som blockerar en order. **Exkludera** skapas en regel som utesluter en regel från att blockera en order. 
2. Välj den **kontostatus** som gör att regeln sätter en spärrad försäljningsorder eller exkluderar den.

### <a name="terms-of-payment"></a>Betalningsvillkor

Välj **betalningsvillkor** om spärregeln gäller för det valda betalningsvillkoret.
1. Välj vilken typ av regel som du ställer in.  **Spärr** kommer att skapa en regel som blockerar en order. **Exkludera** skapas en regel som utesluter en regel från att blockera en order. 
2. Välj den **Betalningsvillkor** som gör att regeln sätter en spärrad försäljningsorder eller exkluderar den.

### <a name="credit-limit-expired"></a>Kreditgränsen har utgått

Öppna fliken **Kreditgränsen förfallen** om spärregeln gäller för kunder med kreditgränser som har upphört att gälla.
1. Välj det kundintervall som regeln **gäller för**.
   - Välj **register** om regeln gäller för en viss kund.
   - Välj **grupp** om regeln tillämpas på kundgruppsnivå. 
   - Välj **Alla** om regeln gäller alla kunder.
2. När du har angett intervallet måste du ange **kontot/gruppen** som ska användas i intervallet.
   - För området **tabell** tillhandahåller sökningen en lista med kunder som du kan välja mellan. 
   - Välj en **grupp** om regeln gäller för en kredithanteringsgrupp.
   - Välj **Alla** om regeln gäller alla kunder. 
3. Välj en **riskgrupp** för att ytterligare begränsa listan med kunder som ska placeras vid kredithanteringsspärr. 
4. Välj vilken typ av regel som du ställer in. 
   - Välj **Spärr** kommer att skapa en regel som blockerar en order. 
   - Välj **exkludera** skapas en regel som utesluter en annan regel från att blockera en order. 
5. Ange den **Dagar för kreditgränsen förfallen** för dagar för den valda spärrningsregeln innan en orderplaceras i en kredithanteringsspärr. Antalet förfallna dagar representerar ytterligare respitdagar som läggs till det antal dagar som kreditgränsen har löpt ut.

### <a name="overdue-amount"></a>Förfallet belopp

Öppna fliken **förfallet belopp** om spärregeln gäller för kunder med förfallna belopp.
1. Välj det kundintervall som regeln **gäller för**.
   - Välj **register** om regeln gäller för en viss kund.
   - Välj **grupp** om regeln tillämpas på kundgruppsnivå. 
   - Välj **Alla** om regeln gäller alla kunder.
2. När du har angett intervallet måste du ange **kontot/gruppen** som ska användas i intervallet.
   - För området **tabell** tillhandahåller sökningen en kundsökning. 
   - Välj en **grupp** om regeln gäller för en kredithanteringsgrupp.
   - Välj **Alla** om regeln gäller alla kunder. 
3. Välj en **riskgrupp** om du vill ytterligare begränsa listan med kunder som ska placeras i kredithanteringsspärr. 
4. Välj vilken typ av regel som du ställer in. 
   - Välj **Spärr** kommer att skapa en regel som blockerar en order. 
   - Välj **exkludera** skapas en regel som utesluter en annan regel från att blockera en order. 
5. Ange den **Förfallet belopp** för dagar för den valda spärrningsregeln innan en orderplaceras i en kredithanteringsspärr för granskning. 
6. Välj den **värdetyp** som definierar den typ av värde som ska användas när du också vill testa hur stor del av kreditgränsen som har använts. Spärregler och undantagsregler tillåter bara ett procenttal för **förfallna belopp**. Tröskeln är relaterad till kreditgränsen.
7. Ange **tröskelvärdet för kreditgräns** för den valda regeln innan en kund övergår till kredithanteringsspärr. Det kan vara ett belopp eller en procentsats som baseras på värdetypen som väljs i värdetypen.
8. Regeln kontrollerar att **Förfallet belopp** överskrids och **Tröskelvärdet för kreditgräns** överskrids. 

### <a name="sales-order"></a>Försäljningsorder 

Välj **försäljningsorder** om spärregeln gäller för försäljningsorderns värde.
1. Välj det kundintervall som regeln **gäller för**.
   - Välj **register** om regeln gäller för en viss kund.
   - Välj **grupp** om regeln tillämpas på kundgruppsnivå. 
   - Välj **Alla** om regeln gäller alla kunder.
2. När du har angett intervallet måste du ange **kontot/gruppen** som ska användas i intervallet.
   - För området **tabell** tillhandahåller sökningen en kundsökning. 
   - Välj en **grupp** om regeln gäller för en kredithanteringsgrupp.
   - Välj **Alla** om regeln gäller alla kunder. 
3. Välj en **riskgrupp** om du vill ytterligare begränsa listan med kunder som ska placeras i kredithanteringsspärr. 
4. Välj vilken typ av regel som du ställer in.  
   - Välj **Spärr** kommer att skapa en regel som blockerar en order. 
   - Välj **exkludera** skapas en regel som utesluter en annan regel från att blockera en order. 
5. Ange den **Försäljningsorderbelopp** för dagar för den valda spärrningsregeln innan en orderplaceras i en kredithanteringsspärr. 

### <a name="credit-limit-used"></a>Kreditgräns som används

Välj **kreditgräns som används** om spärregeln gäller för det utnyttjade gränsbeloppet för kundkredit.
1. Välj det kundintervall som regeln **gäller för**.
   - Välj **register** om regeln gäller för en viss kund.
   - Välj **grupp** om regeln tillämpas på kundgruppsnivå. 
   - Välj **Alla** om regeln gäller alla kunder.
2. När du har angett intervallet måste du ange **kontot/gruppen** som ska användas i intervallet.
   - För området **tabell** tillhandahåller sökningen en kundsökning. 
   - Välj en **grupp** om regeln gäller för en kredithanteringsgrupp.
   - Välj **Alla** om regeln gäller alla kunder. 
3. Välj en **riskgrupp** om du vill ytterligare begränsa listan med kunder som ska placeras i kredithanteringsspärr. 
4. Välj vilken typ av regel som du ställer in.
   - Välj **Spärr** kommer att skapa en regel som blockerar en order. 
   - Välj **exkludera** skapas en regel som utesluter en annan regel från att blockera en order. 
5. Välj den **återstående tröskeln** som definierar den procent av kreditgränsen som blockerar försäljningsordern. Om värdet på en order ökar beloppet för den kreditgräns som används ovanför procenten spärras ordern. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Spärra en försäljningsorder baserat på andra kriterier
  
### <a name="rank-payment-terms"></a>Rangordna betalningsvillkor  

Du kan tvinga reglerna för kreditkontroll att utföras när betalningsvillkoren ändras. Du måste rangordna betalningsvillkoren och tilldela dem ett rangordningsvärde. Om du ändrar betalningsvillkoren på ordern till betalningsvillkor som är högre än de gamla betalningsvillkoren, skickas ordern till kreditstyrning och kräver godkännande.

Du kan ställa in de kostnader som gäller för betalningsvillkor sidan **kredithantering > inställningarna > inställningar för kredithantering > rangordna betalningsvillkoren**.

1. Välj betalningsvillkor som fältet **betalningsvillkor** att rangordna. När du väljer en term visas beskrivningen i fältet **beskrivning**.
2. Välj villkorets rangordning i fältet **rangordning**. Alla värden är relativa till varandra så att du kan använda 1, 2, 3 eller 10, 20, 30. Du kan också använda samma värde för de flesta betalningsvillkoren så att kreditkontrollen initieras genom att bara ett eller två betalningsvillkor inaktiveras.

### <a name="rank-settlement-discounts"></a>Rangordna kvittningsrabatter   

Du kan tvinga reglerna för kreditkontroll att utföras när kvittningsrabatterna ändras. Du måste rangordna kvittningsrabatterna och tilldela dem ett rangordningsvärde. Om du ändrar kvittningsrabatterna på ordern till kvittningsrabatterna som är högre än de gamla kvittningsrabatterna, skickas ordern till kreditstyrning och kräver godkännande.

Du kan ställa in de kostnader som gäller för betalningsvillkor sidan **kredithantering > inställningarna > inställningar för kredithantering > rangordna kvittningsrabatterna**.

1. Välj den **kassarabatt** som du vill rangordna. **Beskrivningen** av kvittningsrabatten visas.
2. Välj värdet **Rangordna**. Alla värden är relativa till varandra så att du kan använda 1, 2, 3 eller 10, 20, 30. Du kan också använda samma värde för de flesta kvittningsrabatterna så att kreditkontrollen initieras genom att bara ett eller två kvittningsrabatterna inaktiveras.

## <a name="sequence-the-application-of-rules"></a>Sekvensen av tillämpning av regler

Regler körs i en viss ordning som du ändrar så att de passar din organisations behov. 

- Med en instans av reglerna för uteslutning av försäljningsorder kan du åsidosätta alla regler som kan blockera en försäljningsorder. Skapa en undantagsregel för försäljningsorder och markera alternativet **Frisläpp försäljningsorder**. Ordern spärras inte om den exkluderande regeln är sann och inga andra regler kontrolleras.
- Spärrningsregler kan göra att ordern spärras.
- Undantagsregler körs efter att reglerna blockerats. Undantagsregler påverkar bara regeln som de har definierats för. 
- Regler för blockering och undantag körs i registret och sedan grupperas alla order. På grund av den här bearbetningsordningen är det möjligt att ha en spärrningsregel på alla nivåer som inte kommer att köras eftersom en undantagsregel på register eller gruppnivån körs.
- Undantag åsidosätter inte spärregeln om de finns på samma nivå. En exkluderingsregel på gruppnivå åsidosätter till exempel inte spärregeln på gruppnivå. Du behöver inte ställa in undantag på alla nivåer utom som det anges ovan med en instans av regeln för uteslutning av försäljningsorder. 

Uppförandet av regeln **kreditgräns som används** kommer att ändras baserat på inställningarna för parametern **Checkkreditgräns för försäljningsorder** hittar du i formuläret för kredit och samling.
- Om parametern är inställd på Nej, kommer regeln för kreditgräns inte att köras.
- Om parametern ställs in på Ja och **meddelandet om att överskrida kreditgränsen** är inställt på varning, får du en varning när kreditgränsen överskrids. Reglerna **kreditgräns används** kommer att köras för att se om du har regler som du vill köra. I det här scenariot lägger du emellertid normalt inte till några regler.
- Om parametern är inställd på Ja och **meddelandet om att överskrida kreditgränsen** har värdet fel, kommer kreditgränsen att kontrolleras och ordern spärras om kreditgränsen överskrids. Dessutom kommer reglerna **kreditgräns används** kommer att köras för att se om du har ytterligare regler som du vill köra. Ett felmeddelande visas inte, men det **överskridna kreditgränsens** spärrningsorsak visas. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>Inställningar som påverkar hur en orderspärras

Order kan exkluderas från en kredithantering även om regler har inträffat. 

- Om du ändrar inställningarna **exkludera kund från kredithantering** i **Snabbfliken Alla kunder > Välj en kund > Kredit och inkasso** till **Ja**, kommer inga order för den kunden att bearbetas.
- Om du ändrar värdet från **exkludera från kredithantering** på **försäljningsorderrubrik** på **snabbfliken kredithantering** till **Ja**, bearbetas inte kredithanteringsreglerna. Den här inställningen kan bara utföras av kreditansvarig eller kreditchef.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>Bearbeta order som spärrats med spärrlistan för kredithantering

I spärrlistan för kredithanterin visas alla försäljningsorder som har spärrats och de kan ta bort spärrar när kreditutleveransen har begränsats. Sidan **spärrlistan för kredithantering** visar alla försäljningsorder som har spärrats. Du kan visa spärrlistan på sidan **alla kreditspärrar** (**kredithantering > spärrlistan för kredithantering > alla kreditspärrar**).
Försäljningsorder från alla juridiska personer skickas till samma undantagslista för kredithantering, vilket ger en centraliserad översikt över alla transaktioner som kräver åtgärd. Användare ser bara information för de juridiska personer som de har tillgång till.

En försäljningsorder kan placeras i en spärrlista av följande orsaker:
1. Kunden har en faktura som har förfallit under ett angivet antal dagar. 
2. Ordern har en specifik kontostatus.
3. Ordern har specifika betalningsvillkor.
4. Kunden har en utgången kreditgräns.
5. Kunden har ett förfallet belopp och har använt en angiven procentandel av dess kreditgräns
6. Försäljningsordern överskrider en viss mängd.
7. Kunden har överskridit en viss procent av dess kreditgräns.
8. Betalningsvillkoren skiljer sig från standardbetalningsvillkoren för kunden.
9. Kvittningsrabatterna skiljer sig från standardkvittningsrabatten för kunden.

Spärrningsorsaken visas för varje försäljningsorder i spärrlistan. Om det finns fler än en orsak till spärrningen visas orsaken som **Flera**. Du kan använda menyn **spärrningsorsaker** i åtgärdsfönstret om du vill visa alla orsaker till att försäljningsordern spärrades. Du kan också visa **spärrningsorsaker** i en faktabox.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Frigöra order från spärrlistan för bearbetning

När du har sökt igenom orsakerna och du har tackat nej till undantaget kan du frisläppa försäljningsorder för vidare bearbetning.

1) Välj en rad i spärrlistan. Du kan frigöra flera order genom att välja mer än en rad.
2) Välj en **frisläppningsorsak** för ordern som har valts för frisläppning.  
3) Ange **frisläppningsdatum** för varje order som har valts för frisläppning.  
4) Klicka på menyn **frisläpp** i åtgärdsfönstret för att frisläppa en order. Den här menyn är bara tillgänglig när du har valt transaktioner. Användaren kan visa två alternativ:
   - Välj **med bokföring** om du vill ta bort spärren och bokföra dokumentet med samma bokföringsprocess som användes när den spärrades. Om till exempel bekräftelsen för försäljningsorder spärrades, slutförs bekräftelsen av försäljningsorder efter frisläppning. Formuläret för bokföring av försäljningsorder kommer att visas så att användaren kan skicka bekräftelsen.
   - Markera **utan att bokföra** om du vill ta bort spärren utan att göra någon ytterligare bearbetning. Försäljningsordern kan bokföras manuellt.

### <a name="rejecting-orders-in-the-hold-list"></a>Avvisa order i spärrlistan
Du kan använda menyn **avvisa** i åtgärdsfönstret för att avvisa en försäljningsorder
1. Välj en rad i spärrlistan. Du kan frigöra flera order genom att välja mer än en rad.
2. Ordern tas bort från spärrlistan och försäljningsorderrubriken uppdateras för att visa att ordern avvisades.

### <a name="automatically-releasing-credit-management-holds"></a>Automatisk frisläppning av kredithanteringsspärrar
Försäljningsorder placeras i spärrlistan baserat på spärrningsreglerna. Vissa orsaker till detta kan emellertid ändras över tiden om försäljningsordern finns kvar i spärrlistan under en tidsperiod. En kund kan t.ex. betala sin faktura och på så vis frisläppa sin kreditgräns. 

Du kan använda menyn **utvärdera för frisläppning** för att granska försäljningsorder i spärrlistan och automatiskt släppa dem om orsaken till spärren har begränsats.
1.  Välj menyn **utvärdera för frisläppning**
2.  Välj **Behandla spärrningsregler** om du vill granska alla försäljningsorder. Välj **Behandla spärrningsregler för valda rader** om du bara vill granska de rader som du har valt.
3. Ett skjutreglage visas så att du kan välja en enskild kund. Låt listruran för kund vara tom för alla kunder. 
4. När du klickar på OK körs processen i bakgrunden och du kan fortsätta att arbeta med andra uppgifter. Om du väljer batchbearbetning innan du klickar på OK kommer processen att köras i batch när du klickar på OK. Det kan ta en stund att bearbeta de väntande orderna i listan, så använd Uppdatera när du vill uppdatera orderstatus. 
5.  Om en spärrningsorsak inte längre kan användas för en order, kommer spärrningsorsaken inte längre att vara giltig och du kan inte längre se en bockmarkering bredvid orsaken när du visar spärrningsorsakerna.
6.  Om alla spärrningsorsaker är avmarkerade, läggs en ny orsak till **Redo att frisläppas**, men den läggs till i listan över spärrningsorsaker. Försäljningsordern kan frisläppas automatiskt.
7.  Om parametern **Automatiskt frisläppa** på fliken **Kredit och inkasso > Inställningar > Parametrar för kredit och inkasso > Kredit > Automatisk frisläppning** anges till **Med bokföring**, då kommer du att uppmanas att posta med bokningsformuläret för det dokument som har blockerats.
8.  Om parametern **Automatiskt frisläppa** på fliken **Kredit och inkasso > Inställningar > Parametrar för kredit och inkasso > Kredit > Automatisk frisläppning** anges till **Utan bokföring**, då måste du bokföra ordern manuellt.

### <a name="credit-management-approval-workflow"></a>Arbetsflöde för godkännande av kredithantering

Du kan också skapa **Arbetsflöden för kredithantering** för att kontrollera frisläppandet av kreditspärrar. När du har ställt in arbetsflödet med sidan **Kredithantering > Inställningar > Arbetsflöden för kredithantering** skickas de order som har markerats för frisläppning eller avvisande till arbetsflödet där de måste godkännas först innan de frigörs eller avvisas. 

Om du inkluderar uppgifterna för frisläppning med bokföring eller frisläppning utan bokföring i arbetsflödet frigörs också försäljningsordern av godkännandet för arbetsflödet. Om det uppstår ett fel i frisläppningsprocessen på grund av att det saknas installationsinformation eller andra orsaker, måste du återkalla försäljningsordern från arbetsflödet, åtgärda problemet som orsakade felet och skicka sedan ordern till arbetsflödet igen.

Om du inte inkluderar aktiviteterna för frisläppning med bokföring eller frisläppning utan att bokföra i arbetsflödet, kan du med arbetsflödets godkännande process enkelt frisläppa försäljningsordern manuellt när godkännandet är slutfört.

### <a name="forced-credit-hold"></a>Framtvingad kreditspärr  
  
Ibland kan försäljningsorder behöva spärras även om ordern inte uppfyller kriterierna i spärreglerna. En kredit ansvarig kan t.ex. meddelas om ett problem som inte är kreditrelaterat med kunden och besluta att manuellt spärra ordern tills problemet har lösts. Du kan manuellt tvinga en försäljningsorder att spärras om den situationen inträffar.

1. Öppna den försäljningsorder som du vill spärra.  
2. Välj **tvinga kreditspärr** på fliken **kredithantering** i åtgärdsfönstret **kredithantering**.
3. Välj en **orsak för påtvingad spärr**.
4. Klicka på **OK.** Försäljningsordern kommer att returneras till spärrlistan för kredithantering.

Du kan också tvinga flera order att spärras med hjälp av sidan **kredithantering > periodiska uppgifter > tvinga kreditspärr**. Du kan till exempel placera alla försäljningsorder spärrade för en viss kund.
1. Välj en **orsak för påtvingad spärr**. 
2. Klicka på **poster som ska inkluderas** för att välja vilka försäljningsorder som ska spärras. 
3. Klicka på **OK** för att behandla de valda försäljningsorderna.

Försäljningsorder som har tvingats att spärras kan inte bearbetas med arbetsflödet.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>Frisläppa order som har lagts till i listan över kredithantering med en tvingad kreditspärr
Försäljningsorder med en påtvingad spärrorsak kan inte frisläppas automatiskt. Om försäljningsordern har spärrats och du har använt en process som automatiskt släpper försäljningsorder, visas försäljningsordern som **Klar att frisläppas** och finns kvar i spärrlistan. Du måste använda menyn **frisläpp** för att frisläppa ordern.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Fritextfakturor, order och stöd för projektfakturor i kredithantering 
Kredithantering kan endast användas för försäljningsorder. Fritextfakturor, kassaorder och kundtjänstorder använder de tillfälliga kreditgränser och försäkringar/garantier som du lägger till för att justera kreditgränsen. De kommer inte att använda spärrningsreglerna och de kommer inte att placeras i spärrlistan om det finns ett problem med kreditgränsen.

Det finns inget stöd för projektfakturor i kredithantering.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
