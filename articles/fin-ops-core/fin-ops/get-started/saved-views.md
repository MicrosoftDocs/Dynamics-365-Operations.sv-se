---
title: Sparade vyer
description: I den här artikeln beskrivs hur du använder funktionerna för sparade vyer.
author: jasongre
ms.date: 07/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 6faf71ec5d14584034f9107c33ccce1cd1d393c7
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220345"
---
# <a name="saved-views"></a>Sparade vyer

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

[!INCLUDE [PEAP](../../../includes/peap-1.md)]

## <a name="introduction"></a>Introduktion

Personlig anpassning spelar en viktig roll där användare och organisationer kan optimera användarupplevelsen för att uppfylla sina behov. Mer information om anpassning finns i [Anpassa användarupplevelsen](personalize-user-experience.md).

Traditionell anpassning låter användarna bara ha en enda uppsättning anpassningar per sida. Funktionen **Sparade vyer** utökas vid anpassning på flera viktiga sätt:

- Vyer gör det möjligt för användarna att ha flera namngivna uppsättningar med anpassningar per formulär som de snabbt kan växla mellan vid behov. På så sätt kan en användare skapa flera optimerade vyer för en sida, där varje vy har anpassats så att den passar affärsuppgifternas behov. 
- Vyer som skapats för vissa sidtyper kan också inkludera användardefinierade filter eller sorteringar, som gör att användarna snabbt kan komma tillbaka till ofta filtrerade datauppsättningar. Mer information finns i avsnittet [Vilka sidor stöder vyer](saved-views.md#what-pages-support-views) för mer information. 
- Vyer kan publiceras till användare i specifika säkerhetsroller och specifika juridiska personer. Därför kan alla användare som har en angiven roll och åtkomst till en angiven juridisk person komma åt och använda den vyn, även om användaren inte har behörighet att anpassa den. Med den här publiceringsfunktionen kan företag definiera företags standardvyer som är optimerade för deras verksamhet. Mer information finns i avsnittet [Hantera anpassningar på en befattningsnivå med vyer](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).
- Till skillnad från traditionell anpassning sparas inte vyer automatiskt när en användare utför anpassningar eller filtrerar en lista. Det krävs explicit sparande för att ge användarna flexibiliteten att skapa en vy före eller efter att de ändringar som är associerade med vyn har gjorts. Detta krav garanterar också att visningsdefinitioner inte oavsiktligt ändras av filter eller anpassningar som inte är avsedda för långsiktig användning. Artiklar som automatiskt sparas som en del av den vanliga sidanvändningen (t.ex. kolumnbredder eller avsnittets utökade eller dolda status) sparas per vy.
- Vyer kan läggas till i arbetsytor som paneler, listor eller länkar. Därför kan en filtrerad datauppsättning placeras på en arbetsyta och användarna kan associera en uppsättning anpassningar som är relevanta för den datauppsättningen med panel eller länk.

## <a name="switching-between-views"></a>Växla mellan vyer

När vyer har aktiverats för en miljö kommer alla sidor som har stöd för vyer att innehålla en komprimerad vyväljarkontroll längst upp som visar namnet på den aktuella vyn.

Det finns två storleksvariationer i vyväljaren: 

- **Stora vyväljare**: sidor som är framträdande med en lista har en större vyväljare av några möjliga orsaker. Större delen av den största viktigaste vyväljaren visar sidorna där vyn kan innehålla användardefinierade filter och sorterar. Eftersom filter och sorterar inkluderas i vyerna är den större väljarstorleken också motiverad eftersom vynamnen ofta är den bästa beskrivningen av de data som visas på skärmen och det förväntas att användarna ska växla mellan vyer oftare på dessa sidtyper. Gruppering i ett rutnät kan också sparas i vyer på en sida med stora visningsväljare. 
    
    [![Stor vyväljare som stöder frågeändringar i vyn.](./media/views-largeViewSelector.png)](./media/views-largeViewSelector.png)

- **Små vyväljare**: alla andra helsidor (med undantag för arbetsytor och instrumentpanelen) har en mindre vyväljare som visas bredvid sidrubriken. Vyer på dessa sidor innehåller bara anpassningar (och inte användardefinierade filter). På dessa sidor är rubriken eller postrubriken ofta den viktigaste informationen längst upp på sidan. Den mindre storleken av vyväljaren återspeglar också en lägre förväntad frekvens av vyväxling på dessa sidor. 
    
    [![LIten vyväljare som inte stöder frågeändringar i vyn.](./media/views-smallViewSelector.png)](./media/views-smallViewSelector.png)
 
Om du väljer vyns namn öppnas vyväljaren och visar listan över tillgängliga vyer för den här sidan.

**Version 10.0.21 eller senare:** Om funktionen **Förbättrat juridiskt personstöd för sparade vyer** aktiveras, visar visningsväljaren de tillgängliga vyerna i två avsnitt. I det första avsnittet visas alla vyer som är specifika för den aktuella juridiska personen, och det andra avsnittet innehåller vyer som är tillgängliga för alla juridiska personer. Det första avsnittet visas bara om det finns vyer specifika för juridiska personer för sidan.

- **Standardvy** – Vyn **Standard** är sidans färdigkonfigurerade vy utan några uttryckliga anpassningar som används.
- **Personliga vyer** – vyerna utan hänglås representerar dina personliga vyer. Detta är vyer som du har skapat eller som en administratör har gett dig.
- **Låsta vyer** – vissa vyer (t.ex. vyn **Standard** och alla vyer som publiceras till din roll) har symbolen för hänglås intill dem i vyväljaren. Den här symbolen visar att du inte kan redigera dessa vyer. Ändringar som återspeglar sid användningen sparas dock automatiskt. Dessa ändringar inkluderar ändringar av bredden på en rutnätskolumn och ändringar i det expanderade eller komprimerade tillståndet för en snabbflik. Du kan dock använda åtgärden **Spara som** för att göra en personlig vy baserat på en låst vy om du har anpassningsprivilegier.
- **Nya vyer** – publicerade vyer som inte har öppnats ännu har en gnistsymbol till vänster om vyns namn.

Om du vill växla till en annan vy öppnar du först vyväljaren och väljer sedan den vy som du vill läsa in. 

## <a name="creating-and-modifying-views"></a>Skapa och ändra vyer

Till skillnad från traditionell anpassning sparas inte vyer automatiskt när en användare anpassar sidan eller när en användare använder ett filter på en lista eller sorterar den. En uttrycklig åtgärd krävs för att spara ändringarna i en vy. Detta krav ger användarna flexibiliteten att skapa en vy före eller efter att de ändringar som är associerade med vyn har gjorts. Det ser också till att visningsdefinitioner inte oavsiktligt ändras genom engångsfilter eller anpassningar. Observera att artiklar som används på sidan (t.ex. kolumnbredder eller avsnittets utökade eller dolda status) automatiskt sparas till den aktuella vyn, även för låsta vyer.

Om du vill se till att vyns aktuella läge är känt när du börjar att ändra en vy genom att anpassa eller filtrera den, visas en asterisk (\*) bredvid namnet på den aktuella vyn. Den här symbolen visar att du tittar på en osparad, modifierad version av vyn.

[![Osparade ändringar i en vy.](./media/views-unsavedChanges.png)](./media/views-unsavedChanges.png)

Om du vill spara ändringarna följer du stegen nedan.

1. Välj ett vynamn för att öppna vyväljaren.
2. För att ändra den befintliga vyn, välj **Spara**. Observera att den här åtgärden inte är tillgänglig för låsta vyer. 
3. För att skapa en ny vy:

    1. Välj **Spara som**. 
    2. I fönstret **Spara vy som** anger du ett namn och (valfritt) en beskrivning för vyn.
    3. Om du vill att denna vy ska utgöra standardvyn väljer du **Fäst som standard**. Mer information om standardvyer finns i avsnittet [Ändra standardvy](#changing-the-default-view) som följer. 
    4. **Version 10.0.21 eller senare:** Om funktionen **Förbättrad juridisk personsupport för sparade vyer** har aktiverats kan du välja huruvida du vill att denna vy ska bli tillgängliga för samtliga juridiska entiteter eller bara en del av dem.
    5. Välj **Spara**.

## <a name="changing-the-default-view"></a>Ändra standardvyn

Standardvyn är den vy som systemet kommer att försöka öppna första gången du öppnar sidan. Du bör ställa in standardvyn till den vy som du förväntar dig att använda oftast. 

> [!NOTE]
> - I basfunktionen **Sparade vyer** finns en enda, global standardvy för juridiska personer. Om du ändrar standardvyn kommer den här vyn att öppnas som standard, oavsett vilken juridisk enhet du befinner dig i.
> - **Version 10.0.21 eller senare:** När funktionen **Förbättrad juridisk personsupport för sparade vyer har aktiverats** kan varje juridisk person få en egen standardvy per sida.

Om du vill ändra standardvyn för en sida ska du följa de här stegen:

1. Växla till den vy som du använder som standard. 
2. Välj ett vynamn för att öppna vyväljaren. 
3. Välj **mer** och sedan **fäst som standard**.

När du skapar en ny vy (med hjälp av åtgärden **Spara som**), kan du också göra den nya vyn till standardvy genom att ange alternativet **fäst som standard** innan du sparar vyn.

> [!WARNING]
> I vissa fall körs inte frågan som är kopplad till standardvyn första gången du öppnar en sida. Om du till exempel öppnarsidan genom en panel, körs panelens fråga oavsett vilken fråga som är kopplad till standardvyn. Om du öppnar en sida vars **standardvy** redan har en definierad fråga kommer den ursprungliga frågan dessutom att köras i stället för standardvyfrågan. I det här fallet visas ett informationsmeddelande när vyn läses in. Om du byter vy när sidan har lästs in ska frågan kunna köras som förväntat. I version 10.0.10 och senare kommer informationsmeddelandet du får att innehålla en inbäddad åtgärd som tillåter att du läser in standardvisningens fråga direkt.

## <a name="managing-personal-views"></a>Hantera personliga vyer

I dialogrutan **Hantera mina vyer** får du grundläggande underhållsfunktioner för dina personliga vyer och ordningen på vyer i vyväljaren. Du öppnar den här sidan genom att klicka på vyns namn för att öppna vyväljarens listruta, välj **Mer** och välj sedan **hantera mina vyer**.

**Version 10.0.21 eller senare:** Om funktionen **Förbättrat juridiskt personsupport för sparade vyer** är aktivera visar avsnittet **Mina vyer** i dialogrutan **Hantera mina vyer** tillgängliga vyer för sidan i avsnitt. Alla vyer som är specifika för den aktuella juridiska personen visas i egna avsnitt. Avsnittet **Globala vyer** visas alltid, så att du kan hantera de vyer som är tillgängliga för sidan i alla juridiska personer. 

För en lista med tillgängliga vyer för sidan är följande åtgärder tillgängliga.

- **Ändra standardvyn** – Använd åtgärden **Fäst som standard** för att göra den valda vyn till standardvy för den här sidan. Om funktionen **Importera juridisk personsupport för sparade vyer** är aktiverad låter avsnittet **Globala vyer** dig göra en vy till standardvy för antingen aktuell juridisk person eller alla juridiska personer.
- **Ändra ordning på vyerna** – Använd åtgärderna **flytta upp** och **flytta ned** om du vill ordna om vyerna i en viss ordning.
- **Byt namn på en vy** – Använd åtgärden **Byt namn** om du vill ändra namnet på den personliga vy som för närvarande är vald. Den här åtgärden är inaktiverad för låsta vyer. 
- **Ta bort en vy** – Använd åtgärden **Ta bort** om du vill ta bort den valda vyn från sidan permanent. Det finns inget sätt att återställa en vy när du har tagit bort den.

Ändringar som görs i den här dialogrutan börjar gälla när du har valt knappen **Uppdatera**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Hantera anpassningar på organisationsnivå med vyer

För att hjälpa dig förstå hur sparade vyer hjälper till att förbättra hanteringen av anpassningar på organisationsnivå, beskriver detta avsnitt vissa skillnader i anpassningshantering med och utan funktionen **sparade vyer**.

Utan vyer kan administratörer tillämpa en uppsättning anpassningar för en sida för en användare eller en grupp användare via sidan Anpassning. Om dessa användare har anpassningsbehörigheter används anpassningarna på den sidan. Det går dock inte att hindra användarna från att ytterligare anpassa sidan, vilket innebar att organisationen inte kunde garantera att användarna hade ett konsekvent användargränssnitt. Om någon av dessa användare inte har några anpassningsrättigheter laddades inte de anpassningar som de har fått av en administratör. Vidare, om nya användare har anställts i en organisation, måste administratörerna manuellt läsa in en uppsättning anpassningar för användaren. Ingen automatisk mekanism för att ange en viss uppsättning anpassningar bör vara tillgänglig för användare i den rollen.

Med funktionen **sparade vyer** blir det betydligt enklare att administrera anpassningar, främst på grund av möjligheten att publicera vyer till grupper av användare. När en vy har publicerats kan alla användare som har en av de definierade säkerhetsrollerna och har åtkomst till de angivna juridiska personerna se och använda vyn, även om användaren kanske inte kan anpassa den. Även om varje användare har en kopia av den publicerade vyn där artiklar för sidanvändning används automatiskt kan inga användare spara anpassningar eller uppdateringar av frågan i den publicerade vyn. Publicerade vyer är med andra ord låsta. Om nya användare ges roller i juridiska personer som vyerna publicerats på, visas dessutom automatiskt de vyer som associeras med deras roller och juridiska enheter. Ingen ytterligare åtgärd krävs av administratören. Detta gäller även om användare ändrar roller i en organisation eller har åtkomst till olika juridiska personer, kanske de inte längre kan komma åt de vyer som tidigare har publicerats på dem. Ingen ytterligare åtgärd krävs av administratören.

Uppdateringar av en publicerad vy kan enkelt distribueras till användare genom att publicera vyn på rätt säkerhetsroller och juridiska personer.

Med den här publiceringsfunktionen kan företag definiera företags standardvyer som är optimerade för deras verksamhet, riktade mot användare i specifika säkerhetsroller.

## <a name="publishing-views"></a>Publicerande vyer

Under publiceringsprocessen kan vyer tilldelas en eller flera säkerhetsroller för en eller flera juridiska personer. Därför kan alla användare som har åtkomst till en juridisk person och som har tilldelats en av dessa roller komma åt och använda vyerna. Användaren kan dock inte redigera vyerna. Som standard har systemadministratörer åtkomst till åtgärden **publicering** på vyväljarens rullgardinsmeny. Andra betrodda användare i organisationen kan emellertid också ges åtkomst att visa publicering via administratörsrollen **sparade vyer**.

Gör så här om du vill publicera en vy:

1. Skapa och spara en personlig kopia av vyn som du vill publicera. 
2. Med den vyn som nu laddas, välj vynamnet för att öppna vyväljarens rullgardinsmeny. 
3. Välj knappen **Mer** och välj sedan **Publicera**. Dialogrutan Publicera öppnas.
4. Ange ett namn för vyn. Det namn du anger är det namn som de användare som får den här vyn visas i vyväljaren. Namnen på publicerade vyer för en sida måste vara unika. Inga dubblettnamn tillåts även om listan över roller eller juridiska personer som vyerna tillämpas på skiljer sig åt.
5. **Uppdatera 10.0.17 eller senare:** Om funktionen **(Förhandsgranska) Översättning till organisationsvyer** aktiveras kan du lägga till översättningar för ditt vynamn på så många språk som din organisation kräver genom att välja knappen **Översättningar** bredvid fältet **Namn**. Visningsnamnet visas sedan för användarna på det aktuella språket. Du kan också ställa in standardspråket och ange vilken översättning som ska visas för de användare som kör de språk som ingen översättning har definierats för.
5. Valfritt: Ange en beskrivning av vyn så att användare som tar emot vyn bättre kan förstå syftet. 
6. Bestämmer om vyn ska publiceras som standardvy för de valda användarna. När en vy görs till standardvy kommer användarna kommer att se nästa gång de öppnar målsidan. Den enkla, globala standardvyn för varje målanvändare kommer att ändras. Användare kan dock fortfarande ändra standardvyn när publicering har skett.

    > [!NOTE]
    > Tänk på följande när du publicerar en vy som standardvy:
    >
    > - Om du publicerar en vy som standardvy för vissa eller alla juridiska personer sker följande beteende:
    >
    >    - Om endast funktionen **Sparade vyer** är aktiverad ändras den enskilda globala standardvyn för alla målanvändare. 
    >    - **Version 10.0.21 eller senare:** Om funktionen **Förbättrat juridiskt personstöd för sparade vyer** har aktiverats och du publicerar vyn till en delmängd av juridiska personer, ändras standardvyn för dessa juridiska personer för alla målanvändare.
    >
    > - Om en användare har roller där flera vyer publiceras som standardvy, används den senast publicerade vyn som användarens standardvy. 

8. Lägg till de säkerhetsroller som motsvarar de användare som inriktas mot denna vy. 
9. Bestäm om du vill publicera vyn till de underordnade rollerna för varje vald säkerhetsroll. Om du gör det, markerar du kryssrutan **Inkludera underordnade roller** i raden för lämpliga säkerhetsroller. Observera att den här kryssrutan inte är tillgänglig för roller som saknar underordnade roller.
10. Lägg till de juridiska personer som den här vyn ska vara tillgänglig för. 

    > [!NOTE]
    > Tänk på följande beteende om du publicerar en vy till en specifik juridisk person, men du publicerar inte den vyn som standardvy:
    >
    > - Om endast basfunktionen **Sparade vyer** har aktiverats visar användarens visningsväljare för sidan till en början vyn endast för angivna juridiska personer. När vyn har lästs in för första gången kommer visningsväljaren för sidan emellertid alltid att visa den, oavsett juridisk person.
    > - **Version 10.0.21 eller senare:** Om funktionen **Förbättrat juridiskt personstöd för sparade vyer** aktiveras, visar visningsväljaren vyn enbart för angivna juridiska personer.

11. Markera **Publicera**.

Observera att i vissa miljöer kan det ta en stund (upp till en timme) innan användarna ser den publicerade vyn.

## <a name="modifying-a-published-view"></a>Ändra en publicerad vy

När du har publicerat en vy kanske du upptäcker att du vill ändra den. Även om du inte kan göra live-ändringar i en publicerad vy, eftersom dessa vyer är låsta för redigering för alla användare (inklusive utgivare), kan du publicera en vy igen för att göra uppdateringar.

Om de ändringar som du vill göra i en publicerad vy bara innefattar publiceringsparametrarna (namnet och beskrivningen för vyn, eller vilka säkerhetsroller vyn publiceras till), gör du följande:

1. Växla till den publicerade vyn för de parametrar som du vill uppdatera. 
2. På listrutan för vyväljaren väljer du **Publicera om**. Om du använder version 10.0.12 eller tidigare, måste du välja **publicera** och sedan **Ja** för att uppdatera den befintliga vyn.
3. Uppdatera vyns namn, beskrivning, säkerhetsroller och juridiska personer. 
4. Markera **Publicera**. Om du först valde den publicerade vyn som standardvy blir den standardvy för användare igen när du har publicerat om den. 

Om ändringarna i den publicerade vyn innefattar ändring av anpassningar eller filter som hör till vyn gör du så här.

1. Läs in den publicerade vyn som du vill ändra. 
2. Gör de ändringar som krävs i det lokala utkastet.
3. På listrutan för vyväljaren väljer du **Publicera om**.
4. Välj **Ja** för att visa att du vill publicera vyn tillsammans med ändringar som inte har sparats. 
5. Justera alla publiceringsparametrar som kräver justering och välj sedan **publicera**. 

## <a name="managing-published-views"></a>Hantera publicerade vyer

På samma sätt som hantering av personliga vyer ger dialogrutan **Hantera mina vyer** användare med publiceringsprivilegier grundläggande underhållsmöjligheter över den sidans publicerade vyer (förutom de egna personliga vyerna). Du öppnar den här sidan genom att klicka på vyns namn för att öppna vyväljarens listruta, välj **Mer** och välj sedan **hantera mina vyer**.

Även om alla användare har en flik med **mina vyer** som visar deras personliga vyer som har publiceringsprivilegier finns även fliken **organisationsvyer** som visar alla publicerade och opublicerade vyer för den sidan. Eftersom flera användare kanske publicerar visningar är det viktigt att du kan hantera hela listan med publicerade vyer, även om du inte är användaren som publicerade en viss vy.

För en lista med alla publicerade vyer för sidan är följande åtgärder tillgängliga. 

- **Publicera om** – Använd åtgärden **Publicera om** om du vill publicera en vy på nytt efter att publiceringsparametrar (namn, beskrivning, säkerhetsroller eller juridiska personer) ändras.
- **Publicera** – Använd åtgärden **Publicera** om du vill publicera en vy som för tillfället avpubliceras. 
- **Avpubliceras** – Använd åtgärden **Avpubliceras** om du vill göra en vy inaktiv. Vyn är fortfarande tillgänglig i systemet, men användarna kan inte se dem i vyns väljare förrän vyn har publicerats igen.
- **Spara som personlig** – Använd åtgärden **Spara som personlig** och skapa en personlig kopia av den publicerade vyn. Den här funktionen kan hjälpa dig att förstå innehållet i en vy som inte har publicerats till dig eller som ännu inte har publicerats. Du kan också använda den för att redigera och publicera om en vy.
- **Ta bort** – Använd åtgärden **Ta bort** för att ta bort en publicerad eller avpublicerad vy permanent. Den här åtgärden tar bort vyn för alla användare i systemet. Borttagningen av publicerade vyer börjar gälla när knappen **Spara** har valts. När en vy har tagits bort kan den inte återställas. 

## <a name="managing-views-globally"></a>Hantera vyer globalt

Även om vissa hanteringsfunktioner ligger på alla sidor, vilket visas i den här artikeln kan **systemadministratörer** och **sparade vyadministratörer** kan hantera vyer mer holistiskt för systemet via sidan **anpassning**. Den här sidan har särskilt följande avsnitt och funktioner: 

- **Publicerade vyer** – i det här avsnittet visas alla vyer som har publicerats för din organisation. Härifrån kan du publicera en vy igen när du har justerat säkerhetsrollerna eller juridiska personer som är mål för vyn. Du kan också exportera, radera eller ta bort publiceringar. Du kan använda **Spara som personlig** för att skapa en personlig kopia av vyn, så att du kan uppdatera vyn eller få en bättre förståelse för innehållet. 
- **Opublicerade vyer** – i det här avsnittet visas alla organisationsvyer i ditt system som inte är publicerade. Dessa vyer kommer oftast in i systemet via importfunktionen. Du kan publicera, exportera eller ta bort dessa vyer. Åtgärden **Snabbpublicering** som har lagts till i version 10.0.12 gör att flera vyer från det här avsnittet kan publiceras i en åtgärd, med hjälp av den befintliga säkerhets rollen och konfigurationen av juridiska enheter. Du kan använda åtgärden **Spara som personlig** för att skapa personliga kopior av dessa vyer, så att du kan få en bättre förståelse av deras antal.
- **Personliga vyer** – Det här avsnittet listar alla vyer som har skapats av användare i systemet. Härifrån kan du publicera en personlig vy till organisationen, eller kopiera en eller flera av dessa vyer till andra användare. Du kan också exportera eller ta bort dessa vyer.
- **Användarinställningar** – Välj en användare som du vill visa eller ändra användarens förmåga att använda anpassning antingen för hela systemet eller för specifika sidor som användaren har besökt. Du kan visa och interagera med användarens anpassningar i systemet. Du kan också ta bort alla anpassningar för användaren eller de aktuella bild texter som gäller för återställning. Om funktionsutlysningar återställs kommer alla popup-fönster som introducerade nya funktioner och som användaren tidigare avfärdats att visas igen nästa gång användaren möter dessa funktioner.
- **Systeminställningar** – Du kan temporärt inaktivera alla anpassningar för samtliga användare i systemet. I det här fallet tas inga anpassningar bort för alla användare, och alla sidor återställs till standardtillståndet. Om du senare aktiverar anpassningen igen kommer alla anpassningar att återappliceras. Du kan också ta bort alla anpassningar permanent för samtliga användare i systemet. Det går inte att återställa anpassningar som har tagits bort. Se därför till att du har exporterat den här uppgiften för att exportera alla anpassningar som du kanske vill ha senare.

Användare som har åtkomst till sidan **anpassning** kan också importera personliga eller organisationsvyer genom att använda knappen **Importera vyer** i åtgärdsfönstret. För organisationsvyer kan du välja **Publicera omedelbart** om du vill göra vyerna tillgängliga för användarna utan att publicera fler explicit.

## <a name="known-issues"></a>Kända problem

En lista med kända problem med sparade vyer finns i [skapa formulär som utnyttjar sparade vyer fullt ut](../../dev-itpro/user-interface/understanding-saved-views.md).

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Hur aktiverar jag sparade vyer i min miljö?

> [!NOTE]
> Funktionen **Sparade vyer** kräver att anpassningssystemet i appar för ekonomi och drift aktiveras. Om anpassningar inaktiveras för hela miljön inaktiveras vyer även om du följer stegen nedan. 

Du kan aktivera och inaktivera funktionen **Sparade vyer** via funktionshantering i alla miljöer. När den har aktiverats aktiveras sparade vyer i alla efterföljande användarsessioner.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Vad händer med befintliga anpassningar när vyer aktiveras? 

När vyer aktiveras sparas alla befintliga anpassningar för en användare och ett formulär i en ny vy som kallas **Min vy** som automatiskt ställs in som standardvy. Detta är avsett att säkerställa att det finns en enhetlig användarupplevelse innan och när vyer har aktiverats, utom för vyväljaren som visas i formulär.

### <a name="what-pages-support-views"></a>Vilka sidor stöder vyer? 

Vyer är tillgängliga på de flesta men inte alla sidor. Vyer är för närvarande tillgängliga på alla helskärmssidor utom för instrumentpaneler. Du kan visa stöd för arbetsytan med funktionen **Sparade vyer för arbetsytor**. Mest icke helskärmssidor, som omfattar nedrullningsbara dialogrutor, uppslag och utökade förhandsgranskningar, stöder för närvarande inte vyer. Du kan visa stöd för dialogrutor med funktionen **Sparade vyer för dialogrutor**.

### <a name="who-is-allowed-to-publish-views"></a>Vem har tillåtelse att publicera vyer?

Endast systemadministratörer och användare som har tilldelats administratörrollen **Sparade vyer** har behörighet att publicera vyer. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Varför kan jag inte spara filter med den här vyn? 

Det finns några anledningar till varför ett filter kanske inte visas för att spara med en vy: 

- Sidan kanske inte stöder sparande av filter som en del av vydefinitionen. Observera att endast sidor med stor vyväljare tillåter att anpassningar och ändringar av frågor sparas som en vy. Se avsnittet **Växla vyer** för mer information. 
- Sidan i fråga kanske inte stöder vyer på rätt sätt, eftersom den kan ignorera vyfrågan helt eller kan fungera på en temporär tabell vars data inte är beständiga. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Vilka data kommer jag att se när jag besöker en sida?

För sidor med små visningsväljare (endast anpassningar kan sparas i vyn) visas samma data som när du besöker sidan. 

För sidor med stora visningsväljare (anpassningar och frågor kan sparas i vyn) visas i huvudsak de data som länkas till den fråga som är kopplad till standardvyn. Det finns två huvudsakliga undantag:

- Om du navigerar från en panel till en sida, körs frågan oavsett vilken fråga som är kopplad till standardvyn. Om du har skapat den panelen efter att vyer har aktiverats öppnas sidan med den vy som är kopplad till den panelen.
- Om du navigerar till en sida och den startpunkten inkluderar en fråga kommer den ursprungliga frågan att köras ursprungligen i stället för standardvyfrågan. Du bör varnas när detta sker via via ett informationsmeddelande visas när vyn läses in. Du kan också bekräfta genom att växla till den här vyn efter att sidan har lästs in, eftersom det gör att vyfrågan körs oavsett.

### <a name="why-is-a-view-that-was-published-for-a-specific-legal-entity-visible-in-all-legal-entities"></a>Varför visas en vy som publiceras för en specifik juridisk person i alla juridiska personer?

Om du publicerar en vy till en specifik juridisk person men inte publicerar den vyn som standardvy, sker följande:

- Om endast basfunktionen **Sparade vyer** har aktiverats visar användarens visningsväljare för sidan till en början vyn endast för angivna juridiska personer. När vyn har lästs in för första gången kommer visningsväljaren för sidan emellertid alltid att visa den, oavsett juridisk person. Beteendet inträffar eftersom användarna får en egen kopia av den publicerade vyn när den läses in, och personliga vyer är globala.
- **Version 10.0.21 eller senare:** Om funktionen **Förbättrat juridiskt personstöd för sparade vyer** aktiveras, visar visningsväljaren vyn enbart för angivna juridiska personer. Detta beteende inträffar eftersom funktionen gör det möjligt att länka vyer (inklusive personliga vyer) till specifika juridiska personer.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

