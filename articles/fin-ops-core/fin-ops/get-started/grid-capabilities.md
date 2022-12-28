---
title: Rutnätsfunktioner
description: I den här artikeln beskrivs flera kraftfulla funktioner i rutnätskontrollen. Du måste aktivera den nya rutnätsfunktionen för att du ska kunna använda dessa funktioner.
author: jasongre
ms.date: 08/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6d14bba13dbf701a8c27c10ac2d318b071092bc1
ms.sourcegitcommit: 77ffeccffff28fbb6ff576864d7abddd412cdab6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2022
ms.locfileid: "9852395"
---
# <a name="grid-capabilities"></a>Rutnätsmöjligheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Den nya rutnätskontrollen innehåller flera användbara och kraftfulla funktioner som kan användas för att förbättra användarproduktiviteten, skapa mer intressanta vyer av dina data och få meningsfulla insikter om dina data. Den här artikeln kommer att omfatta följande funktioner: 

- Visar beräknade värden 
- Skriva före systemet
- Utvärdera matematikuttryck 
- Gruppera data i en tabell (aktiveras separat med hjälp av funktionen **gruppering i rutnät**)
- Låsa kolumner (aktiveras separat med funktionen **Låsa kolumner i rutnät**)
- Autoanpassning av kolumnbredd
- Sträckbara kolumner

## <a name="showing-calculated-values"></a>Visar beräknade värden
I appar för ekonomi och drift kan användarna visa ett beräknat värde för varje numerisk kolumn i ett rutnät. Dessa beräknade värden visas i ett sidfotsavsnitt längst ned i rutnätet.

[![Visar beräknade värden i rutnät.](./media/grids-aggregation.png)](./media/grids-aggregation.png)

I versioner före 10.0.29 är summan det enda beräknade värde som stöds. Från och med version 10.0.29 kan användarna efter att de har aktiverat funktionen **Utökade sammansättningsfunktioner för rutnät** kan användare välja bland följande fyra beräknade värden:

- Minimum
- Maximum
- Totalt
- Genomsnitt

En enstaka kolumn kan endast visa en typ av beräknat värde. Varje kolumn i rutnätet kan dock konfigureras så att olika typer av beräknade värden visas.

### <a name="showing-the-grid-footer"></a>Visa rutnätets sidfot
Det finns ett sidfotsområde längst ned i alla tabellrutnät i appar för ekonomi och drift. Sidfoten kan visa värdefull information som är relaterad till de data som visas i rutnätet. Här följer några exempel på denna information:

- Antalet markerade rader i tabellen (om fler än en post har valts)
- Beräknade värden längst ned i konfigurerade, numeriska kolumner (till exempel totalsummor)
- Antalet rader i datauppsättning 

Den här sidfoten är som standard dold, men den är lätt att aktivera. Om du vill visa sidfoten för ett rutnät, välj knappen **rutnätsalternativet** i rutnätsrubriken och välj alternativet **Visa sidfot**. När du har slå på sidfoten för ett visst rutnät kommer den inställningen att föra in en dag tills användaren väljer att dölja sidfoten. Du döljer sidfoten genom att välja **Dölj sidfot** på menyn **Rutnätsalternativ**.

### <a name="specifying-columns-with-calculated-values"></a>Ange kolumner med beräknade värden
För närvarande visar inga kolumner beräknade värden som standard. I stället betraktas inställningen som en enstaka aktivitet, på samma sätt som du justerar bredden på kolumner i rutnät. När du har angett att du vill visa ett beräknat värde för en kolumn kommer den inställningen att komma ihåg nästa gång du besöker sidan.

Du kan konfigurera en kolumn på två sätt för att visa ett beräknat värde:

- Markera och håll (eller högerklicka) i kolumnen som du vill visa ett beräknat värde för. Om funktionen **Utökade sammansättningsfunktioner för rutnät** har aktiverats väljer du **Visa kolumnsummor** och väljer sedan önskat beräknat värde. Om den funktionen inte är aktiverad väljer du **Summera den här kolumnen**. Den här åtgärden medför att tre händelser inträffar:

    1. Rutnätets sidfot blir synlig. 
    2. Din inställning för att visa ett beräknat värde för kolumnen sparas. 
    3. Den önskade beräkningen initieras för kolumnen och alla andra kolumner som du tidigare konfigurerat för att visa ett beräknat värde. Tiden som krävs för att visa de beräknade värdena beror på datauppsättningens storlek.

- När sidfoten är synlig väljer du **Visa summa** (eller **Välj beräknat värde** om funktionen **Utökade sammansättningsfunktioner för rutnät** är aktiverad) i sidfotsområdet längst ner i kolumnen som du vill se ett beräknat värde för. Om det inte finns några konfigurerade kolumner visas knappen i sidfoten för alla numeriska kolumner.

    När minst en kolumn har konfigurerats för att visa ett beräknat värde blir knappen **Visa summa** (eller **Välj beräknat värde**) bara tillgänglig för hovra eller fokus. Om du väljer knappen sparar du bara din inställning för att visa ett beräknat värde i den här kolumnen, så att inställningen tillämpas vid framtida besök på sidan. I sidfoten markeras det här läget med ett streck som visas i kolumnen. (Observera att det beräknade värdet visas direkt om datauppsättningen är liten nog.)

Om du gör ett misstag och inte längre vill se ett beräknat värde i en specifik kolumn, välj och håll ned (eller högerklicka) i kolumnen och välj sedan **Dölj summa** (eller **Visa kolumnsummor \> Ingen** om funktionen **Utökade sammansättningsfunktioner för rutnät** har aktiverats). Du kan också välja **Dölj summa** (eller **Dölj beräknat värde**) i sidfoten i den kolumnen. Den här inställningen kommer också att sparas för framtida besök på sidan. 

### <a name="calculating-aggregate-values"></a>Beräkna aggregerade värden
När du går till en sida där sidfoten är synlig och kolumner redan har konfigurerats för att visa beräknade värden, kanske dessa värden inte visas i sidfoten. Beteendet beror på storleken på datauppsättningen på sidan. Om datauppsättningen är tillräckligt liten de beräknade värdena automatiskt tillsammans med antalet rader i datauppsättningen. Om det finns streck i sidfoten under kolumnerna som du har konfigurerat är datasetet för stort för att systemet ska kunna visa beräknade värden omedelbart. I det här fallet krävs det en explicit åtgärd för att beräkna värdena. Beräkna värdena genom att klicka på knappen **Beräkna** i sidfoten. Alternativt kan du välja och hålla ned (eller högerklicka) i en kolumn som du vill se summan för och sedan välja **Summera kolumnen** (eller **Visa kolumnsummor** och sedan det önskade beräknade värdet om **Utökade sammansättningsfunktioner för rutnät** är aktiverad).

Om beräkningen tar lång tid att slutföra kan du avbryta åtgärden genom att välja **Avbryt**. Ibland blir datauppsättningen för stor för att beräkna aggregerade värden (en gräns som läggs på av din organisation). I så fall får du i stället ett meddelande om att du behöver filtrera dina data mer.

> [!NOTE]
> Systemadministratörer kan ändra gränsen för antalet poster som är tillgängliga för beräkning av sammanställningar genom att justera parametern **Maximalt antal lokala poster för varje rutnät** på sidan **Prestandaalternativ för klient**. Standardvärdet är 25 000 poster. Administratörer bör vara försiktiga när de justerar det här värdet eftersom ett värde som är för stort kan fylla det tillgängliga minnet på användarens dator. Det rekommenderas att värdet inte överskrider 50 000 poster.

Beräknade värden uppdateras automatiskt när du uppdaterar, tar bort eller skapar rader i datauppsättningen.

## <a name="typing-ahead-of-the-system"></a>Skriva före systemet
I många affärsscenarier är möjligheten att snabbt registrera data i systemet mycket viktig. Innan den nya rutnätskontrollen introducerades kunde användarna bara ändra data på den aktuella raden. Efter att de har gjort ändringar i en rad kan därför användare inte växla till en annan rad eller skapa en ny rad förrän systemet kunde validera ändringarna i den aktuella raden och (i fallet med att skapa rader) körde all logik som är kopplad till skapandet av en ny rad. För att minska den tid som användare spenderar på att vänta på att dessa operationer ska slutföras, och för att förbättra användarens produktivitet, justerar det nya rutnätet dessa åtgärder så att de är asynkrona. Användaren kan skapa nya rader eller flytta till andra rader och göra ändringar medan radvalideringar och logik för att skapa rader väntar. 

[![Skriva före systemet.](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

För att det nya beteendet ska fungera har en ny kolumn för radstatus lagts till höger om kolumnen för radval när rutnätet är i redigeringsläge. I den här kolumnen visas en av följande statusvärden:

- **Tom** – ingen statusbild anger att raden har sparats korrekt av systemet.
- **Bearbetning väntar** – denna status anger att ändringarna i raden ännu inte har sparats av servern men att de finns i en kö med ändringar som måste bearbetas. Innan du utför en åtgärd utanför rutnätet måste du vänta tills alla väntande ändringar har bearbetats. Dessutom är texten i dessa rader kursiv för att ange statusen som inte har sparats för raderna. 
- **Ogiltigt tillstånd** – denna status anger att en del varningar eller meddelanden utlöstes under bearbetningen av raden och kan ha hindrat systemet från att spara ändringarna på den raden. I det gamla rutnätet, om åtgärden inte sparades tvingades du tillbaka till raden för att åtgärda problemet direkt. I det nya rutnätet får du dock ett meddelande om att ett valideringsproblem har uppstått, men du kan bestämma när du vill åtgärda eventuella problem på raden. När du är redo att åtgärda problemet kan du manuellt flytta tillbaka fokus till raden. Du kan också välja åtgärden **Lös problemet**. Den här åtgärden flyttar omedelbart tillbaka fokus till den rad där problemet finns och gör att du kan redigera det inuti eller utanför rutnätet. Observera att bearbetningen av efterföljande väntande rader stoppas tills den här valideringsvarningen har lösts. 
- **Paus** – denna status anger att servern håller på att göra paus eftersom validering av raden utlöst en popup-dialogruta som kräver användarindata. Eftersom användaren kan mata in data på en annan rad visas inte dialogrutan direkt för den användaren. Den visas i stället när användaren väljer att återuppta bearbetningen. Denna status åtföljs av ett meddelande som informerar användaren om situationen. Meddelandet innehåller en åtgärd **återuppta bearbetning** som utlöser popup-dialogrutan.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Differenser när data förs in i systemet
När du anger data i förväg från den plats där systemet bearbetas kan du förvänta dig några ändringar av inmatningsupplevelsen:

- Du kommer att märka att det inte finns några listrutan, fältvärden valideras inte efter att du har flyttat till en annan kolumn i samma rad och kolumnerna visar inte inledningsvis standardvärden. Detta beteende inträffar när du skapar eller uppdaterar i förväg av systemet. Efter det att systemet har redigerar upp dig på det ställe där du redigerar kommer standarderfarenheten att återupptas. Om du gör ändringar i ett fält som vanligtvis får ett standardvärde, åsidosätter dina ändringar standardvärdet i fältet när servern börjar bearbeta raden.
- Om du skapar en ny rad med hjälp av **nedåtpilstangenten**, visas alla kolumner i rutnätet som redigerbara. Som standard sätts fokus i den första kolumnen på den nya raden. Den här kolumnen kanske inte är samma kolumn som mottog det ursprungliga fokuset i det äldre rutnätet, eller samma kolumn som får fokus när du valt knappen **ny**. Din organisation kan anpassa systemet och ändra kolumnen som får det inledande fokuset när **nedåtpilstangenten** markeras. Mer information finns i avsnittet [Ange kolumnen som får det initiala fokuset när nya rader skapas med hjälp av nedåtpilen](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key). Oavsett personanpassning kan du optimera varje rutnät för inmatning av data. Du kan beställningsfält så att den första kolumnen är den kolumn där du vill börja ange data. Du kanske också vill beställa om fälten i allmänhet för datainmatning, minska flikarna och dölja de fält som inte krävs för datainmatning i den här vyn.

### <a name="pasting-from-excel"></a>Klistra in från Excel
Användare har alltid kunnat exportera data från rutnät i appar för ekonomi och drift till Microsoft Excel med hjälp av funktionen **Exportera till Excel**. Möjligheten att mata in data före systemet gör emellertid att det nya rutnätet kan användas för att kopiera tabeller från Excel och klistra in dem direkt i rutnät appar för ekonomi och drift. Rutnätscellen som Inklistringsåtgärden initieras från avgör var den kopierade tabellen börjar klistras in. Innehållet i rutnätet skrivs över av innehållet i den kopierade tabellen, utom i två fall:

- Om antalet kolumner i den kopierade tabellen överstiger antalet kolumner som finns kvar i rutnätet, från inklistringsplatsen meddelas användaren att de extra kolumnerna har ignorerats. 
- Om antalet rader i den kopierade tabellen överstiger antalet rader i rutnätet, med början från inklistringsområdet, skrivs de befintliga cellerna över av det inklistrade innehållet och eventuella extra rader från den kopierade tabellen infogas som nya rader längst ned i rutnätet. 

## <a name="evaluating-math-expressions"></a>Utvärdera matematikuttryck
Som en produktivitetsförstärkning kan användarna ange matematiska formler i numeriska celler i ett rutnät. De behöver inte utföra beräkningen i en app utanför systemet. Om du till exempel anger **=15\*4** och tryck sedan på **Tabb** tangenten för att flytta ut ur fältet, utvärderas uttrycket och värdet **60** för fältet sparas.

[![Utvärdera matematikuttryck.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Om du vill att ett värde ska beaktas som ett uttryck i systemet startar du värdet med ett likhetstecken (**=**). Mer information om operatorer och syntax som stöds finns i [matematiska symboler som stöds](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

Vid version 10.0.29 har möjligheten att utvärdera numeriska kontroller utökas och är nu även tillgänglig utanför rutnätet.

## <a name="grouping-tabular-data"></a>Gruppera data i tabellform
Företagsanvändare behöver ofta för att utföra ad hoc-analys av data. Även om denna analys kan utföras genom att exportera data till Microsoft Excel och med hjälp av fästpunktstabeller gör funktionen **Gruppera i rutnät**, som är beroende av den nya kontrollfunktionen för rutnät, det möjligt för användare att organisera sina tabelldata på intressanta sätt i appar för ekonomi och drift. Eftersom denna funktion utökar funktionen **Beräknade värden**, **Gruppera** låter dig få meningsfulla insikter i data genom att tillhandahålla beräknade värden (till exempel delsummor) på gruppnivå.

[![Gruppera data i ett rutnät.](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

Om du vill använda den här funktionen högerklickar du på den kolumn som du vill gruppera efter och väljer **gruppera efter denna kolumn**. Den här åtgärden sorterar data efter den markerade kolumnen, lägger till en ny **Gruppera efter**-kolumn i början av rutnätet och infogar "rubrikrader" i början av varje grupp. Dessa rubrikrader innehåller följande information om varje grupp:

- Datavärde för gruppen 
- Kolumnnamn (den här informationen är särskilt användbar när du har flera grupperingsnivåer)
- Antal data rader i den här gruppen
- Beräknade värden för alla konfigurerade kolumner (till exempel delsummor om kolumnen är konfigurerad att visa en summa)

När [sparade vyer](saved-views.md) är aktiverade kan du spara gruppering som en del av en vy på sidor där frågor kan sparas i vyer. Exempel: sådana med stora visningsväljare. Se avsnittet [Växla mellan vyer](saved-views.md#switching-between-views) för mer information. 

### <a name="multiple-levels-of-grouping"></a>Flera nivåer av gruppering
När du har grupperat data efter en enda kolumn kan du gruppera data efter en annan kolumn genom att välja **Gruppera efter denna kolumn** i önskad kolumn. Den här processen kan upprepas tills du har fem kapslade nivåer för gruppering, vilket är det maximala djup som stöds. I det här läget kan du inte längre gruppera efter ytterligare kolumner.

Du kan när som helst ta bort grupperingen i valfri kolumn genom att högerklicka på kolumnen och välja **Dela upp**. Du kan också ta bort grupperingen från alla kolumner genom att välja **rutnätsalternativ** och sedan **Dela upp alla**.

### <a name="sorting-grouped-data"></a>Sortera grupperade data
När du har grupperat data efter en eller flera kolumner kan du ändra sorteringsriktningen för en valfri grupperingskolumn genom motsvarande kolumnrubrik. 

Om du sorterar på en icke-grupperad kolumn förblir gruppningen intakt. Informationen sorteras i varje grupp, baserat på den valda kolumnen.

### <a name="expanding-and-collapsing-groups"></a>Expandera och komprimera grupper
Den första grupperingen av data kommer att ha alla grupper expanderade. Du kan skapa sammanfattade vyer över informationen genom att dölja enskilda grupper, eller så kan du använda expandera och komprimera grupp för att underlätta navigeringen mellan data. Om du vill expandera eller komprimera en grupp, markerar du knappen (>) i motsvarande grupprubrikrad. Observera att läget utöka/komprimera för enskilda grupper **inte** sparas i anpassning.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Markera och avmarkera rader på gruppnivå
På samma sätt som du kan markera (eller avmarkera) alla rader i rutnätet genom att markera kryssrutan högst upp i den första kolumnen i rutnätet kan du snabbt markera (eller avmarkera) alla raderna i en grupp genom att markera kryssrutan i motsvarande grupprubrikrad. Kryssrutan på raden i grupphuvudet visar alltid aktuell markeringsstatus för rader i den gruppen, oavsett om alla rader har markerats eller om alla rader är markerade, eller om bara vissa rader är markerade.

### <a name="hiding-column-names"></a>Dölja kolumnnamn
När du grupperar data är standardfunktionen att visa kolumnnamnet i grupprubrikraden. Du kan välja att utelämna kolumnnamnet i grupphuvud rader genom att välja **Rutnätsalternativ** > **Dölj gruppkolumnnamn**.

### <a name="grouping-on-date-and-time-columns"></a>Gruppering efter datum- och tidskolumner
När du grupperar på fälten Datum eller DateTime har du alternativet att gruppera efter år, månad eller dag. Gruppen "värde" på motsvarande rubrikrad matchar formatet från det fältet. I fälten DateTime och Time kan du gruppera efter timme, minut eller sekund.

> [!IMPORTANT]
> Användarna kan för närvarande inte lägga till en grupperingskolumn efter att de har gruppering i ett segment i en datum- eller tidskolumn.

## <a name="freezing-columns"></a>Låsa kolumner
En del kolumner i ett rutnät kan vara så viktiga för sammanhanget att du inte vill att de ska rulla ut ur visningen. Istället vill du att värdena i dessa kolumner alltid ska vara synliga. Funktionen **Lås kolumner i rutnät** flexibiliteten för användarna. 

[![Frysa kolumner i rutnät.](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Om du vill låsa en kolumn högerklickar du i kolumnens rubrik och väljer sedan **Lås kolumn**. Första gången du slutför det här steget blir den valda kolumnen den första kolumnen och kan inte längre rulla ut ur visningen. Alla efterföljande kolumner som du fryser läggs till höger om den sista låsta kolumnen. Du kan använda standardfunktionen Flytta om du vill beställa om låsta kolumner efter behov. Låsta kolumner kan emellertid inte flyttas så att de visas bland de olästa kolumnerna. Ej låsta kolumner kan emellertid inte flyttas så att de visas bland de låsta kolumnerna.

Om du vill låsa upp en kolumn högerklickar du i kolumnens rubrik och väljer sedan **Lås upp kolumn**. 

Observera att radurvalet och radstatuskolumnerna i det nya rutnätet alltid är låsta som de första två kolumnerna. När dessa kolumner tas med i ett rutnät visas de därför alltid för användaren, oavsett den vågräta rullningspositionen i rutnätet. Dessa två kolumner kan inte beställas om.

## <a name="autofit-column-width"></a>Autoanpassning av kolumnbredd
Användare i Excel kan automatiskt tvinga en kolumn att ändra storlek baserat på det innehåll som visas i den. Du kan bara dubbelklicka på storlekshanterarna i kolumnen. Du kan också lägga fokus i kolumnrubriken och sedan välja **A**-nyckeln (för autoanpassning).

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hur aktiverar jag den nya rutnätskontrollen i min miljö? 

Funktionen **Ny rutnätskontroll** är tillgänglig direkt i funktionshantering i alla miljöer. När funktionen har inaktiverats i funktionshanteringen kommer alla efterföljande användarsessioner att använda den nya rutnätskontrollen. 

Den här funktionen har som standard aktiverats i version 10.0.21. Målet är att den ska bli obligatorisk i oktober 2022.

## <a name="developer-topics"></a>Utvecklingsämnen 

### <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Utvecklare] Avanmäl individuella sidor från att använda det nya rutnätet 
Om din organisation hittar en sida med vissa problem med att använda det nya rutnätet, finns det en API som gör det möjligt för ett enskilt formulär att använda den gamla rutnätskontrollen samtidigt som resten av systemet tillåter att den nya rutnätskontrollen används. Om du vill välja en enskild sida från det nya rutnätet lägger du till följande samtalspost `super()` i formulärets `run()`-metod.

```this.forceLegacyGrid();```

Denna API avakteras så småningom så att det går att ta bort den äldre rutnätskontrollen. Den kommer dock att vara tillgänglig i minst 12 månader efter det att avvisningen har avsekats. Om något problem kräver att denna API används rapporterar du dem till Microsoft.

#### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Tvinga en sida att använda det nya rutnätet efter att tidigare valt ut rutnätet
Om du har valt att inte använda det nya rutnätet för en enskild sida kanske du senare vill aktivera det nya rutnätet igen efter att de underliggande frågorna inte har lösts. Om du vill göra detta måste du bara ta bort samtalet `forceLegacyGrid()`. Ändringen börjar inte gälla förrän något av följande inträffar:

- **Omdistribuering av miljö**: När en miljö uppdateras och omplaceras rensas tabellen som lagrar sidorna som har valt bort det nya rutnätet (FormControlReactGridState) automatiskt.
- **Manuell clearing av registret**: För utvecklingsscenarier måste du använda SQL för att rensa tabellen FormControlReactGridState och sedan starta om AOS. Den här kombinationen av åtgärder återställer cachningen av sidor som har valt att inte använda det nya rutnätet.

### <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Utvecklare] Välja enskilda rutnät utanför skriva före systemkapaciteten
Vissa scenarier har uppstått som inte lämpar sig för att fungera bra med funktionen *Skriva före systemet* för rutnätet. (Till exempel, en del kod som utlöses när en rad valideras gör att en datakällforskning utlöses, och forskningen kan sedan korrumpera oengagerade redigeringar på befintliga rader.) Om din organisation upptäcker ett sådant scenario finns ett API tillgängligt som låter en utvecklaren väljer bort ett individuellt rutnät från asynkron radvalidering och återgår till det äldre beteendet.

När asynkron radvalidering inaktiveras i ett rutnät kan användarna inte skapa någon ny rad eller flytta till en annan befintlig rad i rutnätet när det finns valideringsproblem på den aktuella raden. En sidoeffekt av denna åtgärd är att tabeller inte kan klistras in från Excel till rutnät i Ekonomi och drift.

För att välja bort asynkron radvalidering för ett enskilt rutnät, lägg till följande anrop efter `super()` i formulärets `run()`-metod.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Detta anrop ska endast anropas i sällsynta fall och ska inte vara norm för alla rutnät.
> - Du bör inte växla detta API vid körning efter formulärets in läses in.

### <a name="developer-size-to-available-width-columns"></a>[Utvecklare] kolumner med storlek till tillgänglig bredd
Om en utvecklare ställer in egenskapen **WidthMode** på **SizeToAvailable** för kolumner inuti det nya rutnätet, har de kolumnerna samma bredd som de skulle ha om egenskapen hade värdet **SizeToContent**. De sträcker sig däremot åt att använda valfri tillgänglig bredd i rutnätet. Om egenskapen har ställts in på **SizeToAvailable** för flera kolumner, delar alla dessa kolumner all tillgänglig bredd i rutnätet. Om en användare manuellt ändrar storleken på en av dessa kolumner blir kolumnen statisk. Den kommer att finnas kvar till den bredden och kan inte längre sträckas ut för att ta upp extra tillgängligt rutnäts bredd.

### <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Utvecklare] Ange kolumnen som får det initiala fokuset när nya rader skapas med hjälp av nedåtpilen
Som diskuterades i avsnittet [Skillnader vid inmatning av data före systemet](#differences-when-entering-data-ahead-of-the-system) för "Skriv före systemet" är aktiverad och en användare skapar en ny rad med hjälp av tangenten **nedåtpil** är standardbeteendet att lägga fokus i den första kolumnen i den nya raden. Den här erfarenheten kan skilja sig från erfarenheten i det äldre rutnätet eller när en **ny** knapp väljs.

Användare och organisationer kan skapa sparade vyer som har optimerats för datainmatning. (Du kan till exempel ändra ordning på kolumner så att den första kolumnen är den som du vill börja ange data i.) Dessutom, från och med version 10.0.29, kan organisationer justera detta beteende genom att använda metoden **selectedControlOnCreate()**. Den här metoden låter en utvecklare specificera kolumnen som ska få det initiala fokuset när en ny rad skapas med hjälp av **nedåtpilen**. Som indata tar denna API kontroll-ID som motsvarar kolumnen som ska få det inledande fokuset.

### <a name="developer-handling-grids-with-non-react-extensible-controls"></a>[Utvecklare] Hantera rutnät med kontroller som inte är utdragbara kontroller
När ett rutnät läses in innebär det att en utökningsbar kontroll som inte är stödbaserad av ett rutnät påträffas, och i stället tvingar systemet det äldre rutnätet att återges. När en användare stöter på denna situation för första gången visas ett meddelande som anger att sidan måste uppdateras. Därefter läser den här sidan in det äldre rutnätet automatiskt utan ytterligare meddelanden till användarna till nästa systemuppdatering. 

För att lösa den här situationen permanent kan författare av extensible control skapa en version av den här kontrollen som ska användas i rutnätet.  När den väl utvecklats kan X++-klassen för kontrollen dekoreras med attributet **FormReactControlAttribute** för att ange platsen för React-paketet som ska laddas för den kontrollen. Se `SegmentedEntryControl` klassen som ett exempel.  

## <a name="known-issues"></a>Kända problem
I det här avsnittet finns en lista över kända problem för den nya rutnätskontrollen.

### <a name="open-issues"></a>Öppna ärenden
- När funktionen för **ny rutnätskontroll** aktiveras fortsätter vissa sidor att använda den befintliga rutnätskontrollen. Detta sker i följande situationer:
 
    - [Löst] Problem 762533: Oväntat klientfel när du väljer en rad i en kortlista.
    - [Löst] Det finns en kortlista på sidan som renderas i flera kolumner.
        - Den här typen av kortlista stöds av den **nya rutnätskontrollen** som startar i version 10.0.30. All användning av forceLegacyGrid() detta syfte kan tas bort. 
    - [Löst] Det finns en grupperad kortlista på sidan.
        - Grupperade kortlistor stöds av **nya rutnätskontrollen** som startar i version 10.0.30. All användning av forceLegacyGrid() detta syfte kan tas bort. 
    - [Löst] En rutnätskolumn med en icke-reagerande utökningsbar kontroll.
        - Utökningsbara kontroller kan tillhandahålla en React-version av deras kontroll som kommer att laddas när de placeras i rutnätet och justera deras kontrolldefinition för att ladda denna kontroll när den används i rutnätet. Mer information finns i motsvarande utvecklaravsnitt. 

    När en användare först stöter på en av dessa situationer, visas ett meddelande om att sidan ska uppdateras. När det här meddelandet visas fortsätter sidan att använda det befintliga rutnätet för alla användare tills nästa versionsuppdatering av produkten sker. En bättre hantering av dessa scenarier, så att det nya rutnätet kan användas, övervägs för framtida uppdateringar.

- [KB-4582758] Poster är suddiga när du ändrar zoom från 100 till någon annan procentsats

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

