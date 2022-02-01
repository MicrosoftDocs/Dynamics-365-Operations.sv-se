---
title: Rutnätsmöjligheter
description: I det här avsnittet beskrivs flera kraftfulla funktioner i rutnätskontrollen. Du måste aktivera den nya rutnätsfunktionen för att du ska kunna använda dessa funktioner.
author: jasongre
ms.date: 12/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 37484ce022085dfac66edba31b7adf9af4095df8
ms.sourcegitcommit: bbe8ab054ad7cc00a63c63e02dc90bfa8ede15bb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/14/2022
ms.locfileid: "7974391"
---
# <a name="grid-capabilities"></a>Rutnätsmöjligheter

[!include [banner](../includes/banner.md)]

Den nya rutnätskontrollen innehåller flera användbara och kraftfulla funktioner som kan användas för att förbättra användarproduktiviteten, skapa mer intressanta vyer av dina data och få meningsfulla insikter om dina data. Den här artikeln kommer att omfatta följande funktioner: 

-  Beräknar summor
-  Skriva före systemet
-  Utvärdera matematikuttryck 
-  Gruppera data i en tabell (aktiveras separat med hjälp av funktionen **gruppering i rutnät**)
-  Låsa kolumner
-  Autoanpassning av kolumnbredd
-  Sträckbara kolumner

## <a name="calculating-totals"></a>Beräknar summor
I Finance and Operations-appar har användare möjlighet att visa summor längst ned på numeriska kolumner i rutnät. Dessa summor visas i ett sidfotsavsnitt längst ned i rutnätet. 

### <a name="showing-the-grid-footer"></a>Visa rutnätets sidfot
Det finns ett sidfotsområde längst ned i alla tabell rutnät i Finance and Operations-program. Sidfoten kan visa värdefull information som är relaterad till de data som visas i rutnätet. Här följer några exempel på denna information:

- Antalet markerade rader i tabellen (om fler än en post har valts)
- Total summor längst ned i konfigurerade numeriska kolumner
- Antalet rader i datauppsättning 

Den här sidfoten är som standard dold, men den är lätt att aktivera. Om du vill visa sidfoten för ett rutnät, välj knappen **rutnätsalternativet** i rutnätsrubriken och välj alternativet **Visa sidfot**. När du har slå på sidfoten för ett visst rutnät kommer den inställningen att föra in en dag tills användaren väljer att dölja sidfoten. Du döljer sidfoten genom att välja **Dölj sidfot** på menyn **Rutnätsalternativ**.  

### <a name="specifying-columns-with-totals"></a>Ange kolumner med summor
I nuläget visas för närvarande inga kolumner summor som standard. I stället betraktas detta som en enstaka inställningsaktivitet, på samma sätt som du justerar bredden på kolumner i rutnät. När du har angett att du vill visa summorna för en kolumn kommer den inställningen att komma ihåg nästa gång du besöker sidan.  

Du kan konfigurera en kolumn på två sätt för att visa en summa: 

- Högerklicka i kolumnen som du vill se summa för och välj sedan **Summa den här kolumnen**. Den här åtgärden medför att tre händelser inträffar:

    1. Sidfoten blir synlig. 
    2. Din preferens för att se summan för den här kolumnen sparas. 
    3. En beräkning av summor initieras för den här kolumnen och alla andra kolumner som du tidigare har konfigurerat för att se summor för. Den tid som krävs för att visa en summa beror på storleken på den datauppsättning som du summerar.

- När sidfoten är synlig väljer du **Visa summa** i sidfotsområdet längst ned i kolumnen som du vill se en total summa för. Om det inte finns några konfigurerade kolumner visas knappen **Visa summa** för alla numeriska kolumner. 

    När minst en kolumn har konfigurerats för summor, kommer knapparna **Visa summa** endast att vara tillgängliga vid hovring eller fokus. Om du väljer **Visa total** sparar du bara din inställning för att se en summa i den här kolumnen, så att inställningen tillämpas vid framtida besök på sidan. I sidfoten markeras det här läget med ett streck som visas i kolumnen. (Alternativt, om datauppsättning är tillräckligt litet visas en summa omedelbart.)

Om du gör ett misstag och inte längre vill se en summa i en viss kolumn högerklickar du på kolumnen och väljer **Dölj summa** eller väljer knappen **Dölj summa** i sidfoten i den kolumnen. Den här inställningen kommer också att sparas för framtida besök på sidan. 

### <a name="calculating-totals"></a>Beräknar summor
När du kommer till en sida med sidfoten synlig och kolumner som redan konfigurerats för summor kan det hända att summorna inte visas i sidfoten. Beteendet beror på storleken på datauppsättningen på sidan. Om datauppsättningen är tillräckligt liten visas summorna automatiskt tillsammans med antalet rader i datauppsättningen. Om det finns bindestreck i sidfoten under de kolumner som du har konfigurerat för summor, är datauppsättningen för stor för systemet att visa summor omedelbart och en uttrycklig åtgärd krävs för att beräkna summorna. Det gör du genom att klicka på knappen **Beräkna** i sidfoten, eller högerklicka på en kolumn som du vill ha en summa för och välja **Summa den här kolumnen**.  

Om beräkningen tar för lång tid kan du avbryta operationen genom att välja knappen **Avbryt**. Ibland är datauppsättningen för stor för att beräkna summor (en begränsning som din organisation anger) och du ska istället bli meddelad om att filtrera data mer.

Summor uppdateras automatiskt när du uppdaterar, tar bort eller skapar rader i datauppsättningen.  

## <a name="typing-ahead-of-the-system"></a>Skriva före systemet
I många affärsscenarier är möjligheten att snabbt registrera data i systemet mycket viktig. Innan den nya rutnätskontrollen introducerades kunde användarna bara ändra data på den aktuella raden. Innan de kan skapa en ny rad eller växla till en annan rad tvingades de vänta på att kontrollera ändringar i systemet. I ett försök att minska den tid som användarna väntar på att dessa valideringar ska slutföras, och för att förbättra användarproduktiviteten, justerar det nya rutnätet dessa valideringar så att de är asynkrona. Användaren kan därför flytta till andra rader och göra ändringar medan föregående radvalideringar väntar. 

För att det nya beteendet ska fungera har en ny kolumn för radstatus lagts till höger om kolumnen för radval när rutnätet är i redigeringsläge. I den här kolumnen visas en av följande statusvärden:

- **Tom** – ingen statusbild anger att raden har sparats korrekt av systemet.
- **Bearbetning väntar** – denna status anger att ändringarna i raden ännu inte har sparats av servern men att de finns i en kö med ändringar som måste bearbetas. Innan du utför en åtgärd utanför rutnätet måste du vänta tills alla väntande ändringar har bearbetats. Dessutom är texten i dessa rader kursiv för att ange statusen som inte har sparats för raderna. 
- **Ogiltigt tillstånd** – denna status anger att en del varningar eller meddelanden utlöstes under bearbetningen av raden och kan ha hindrat systemet från att spara ändringarna på den raden. I det gamla rutnätet, om åtgärden inte sparades tvingades du tillbaka till raden för att åtgärda problemet direkt. I det nya rutnätet får du dock ett meddelande om att ett valideringsproblem har uppstått, men du kan bestämma när du vill åtgärda eventuella problem på raden. När du är redo att åtgärda problemet kan du manuellt flytta tillbaka fokus till raden. Du kan också välja åtgärden **Lös problemet**. Den här åtgärden flyttar omedelbart tillbaka fokus till den rad där problemet finns och gör att du kan redigera det inuti eller utanför rutnätet. Observera att bearbetningen av efterföljande väntande rader stoppas tills den här valideringsvarningen har lösts. 
- **Paus** – denna status anger att servern håller på att göra paus eftersom validering av raden utlöst en popup-dialogruta som kräver användarindata. Eftersom användaren kan mata in data på en annan rad visas inte dialogrutan direkt för den användaren. Den visas i stället när användaren väljer att återuppta bearbetningen. Denna status åtföljs av ett meddelande som informerar användaren om situationen. Meddelandet innehåller en åtgärd **återuppta bearbetning** som utlöser popup-dialogrutan.  
    
När användarna skriver in data i förväg på den plats där servern bearbetas, kan de förvänta sig en del graderingar i data inmatningsupplevelsen, t.ex. brist på sökningar, validering på kontrollnivå och registrering av standardvärden. Användare som behöver en nedrullningsbar lista för att hitta ett värde bör vänta på att servern ska fånga upp den aktuella raden. Verifiering och inmatning av standardvärden på kontrollnivå görs också när servern bearbetar raden.   

### <a name="pasting-from-excel"></a>Klistra in från Excel
Användare har alltid kunnat exportera data från rutnät i Finance and Operations-appar till Microsoft Excel med hjälp av funktionen **exportera till Excel**. Möjligheten att föra in data i förväg av systemet gör dock att det nya rutnätet kan användas för att kopiera tabeller från Excel och klistra in dem direkt i rutnät Finance and Operations-appar. Rutnätscellen som Inklistringsåtgärden initieras från avgör var den kopierade tabellen börjar klistras in. Innehållet i rutnätet skrivs över av innehållet i den kopierade tabellen, utom i två fall:

- Om antalet kolumner i den kopierade tabellen överstiger antalet kolumner som finns kvar i rutnätet, från inklistringsplatsen meddelas användaren att de extra kolumnerna har ignorerats. 
- Om antalet rader i den kopierade tabellen överstiger antalet rader i rutnätet, med början från inklistringsområdet, skrivs de befintliga cellerna över av det inklistrade innehållet och eventuella extra rader från den kopierade tabellen infogas som nya rader längst ned i rutnätet. 

## <a name="evaluating-math-expressions"></a>Utvärdera matematikuttryck
Som en produktivitetsförstärkning kan användarna ange matematiska formler i numeriska celler i ett rutnät. De behöver inte utföra beräkningen i en app utanför systemet. Om du till exempel anger **=15\*4** och tryck sedan på **Tabb** tangenten för att flytta ut ur fältet, utvärderas uttrycket och värdet **60** för fältet sparas.

Om du vill att ett värde ska identifieras som ett uttryck i systemet startar du värdet med ett likhetstecken (**=**). Mer information om operatorer och syntax som stöds finns i [matematiska symboler som stöds](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Gruppera data i tabellform
Företagsanvändare behöver ofta för att utföra ad hoc-analys av data. Det kan du göra genom att exportera data till Microsoft Excel och med hjälp av pivottabeller och funktionen (förhandsversion) **gruppera i rutnät** som är beroende av den nya nätkontrollfunktionen, tillåter användare att organisera sina tabelldata på intressanta sätt i Finance and Operations-appar. När funktionen utökas kommer funktionen **Summor**, **Gruppera** också få meningsfulla insikter i data genom att tillhandahålla delsummor på gruppnivån.

Om du vill använda den här funktionen högerklickar du på den kolumn som du vill gruppera efter och väljer **gruppera efter denna kolumn**. Den här åtgärden sorterar data efter den markerade kolumnen, lägger till en ny **Gruppera efter**-kolumn i början av rutnätet och infogar "rubrikrader" i början av varje grupp. Dessa rubrikrader innehåller följande information om varje grupp: 
-  Datavärde för gruppen 
-  Kolumnnamn (den här informationen är särskilt användbar när du har flera grupperingsnivåer)  
-  Antal data rader i den här gruppen
-  Delsummor för alla kolumner som konfigurerats att visa summor

När [sparade vyer](saved-views.md) är aktiverad kan den här gruppen sparas med personlig anpassning som en del av en vy för snabbåtkomst nästa gång du besöker sidan.  

### <a name="multiple-levels-of-grouping"></a>Flera nivåer av gruppering
När du har grupperat data efter en enda kolumn kan du gruppera data efter en annan kolumn genom att välja **Gruppera efter denna kolumn** i önskad kolumn. Den här processen kan upprepas tills du har fem kapslade nivåer för gruppering, vilket är det maximala djup som stöds. I det här läget kan du inte längre gruppera efter ytterligare kolumner.  

Du kan när som helst ta bort grupperingen i valfri kolumn genom att högerklicka på kolumnen och välja **Dela upp**. Du kan också ta bort grupperingen från alla kolumner genom att välja **rutnätsalternativ** och sedan **Dela upp alla**.   

### <a name="expanding-and-collapsing-groups"></a>Expandera och komprimera grupper
Den första grupperingen av data kommer att ha alla grupper expanderade. Du kan skapa sammanfattade vyer över informationen genom att dölja enskilda grupper, eller så kan du använda expandera och komprimera grupp för att underlätta navigeringen mellan data. Om du vill expandera eller komprimera en grupp, markerar du knappen (>) i motsvarande grupprubrikrad. Observera att läget utöka/komprimera för enskilda grupper **inte** sparas i anpassning.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Markera och avmarkera rader på gruppnivå
På samma sätt som du kan markera (eller avmarkera) alla rader i rutnätet genom att markera kryssrutan högst upp i den första kolumnen i rutnätet kan du snabbt markera (eller avmarkera) alla raderna i en grupp genom att markera kryssrutan i motsvarande grupprubrikrad. Kryssrutan på raden i grupphuvudet visar alltid aktuell markeringsstatus för rader i den gruppen, oavsett om alla rader har markerats eller om alla rader är markerade, eller om bara vissa rader är markerade.

### <a name="hiding-column-names"></a>Dölja kolumnnamn
När du grupperar data är standardfunktionen att visa kolumnnamnet i grupprubrikraden. Du kan välja att utelämna kolumnnamnet i grupphuvud rader genom att välja **Rutnätsalternativ** > **Dölj gruppkolumnnamn**.

### <a name="grouping-on-date-and-time-columns"></a>Gruppering efter datum- och tidskolumner
Från och med version 10.0.24 för fälten Datum eller DateTime har alternativet lagts till i gruppering efter år, månad eller dag. Gruppen "värde" på motsvarande rubrikrad matchar formatet från det fältet. I fälten DateTime och Time kan du dessutom gruppera efter timme, minut eller andra.    

## <a name="freezing-columns"></a>Låsa kolumner
En del kolumner i ett rutnät kan vara så viktiga för sammanhanget att du inte vill att de ska rulla ut ur visningen. Istället vill du att värdena i dessa kolumner alltid ska vara synliga. Funktionen **Lås kolumner i rutnät** flexibiliteten för användarna. 

Om du vill låsa en kolumn högerklickar du i kolumnens rubrik och väljer sedan **Lås kolumn**. Första gången du slutför det här steget blir den valda kolumnen den första kolumnen och kan inte längre rulla ut ur visningen. Alla efterföljande kolumner som du fryser läggs till till höger om den sista låsta kolumnen. Du kan använda standardfunktionen Flytta om du vill beställa om låsta kolumner efter behov. Låsta kolumner kan emellertid inte flyttas så att de visas bland de olästa kolumnerna. Ej låsta kolumner kan emellertid inte flyttas så att de visas bland de låsta kolumnerna.

Om du vill låsa upp en kolumn högerklickar du i kolumnens rubrik och väljer sedan **Lås upp kolumn**. 

Observera att radurvalet och radstatuskolumnerna i det nya rutnätet alltid är låsta som de första två kolumnerna. När dessa kolumner tas med i ett rutnät visas de därför alltid för användaren, oavsett den vågräta rullningspositionen i rutnätet. Dessa två kolumner kan inte beställas om.

## <a name="autofit-column-width"></a>Autoanpassning av kolumnbredd
Användare i Excel kan automatiskt tvinga en kolumn att ändra storlek baserat på det innehåll som visas i kolumnen. Det gör du genom att dubbelklicka på storlekshanterarna i kolumnen eller genom att sätta fokus i kolumnrubriken och trycka på **A** (för autoanpassning). Den här funktionen är tillgänglig från och med version 10.0.23.  

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hur aktiverar jag den nya rutnätskontrollen i min miljö? 

Funktionen **Ny rutnätskontroll** är tillgänglig direkt i funktionshantering i alla miljöer. När funktionen har inaktiverats i funktionshanteringen kommer alla efterföljande användarsessioner att använda den nya rutnätskontrollen. 

Den här funktionen aktiveras som standard med start i version 10.0.21 och är avsedd att bli obligatorisk med version 10.0.25. 

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Utvecklare] Avanmäl individuella sidor från att använda det nya rutnätet 
Om din organisation hittar en sida med vissa problem med att använda det nya rutnätet, finns det en API som gör det möjligt för ett enskilt formulär att använda den gamla rutnätskontrollen samtidigt som resten av systemet tillåter att den nya rutnätskontrollen används. Om du vill välja en enskild sida från det nya rutnätet lägger du till följande samtalspost `super()` i formulärets `run()`-metod.

 ```this.forceLegacyGrid();```

Detta API sätts in tills den nya rutnätskontrollen blir obligatorisk, som är avsedd för april 2022. Om något problem kräver att denna API används rapporterar du dem till Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Tvinga en sida att använda det nya rutnätet efter att tidigare valt ut rutnätet
Om du har valt att inte använda det nya rutnätet för en enskild sida kanske du senare vill aktivera det nya rutnätet igen efter att de underliggande frågorna inte har lösts. Om du vill göra detta måste du bara ta bort samtalet `forceLegacyGrid()`. Ändringen börjar inte gälla förrän något av följande inträffar:

- **Omdistribuering av miljö**: När en miljö uppdateras och omplaceras rensas tabellen som lagrar sidorna som har valt bort det nya rutnätet (FormControlReactGridState) automatiskt.

- **Manuell clearing av registret**: För utvecklingsscenarier måste du använda SQL för att rensa tabellen FormControlReactGridState och sedan starta om AOS. Den här kombinationen av åtgärder återställer cachningen av sidor som har valt att inte använda det nya rutnätet.  

## <a name="developer-size-to-available-width-columns"></a>[Utvecklare] kolumner med storlek till tillgänglig bredd
Om en utvecklare ställer in egenskapen **WidthMode** på **SizeToAvailable** för kolumner inuti det nya rutnätet, har de kolumnerna samma bredd som de skulle ha om egenskapen hade värdet **SizeToContent**. De sträcker sig däremot åt att använda valfri tillgänglig bredd i rutnätet. Om egenskapen har ställts in på **SizeToAvailable** för flera kolumner, delar alla dessa kolumner all tillgänglig bredd i rutnätet. Om en användare manuellt ändrar storleken på en av dessa kolumner blir kolumnen statisk. Den kommer att finnas kvar till den bredden och kan inte längre sträckas ut för att ta upp extra tillgängligt rutnäts bredd.  

## <a name="known-issues"></a>Kända problem
I det här avsnittet finns en lista över kända problem för den nya rutnätskontrollen.  

### <a name="open-issues"></a>Öppna ärenden
-  När funktionen för **ny rutnätskontroll** aktiveras fortsätter vissa sidor att använda den befintliga rutnätskontrollen. Detta sker i följande situationer:  
    -  Det finns en kortlista på sidan som renderas i flera kolumner.
    -  Det finns en grupperad kortlista på sidan.
    -  En rutnätskolumn med en icke-reagerande utökningsbar kontroll.

    När en användare först stöter på en av dessa situationer, visas ett meddelande om att sidan ska uppdateras. När det här meddelandet visas fortsätter sidan att använda det befintliga rutnätet för alla användare tills nästa versionsuppdatering av produkten sker. En bättre hantering av dessa scenarier, så att det nya rutnätet kan användas, övervägs för framtida uppdateringar.    
    
-  [KB-4582758] Poster är suddiga när du ändrar zoom från 100 till något annat procenttal
-  [KB 4592012] Oväntat klientfel i IE11 när du klistrar in flera rader från Excel
    -  Microsoft följer ingen åtgärd för det här problemet

### <a name="fixed-as-part-of-10016"></a>Korrigerat som en del av 10.0.16

-  [KB 4598335] Strängkontroller med flera linjer följer inte deras DisplayHeorgans i listor/kort 
-  [KB 4591891] Fakturaförslagsrader försvinner när rader avmarkeras
-  [KB 4592104] Det gick inte att redigera poster efter att ha klickat på "Korrigera problem" och flyttat till en annan rad utan att korrigera valideringsproblemet
-  [KB 4594449] Knapparna "Aldrig" och "Rensa" saknas i datumplockningen 
-  [KB 4594448] När du anger tid behandlas det nya rutnätet på ett annat sätt
-  [KB 4600059] Oväntat klientfel med e-postbegränsning
-  [KB 4574584] Förhandsgranskning av utgiftsbilagan är inte tillgänglig när du hovrar över kvittoikonen

### <a name="fixed-as-part-of-10015"></a>Korrigerat som en del av 10.0.15    

-  (Kvalitetsuppdatering) [KB 4594444] Oväntat klientfel med förhandsgranskning av segmenterad inmatningskontroll
-  [KB 4582723] Visningsalternativ visas inte när de utförs senare i formuläret livscykel
-  [KB 4591988] Problem med tangentbordstangentborden för att välja ett värde från en referensgrupps uppslag
-  [KB 4588958] Regression Suite Automation Tool (RSAT) misslyckas med felet: TypeError: Cannot read property 'text' of undefined
-  [KB 4591970] Oväntat klientfel när du klistrar in från Excel direkt efter att du klickat i rutnätet
-  [KB 4591904] Dataändringar sparas inte om användaren omedelbart klickade på en kontroll och öppnade sökning efter en annan kontroll
-  [KB 4584752] Oväntat klientfel på sidan för projektfakturaförslag
-  [KB 4584540] Det gick inte att lämna rutnätet efter att en enskild rad har klistrats in i en journalrad
-  [KB 4591908] När du skapar en ny rad är du inte försent med dig i kolumnen du skapade en ny rad.

### <a name="fixed-as-part-of-10014"></a>Korrigerat som en del av 10.0.14

-  (Kvalitetsuppdatering) [KB 4584752] Oväntat klientfel på sidan för projektfakturaförslag
-  [KB-4583880] Regression Suite Automation Tool (RSAT)-tester misslyckas vid OpenLookup-åtgärd med "Cannot read property RowIndex of undefined"
-  [KB 4583847] Oväntat klientfel vid navigering i sökningar

### <a name="fixed-as-part-of-10013"></a>Korrigerat som en del av 10.0.13

-  (Kvalitetsuppdatering) [KB 4584752] Oväntat klientfel på sidan för projektfakturaförslag
-  [KB-4583880] Regression Suite Automation Tool (RSAT)-tester misslyckas vid OpenLookup-åtgärd med "Cannot read property RowIndex of undefined"
-  (Kvalitetsuppdatering) [KB 4583847] Oväntat klientfel vid navigering i sökningar 
-  (Kvalitetsuppdatering) [Fel 471777] Det går inte att markera fält i ett rutnät för att redigera eller skapa en mobilapp
-  [KB 4582727] Rutnätet fryses när användaren får dialog för objekt med flera kvantiteter
-  [Fel 474851] Hyperlänkar i referensgruppskontroller fungerar inte 
-  [Fel 474848] Utökade förhandsgranskningar med rutnät visas inte
-  [KB 4582726] Egenskapen RotateSign respekteras inte  
-  [Fel 470173] Kryssrutor på inaktiva rader växlar när användaren klickar på blanksteg i cellen
-  [Fel 474848] Utökade förhandsgranskningar med rutnät visas inte
-  [Fel 474851] Hyperlänkar i referensgruppskontroller fungerar inte 
-  [Fel 471777] Det går inte att markera fält i ett rutnät för att redigera eller skapa en mobilapp
-  [KB 4569441] Problem med återgivning av kortlistor för flera kolumner, knappbeskrivningar på bilder och visningsalternativ för vissa fält
-  [KB 4575279] Alla markerade rader raderas inte i redovisningsjournalen
-  [KB 4575233] Visningsalternativ återställs inte efter flyttning till en annan rad
-  [Fel-477884] Sökningar returnerar fel värde/post om ny rutnätskontroll aktiveras
-  [KB 4571095] Bokföring av produktinleverans sker när användaren råkar trycka på retur (korrekt hantering av sidans standardåtgärd)
-  [KB 4575437] Sökningar med redigerbara kontroller stängs oväntat
-  [KB 4569418] Formuläret duplicerad rad har skapats i leveransschemaformuläret
-  [KB 4575435] Förbättrad förhandsgranskning är ibland även om muspekaren inte är nära fältet
-  [KB 4575434] Sökningen filtreras inte när fältet har ändrats
-  [KB 4575430] Värden i lösenordsfält maskeras inte i rutnätet
-  [KB 4569438] "Bearbetning har avbrutits på grund av ett valideringsproblem" visar efter markeringsrader under kvittning av leverantörstransaktioner
-  [KB 4569434] Att uppdatera formuläret juridiska personer resulterar i färre poster
-  [KB 4575297] Fokus flyttas till fönstret uppgiftsinspelaren när du redigerar och tabbar genom ett rutnät
-  [KB 4566773] Korrigeringstransaktioner som inte visas som negativa på transaktioner i verifikationstransaktioner 
-  [KB 4575288] Fokus återställs till den aktiva raden när kantlinjen mellan raderna i en enkel lista markeras
-  [KB 4575287] Fokus återgår inte till den första kolumnen när du använder nedpil för att skapa en ny rad i journaler
-  [KB 4564819] Det går inte att ta bort rader i en fritext faktura (eftersom datakällan ChangeGroupMode=ImplicitInnerOuter)
-  [KB 4563317] Knappbeskrivningar/förbättrade förhandsgranskningar visas inte för bilder

### <a name="fixed-as-part-of-10012"></a>Korrigerat som en del av 10.0.12

- [KB 4558545] Register kontroller uppdaterar inte innehållet i visade objekt.
- [KB 4558570] Objekten visas fortfarande på sidan när posten har tagits bort.
- [KB 4558572] Formatering som associeras med **ExtendedStyle** på listpanelen används inte.
- [KB 4558573] Valideringsfel kan inte åtgärdas när den obligatoriska ändringen ligger utanför rutnätet.
- [KB 4558584] Negativa tal återges inte korrekt.
- [KB 4560726] Ett "oväntat klientfel" inträffar när växlingen mellan listor har utförts med en listvy.
- [KB 4562141] Rutnätsindex är inaktiverade efter att en ny post har lagts till.
- [KB 4562151] alternativen **validera** och **kopiera** uppgiftsinspelning är inte tillgängliga för kontroll av datum/nummer. 
- [KB 4562153] Kryssrutor med flera markeringar visas inte i list- eller kortrutnätet.
- [KB 4562646] Ibland kan du inte klicka utanför rutnätet när du har flera markeringar i rutnätet.
- [KB 4562647] Fokus återställs till den första kontrollen i dialogrutan **publicera** efter att en ny rad har lagts till i rutnätet för säkerhetsroller.
- [KB 4563310] Den utökade förhandsgranskningen stängs inte efter att en rad har ändrats.
- [KB 4563313] Ett oväntat klientfel inträffar i Internet Explorer när ett värde väljs i en sökning.
- [KB 4564557] Uppslag och nedrullningsbara menyer öppnas inte i Internet Explorer
- [KB 4563324] Navigeringen fungerar inte när arbetsytan **personalhantering** har öppnats.

### <a name="fixed-as-part-of-10011"></a>Korrigerat som en del av 10.0.11

- [Problem 432458] Tomma eller duplicerade rader visas i början av vissa underordnade samlingar.
- [KB 4549711] Rader i ett betalningsförslag kan inte tas bort korrekt när den nya rutnätskontrollen är aktiverad.
- [KB 4558374] Poster som kräver en dialogruta med polymorfa väljare kan inte skapas.
- [KB 4558375] Hjälptexten visas inte på kolumnerna i det nya rutnätet.
- [KB 4558376] Listpanelens rutnät återges inte på rätt höjd i Internet Explorer.
- [KB 4558377] Kolumner med kombinationsrutor som har en bredd på **SizeToAvailable** återges inte på vissa sidor.
- [KB 4558378] Visning ibland öppnar fel post.
- [KB 4558379] Ett fel uppstår när sökningar öppnas där **ReplaceOnLookup**=**Nej**.
- [KB 4558380] Det tillgängliga utrymmet i rutnätet fylls inte direkt efter att en del av sidan har dolts.
- [KB 4558381] Negativa tal återges inte korrekt, utan att användarna ibland blir låsta när det har uppstått valideringsproblem.
- [KB 4558382] Oväntade klientfel uppstår.
- [KB 4558383] Kontroller utanför rutnätet uppdateras inte efter att sista posten har tagits bort.
- [KB 4558587] Referensgrupper som har kombinationsrutor för ersättningsfält visar inte värden.
- [KB 4562143] Fält uppdateras inte efter att en rad ändring/rutnätsbehandling har fastnat efter att rader har tagits bort.
- [KB 4562645] Ett undantag uppstår när ett uppslag öppnas när tester av Regression Suite Automation Tool (RSAT) körs.

### <a name="fixed-as-part-of-10010"></a>Korrigerat som en del av 10.0.10

- [Problem 414301] Vissa data från tidigare rader försvinner när nya rader skapas.
- [Fel 417044] Det finns inget tomt rutnätsmeddelande för rutnät med listformat.
- [KB 4539058] Vissa rutnät (vanligtvis på snabbflikar) återges ibland inte (men de visas om du zoomar ut).
- [KB 4549734] Aktiva rader behandlas inte som markerade om markeringskolumnen är dold.
- [KB 4549796] Det går inte att redigera värden i ett rutnät när det är i visningsläge.
- [KB 4558367] Textmarkeringen är inkonsekvent när rader ändras.
- [KB 4558368] Flerval via tangentbordet tillåts vid scenarier med ett val.
- [KB 4558369] Statusbilder försvinner i det hierarkiska rutnätet.
- [KB 4558370] En ny rad rullas inte in i bild.
- [KB 4558372] Det nya rutnätet fastnar i bearbetningsläget om antalet kolumner i innehållet som klistras in överskrider antalet återstående kolumner i rutnätet.
- [KB 4562631] Tidsvärden formateras inte korrekt.

### <a name="quality-update-for-1009platform-update-33"></a>Kvalitetsuppdatering för 10.0.9/plattformsuppdatering 33

- [KB 4550367] Tidsvärden formateras inte korrekt.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
