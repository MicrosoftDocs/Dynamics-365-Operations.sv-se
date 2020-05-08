---
title: Rutnätsmöjligheter
description: I det här avsnittet beskrivs flera kraftfulla funktioner i rutnätskontrollen. Den nya rutnätsfunktionen måste aktiveras för att du ska kunna använda dessa funktioner.
author: jasongre
manager: AnnBe
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: fd45f71fc15e467c461433682310ab7b7cc0158a
ms.sourcegitcommit: 0d7b700950b1f95dc030ceab5bbdfd4fe1f79ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284414"
---
# <a name="grid-capabilities"></a>Rutnätsmöjligheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Den nya rutnätskontrollen innehåller flera användbara och kraftfulla funktioner som kan användas för att förbättra användarproduktiviteten, skapa mer intressanta vyer av dina data och få meningsfulla insikter om dina data. Den här artikeln kommer att omfatta följande funktioner: 

-  Beräknar summor
-  Gruppera data
-  Skriva före systemet
-  Utvärdera matematikuttryck 

## <a name="calculating-totals"></a>Beräknar summor
I Finance and Operations-appar har användare möjlighet att visa summor längst ned på numeriska kolumner i rutnät. Dessa summor visas i ett sidfotsavsnitt längst ned i rutnätet. 

### <a name="showing-the-grid-footer"></a>Visa rutnätets sidfot
Det finns ett sidfotsområde längst ned i alla tabell rutnät i Finance and Operations-program. Sidfoten kan visa värdefull information som är relaterad till de data som visas i rutnätet. Här följer några exempel på denna information:

- Antalet markerade rader i tabellen (om fler än en post har valts)
- Total summor längst ned i konfigurerade numeriska kolumner
- Antalet rader i datauppsättning 

Den här sidfoten är som standard dold, men den är lätt att aktivera. Om du vill visa sidfoten för ett rutnät högerklickar du på en kolumn rubrik i rutnätet och väljer alternativet **Visa sidfot**. När sidfoten har aktiverats för ett visst rutnät kommer denna inställning att kommas ihåg tills användaren väljer att dölja sidfoten, som du kan göra genom att högerklicka på en kolumnrubrik och välja **Dölj sidfot**.  Observera placeringen av åtgärden **Visa sidfot/Dölja sidfot** förväntas ligga i en senare uppdatering. 

### <a name="specifying-columns-with-totals"></a>Ange kolumner med summor
För närvarande kommer inga kolumner att konfigureras för att visa summor som standard. I stället betraktas detta som en enstaka inställningsaktivitet, på samma sätt som du justerar bredden på kolumner i rutnät. När du har angett att du vill visa summorna för en kolumn kommer den inställningen att komma ihåg nästa gång du besöker sidan.  

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

## <a name="grouping-data"></a>Gruppera data
Företagsanvändare behöver ofta för att utföra ad hoc-analys av data. Det kan du göra genom att exportera data till Microsoft Excel och med hjälp av pivottabeller och funktionen **gruppera** i tabellrutnät gör att användarna kan ordna sina data på intressanta sätt inom Finance and Operations-appar. När funktionen utökas kommer funktionen **Summor**, **Gruppera** också få meningsfulla insikter i data genom att tillhandahålla delsummor på gruppnivån.

Om du vill använda den här funktionen högerklickar du på den kolumn som du vill gruppera efter och väljer **gruppera efter denna kolumn**. Den här åtgärden sorterar data efter den markerade kolumnen, lägger till en ny grupp efter kolumn i början av rutnätet och infogar "rubrikrader" i början av varje grupp. Dessa rubrikrader innehåller följande information om varje grupp: 
-  Datavärde för gruppen 
-  Kolumnetikett (den här informationen är särskilt användbar när flera grupperingsnivåer stöds.)
-  Antal data rader i den här gruppen
-  Delsummor för alla kolumner som konfigurerats att visa summor

När [sparade vyer](saved-views.md) är aktiverad kan den här gruppen sparas med personlig anpassning som en del av en vy för snabbåtkomst nästa gång du besöker sidan.  

Om du väljer **gruppera efter denna kolumn** i en annan kolumn, ersätts den ursprungliga grupperingen eftersom det bara går att använda en grupperingsnivå i version 10.0.9 med plattformsuppdatering 33.

Om du vill ångra grupperingar i ett rutnät högerklickar du på grupperingskolumnen och väljer **Ta bort grupp**.  

## <a name="typing-ahead-of-the-system"></a>Skriva före systemet
I många affärsscenarier är möjligheten att snabbt registrera data i systemet mycket viktig. Innan den nya rutnätskontrollen introducerades kunde användarna bara ändra data på den aktuella raden. Innan de kan skapa en ny rad eller växla till en annan rad tvingades de vänta på att kontrollera ändringar i systemet. I ett försök att minska den tid som användarna väntar på att dessa valideringar ska slutföras, och för att förbättra användarproduktiviteten, justerar det nya rutnätet dessa valideringar så att de är asynkrona. Användaren kan därför flytta till andra rader och göra ändringar medan föregående radvalideringar väntar. 

För att det nya beteendet ska fungera har en ny kolumn för radstatus lagts till överst i rutnätet när rutnätet är i redigeringsläge. I den här kolumnen visas en av följande statusvärden:

- **Tom** – ingen statusbild anger att raden har sparats korrekt av systemet.
- **Bearbetning väntar** – denna status anger att ändringarna i raden ännu inte har sparats av servern men att de finns i en kö med ändringar som måste bearbetas. Innan du utför en åtgärd utanför rutnätet måste du vänta tills alla väntande ändringar har bearbetats. Dessutom är texten i dessa rader kursiv för att ange statusen som inte har sparats för raderna. 
- **Valideringsvarning** – den här statusen anger att systemet inte kan spara ändringarna på raden på grund av ett valideringsproblem. I det gamla rutnätet tvingades du tillbaka till raden för att åtgärda problemet direkt. I det nya rutnätet får du dock ett meddelande om att ett valideringsproblem har uppstått, men du kan bestämma när du vill åtgärda eventuella problem på raden. När du är redo att åtgärda problemet kan du manuellt flytta tillbaka fokus till raden. Du kan också välja åtgärden **Lös problemet**. Den här åtgärden flyttar omedelbart tillbaka fokus till den rad där problemet finns och gör att du kan redigera det inuti eller utanför rutnätet. Observera att bearbetningen av efterföljande väntande rader stoppas tills den här valideringsvarningen har lösts. 
- **Paus** – denna status anger att servern håller på att göra paus eftersom validering av raden utlöst en popup-dialogruta som kräver användarindata. Eftersom användaren kan mata in data på en annan rad visas inte dialogrutan direkt för den användaren. Den visas i stället när användaren väljer att återuppta bearbetningen. Denna status åtföljs av ett meddelande som informerar användaren om situationen. Meddelandet innehåller en åtgärd **återuppta bearbetning** som utlöser popup-dialogrutan.  
    
När användarna skriver in data i förväg på den plats där servern bearbetas, kan de förvänta sig en del graderingar i data inmatningsupplevelsen, t.ex. brist på sökningar, validering på kontrollnivå och registrering av standardvärden. Användare som behöver en nedrullningsbar lista för att hitta ett värde bör vänta på att servern ska fånga upp den aktuella raden. Verifiering och inmatning av standardvärden på kontrollnivå görs också när servern bearbetar raden.   

### <a name="pasting-from-excel"></a>Klistra in från Excel
Användare har alltid kunnat exportera data från rutnät i Finance and Operations-appar till Excel med hjälp av funktionen **exportera till Excel**. Möjligheten att föra in data i förväg av systemet gör dock att det nya rutnätet kan användas för att kopiera tabeller från Excel och klistra in dem direkt i rutnät Finance and Operations-appar. Rutnätscellen som Inklistringsåtgärden initieras från avgör var den kopierade tabellen börjar klistras in. Innehållet i rutnätet skrivs över av innehållet i den kopierade tabellen, utom i två fall:

- Om antalet kolumner i den kopierade tabellen överstiger antalet kolumner som finns kvar i rutnätet, från inklistringsplatsen meddelas användaren att de extra kolumnerna har ignorerats. 
- Om antalet rader i den kopierade tabellen överstiger antalet rader i rutnätet, med början från inklistringsområdet, skrivs de befintliga cellerna över av det inklistrade innehållet och eventuella extra rader från den kopierade tabellen infogas som nya rader längst ned i rutnätet. 

## <a name="evaluating-math-expressions"></a>Utvärdera matematikuttryck
Som en produktivitetsförstärkning kan användarna ange matematiska formler i numeriska celler i ett rutnät. De behöver inte utföra beräkningen i en app utanför systemet. Om du till exempel anger **=15\*4** och tryck sedan på **Tabb** tangenten för att flytta ut ur fältet, utvärderas uttrycket och värdet **60** för fältet sparas.

Om du vill att ett värde ska identifieras som ett uttryck i systemet startar du värdet med ett likhetstecken (**=**). Mer information om operatorer och syntax som stöds finns i [matematiska symboler som stöds](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="frequently-asked-questions"></a>Vanliga frågor
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Hur aktiverar jag den nya rutnätskontrollen i min miljö? 

**10.0.9/plattformsuppdatering 33 och senare** funktionen **ny rutnätskontroll** är tillgänglig direkt i funktionshantering i alla miljöer. Liksom andra offentliga förhandsgranskningsfunktioner är aktivering av den här funktionen i produktion är föremål för [Tilläggsavtal för användarvillkor](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/plattformsuppdatering 32 och 10.0.7/plattformsuppdatering 31** kan funktionen **ny rutnätskontroll** aktiveras i miljöer med nivå 1 (utv/test) och nivå 2 (sandbox) för att ge ytterligare tester och designändringar genom att följa stegen nedan.

1.  **Aktivera flygningen**: kör följande SQL-uttryck: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Återställ IIS** för att rensa den statiska förhandsversionscachen. 

3.  **Hitta funktionen**: gå till arbetsytan **Funktionshantering**. Om **ny rutnätskontroll** inte visas i listan över alla funktioner väljer du **Sök efter uppdateringar**.   

4.  **Aktivera funktionen**: Leta upp funktionen **Ny rutnätskontroll** i listan över funktioner och välj **Aktivera nu** i informationsfönstret. Observera att en uppdatering av webbläsaren krävs. 

Alla efterföljande användarsessioner börjar med att aktivera nya rutnätskontrollen.

## <a name="known-issues"></a>Kända problem
Det här avsnittet innehåller en lista med kända problem för den nya rutnätskontrollen medan funktionen är i förhandsgranskningsläge.  

### <a name="open-issues"></a>Öppna ärenden

- Kortlistor som återges som flera kolumner återges nu som en enda kolumn.
- Grupperade listor återges inte som grupper eller i separata kolumner.
- Knappbeskrivningar visas inte för bilder.
- Stödlinjerna visas inte för alla fälttyper.
- Ibland kan du inte klicka utanför rutnätet när du har flera markeringar i alla rader.
- Alternativen **validera** och **kopiera** uppgiftsinspelning är inte tillgängliga för kontroll av datum/nummer.

### <a name="fixed-as-part-of-10012"></a>Korrigerat som en del av 10.0.12

> [!Note]
> Följande information finns tillgänglig så att du kan planera i enlighet med detta. Mer information om målinriktad publicering av version 10.0.12 finns i [Tillgänglighet för tjänstuppdateringar](../../fin-ops/get-started/public-preview-releases.md).

- [Problem 429126] Kontroller utanför rutnätet uppdateras inte efter att sista posten har tagits bort.
- [Problem 430575] Register kontroller uppdaterar inte innehållet i visade objekt.
- [KB 4558570] Objekten visas fortfarande på sidan när posten har tagits bort.
- [KB 4558584] Negativa tal återges inte korrekt.
- [KB 4558575] Fält uppdateras inte efter att en rad ändring/rutnätsbehandling har fastnat efter att rader har tagits bort.
- [Problem 436980] Formatering som associeras med **ExtendedStyle** på listpanelen används inte.
- [KB 4558573] Valideringsfel kan inte åtgärdas när den obligatoriska ändringen ligger utanför rutnätet.
    
### <a name="quality-update-for-10011"></a>Kvalitetsuppdatering för 10.0.11

- [KB 4558381] Negativa tal återges inte korrekt, utan att användarna ibland blir låsta när det har uppstått valideringsproblem.

### <a name="fixed-as-part-of-10011"></a>Korrigerat som en del av 10.0.11

- [KB 4558374] Poster som kräver en dialogruta med polymorfa väljare kan inte skapas.
- [KB 4558382] Oväntade klientfel uppstår.
- [KB 4558375] Hjälptexten visas inte på kolumnerna i det nya rutnätet.
- [KB 4558376] Listpanelens rutnät återges inte på rätt höjd i Internet Explorer.
- [KB 4558377] Kolumner med kombinationsrutor som har en bredd på **SizeToAvailable** återges inte på vissa sidor.
- [KB 4549711] Rader i ett betalningsförslag kan inte tas bort korrekt när den nya rutnätskontrollen är aktiverad.
- [KB 4558378] Visning ibland öppnar fel post.
- [KB 4558379] Ett fel uppstår när sökningar öppnas där **ReplaceOnLookup**=**Nej**.
- [KB 4558380] Det tillgängliga utrymmet i rutnätet fylls inte direkt efter att en del av sidan har dolts.
- [Problem 432458] Tomma eller duplicerade rader visas i början av vissa underordnade samlingar.
- [KB 4558587] Referensgrupper som har kombinationsrutor för ersättningsfält visar inte värden.

### <a name="fixed-as-part-of-10010"></a>Korrigerat som en del av 10.0.10

- [Problem 414301] Vissa data från tidigare rader försvinner när nya rader skapas.
- [KB 4550367] Tidsvärden formateras inte korrekt.
- [KB 4549734] Aktiva rader behandlas inte som markerade om markeringskolumnen är dold.
- [Fel 417044] Det finns inget tomt rutnätsmeddelande för rutnät med listformat.
- [KB 4558367] Textmarkeringen är inkonsekvent när rader ändras.
- [KB 4558372] Det nya rutnätet fastnar i bearbetningsläget om antalet kolumner i innehållet som klistras in överskrider antalet återstående kolumner i rutnätet.
- [KB 4558368] Flerval via tangentbordet tillåts vid scenarier med ett val.
- [KB 4539058] Vissa rutnät (vanligtvis på snabbflikar) återges ibland inte (men de visas om du zoomar ut).
- [KB 4558369] Statusbilder försvinner i det hierarkiska rutnätet.
- [KB 4558370] En ny rad rullas inte in i bild.
- [KB 4549796] Det går inte att redigera värden i ett rutnät när det är i visningsläge.

### <a name="quality-update-for-1009platform-update-33"></a>Kvalitetsuppdatering för 10.0.9/plattformsuppdatering 33

- [KB 4550367] Tidsvärden formateras inte korrekt.
