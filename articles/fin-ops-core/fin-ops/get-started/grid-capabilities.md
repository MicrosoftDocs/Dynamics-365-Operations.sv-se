---
title: Rutnätsfunktioner
description: I den här artikeln beskrivs flera kraftfulla funktioner i rutnätskontrollen. Du måste aktivera den nya rutnätsfunktionen för att du ska kunna använda dessa funktioner.
author: jasongre
ms.date: 04/25/2022
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
ms.openlocfilehash: 07791afb2de670a5b9b910e441395c2949460394
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124723"
---
# <a name="grid-capabilities"></a>Rutnätsmöjligheter

[!include [banner](../includes/banner.md)]

Den nya rutnätskontrollen innehåller flera användbara och kraftfulla funktioner som kan användas för att förbättra användarproduktiviteten, skapa mer intressanta vyer av dina data och få meningsfulla insikter om dina data. Den här artikeln kommer att omfatta följande funktioner: 

- Beräknar summor
- Skriva före systemet
- Utvärdera matematikuttryck 
- Gruppera data i en tabell (aktiveras separat med hjälp av funktionen **gruppering i rutnät**)
- Låsa kolumner (aktiveras separat med funktionen **Låsa kolumner i rutnät**)
- Autoanpassning av kolumnbredd
- Sträckbara kolumner

## <a name="calculating-totals"></a>Beräknar summor
I appar för ekonomi och drift har användare möjlighet att visa summor längst ned i numeriska kolumner i rutnät. Dessa summor visas i ett sidfotsavsnitt längst ned i rutnätet. 

### <a name="showing-the-grid-footer"></a>Visa rutnätets sidfot
Det finns ett sidfotsområde längst ned i alla tabellrutnät i appar för ekonomi och drift. Sidfoten kan visa värdefull information som är relaterad till de data som visas i rutnätet. Här följer några exempel på denna information:

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

Om beräkningen tar lång tid att slutföra kan du avbryta åtgärden genom att välja knappen **Avbryt**. Ibland är datauppsättningen för stor för att beräkna summor (en begränsning som din organisation implementerat) och du kommer istället att få ett meddelande om att filtrera dina data mer. 

> [!NOTE]
> Systemadministrationer kan ändra gränsen för antalet poster som är tillgängliga för beräkning av summor genom att justera parametern **Maximalt antal lokala poster för varje rutnät** på sidan **Prestandaalternativ för klient**. Standardvärdet är 25 000 poster. Administratörer bör vara försiktiga när de justerar det här värdet eftersom ett värde som är för stort kan fylla det tillgängliga minnet på användarens dator. Det rekommenderas att inte överskrida 50 000 poster.   

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
Användare har alltid kunnat exportera data från rutnät i appar för ekonomi och drift till Microsoft Excel med hjälp av funktionen **Exportera till Excel**. Möjligheten att mata in data före systemet gör emellertid att det nya rutnätet kan användas för att kopiera tabeller från Excel och klistra in dem direkt i rutnät appar för ekonomi och drift. Rutnätscellen som Inklistringsåtgärden initieras från avgör var den kopierade tabellen börjar klistras in. Innehållet i rutnätet skrivs över av innehållet i den kopierade tabellen, utom i två fall:

- Om antalet kolumner i den kopierade tabellen överstiger antalet kolumner som finns kvar i rutnätet, från inklistringsplatsen meddelas användaren att de extra kolumnerna har ignorerats. 
- Om antalet rader i den kopierade tabellen överstiger antalet rader i rutnätet, med början från inklistringsområdet, skrivs de befintliga cellerna över av det inklistrade innehållet och eventuella extra rader från den kopierade tabellen infogas som nya rader längst ned i rutnätet. 

## <a name="evaluating-math-expressions"></a>Utvärdera matematikuttryck
Som en produktivitetsförstärkning kan användarna ange matematiska formler i numeriska celler i ett rutnät. De behöver inte utföra beräkningen i en app utanför systemet. Om du till exempel anger **=15\*4** och tryck sedan på **Tabb** tangenten för att flytta ut ur fältet, utvärderas uttrycket och värdet **60** för fältet sparas.

Om du vill att ett värde ska beaktas som ett uttryck i systemet startar du värdet med ett likhetstecken (**=**). Mer information om operatorer och syntax som stöds finns i [matematiska symboler som stöds](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Gruppera data i tabellform
Företagsanvändare behöver ofta för att utföra ad hoc-analys av data. Även om detta kan utföras genom att exportera data till Microsoft Excel och med hjälp av fästpunktstabeller gör funktionen **Gruppera i rutnät**, som är beroende av den nya kontrollfunktionen för rutnät, det möjligt för användare att organisera sina tabelldata på intressanta sätt i appar för ekonomi och drift. När funktionen utökas kommer funktionen **Summor**, **Gruppera** också få meningsfulla insikter i data genom att tillhandahålla delsummor på gruppnivån.

Om du vill använda den här funktionen högerklickar du på den kolumn som du vill gruppera efter och väljer **gruppera efter denna kolumn**. Den här åtgärden sorterar data efter den markerade kolumnen, lägger till en ny **Gruppera efter**-kolumn i början av rutnätet och infogar "rubrikrader" i början av varje grupp. Dessa rubrikrader innehåller följande information om varje grupp:

- Datavärde för gruppen 
- Kolumnnamn (den här informationen är särskilt användbar när du har flera grupperingsnivåer)
- Antal data rader i den här gruppen
- Delsummor för alla kolumner som konfigurerats att visa summor

När [sparade vyer](saved-views.md) är aktiverade kan du spara gruppering som en del av en vy på sidor där frågor kan sparas i vyer. Exempel: sådana med stora visningsväljare. Se avsnittet [Växla mellan vyer](saved-views.md#switching-between-views) för mer information. 

### <a name="multiple-levels-of-grouping"></a>Flera nivåer av gruppering
När du har grupperat data efter en enda kolumn kan du gruppera data efter en annan kolumn genom att välja **Gruppera efter denna kolumn** i önskad kolumn. Den här processen kan upprepas tills du har fem kapslade nivåer för gruppering, vilket är det maximala djup som stöds. I det här läget kan du inte längre gruppera efter ytterligare kolumner.

Du kan när som helst ta bort grupperingen i valfri kolumn genom att högerklicka på kolumnen och välja **Dela upp**. Du kan också ta bort grupperingen från alla kolumner genom att välja **rutnätsalternativ** och sedan **Dela upp alla**.

### <a name="sorting-grouped-data"></a>Sortera grupperade data
När du har grupperat data efter en eller flera kolumner kan du ändra sorteringsriktningen för en valfri grupperingskolumn genom motsvarande kolumnrubrik. 

Hur du sorterar på icke-grupperade kolumner beror på produktversionen:

- Om du sorterar på en icke-grupperad kolumn i version 10.0.24 och tidigare, tas grupperingen bort från alla kolumner och data sorteras på den valda kolumnen. 
- I version 10.0.25 och senare, om du sorterar på en icke-grupperad kolumn, förblir grupperingen intakt och data sorteras inuti varje grupp, baserat på den valda kolumnen.

### <a name="expanding-and-collapsing-groups"></a>Expandera och komprimera grupper
Den första grupperingen av data kommer att ha alla grupper expanderade. Du kan skapa sammanfattade vyer över informationen genom att dölja enskilda grupper, eller så kan du använda expandera och komprimera grupp för att underlätta navigeringen mellan data. Om du vill expandera eller komprimera en grupp, markerar du knappen (>) i motsvarande grupprubrikrad. Observera att läget utöka/komprimera för enskilda grupper **inte** sparas i anpassning.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Markera och avmarkera rader på gruppnivå
På samma sätt som du kan markera (eller avmarkera) alla rader i rutnätet genom att markera kryssrutan högst upp i den första kolumnen i rutnätet kan du snabbt markera (eller avmarkera) alla raderna i en grupp genom att markera kryssrutan i motsvarande grupprubrikrad. Kryssrutan på raden i grupphuvudet visar alltid aktuell markeringsstatus för rader i den gruppen, oavsett om alla rader har markerats eller om alla rader är markerade, eller om bara vissa rader är markerade.

### <a name="hiding-column-names"></a>Dölja kolumnnamn
När du grupperar data är standardfunktionen att visa kolumnnamnet i grupprubrikraden. Du kan välja att utelämna kolumnnamnet i grupphuvud rader genom att välja **Rutnätsalternativ** > **Dölj gruppkolumnnamn**.

### <a name="grouping-on-date-and-time-columns"></a>Gruppering efter datum- och tidskolumner
Från och med version 10.0.24 för fälten Datum eller DateTime har alternativet lagts till i gruppering efter år, månad eller dag. Gruppen "värde" på motsvarande rubrikrad matchar formatet från det fältet. I fälten DateTime och Time kan du gruppera efter timme, minut eller sekund. 

## <a name="freezing-columns"></a>Låsa kolumner
En del kolumner i ett rutnät kan vara så viktiga för sammanhanget att du inte vill att de ska rulla ut ur visningen. Istället vill du att värdena i dessa kolumner alltid ska vara synliga. Funktionen **Lås kolumner i rutnät** flexibiliteten för användarna. 

Om du vill låsa en kolumn högerklickar du i kolumnens rubrik och väljer sedan **Lås kolumn**. Första gången du slutför det här steget blir den valda kolumnen den första kolumnen och kan inte längre rulla ut ur visningen. Alla efterföljande kolumner som du fryser läggs till höger om den sista låsta kolumnen. Du kan använda standardfunktionen Flytta om du vill beställa om låsta kolumner efter behov. Låsta kolumner kan emellertid inte flyttas så att de visas bland de olästa kolumnerna. Ej låsta kolumner kan emellertid inte flyttas så att de visas bland de låsta kolumnerna.

Om du vill låsa upp en kolumn högerklickar du i kolumnens rubrik och väljer sedan **Lås upp kolumn**. 

Observera att radurvalet och radstatuskolumnerna i det nya rutnätet alltid är låsta som de första två kolumnerna. När dessa kolumner tas med i ett rutnät visas de därför alltid för användaren, oavsett den vågräta rullningspositionen i rutnätet. Dessa två kolumner kan inte beställas om.

## <a name="autofit-column-width"></a>Autoanpassning av kolumnbredd
Användare i Excel kan automatiskt tvinga en kolumn att ändra storlek baserat på det innehåll som visas i kolumnen. Det gör du genom att dubbelklicka på storlekshanterarna i kolumnen eller genom att sätta fokus i kolumnrubriken och trycka på **A** (för autoanpassning). Den här funktionen är tillgänglig från och med version 10.0.23.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hur aktiverar jag den nya rutnätskontrollen i min miljö? 

Funktionen **Ny rutnätskontroll** är tillgänglig direkt i funktionshantering i alla miljöer. När funktionen har inaktiverats i funktionshanteringen kommer alla efterföljande användarsessioner att använda den nya rutnätskontrollen. 

Den här funktionen aktiveras som standard med start i version 10.0.21 och är avsedd att bli obligatorisk i oktober 2022.  

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Utvecklare] Avanmäl individuella sidor från att använda det nya rutnätet 
Om din organisation hittar en sida med vissa problem med att använda det nya rutnätet, finns det en API som gör det möjligt för ett enskilt formulär att använda den gamla rutnätskontrollen samtidigt som resten av systemet tillåter att den nya rutnätskontrollen används. Om du vill välja en enskild sida från det nya rutnätet lägger du till följande samtalspost `super()` i formulärets `run()`-metod.

```this.forceLegacyGrid();```

Denna API kommer att hedras tills den nya nätkontrollen blir obligatorisk. Den ändringen är just nu avsedd för oktober 2022. Om något problem kräver att denna API används rapporterar du dem till Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Tvinga en sida att använda det nya rutnätet efter att tidigare valt ut rutnätet
Om du har valt att inte använda det nya rutnätet för en enskild sida kanske du senare vill aktivera det nya rutnätet igen efter att de underliggande frågorna inte har lösts. Om du vill göra detta måste du bara ta bort samtalet `forceLegacyGrid()`. Ändringen börjar inte gälla förrän något av följande inträffar:

- **Omdistribuering av miljö**: När en miljö uppdateras och omplaceras rensas tabellen som lagrar sidorna som har valt bort det nya rutnätet (FormControlReactGridState) automatiskt.
- **Manuell clearing av registret**: För utvecklingsscenarier måste du använda SQL för att rensa tabellen FormControlReactGridState och sedan starta om AOS. Den här kombinationen av åtgärder återställer cachningen av sidor som har valt att inte använda det nya rutnätet.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Utvecklare] Välja enskilda rutnät utanför skriva före systemkapaciteten
Vissa scenarier har uppstått som inte lämpar sig för att fungera bra med funktionen *Skriva före systemet* för rutnätet. (Till exempel, en del kod som utlöses när en rad valideras gör att en datakällforskning utlöses, och forskningen kan sedan korrumpera oengagerade redigeringar på befintliga rader.) Om din organisation upptäcker ett sådant scenario finns ett API tillgängligt som låter en utvecklaren väljer bort ett individuellt rutnät från asynkron radvalidering och återgår till det äldre beteendet.

När asynkron radvalidering inaktiveras i ett rutnät kan användarna inte skapa någon ny rad eller flytta till en annan befintlig rad i rutnätet när det finns valideringsproblem på den aktuella raden. En sidoeffekt av denna åtgärd är att tabeller inte kan klistras in från Excel till rutnät i Ekonomi och drift.

För att välja bort asynkron radvalidering för ett enskilt rutnät, lägg till följande anrop efter `super()` i formulärets `run()`-metod.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Detta anrop ska endast anropas i sällsynta fall och ska inte vara norm för alla rutnät.
> - Du bör inte växla detta API vid körning efter formulärets in läses in.

## <a name="developer-size-to-available-width-columns"></a>[Utvecklare] kolumner med storlek till tillgänglig bredd
Om en utvecklare ställer in egenskapen **WidthMode** på **SizeToAvailable** för kolumner inuti det nya rutnätet, har de kolumnerna samma bredd som de skulle ha om egenskapen hade värdet **SizeToContent**. De sträcker sig däremot åt att använda valfri tillgänglig bredd i rutnätet. Om egenskapen har ställts in på **SizeToAvailable** för flera kolumner, delar alla dessa kolumner all tillgänglig bredd i rutnätet. Om en användare manuellt ändrar storleken på en av dessa kolumner blir kolumnen statisk. Den kommer att finnas kvar till den bredden och kan inte längre sträckas ut för att ta upp extra tillgängligt rutnäts bredd.

## <a name="known-issues"></a>Kända problem
I det här avsnittet finns en lista över kända problem för den nya rutnätskontrollen.

### <a name="open-issues"></a>Öppna ärenden
- När funktionen för **ny rutnätskontroll** aktiveras fortsätter vissa sidor att använda den befintliga rutnätskontrollen. Detta sker i följande situationer:
 
    - Det finns en kortlista på sidan som renderas i flera kolumner.
    - Det finns en grupperad kortlista på sidan.
    - En rutnätskolumn med en icke-reagerande utökningsbar kontroll.

    När en användare först stöter på en av dessa situationer, visas ett meddelande om att sidan ska uppdateras. När det här meddelandet visas fortsätter sidan att använda det befintliga rutnätet för alla användare tills nästa versionsuppdatering av produkten sker. En bättre hantering av dessa scenarier, så att det nya rutnätet kan användas, övervägs för framtida uppdateringar.

- [KB-4582758] Poster är suddiga när du ändrar zoom från 100 till någon annan procentsats
- [KB 4592012] Oväntat klientfel i IE11 när du klistrar in flera rader från Excel

    Microsoft följer ingen åtgärd för det här problemet


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

