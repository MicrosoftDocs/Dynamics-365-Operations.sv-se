---
title: Visuella konfigurationer för kassaanvändargränssnitt
description: Det här avsnittet innehåller information om skärmlayouter för Dynamics 365 Commerce kassamiljöer (POS)-uppgifter.
author: boycezhu
manager: annbe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2a6fdbc957a50adba38627bc37622c17ab4be419
ms.sourcegitcommit: 510ca8b14d8b5334e50aca1b15d636c65fcc9888
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4415964"
---
# <a name="pos-user-interface-visual-configurations"></a>Visuella konfigurationer för kassaanvändargränssnitt

[!include [banner](includes/banner.md)]


Användargränssnittet (UI) för Microsoft Dynamics 365 Commerce kassa (POS) kan konfigureras med en kombination av visuella profiler och skärmlayouter, tilldelade till butiker, kassor och användare. Det här avsnittet innehåller information om dessa konfigurationsalternativ.

Följande bild visar förhållandet mellan de olika enheter som utgör de konfigurerbara elementen i Användargränssnittet för kassa.

![Entiteter för kassaskärmlayout](../commerce/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Visuell profil

Visuella profiler tilldelas till kassor och de anger visuella element som är kassaspecifika och delade för användare. Alla användare som loggar in på kassan ser samma tema, layout, färger och bilder.

![Välkommen till POS-skärmen med ljust tema](../commerce/media/POS-Welcome-Screen-with-Light-theme.png)

![POS-transaktionsskärmen med mörkt tema](../commerce/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Profilnummer** - Profilnumret är en unik identifierare för den visuella profilen.
- **Beskrivning** - Du kan ange ett beskrivande namn som gör det lättare att identifiera korrekt profil för din situation.
- **Tema** – Du kan välja mellan programtema **Ljus** och **Mörk**. Temat påverkar teckensnitt och bakgrundsfärg färgerna i hela programmet.
- **Accentfärg** - Accentfärgen används i hela kassan för att åtskilja eller framhäva vissa visuella element som rubriker, kommandoknappar eller hyperlänkar. Dessa element är vanligtvis åtgärdbara.
- **Färgen på rubriken** – du kan konfigurera färgen på sidhuvudet för att tillgodose återförsäljarens varumärkeskrav.
- **Teckensnittsschema** – du kan välja mellan **standard** och **stora** teckensnittsscheman. Teckensnittsschemat påverkar teckenstorleken i hela programmet. Standardvalet är **Standard**.
- **Visa alltid programfältets etiketter** – när det här alternativet är aktiverat är etikettexten alltid synlig under knapparna i programfältet.
- **Layout** – du kan välja mellan layouterna **centrerad** och **höger**. Layouten påverkar justeringen av inloggningsrutan på inloggningsskärmen. Standardvalet är **centrerad**.
- **Visa datum/tid** – när det här alternativet är aktiverat visas aktuellt datum och aktuell tid i kassarubriken och på inloggningsskärmen.
- **Tangentbord** – du kan välja mellan **Standard till OS-tangentbord** och **Visa numeriskt knappsats** om du vill ange vilket standardtangentbord som används för inmatning på inloggningsskärmen. Det numeriska tangent bordet är ett virtuellt tangent bord som huvudsakligen används för beröringsbaserade enheter. Standardvalet är **Standard till OS-tangentbord**.
- **Logotypbild** – du kan ange en logotypbild som visas på inloggningsskärmen. Vi rekommenderar att du använder en bild som har transparent bakgrund. Bildfilens storlek bör hållas så liten som möjligt, eftersom lagring och inläsning av stora filer kan påverkas när stora filer lagras och överförs.
- **Inloggningsbakgrund** - Du kan ange en bakgrundsbild för inloggningsskärmen. Filstorleken för bakgrundsbilder ska hållas så liten som möjligt.
- **Bakgrund** - Du kan ange en bakgrundsbild som används istället för den fasta temafärgen i hela programmet. Som bakgrundsbilder för inloggningsskärmen ska filstorleken hållas så liten som möjligt.

> [!NOTE]
> Layouten **höger** och datum/tid-visning gäller inte för inloggningsskärmen i den kompakta vyn.

Du måste köra distributionschemajobbet **1090** (**Kassor**) för att synkronisera de senaste inställningarna för visuell profil i kanaldatabasen.

## <a name="screen-layouts"></a>Skärmlayouter

Skärmlayoutkonfigurationen avgör åtgärderna, innehållet i och placeringen av gränssnittskontrollerna på kassans **välkomst**-skärm och **transaktions**-skärmen.

![Visa vy för kassaskärmslayout](../commerce/media/POS-Screen-Layout-View.png)

- **Välkomstskärm**- I de flesta fall är välkomstskärmen den sida som användare ser när de först loggar in i kassan. Välkomstskärmen kan bestå av ett varumärke och knappsatser som ger åtkomst till kassaåtgärder. Åtgärder som inte är specifika för den aktuella transaktionen är oftast placerade på den här skärmen.

    ![Kassavälkomstskärm](../commerce/media/POS-Welcome-Screen.png)

- **Transaktionsskärm** – **Transaktionsskärmen** är huvudskärmen i kassan för bearbetning av försäljningstransaktioner och order. Innehåll och layout konfigureras med skärmlayoutdesignern.

    ![POS transaktionen skärm](../commerce/media/POS-Transaction-Screen.png)

- **Standardstartskärm** – Vissa återförsäljare föredrar att kassören går direkt till **Transaktionsskärmen** efter inloggning. Inställningen för **standardstartskärmen** låter dig ange den standardskärm som visas efter inloggning för varje skärmlayout.

### <a name="assignment"></a>Uppdrag

Skärmlayouter kan tilldelas på butik-, kassa- och användarnivå. Användartilldelningen åsidosätter kassa- och butikstilldelningen, och kassatilldelningen åsidosättningar butikstilldelningen. I ett enkelt scenario där alla användare använder samma layout oavsett kassa eller roll kan skärmlayouten endast anges för butiksnivå. I de scenarier där vissa kassor eller användare kräver specialiserade layouter, kan dessa layouter tilldelas.

Beroende på vilken nivå du har tilldelat webblayouterna måste du köra distributionschemajobbet **1070** (**kanalkonfiguration**), **1090** (**kassor**) och/eller **1060** (**personal**) för att synkronisera de senaste konfigurationerna för skärmlayout med kanaldatabasen.

### <a name="layout-sizes"></a>Layoutstorlekar

De flesta delar i användargränssnittet för kassa är responsiva och layouten ändrar automatiskt storlek och justeras beroende på skärmens storlek och orientering. Dock måste **kassatransaktionsskärmen** konfigureras för varje skärmupplösning som förväntas.

Vid uppstart väljer kassaprogrammet automatiskt den närmaste layoutstorleken som är konfigurerad för enheten. En skärmlayout kan även innehålla konfigurationer för både stående och liggande lägen och både stora och komprimerade enheter. Därför kan användare tilldelas till en enda skärmlayout som fungerar för olika storlekar och formfaktorer som används i butiken.

![Kassalayoutstorlekar](../commerce/media/POS-Screen-Layout-Sizes.png)

- **Namn** – du kan ange ett beskrivande namn för att identifiera skärmens storlek.
- **Layouttyp** – Kassaprogrammet kan visa sitt användargränssnitt i olika lägen för att ge den bästa användarupplevelsen på en viss enhet.

    - **Modern POS - fullständig** - Fullständiga layouter används oftast bäst för större skärmar, till exempel datorskärmar och surfplattor. Du kan markera de UI-element som ska ingå, ange storlek och placering av elementen och konfigurera de detaljerade egenskaperna. Fullständiga layouter stöder både stående och liggande konfigurationer.
    - **Modern POS - komprimerad** - Komprimerad layout används oftast bäst för telefoner eller små surfplattor. Designmöjligheterna är begränsade för kompakta enheter. Användare kan konfigurera kolumner och fält för kvitto- och summapaneler.

- **Bredd eller höjd** – dessa värden representerar den effektiva skärmstorlek, i pixlar som förväntas för layouten. Kom ihåg att vissa operativsystem använder skalning för bildskärmar med hög upplösning.

> [!TIP]
> Du kan ta reda på layoutstorleken som krävs för kassaskärmen genom att visa upplösningen i programmet. Starta kassan och gå till **inställningar \>sessionsinformation**. POS visar skärmens storlek och position som för närvarande är inläst, layoutstorlek och upplösning i programfönstret.

![Kassainformationssida som visar den för närvarande laddade skärmlayouten, layoutstorleken och upplösningen i appfönstret](../commerce/media/POS-Session-Information.png)

### <a name="button-grids"></a>Knappsatser

För varje layoutstorlek i en skärmlayout kan du konfigurera och tilldela knappsatser för kassavälkomstskärmen och **transaktionsskärmen**. Knappsatser på välkomstskärmen placeras ut automatiskt från vänster till höger, från det lägsta numret (välkomstskärm 1) till det högsta numret.

I fullständiga kassalayouter anges placeringen av knappsatser i skärmlayoutdesignern.

I kompakta kassalayouter placeras knappsatser på välkomstskärmen ut automatiskt uppifrån och ned (transaktionsskärm 1) till det högsta numret. De kan användas på menyn **åtgärder**.

![Komprimera layoutens knappsatser](../commerce/media/Compact-View-Button-Grids.png)

### <a name="images"></a>Bilder

För varje layoutstorlek i en skärmlayout kan du ange bilder som ska inkluderas i kassagränssnittet. För fullständiga kassalayouter kan en enda bild anges för välkomstskärmen. Den här bilden visas som det första gränssnittselement till vänster. På skärmen **transaktion** kan bilder användas som flikbilder eller logga. Komprimerade kassalayouter använder inte dessa bilder.

### <a name="screen-layout-designer"></a>Layoutdesigner för skärm

Skärmlayoutdesignern låter dig konfigurera olika aspekter av **kassatransaktionsskärmen** för varje storlek i både stående och liggande visning, layout och både fullständig och komprimerad layout. Skärmlayoutdesignern använder ClickOnce-distributionsteknik för att hämta, installera och starta den senaste versionen av programmet varje gång användaren öppnar den. Kom ihåg att kontrollera webbläsarkrav för ClickOnce. Vissa webbläsare, till exempel Google Chrome kräver filnamnstillägg.

> [!IMPORTANT]
> Du måste konfigurera en skärmlayout enbart för varje layoutstorlek som definieras och som används av kassan.

### <a name="full-layout-designer"></a>Fullständig layoutdesigner

Den fullständiga layoutdesignern låter användarna dra gränssnittskontroller till **kassatransaktionsskärmen** och konfigurera inställningarna för dessa kontroller.

![Fullständig layoutdesigner för kassa (liggande)](../commerce/media/POS-Full-Layout-Designer-Landscape.png)

- **Importera layout/exportera layout** – du kan exportera och importera layoutdesign för kassaskärm som XML-filer så att du enkelt kan återanvända och dela dem med andra miljöer. Det är viktigt att du importerar layoutdesigner för rätt layoutstorlekar. I annat fall kanske inte gränssnittselement passar på skärmen.
- **Liggande eller stående** – om användarna av kassaenheten kan växla mellan stående och liggande visning, måste du definiera en skärmlayout för varje läge. Kassan identifierar skärmrotation automatiskt och visar rätt layout.
- **Layoutrutnätet** – Kassalayoutdesignern använder 4-pixelrutnät. Användargränssnittets kontroller ”snäpps fast” i rutnätet för att hjälpa dig att justera innehållet korrekt.
- **Designerzoom** – du kan zooma in och ut designervyn för att bättre visa innehållet på kassaskärmen. Denna funktion är användbar när skärmupplösningen i kassan skiljer sig avsevärt från upplösningen på skärmen som används i designern.
- **Visa/dölj navigeringsfältet** – för fullständiga kassalayouter kan du välja om det vänstra navigationsfältet ska synas på skärmen **transaktion**. Den här funktionen är användbar för skärmar som har lägre upplösning. Om du vill ange synlighet, högerklicka på navigeringsfältet i designern och markera eller avmarkera kryssrutan **alltid synlig**. Om fältet är dolt kan kassaanvändare fortfarande komma åt det via menyn längst upp till vänster.

    ![Visa eller dölj navigeringsfältet](../commerce/media/Navigation-Bar.PNG)

- **Kassakontroller** – Kassalayoutdesignern stöder följande kontroller. Du kan konfigurera många kontroller genom att högerklicka och använda snabbmenyn.

    ![Kontroller för kassagränssnittet](../commerce/media/POS-UI-Controls.png)

    - **Numerisk knappsats** – Den numeriska knappsatsen är den huvudsakliga användarinmatningen på kassans **Transaktionsskärm**. Du kan konfigurera kontrollen så att fullständig numeriskt knappsats visas. Det här alternativet är idealiskt för pekskärmsenheter. Du kan också konfigurera det så att endast inmatningsfältet visas. I det här fallet används ett fysiskt tangentbord för inmatning. Inställningarna för knappsats finns bara i den fullständiga layouten. För kompakta layouter visas alltid fullständig numerisk knappsats på **transaktionsskärmen**.
    - **Summapanel** - Summapanelen kan konfigureras i en eller två kolumner för att visa värden såsom radantal, rabattbelopp, avgifter, delsumma och skatt. Komprimerad layout stöder bara en enda kolumn.
    - **Kvittopanel** - Kvittopanelen innehåller försäljningsrader, betalningsrader och leveransinformation för produkterna och tjänsterna som bearbetas i kassan. Du kan ange kolumner, bredd och placering. I kompakta layouter kan du också konfigurera ytterligare information som visas på raden under huvudfönstret.
    - **Kundkort** - Kundkortet visar information som hör till kunden som är kopplade till den aktuella transaktionen. Kundkortet kan konfigureras för att dölja eller visa ytterligare information.
    - **Flikkontroll** - Flikkontrollen kan placeras på en skärmlayout och sedan placera andra kontroller, till exempel numeriskt knappsats, kundkort eller knapprutnät på den. Flikkontrollen är en behållare som hjälper dig att få plats med mer innehåll på skärmen. Flikkontrollen är bara tillgänglig för fullständiga layouter.
    - **Bild** – Bildkontrollen kan användas för att visa butikens logotyp eller annat varumärke på **Transaktionsskärmen**. Bildkontrollen är bara tillgänglig för fullständiga layouter.
    - **Rekommenderade produkter** - Om det är konfigurerat för miljön, visar kontrollen för rekommenderade produkter produktförslag baserade på maskininlärning.
    - **Anpassad kontroll** – Den anpassade kontrollen fungerar som platshållare i skärmlayouten så att du kan reservera utrymme för anpassat innehåll. Den anpassade kontrollen är bara tillgänglig för fullständiga layouter.

### <a name="compact-layout-designer"></a>Kompakt layoutdesigner

Liksom den fullständiga layoutdesignern kan du med den komprimerade layoutdesignern konfigurera kassaskärmlayout enbart för mobiltelefoner och små surfplattor. Men då har själva layouten åtgärdats. Du kan konfigurera kontrollerna genom att högerklicka och använda snabbmenyn. Du kan däremot inte använda dra och släpp-åtgärder för ytterligare innehåll.

![Kompakt layoutdesigner](../commerce/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Knappsatsdesigner

Knappsatsdesignern låter dig konfigurera knappsatser som kan användas i kassavälkomstskärmen och **transaktionsskärmen** för både fullständig och komprimerad layout. Samma knappsats kan användas för olika layouter och typer av layout. Liksom skärmlayoutdesignern använder knappsatsdesignern ClickOnce-distributionsteknik för att hämta, installera och starta den senaste versionen av programmet varje gång användaren öppnar den. Kom ihåg att kontrollera webbläsarkrav för ClickOnce. Vissa webbläsare, till exempel Google Chrome kräver filnamnstillägg.

![Knappsatsdesigner](../commerce/media/Button-Grid-Designer.png)

- **Knappen Ny** – Klicka om du vill lägga till en ny knapp i knappsatsen. Som standard visas nya knappar längst upp till vänster i rutnätet. Du kan emellertid ordna knappar genom att dra dem i layouten.

    > [!IMPORTANT]
    > Innehållet i knappsatsen kan överlappa. Se till att knapparna inte döljer andra knappar när du ordnar dem.

- **Ny design** – Klicka för att automatiskt skapa en layout för knappsatsen genom att ange hur många knappar per rad och kolumn.
- **Knappegenskaper** – du kan konfigurera knappegenskaper genom att högerklicka på knappen och med hjälp av snabbmenyn.

    > [!IMPORTANT]
    > Vissa inställningar för knappsatser gäller bara för Enterprise POS inte för Modern POS eller Cloud POS.

    ![Egenskaper för knappsats](../commerce/media/Button-grid-button-properties.png)

    - **Åtgärd** - I listan med tillämpliga kassaåtgärder, välj den åtgärd som startar när användaren klickar på knappen i kassan.

        För listan över kassaåtgärder som stöds, se [kassaåtgärder, online och offline](pos-operations.md).

    - **Åtgärdsparametrar** – Vissa kassaåtgärder använder ytterligare parametrar när de anropas. T.ex. för åtgärden Lägg till produkt kan användare ange produkten som ska läggas till.
    - Ange den text som ska visas på knappen i fältet **Knapptext** .
    - **Dölja knapptext** – Använd den här kryssrutan om du vill dölja eller visa texten på knappen. Knapptexten döljs ofta för små knappar som bara visar en ikon.
    - **Knappbeskrivning** – ange ytterligare hjälptext som visas när användarna placerar muspekaren över knappen.
    - **Storlek i kolumner/storlek i rader** – du kan ange hur hög och bred knappen ska vara.

        ![Kassaknappstorlek i rader och kolumner](../commerce/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Anpassade teckensnitt** – när du markerar kryssrutan **Aktivera anpassade teckensnitt för kassa** kan du ange ett annat teckensnitt än systemets standardteckensnitt för kassan.
    - **Anpassa tema** – som standard använder kassaknappar accentfärg från den visuella profilen. När du markerar kryssrutan **Använd anpassat tema** kan du ange ytterligare färger.

        > [!NOTE]
        > Modern POS och Cloud POS använder endast värdena **bakgrundsfärg** och **teckenfärg**.

    - **Bild av knappen** – knappar kan innehålla bilder och ikoner. Välj bland de tillgängliga bilderna som angetts i **Butik och handel \> kanalinställning \> kassainställning \> kassa \> bilder**.

![Exempel på knappsats i kassan](../commerce/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Installera layoutdesignern för detaljhandelskassa (POS)](install-pos-layout-designer.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]