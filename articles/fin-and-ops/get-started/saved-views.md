---
title: Sparade vyer
description: I det här avsnittet beskrivs hur du använder funktionerna för sparade vyer.
author: jasongre
manager: AnnBe
ms.date: 06/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: ea2f2dbd615480bb76e1d04a106ae69bf6f45f4b
ms.sourcegitcommit: fcae2e7938d7dbd94b76b0948b084d90d5fc919c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620788"
---
# <a name="saved-views"></a>Sparade vyer

[!include [banner](../includes/banner.md)]
[!include [private preview banner](../includes/private-preview-banner.md)]

## <a name="introduction"></a>Introduktion
Personlig anpassning spelar en viktig roll där användare och organisationer kan optimera användarupplevelsen för Microsoft Dynamics 365 for Finance and Operations för att uppfylla sina behov. Mer information om anpassning finns i [Anpassa användarupplevelsen](personalize-user-experience.md).

Med traditionell anpassning kan användarna bara ha en enda uppsättning anpassningar per formulär. Sparade vyer utökas vid anpassning på flera viktiga sätt:

-    Vyer gör det möjligt för användarna att ha flera namngivna uppsättningar med anpassningar per formulär som de snabbt kan växla mellan vid behov. På så sätt kan en användare skapa flera optimerade vyer för en sida, där varje vy har anpassats så att den passar affärsuppgifternas behov. 

-    Vyer som skapats för vissa sidtyper kan också inkludera användardefinierade filter eller sorteringar, som gör att användarna snabbt kan komma tillbaka till ofta filtrerade datauppsättningar. Mer information finns i avsnittet [Vilka sidor stöder vyer](saved-views.md#what-pages-support-views) för mer information. 

-    Vyer kan publiceras i säkerhetsroller, vilket innebär att alla användare med den rollen kan komma åt och använda den vyn, oavsett användarens möjlighet att anpassa. Med den här publiceringsfunktionen kan företag definiera företags standardvyer som är optimerade för deras verksamhet. Mer information finns i avsnittet [Hantera anpassningar på en befattningsnivå med vyer](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    Till skillnad från traditionell anpassning sparas inte vyer automatiskt när en användare utför explicita anpassningar eller filtrerar en lista. Det krävs explicita sparanden för att skapa en vy före eller efter att de ändringar som är associerade med vyn har gjorts och för att se till att definitioner inte oavsiktligt ändras av filter eller anpassningar som inte är avsedda för långsiktig användning.  

## <a name="switching-between-views"></a>Växla mellan vyer
När vyer har aktiverats för en miljö kommer alla sidor som har stöd för vyer att innehålla en komprimerad vyväljarkontroll längst upp i formuläret som visar namnet på den aktuella vyn.  

Det finns två storleksvariationer i vyväljaren: 

-   **Stora vyväljare**: sidor som är framträdande med en lista har en större vyväljare av några möjliga orsaker. Större delen av den största viktigaste vyväljaren visar sidorna där vyn kan innehålla användardefinierade filter. Eftersom filter inkluderas i vyerna är den större väljarstorleken också motiverad eftersom vynamnen ofta är den bästa beskrivningen av de data som visas på skärmen och det förväntas att användarna ska växla mellan vyer oftare på dessa sidtyper.  
 
-   **Smǻ vyväljare**: alla andra helsideformulär har en mindre vyväljare som visas bredvid sidrubriken. Vyer på dessa sidor innehåller bara anpassningar (och inte användardefinierade filter). På dessa sidor är formulärrubriken eller postrubriken ofta den viktigaste informationen längst upp i formuläret. Den mindre storleken återspeglar också en lägre förväntad frekvens av vyväxling på dessa sidor. 
 
Om du klickar på vyns namn öppnas vyväljaren och visar listan över tillgängliga vyer för den här sidan.

-    **Klassiskt läge**: Den klassiska vyn är sidans färdigkonfigurerade vy utan några uttryckliga anpassningar som används.  
-    **Personliga vyer**: vyerna utan hänglås representerar dina personliga vyer. Detta är vyer som du har skapat eller som en administratör har gett dig.  
-    **Låsta vyer**: vissa vyer (som den klassiska vyn och alla vyer som har publicerats i din roll) har ett hänglås bredvid dem i vyväljaren, vilket indikerar att du inte kan redigera dessa vyer. Implicita anpassningar runt sidanvändningen sparas automatiskt, till exempel för att ändra bredden på en rutnätskolumn eller för att expandera eller komprimera en snabbflik. Du kan dock göra en personlig vy baserat på en låst vy med åtgärden **Spara en kopia** om du har anpassningsprivilegier.
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
     1.    Välj **Spara en kopia**. 
     2.    Ange ett vynamn och en beskrivning (tillval).
     3.    Välj **Spara**.

## <a name="changing-the-default-view"></a>Ändra standardvyn
Standardvyn är den vy som systemet kommer att försöka öppna första gången du navigerar till sidan. Du bör ställa in det här till den vy som du förväntar dig att använda ofta.  

Om du vill ändra standardvyn för en sida ska du följa de här stegen: 
1.  Växla till den vy som du använder som standard. 
2.  Välj ett vynamn för att öppna vyväljaren. 
3.  Välj **mer** och sedan **fäst som standard**.  

När du skapar en ny vy (med hjälp av åtgärden **Spara en kopia**), kan du också göra den nya vyn till standardvy genom att ange alternativet **fäst som standard** innan du sparar vyn.  

Observera att i vissa fall körs inte frågan som är kopplad till standardvyn första gången du navigerar till en sida. Om du till exempel navigerar genom en panel till en sida, körs panelens fråga oavsett vilken fråga som är kopplad till standardvyn. Om du navigerar till en sida vars klassiskat vy redan har en definierad fråga kommer den ursprungliga frågan att köras ursprungligen i stället för standardvyfrågan. När detta inträffar får du ett meddelande om att ett informationsmeddelande visas när vyn läses in. När du byter vy efter det att sidan har lästs in ska vyfrågan köras som förväntat.

## <a name="managing-personal-views"></a>Hantera personliga vyer 
I dialogrutan **Hantera mina vyer** får du grundläggande underhållsfunktioner för dina personliga vyer och ordningen på vyer i vyväljaren. Du öppnar den här sidan genom att klicka på vyns namn för att öppna vyväljarens listruta, välj **Mer** och välj sedan **hantera mina vyer**.  

För en lista med tillgängliga vyer för sidan är följande åtgärder tillgängliga.  
-    **Ändra standardvyn**: Använd åtgärden **Fäst som standard** för att göra den markerade vyn till standardvy för den här sidan.  
-    **Ändra ordning på vyerna**Använd åtgärderna **flytta upp** och **flytta ned** om du vill ordna om vyerna i en viss ordning.  
-    **Byt namn på en vy**: Använd åtgärden **Byt namn** om du vill ändra namnet på den personliga vy som för närvarande är markerad. Den här åtgärden är inaktiverad för låsta vyer. 
-    **Ta bort en vy**: Använd åtgärden **Byt namn** om du vill ta bort den markerade vyn från sidan permanent. Det finns inget sätt att återställa en vy när du har tagit bort den.  

Ändringar som görs i den här dialogrutan börjar gälla när du har valt knappen **Spara**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Hantera anpassningar på organisationsnivå med vyer
Om du vill förstå förbättringarna i hantera anpassningar på organisationsnivå bör du först se hur hanteringen av anpassning som har utförts före vyer.  

Utan vyer kan administratörer tillämpa en uppsättning anpassningar för en sida för en användare, en grupp användare eller användare med hjälp av formuläret Anpassning. Om dessa användare har anpassningsbehörigheter används anpassningarna på den sidan. Det går dock inte att hindra användarna från att ytterligare anpassa sidan, vilket innebar att organisationen inte kunde garantera att användarna hade ett konsekvent användargränssnitt. Om någon av dessa användare inte har några anpassningsrättigheter laddades inte de anpassningar som de har fått av en administratör. Vidare, om nya användare har anställts i en organisation, måste administratörerna manuellt läsa in en uppsättning anpassningar för användaren. Ingen automatisk mekanism för att ange en viss uppsättning anpassningar bör vara tillgänglig för den användaren.

Med funktionen sparade vyer blir det betydligt enklare att administrera anpassningar, främst på grund av möjligheten att publicera vyer till säkerhetsroller. När en vy har har publiceras kan alla användare med den rollen kan komma åt och använda den vyn, oavsett användarens möjlighet att anpassa. Även om varje användare har en kopia av den publicerade vyn där sidanvändning (implicita anpassningar) används automatiskt kan inga användare spara uttryckliga anpassningar eller uppdateringar av frågan i den publicerade vyn (vilket innebär att publicerade vyer låses). Dessutom, om nya användare ges en roll som vyn har publicerats på, visas automatiskt de vyer som associeras med deras roller utan någon åtgärd från administratören. Om en användare ändrar roller i en organisation kommer de vyer som har associerats med deras gamla roll inte längre att vara tillgängliga för dem, utan att administratören vidtar någon åtgärd. Uppdateringar av en publicerad vy kan enkelt distribueras till användare genom att publicera vyn på rätt säkerhetsroller.

Med den här publiceringsfunktionen kan företag definiera företags standardvyer som är optimerade för deras verksamhet, riktade mot användare i specifika säkerhetsroller.  

## <a name="publishing-views"></a>Publicerande vyer
Under publiceringsprocessen kan vyer tilldelas till en eller flera säkerhetsroller, vilket innebär att alla användare med den rollen kan komma åt och använda den vyn, även om de inte kan redigera vyn. För närvarande har endast systemadministratörer behörighet för åtgärder **publicering** på vyväljarens rullgardinsmeny.  

Gör så här om du vill publicera en vy: 
1.  Skapa och spara en personlig kopia av vyn som du vill publicera. 
2.  Med den vyn som nu laddas, välj vynamnet för att öppna vyväljarens rullgardinsmeny. 
3.  Välj knappen **Mer** och välj sedan **Publicera**. Dialogrutan Publicera öppnas.  
4.  Ange ett vynamn och en beskrivning (tillval) för vyn. Det här är det namn som de användare som får den här vyn visas i vyväljaren. Observera att inga dubblettnamn för publicerade vyer tillåts för en sida, även om listan över roller som de tillämpas på skiljer sig åt.  
5.  Lägg till de säkerhetsroller som motsvarar de användare som kommer att få vyn.  
6.  Markera **Publicera**.

Observera att i vissa miljöer kan det ta en stund (upp till en timme) innan användarna ser den publicerade vyn.

## <a name="modifying-a-published-view"></a>Ändra en publicerad vy
När du har publicerat en vy kanske du upptäcker att du vill göra ändringar i en publicerad vy. Även om du inte kan göra live-ändringar i en publicerad vy, eftersom dessa vyer är låsta för redigering för alla användare (inklusive utgivare), kan du publicera en vy igen för att göra uppdateringar.  

Om de ändringar som du vill göra i en publicerad vy bara innefattar publiceringsparametrarna (namnet och beskrivningen för vyn, eller vilka säkerhetsroller vyn publiceras till), gör du följande: 
1.  Växla till den publicerade vyn för de parametrar som du vill uppdatera. 
2.  Välj **Publicera** från vyväljarens listruta. 
3.  Välj **ja** om du vill uppdatera den befintliga vyn (eller **nej** om du vill publicera den med ett annat namn).
4.  Uppdatera vyns namn, beskrivning och/eller säkerhetsroller. 
5.  Markera **Publicera**. 
6.  Om du har uppdaterat namnet på den publicerade vyn måste du också ta bort den publicerade vyn med det gamla namnet (mer information finns i avsnittet **hantera publicerade vyer**). 

Om ändringarna i den publicerade vyn innefattar ändring av anpassningar eller filter som hör till vyn gör du så här: 
1.  Växla till den publicerade vyn som du vill ändra. 
2.  Spara en kopia av den publicerade vyn om du vill skapa ett lokalt utkast av den publicerade vyn. 
3.  Ändra det lokala utkastet med ändringarna som krävs.
4.  Publicera vyn med det ursprungliga namnet. 

## <a name="managing-published-views"></a>Hantera publicerade vyer
På samma sätt som hantring av personliga vyer ger dialogrutan **Hantera mina vyer** användare med publiceringsprivilegier grundläggande underhållsmöjligheter över den sidans publicerade vyer (förutom de egna personliga vyerna). Du öppnar den här sidan genom att klicka på vyns namn för att öppna vyväljarens listruta, välj **Mer** och välj sedan **hantera mina vyer**.

Medan alla användare ser fliken **mina vyer** med deras personliga vyer ser även användare med publiceringsprivilegier fliken **publicerad** som visar alla publicerade vyer för den sidan. Eftersom det kan finnas flera användare som publicerar vyer är det viktigt att du kan hantera den fullständiga listan med publicerade vyer, oavsett om du var den användare som faktiskt publicerade vyn.

För en lista med alla publicerade vyer för sidan är följande åtgärder tillgängliga. 

-    **Publicera**: Använd åtgärden **publicera** om du vill publicera en vy på nytt med ändrade publiceringsparametrar (namn, beskrivning, säkerhetsroller).  
-    **Ta bort**: Använd åtgärden **Ta bort** för att ta bort en publicerad vy permanent. Den här åtgärden tar bort vyn för alla användare i systemet.  
 
Ändringar som görs i den här dialogrutan börjar gälla när du har valt knappen **Spara**.

## <a name="frequently-asked-questions"></a>Vanliga frågor
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Hur aktiverar jag sparade vyer i min miljö? 
Om du vill aktivera sparade vyer ska en systemadministratör göra följande: 
1.  Gå till sidan **anpassning** med hjälp av navigeringssökning. 
2.  Välj fliken **Inställningar**.
3.  Ge alternativet **Aktivera sparade vyer** värdet **Ja**.

När den här funktionen har aktiverats startar alla följande användarsessioner med aktiverade vyer.  

Observera att om anpassningar inaktiveras för miljön aktiveras vyer även om du följer stegen ovan. Detta beror på att vyerna bygger på under systemet för anpassning.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Vad händer med befintliga anpassningar när vyer aktiveras? 
När vyer aktiveras sparas alla befintliga anpassningar för en användare och ett formulär i en ny vy som kallas **Min vy** som automatiskt ställs in som standardvy. Detta är avsett att säkerställa att det finns en enhetlig användarupplevelse innan och när vyer har aktiverats, utom för vyväljaren som visas i formulär.  

### <a name="what-pages-support-views"></a>Vilka sidor stöder vyer? 
Vyer är tillgängliga på de flesta men inte alla sidor i Finance and Operations. Vyer är för närvarande tillgängliga på alla helskärmssidor utom för instrumentpaneler och arbetsytor. Icke helskärmssidor, som omfattar dialogrutor, nedrullningsbara dialogrutor, uppslag, utökade förhandsgranskningar, stöder för närvarande inte vyer. Visa stöd för fler sidtyper, t.ex. arbetsytor och dialogrutor, kan komma att överväga för framtida uppdateringar.   

### <a name="who-is-allowed-to-publish-views"></a>Vem har tillåtelse att publicera vyer?
För närvarande är systemadministratörer de enda användare som har behörighet att publicera vyer.  En ny säkerhetsroll är planerad, vilket ger kunderna större flexibilitet för vem som kan publicera dem.  

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Varför kan jag inte spara filter med den här vyn? 
Det finns några anledningar till varför ett filter kanske inte visas för att spara med en vy: 

- Sidan kanske inte stöder sparande av filter som en del av vydefinitionen. Observera att endast sidor med stor vyväljare tillåter att anpassningar och ändringar av frågor sparas som en vy. Se avsnittet "Växla vyer" för mer information. 

- Om vyn är standardvy och navigeringssökvägen till sidan innehåller en fråga, vyns fråga kanske inte tillämpas från början. De två primära scenarierna för detta är: 
     - Om du navigerar från en panel till en sida, körs frågan oavsett vilken fråga som är kopplad till standardvyn. 
     - Om du navigerar till en sida och den startpuunkten inkluderar en fråga kommer den ursprungliga frågan att köras ursprungligen i stället för standardvyfrågan. 
     
  Du bör få en avisering när detta inträffar av ett informationsmeddelande när vyn läses in. Du kan också bekräfta genom att växla till den här vyn efter att sidan har lästs in, eftersom det gör att vyfrågan körs oavsett.  

- Den aktuella sidan kanske inte stöder vyer på rätt sätt, eftersom frågan i vyn kan ignoreras helt. Rapportera alla sådana instanser via **feedback**-funktionen. Gå till sidan feedback genom att klicka på **hjälp och support** och sedan på **feedback**.  
