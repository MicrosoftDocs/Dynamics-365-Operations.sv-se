---
title: Sparade vyer
description: I det här avsnittet beskrivs hur du använder funktionerna för sparade vyer.
author: jasongre
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: fe79558b9d2ac4ef1c83918b949d11983b2cc0d8
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260493"
---
# <a name="saved-views"></a>Sparade vyer

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Introduktion
Personlig anpassning spelar en viktig roll där användare och organisationer kan optimera användarupplevelsen för att uppfylla sina behov. Mer information om anpassning finns i [Anpassa användarupplevelsen](personalize-user-experience.md).

Med traditionell anpassning kan användarna bara ha en enda uppsättning anpassningar per formulär. Sparade vyer utökas vid anpassning på flera viktiga sätt:

-    Vyer gör det möjligt för användarna att ha flera namngivna uppsättningar med anpassningar per formulär som de snabbt kan växla mellan vid behov. På så sätt kan en användare skapa flera optimerade vyer för en sida, där varje vy har anpassats så att den passar affärsuppgifternas behov. 

-    Vyer som skapats för vissa sidtyper kan också inkludera användardefinierade filter eller sorteringar, som gör att användarna snabbt kan komma tillbaka till ofta filtrerade datauppsättningar. Mer information finns i avsnittet [Vilka sidor stöder vyer](saved-views.md#what-pages-support-views) för mer information. 

-    Vyer kan publiceras till användare i specifika säkerhetsroller och specifika juridiska personer. Därför kan alla användare som har en angiven roll och åtkomst till en angiven juridisk person komma åt och använda den vyn, även om användaren kanske inte kan anpassa den. Med den här publiceringsfunktionen kan företag definiera företags standardvyer som är optimerade för deras verksamhet. Mer information finns i avsnittet [Hantera anpassningar på en befattningsnivå med vyer](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    Till skillnad från traditionell anpassning sparas inte vyer automatiskt när en användare utför explicita anpassningar eller filtrerar en lista. Det krävs explicita sparanden för att skapa en vy före eller efter att de ändringar som är associerade med vyn har gjorts och för att se till att definitioner inte oavsiktligt ändras av filter eller anpassningar som inte är avsedda för långsiktig användning.  

-    Vyer kan läggas till i arbetsytor som paneler, listor eller länkar. Därför kan en filtrerad datauppsättning placeras på en arbetsyta och användarna kan associera en uppsättning anpassningar som är relevanta för den datauppsättningen med panel eller länk.

## <a name="switching-between-views"></a>Växla mellan vyer
När vyer har aktiverats för en miljö kommer alla sidor som har stöd för vyer att innehålla en komprimerad vyväljarkontroll längst upp i formuläret som visar namnet på den aktuella vyn.  

Det finns två storleksvariationer i vyväljaren: 

-   **Stora vyväljare**: sidor som är framträdande med en lista har en större vyväljare av några möjliga orsaker. Större delen av den största viktigaste vyväljaren visar sidorna där vyn kan innehålla användardefinierade filter. Eftersom filter inkluderas i vyerna är den större väljarstorleken också motiverad eftersom vynamnen ofta är den bästa beskrivningen av de data som visas på skärmen och det förväntas att användarna ska växla mellan vyer oftare på dessa sidtyper.  
 
-   **Små vyväljare**: alla andra helsideformulär (med undantag för arbetsytor och instrumentpanelen) har en mindre vyväljare som visas bredvid sidrubriken. Vyer på dessa sidor innehåller bara anpassningar (och inte användardefinierade filter). På dessa sidor är formulärrubriken eller postrubriken ofta den viktigaste informationen längst upp i formuläret. Den mindre storleken återspeglar också en lägre förväntad frekvens av vyväxling på dessa sidor. 
 
Om du klickar på vyns namn öppnas vyväljaren och visar listan över tillgängliga vyer för den här sidan.

-    **Standardvy**: Vyn **Standard** (tidigare kallad **klassisk** vy) är sidans färdigkonfigurerade vy, där inga uttryckliga anpassningar tillämpas.
-    **Personliga vyer**: vyerna utan hänglås representerar dina personliga vyer. Detta är vyer som du har skapat eller som en administratör har gett dig.  
-    **Låsta vyer**: vissa vyer (t.ex. vyn **Standard** och alla vyer som publiceras till din roll) har symbolen för hänglås intill dem i vyväljaren. Den här symbolen visar att du inte kan redigera dessa vyer. Implicita anpassningar som återspeglar sid användningen sparas dock automatiskt. De här implicita anpassningarna inkluderar en ändring av bredden på en rutnätskolumn, eller en utvidgning eller komprimering av en snabbflik. Du kan dock använda åtgärden **Spara som** för att göra en personlig vy baserat på en låst vy om du har anpassningsprivilegier.
-    **Nya vyer**: publicerade vyer som inte har öppnats ännu är avgränsade med en gnista till vänster om vyns namn.  

Om du vill växla till en annan vy öppnar du först vyväljaren och väljer sedan den vy som du vill läsa in. 

## <a name="creating-and-modifying-views"></a>Skapa och ändra vyer
Till skillnad från traditionell anpassning sparas inte vyer automatiskt när en användare utför explicita anpassningar (eller filtrerar en lista). En uttrycklig åtgärd krävs för att spara ändringarna i en vy. Denna leverntör använder flexibilitet för att skapa en vy före eller efter att de ändringar som är associerade med vyn har gjorts och säkerställer även att definitioner inte oavsiktligt ändras av engångsfilter eller anpassningar. Observera att implicita anpassningar (t.ex. expandera eller dölja en snabbflik eller ändra bredden på en rutnätskolumn) sparas automatiskt öven för låsta vyer. 

Om du vill se till att vyns aktuella läge är känt när du börjar att göra ändringar i en vy genom att utföra en explicit anpassning eller filtrering, visas en asterisk bredvid det aktuella vynamnet som anger att du tittar på en osparad, modifierad version av den vyn.

Om du vill spara ändringarna följer du stegen nedan.
1.  Välj ett vynamn för att öppna vyväljaren.
2.  Så här ändrar du den befintliga vyn:
     1. Välj **Spara**. Observera att den här åtgärden inte kan aktiveras för låsta vyer. 
3.  För att skapa en ny vy:
     1.    Välj **Spara som**. 
     2.    Ange ett vynamn och en beskrivning (tillval).
     3.    Välj **Spara**.

## <a name="changing-the-default-view"></a>Ändra standardvyn
Standardvyn är den vy som systemet kommer att försöka öppna första gången du navigerar till sidan. Du bör ställa in det här till den vy som du förväntar dig att använda oftast.  

Om du vill ändra standardvyn för en sida ska du följa de här stegen: 
1.  Växla till den vy som du använder som standard. 
2.  Välj ett vynamn för att öppna vyväljaren. 
3.  Välj **mer** och sedan **fäst som standard**.  

När du skapar en ny vy (med hjälp av åtgärden **Spara som**), kan du också göra den nya vyn till standardvy genom att ange alternativet **fäst som standard** innan du sparar vyn.

Observera att i vissa fall körs inte frågan som är kopplad till standardvyn första gången du navigerar till en sida. Om du till exempel navigerar genom en panel till en sida, körs panelens fråga oavsett vilken fråga som är kopplad till standardvyn. Om du navigerar till en sida vars standard vy redan har en definierad fråga kommer den ursprungliga frågan att köras i stället för standardvyfrågan. När detta inträffar får du ett meddelande om att ett informationsmeddelande visas när vyn läses in. När du byter vy efter det att sidan har lästs in ska vyfrågan köras som förväntat. Från och med version 10.0.10 plattformsuppdatering 34 kommer informationsmeddelandet att innehålla en inbäddad åtgärd som tillåter att du läser in standardvisningens fråga direkt.

## <a name="managing-personal-views"></a>Hantera personliga vyer 
I dialogrutan **Hantera mina vyer** får du grundläggande underhållsfunktioner för dina personliga vyer och ordningen på vyer i vyväljaren. Du öppnar den här sidan genom att klicka på vyns namn för att öppna vyväljarens listruta, välj **Mer** och välj sedan **hantera mina vyer**.  

För en lista med tillgängliga vyer för sidan är följande åtgärder tillgängliga.  
-    **Ändra standardvyn**: Använd åtgärden **Fäst som standard** för att göra den markerade vyn till standardvy för den här sidan.  
-    **Ändra ordning på vyerna**Använd åtgärderna **flytta upp** och **flytta ned** om du vill ordna om vyerna i en viss ordning.  
-    **Byt namn på en vy**: Använd åtgärden **Byt namn** om du vill ändra namnet på den personliga vy som för närvarande är markerad. Den här åtgärden är inaktiverad för låsta vyer. 
-    **Ta bort en vy**: Använd åtgärden **Byt namn** om du vill ta bort den markerade vyn från sidan permanent. Det finns inget sätt att återställa en vy när du har tagit bort den.  

Ändringar som görs i den här dialogrutan börjar gälla när du har valt knappen **Spara**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Hantera anpassningar på organisationsnivå med vyer
För att hjälpa dig förstå hur sparade vyer hjälper till att förbättra hanteringen av anpassningar på organisationsnivå, beskriver detta avsnitt vissa skillnader i anpassningshantering med och utan funktionen sparade vyer.

Utan vyer kan administratörer tillämpa en uppsättning anpassningar för en sida för en användare eller en grupp användare via sidan Anpassning. Om dessa användare har anpassningsbehörigheter används anpassningarna på den sidan. Det går dock inte att hindra användarna från att ytterligare anpassa sidan, vilket innebar att organisationen inte kunde garantera att användarna hade ett konsekvent användargränssnitt. Om någon av dessa användare inte har några anpassningsrättigheter laddades inte de anpassningar som de har fått av en administratör. Vidare, om nya användare har anställts i en organisation, måste administratörerna manuellt läsa in en uppsättning anpassningar för användaren. Ingen automatisk mekanism för att ange en viss uppsättning anpassningar bör vara tillgänglig för användare i den rollen.

Med funktionen sparade vyer blir det betydligt enklare att administrera anpassningar, främst på grund av möjligheten att publicera vyer till grupper av användare. När en vy har publicerats kan alla användare som har en av de definierade säkerhetsrollerna och har åtkomst till de angivna juridiska personerna se och använda vyn, även om användaren kanske inte kan anpassa den. Även om varje användare har en kopia av den publicerade vyn där sidanvändning (implicita anpassningar) används automatiskt kan inga användare spara uttryckliga anpassningar eller uppdateringar av frågan i den publicerade vyn. Publicerade vyer är med andra ord låsta. Om nya användare ges roller i juridiska personer som vyerna publicerats på, visas dessutom automatiskt de vyer som associeras med deras roller och juridiska enheter. Ingen ytterligare åtgärd krävs av administratören. Detta gäller även om användare ändrar roller i en organisation eller har åtkomst till olika juridiska personer, kanske de inte längre kan komma åt de vyer som tidigare har publicerats på dem. Ingen ytterligare åtgärd krävs av administratören.

Uppdateringar av en publicerad vy kan enkelt distribueras till användare genom att publicera vyn på rätt säkerhetsroller och juridiska personer.

Med den här publiceringsfunktionen kan företag definiera företags standardvyer som är optimerade för deras verksamhet, riktade mot användare i specifika säkerhetsroller.  

## <a name="publishing-views"></a>Publicerande vyer
Under publiceringsprocessen kan vyer tilldelas till en eller flera säkerhetsroller för en eller flera juridiska personer. Därför kan alla användare som har åtkomst till en juridisk person och som har tilldelats en av dessa roller komma åt och använda vyerna, även om de inte kan redigera dem. Systemadministratörer har åtkomst till åtgärden **publicering** på vyväljarens rullgardinsmeny. Andra betrodda användare i organisationen kan emellertid också ges åtkomst att visa publicering via administratörsrollen **sparade vyer**.

Gör så här om du vill publicera en vy: 
1.  Skapa och spara en personlig kopia av vyn som du vill publicera. 
2.  Med den vyn som nu laddas, välj vynamnet för att öppna vyväljarens rullgardinsmeny. 
3.  Välj knappen **Mer** och välj sedan **Publicera**. Dialogrutan Publicera öppnas.  
4.  Ange ett vynamn och en beskrivning (tillval) för vyn. Det namn du anger är det namn som de användare som får den här vyn visas i vyväljaren. Namnen på publicerade vyer för en sida måste vara unika. Inga dubblettnamn tillåts även om listan över roller eller juridiska personer som vyerna tillämpas på skiljer sig åt.
5.  Lägg till de säkerhetsroller som motsvarar de användare som inriktas mot denna vy.
6. Lägg till de juridiska personer som den här vyn ska vara tillgänglig för. 
7. [10.0.9/plattformsuppdatering 33 eller senare] kontrollera om vyn ska publiceras som standardvy för de valda användarna. Att göra en vy som standard innebär att detta är den vy som användarna kommer att se nästa gång de öppnar målsidan. Då ändras standardvyn för dessa användare. användare kan dock fortfarande ändra sin standardvy när publiceringen har skett.    
8.  Markera **Publicera**.

Observera att i vissa miljöer kan det ta en stund (upp till en timme) innan användarna ser den publicerade vyn.

## <a name="modifying-a-published-view"></a>Ändra en publicerad vy
När du har publicerat en vy kanske du upptäcker att du vill göra ändringar i en publicerad vy. Även om du inte kan göra live-ändringar i en publicerad vy, eftersom dessa vyer är låsta för redigering för alla användare (inklusive utgivare), kan du publicera en vy igen för att göra uppdateringar.  

Om de ändringar som du vill göra i en publicerad vy bara innefattar publiceringsparametrarna (namnet och beskrivningen för vyn, eller vilka säkerhetsroller vyn publiceras till), gör du följande: 
1.  Växla till den publicerade vyn för de parametrar som du vill uppdatera. 
2.  Välj **Publicera** från vyväljarens listruta. 
3.  Välj **ja** om du vill uppdatera den befintliga vyn (eller **nej** om du vill publicera den med ett annat namn).
4.  Uppdatera vyns namn, beskrivning och/eller säkerhetsroller. 
5.  Markera **Publicera**. 
6.  [10.0.8/plattformsuppdatering 32 eller tidigare] Om du har uppdaterat namnet på den publicerade vyn måste du också ta bort den publicerade vyn med det gamla namnet (mer information finns i avsnittet **hantera publicerade vyer**). 
7. [10.0.9/plattformsuppdatering 33 eller senare] om du ursprungligen har valt att den här publicerade vyn ska vara standardvy, blir den standardvyn för dessa användare igen efter publicera igen.  

Om ändringarna i den publicerade vyn innefattar ändring av anpassningar eller filter som hör till vyn gör du så här: 
1.  Växla till den publicerade vyn som du vill ändra. 
2.  Spara en kopia av den publicerade vyn om du vill skapa ett lokalt utkast av den publicerade vyn. 
3.  Ändra det lokala utkastet med ändringarna som krävs.
4.  Publicera vyn med det ursprungliga namnet. 

## <a name="managing-published-views"></a>Hantera publicerade vyer
På samma sätt som hantering av personliga vyer ger dialogrutan **Hantera mina vyer** användare med publiceringsprivilegier grundläggande underhållsmöjligheter över den sidans publicerade vyer (förutom de egna personliga vyerna). Du öppnar den här sidan genom att klicka på vyns namn för att öppna vyväljarens listruta, välj **Mer** och välj sedan **hantera mina vyer**.

Medan alla användare ser fliken **mina vyer** med deras personliga vyer ser även användare med publiceringsprivilegier fliken **publicerad** som visar alla publicerade vyer för den sidan. Eftersom det kan finnas flera användare som publicerar vyer är det viktigt att du kan hantera den fullständiga listan med publicerade vyer, oavsett om du var den användare som faktiskt publicerade vyn.

För en lista med alla publicerade vyer för sidan är följande åtgärder tillgängliga. 

-    **Publicera**: Använd åtgärden **publicera** om du vill publicera en vy på nytt efter att publiceringsparametrar (namn, beskrivning, säkerhetsroller eller juridiska personer) ändras.
-    **Ta bort**: Använd åtgärden **Ta bort** för att ta bort en publicerad vy permanent. Den här åtgärden tar bort vyn för alla användare i systemet. Borttagningen av publicerade vyer börjar gälla när knappen **Spara** har valts.

## <a name="frequently-asked-questions"></a>Vanliga frågor
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Hur aktiverar jag sparade vyer i min miljö? 
Obs! funktionen **sparade vyer** kräver att anpassningssystemet i Finance and Operations aktiveras. Om anpassningar inaktiveras för hela miljön inaktiveras vyer även om du följer stegen nedan. 

**10.0.9/plattformsuppdatering 33 och senare** funktionen **sparade vyer** är tillgänglig direkt i funktionshantering i alla miljöer. Liksom andra offentliga förhandsgranskningsfunktioner är aktivering av den här funktionen i produktion är föremål för [Tilläggsavtal för användarvillkor](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/plattformsuppdatering 32 och tidigare** funktionen **sparade vyer** kan aktiveras i miljöer med nivå 1 (utv/test) och nivå 2 (sandbox) för att ge ytterligare tester och designändringar genom att följa stegen nedan.

1.  **Aktivera flygningen**: kör följande SQL-uttryck: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Återställ IIS** för att rensa den statiska förhandsversionscachen. 

3.  **Hitta funktionen**: gå till arbetsytan **Funktionshantering**. Om **sparade vyer** inte visas i listan väljer du **Kontrollera uppdateringar**.   

4.  **Aktivera funktionen**: Leta upp funktionen **Sparade vyer** i listan över funktioner och välj **Aktivera nu** i informationsfönstret.

Alla efterföljande användarsessioner börjar med att sparade vyer aktiveras.


### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Vad händer med befintliga anpassningar när vyer aktiveras? 
När vyer aktiveras sparas alla befintliga anpassningar för en användare och ett formulär i en ny vy som kallas **Min vy** som automatiskt ställs in som standardvy. Detta är avsett att säkerställa att det finns en enhetlig användarupplevelse innan och när vyer har aktiverats, utom för vyväljaren som visas i formulär.  

### <a name="what-pages-support-views"></a>Vilka sidor stöder vyer? 
Vyer är tillgängliga på de flesta men inte alla sidor. Vyer är för närvarande tillgängliga på alla helskärmssidor utom för instrumentpaneler och arbetsytor. Icke helskärmssidor, som omfattar dialogrutor, nedrullningsbara dialogrutor, uppslag, utökade förhandsgranskningar, stöder för närvarande inte vyer. Visa stöd för fler sidtyper, t.ex. arbetsytor och dialogrutor, kan komma att överväga för framtida uppdateringar.   

### <a name="who-is-allowed-to-publish-views"></a>Vem har tillåtelse att publicera vyer?
Endast systemadministratörer och användare som har tilldelats administratörrollen **Sparade vyer** har behörighet att publicera vyer. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Varför kan jag inte spara filter med den här vyn? 
Det finns några anledningar till varför ett filter kanske inte visas för att spara med en vy: 

- Sidan kanske inte stöder sparande av filter som en del av vydefinitionen. Observera att endast sidor med stor vyväljare tillåter att anpassningar och ändringar av frågor sparas som en vy. Se avsnittet **Växla vyer** för mer information. 

- Sidan i fråga kanske inte stöder vyer på rätt sätt, eftersom den kan ignorera vyfrågan helt eller kan fungera på en temporär tabell vars data inte är beständiga. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Vilka data kommer jag att se när jag besöker en sida? 
För sidor med små visningsväljare (endast anpassningar kan sparas i vyn) visas samma data som när du besöker sidan. 

För sidor med stora visningsväljare (anpassningar och frågor kan sparas i vyn) visas i huvudsak de data som länkas till den fråga som är kopplad till standardvyn. Det finns två huvudsakliga undantag från detta: - Om du navigerar från en panel till en sida, körs frågan oavsett vilken fråga som är kopplad till standardvyn. Om du har skapat den panelen efter att vyer har aktiverats öppnas sidan med den vy som är kopplad till den panelen.   
     - Om du navigerar till en sida och den startpunkten inkluderar en fråga kommer den ursprungliga frågan att köras ursprungligen i stället för standardvyfrågan. Du bör varnas när detta sker via via ett informationsmeddelande visas när vyn läses in. Du kan också bekräfta genom att växla till den här vyn efter att sidan har lästs in, eftersom det gör att vyfrågan körs oavsett.  


