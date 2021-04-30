---
title: Arbeta med platsdirektiv
description: I det här avsnittet beskrivs hur du arbetar med platsdirektiv. Platsdirektiv är användardefinierade regler som hjälper till att identifiera plockning och inlagringsplatser för lagerrörelse.
author: Mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: f46d55bf7a670e983fb65a9ca303bc02568247ed
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911306"
---
# <a name="work-with-location-directives"></a>Arbeta med platsdirektiv

[!include [banner](../includes/banner.md)]

Placering av direktiven är regler som hjälper till att identifiera och sätta platserna för lager. Exempelvis i en försäljningsorder transaktion, en plats direktiv bestämmer var objekten ska plockas, och där plockade artiklar kommer att användas. Platsdirektiv består av ett rubrik och tillhör ande rader. De skapas för specifika *arbetsordertyper*.

> [!NOTE]
> Det här ämnet gäller funktioner i modulen **Lagerstyrning**. Den gäller inte funktioner i modulen [Lagerhantering](../inventory/inventory-home-page.md).

Du kan använda platsdirektiv när du slutför följande uppgifter:

- Inlagra inkommande artiklar.
- Plocka och placera artiklar för utgående transaktioner.
- Plocka och placera råmaterial för produktion.
- Påfyllnadsplatser.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan skapa ett platsdirektiv måste du följa dessa steg för att se till att kraven är på plats.

1. Kontrollera att den begärda licensnyckeln är aktiverad. Gå till **Systemadministration \> Konfigurera \> Licenskonfiguration** expandera licensnyckeln **Handel** och väljer sedan konfigurationsnyckeln **Hantering av lager och transport**. Observera att administratörsåtkomst krävs för det här steget.
1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
1. Skapa ett lagerställe.
1. På snabbfliken **Lagerställe** ange alternativet **Använd lagerstyrningsprocesser** till *Ja*.
1. Skapa platser, platstyper, platsprofiler och platsformat. Mer information finns i [Konfigurera platser i ett WMS-aktiverat lagerställe](./tasks/configure-locations-wms-enabled-warehouse.md).
1. Skapa platser, zoner och zongrupper. Mer information finns i [Konfigurera lagerställe](../../commerce/channels-setup-warehouse.md) och [Konfigurera platser i ett WMS-aktiverat lagerställe](./tasks/configure-locations-wms-enabled-warehouse.md).

## <a name="work-order-types-for-location-directives"></a>Arbetsordertyper för platsdirektiv

Många av fälten som kan ställas in för platsdirektiv är gemensamma för alla arbetsordertyper. Andra fält är dock specifika för särskilda arbetsordertyper.

![Arbetsordertyper för platsdirektiv](media/Location_Directives_Work_Order_Types.png "Arbetsordertyper för platsdirektiv")

> [!NOTE]
> Två arbetsordertyper, *annullerade arbeten* och *rullande inventering*, används endast i systemet. Platsdirektiv kan inte skapas för dessa arbetsordertyper.

I tabellerna i följande underavsnitt finns en lista över vanliga och arbetsordertyper – specifika fält som är tillgängliga när du ställer in ett platsdirektiv.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Fält som är gemensamma för alla arbetsordertyper

I följande tabell visas de fält som är gemensamma för alla arbetsordertyper.

| Snabbflik | Fält |
|---|---|
| Platsdirektiv | Arbetstyp |
| Platsdirektiv | Site |
| Platsdirektiv | Lagerställe |
| Platsdirektiv | Direktivkod |
| Platsdirektiv | Flera SKU-enheter |
| Rader | Löpnummer |
| Rader | Från-kvantitet |
| Rader | Till-kvantitet |
| Rader | Enhet |
| Rader | Hitta kvantitet |
| Rader | Begränsa per enhet |
| Rader | Avrunda uppåt till enhet |
| Rader | Placera förpackningskvantitet |
| Rader | Tillåt delning |
| Platsdirektivåtgärder | Löpnummer |
| Platsdirektivåtgärder | Namn |
| Platsdirektivåtgärder | Användning av fast lagerplats |
| Platsdirektivåtgärder | Tillåt negativt lager |
| Platsdirektivåtgärder | Batch aktiverad |
| Platsdirektivåtgärder | Strategi |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Fält som är specifika för alla arbetsordertyper

I följande tabell visas de fält som är specifika för vissa arbetsordertyper.

| Snabbflik | Fält | Typ av arbetsorder |
|---|---|---|
| Platsdirektiv | Placera efter | Inköpsorder |
| Platsdirektiv | Tillämplig dispositionskod | Inköpsorder |
| Platsdirektiv | Dispositionskod | Inköpsorder |
| Platsdirektiv | Tillämplig dispositionskod | Plats för slutförda varor |
| Platsdirektiv | Dispositionskod | Plats för slutförda varor |
| Platsdirektiv | Tillämplig dispositionskod | Returorder |
| Platsdirektiv | Dispositionskod | Returorder |
| Platsdirektiv | Tillämplig dispositionskod | Kanban-plats |
| Platsdirektiv | Tillämplig dispositionskod | Kanban-plockning |
| Rader | Mall för omedelbar lagerpåfyllnad | Försäljningsorder |
| Rader | Mall för omedelbar lagerpåfyllnad | Råmaterialhämtning |
| Rader | Mall för omedelbar lagerpåfyllnad | Överför leverans |
| Rader | Mall för omedelbar lagerpåfyllnad | Kanban-plockning |

## <a name="open-the-location-directives-page"></a>Öppna sidan platsdirektiv

För att öppna sidan **Platsdirektiv** gå till **Lagerstyrning \> Inställning \> Platsdirektiv**.

Därifrån kan du visa, skapa och redigera dina platsdirektiv med hjälp av kommandona i åtgärdsfönstret. Se de återstående avsnitten i detta ämne för information om hur du använder alla fälten som är tillgängliga på sidan.

## <a name="action-pane"></a>Åtgärdsfönster

Åtgärdsfönstret på sidan **Platsdirektiv** innehåller knappar som du kan använda när du vill skapa, redigera och ta bort direktiv (**Redigera**, **Ny**, och **Ta bort**). Den innehåller också följande knappar som du kan använda för att justera sekvensen som platsdirektivet bearbetas i och konfigurera en frågeställning som definierar kriterierna för tillämpning av platsdirektivet:

- **Flytta upp** – flytta det valda platsdirektivet uppåt i sekvensen. Du kan t.ex. flytta den från serienummer 4 till serienummer 3.
- **Flytta ned** – flytta det valda platsdirektivet nedåt i sekvensen. Du kan t.ex. flytta den från serienummer 4 till serienummer 5.
- **Redigera fråga** – öppna en dialogruta där du kan definiera de villkor som det valda platsdirektivet ska bearbetas under. Du kanske till exempel vill att det bara ska gälla ett specifikt lagerställe.

## <a name="location-directives-header"></a>Rubrik för platsdirektiv

Rubrik för platsdirektiv innehåller följande fält för sekvensnumret och det beskrivande namnet på platsdirektivet:

- **Sekvensnummer** – i det här fältet visas den sekvens som används i systemet vid försök att tillämpa varje platsdirektiv i för den valda arbetsordertypen. Låga nummer används först. Du kan ändra ordningsföljden genom att använda knapparna **Flytta upp** och **Flytta ned** i åtgärdsfönstret.
- **Namn** – Ange ett beskrivande namn för platsdirektivet. Det här namnet bör hjälpa till att identifiera det allmänna syftet med direktivet. Ange till exempel *plockning av försäljningsorder i distributionslager 24*.

## <a name="location-directives-fasttab"></a>Snabbfliken platsdirektiv

Fälten på snabbfliken **platsdirektiv** är specifika för arbetsordertypen som har valts i fältet **arbetsordertyp** i listrutan.

- **Arbetstyp** – Välj den typ av arbete som ska utföras. Tillgängliga värden beror på den typ av lagertransaktion som du har valt i fältet **Arbetsordertyp**. Välj ett av följande värden:

    - **Placera** – platsdirektivet gör ett försök att hitta den bästa platsen för att placera eller hitta det lager som kommer till systemet via mottagnings-, produktions- eller lagerjusteringar. Den kan också användas för att definiera en fasplats eller vikdörr som leveransplatsen.
    - **Plocka** – platsdirektivet kommer att försöka hitta de bästa platserna för fysiskt reservlager från (skapa arbete). Plockningen kan slutföras (plocka arbetsrad kan stängas), även om arbetet inte slutförs. Användaren kan slutföra fysisk plockning. I systemet är den åtgärden ett plockningssteg. Användaren kan sedan avbryta från en mobil enhet och slutföra arbetet senare. Arbetsrubriken stängs när första platsen slutförs.

    > [!IMPORTANT]
    > De andra värdena i fältet **arbetstyp** är inte relevanta för platsdirektiv. De visas bara eftersom fältet inte har filtrerats för att matcha den valda arbetsordertypen.

- **Plats** – Det här fältet är obligatoriskt eftersom platsdirektivet måste kunna avgöra vilken webbplats och lager det är giltigt för.
- **Distributionslager** – Det här fältet är obligatoriskt eftersom platsdirektivet måste kunna avgöra vilken webbplats och lager det är giltigt för.
- **Direktivkod** – Välj direktivkod som ska associeras till en arbetsmall eller lagerpåfyllnadsmall. På sidan **direktivkod** kan du skapa nya koder som kan användas för att koppla arbetsmallar eller påfyllnadsmallar till ett platsdirektiv. Direktivkoder kan också användas för att fastställa sambandet mellan alla arbetsmallrader och platsdirektiv (t.ex. vikdörr eller fasplats).

    > [!TIP]
    > Om en direktivkod ställs in kommer systemet inte att söka efter platsdirektiv med sekvensnummer när arbete måste genereras. I stället sker sökningen efter en direktivkod. På detta sätt kan du vara mer specifik om det platsdirektiv som används för ett visst steg i en arbetsmall, till exempel steget för att iscensätta materialen.

- **Flera SKU-enheter** – Ange det här alternativet till *Ja* för att möjliggöra att flera lagerhållningsenheter (SKU) kan användas på en plats. Till exempel måste flera SKU-enheter vara aktiverade för vikdörrens plats. Om du aktiverar flera SKU-enheter anges din plats i arbete, som förväntat. Platsen kan dock bara hantera en placering av flera artiklar (om arbete inkluderar olika SKU-enheter som måste plockas och placeras). Det går inte att hantera en placering med en SKU. Om du ställer in detta alternativ till *Nej*, anges din plats bara om din placering har en enda typ av SKU.

    > [!IMPORTANT]
    > Om du vill kunna utföra placeringar av flera artiklar och placeringar av en SKU måste du ange två rader som har samma struktur och inställning, men du måste ställa in alternativet **Flera SKU-enheter** till *Ja* för en rad och *Nej* för den andra. För placeringsoperationer måste du därför ha två identiska platsdirektiv, även om du inte behöver skilja enskilda SKU:er och flera SKU:er på ett arbets-ID. Om du inte ställer in båda dessa platsdirektiv kommer oväntade platser för affärsprocesser från det tillämpliga platsdirektivet. Du måste använda en liknande inställning för plats direktiv som har **arbetstypen** *plocka* om du behöver bearbeta order som innehåller flera SKU:er.

    Använd alternativet **Flera SKU-enheter** för arbetsrader som hanterar fler än ett artikelnummer. (Artikelnumret kommer att vara tomt i arbetsuppgifterna och visas som **Flera** på bearbetningssidorna i mobilappen för distributionslagerhantering.)

    I ett typiskt exempelscenario har en arbetsmall ställts in så att den har fler än ett plocknings-/placeringspar. I det här fallet vill du kanske söka efter en viss mellanlagringsplats att använda för rader med **arbetstypen** *placera*.

    > [!NOTE]
    > Om alternativet **Flera SKU-enheter** anges till *Ja* kan du välja **Redigera fråga** i åtgärdsfönstret eftersom frågeställningen inte kan utvärderas på artikelnivå när det finns flera artiklar. Om du vill vara säker på att det önskade platsdirektivet har valts använder du fältet **direktivkod** för att vägleda urvalet av platsdirektivet som är relaterat till de artikelrader där den här direktiv koden tilldelas i arbetsmallen.

    Om du inte alltid arbetar med antingen en artikel eller med blandad artikel, är det viktigt att du definierar två plats direktiv för arbetstypen *placera*: ett där alternativet **flera SKU-enheter** ställs in på *Ja* och ett där det har värdet *Nej*.

- **Tillämplig dispositionskod** – Ange om dispositionskoden i platsdirektivet måste matcha den dispositionskod som används när artikeln tas emot eller om platsdirektivet kan väljas utifrån en dispositionskod. Om du väljer *exakt matchning* och fältet **dispositionskod** är tomt, beaktas endast tomma dispositionskoder för detta platsdirektiv.

    > [!NOTE]
    > Det här fältet är endast tillgängligt för de valda arbetsordertyperna där lagerpåfyllnad är tillåtet. En fullständig lista finns i [fält som är specifika för avsnittet arbetsordertyper](#fields-specific-types) tidigare i det här avsnittet.

- **Placera efter** – Ange om inleveranskvantitet ska vara hela kvantiteten på ID-numret, eller om den ska vara artikel efter artikel. Använd det här fältet för att se till att allt innehåll på ett ID-nummer placeras på en plats, och att systemet inte föreslår att du delar upp innehållet på flera platser för **ASN** (inleverans av ID-nummer), inleverans av **Blandade ID-nummer** och **Kluster** inleveransprocesser. (**Kluster** inleveransprocess kräver att funktionen *klusterinlagring* aktiveras). Uppförandet av platsdirektivfrågan, raderna och platsdirektivets åtgärder kommer att variera beroende på vilket värde du väljer. Snabbfliken **Rader** används bara när alternativet **Placera efter** är inställt på *Artikel*.

    > [!NOTE]
    > Det här fältet är endast tillgängligt för de valda arbetsordertyperna där lagerpåfyllnad är tillåtet. En fullständig lista finns i [fält som är specifika för avsnittet arbetsordertyper](#fields-specific-types).

- **Dispositionskod** – Det här fältet används för platsdirektiv som har en arbetsordertyp *Inköpsorder orders*, *Plats för slutförda varor* eller *Returorders* och arbetstypen *Placera*. Använd den för att vägleda flödet att använda ett visst platsdirektiv, beroende på dispositionskoden som en arbetare har valts i mobilappen för distributionslagerhantering. Du kan till exempel dirigera returnerade varor till en inspektionsplats innan de returneras till lagret. En dispositionskod kan kopplas till en lagerstatus. På så sätt kan den användas för att ändra lagerstatus som en del i en inleveransprocess. Du har till exempel en dispositionskod, *kvalitetskontroll* svar, som anger lagerstatus till *kvalitetskontroll*. Du kan sedan ha ett separat platsdirektiv för att flytta det lagret till en karantänplats.

    > [!NOTE]
    > Det här fältet är endast tillgängligt för de valda arbetsordertyperna där lagerpåfyllnad är tillåtet. En fullständig lista finns i [fält som är specifika för avsnittet arbetsordertyper](#fields-specific-types).

## <a name="lines-fasttab"></a>Snabbfliken Rader

Använd snabbfliken **Rader** om du vill skapa villkor för att tillämpa de relaterade åtgärder som anges på snabbfliken **Platsdirektivåtgärder**. För varje rad kan du ange en minsta kvantitet och en högsta kvantitet som åtgärderna ska gälla för. Du kan även ange att åtgärderna ska gälla för en viss lagerenhet.

- **Sekvensnummer** – Ange i vilken ordning som varje platsdirektivrad ska bearbetas i för den valda arbetstypen. Du kan ändra ordningsföljden efter behov genom att använda knapparna **Flytta upp** och **Flytta ned** i verktygsfältet.
- **Från kvantitet** – Ange starten för det intervall av kvantiteter som raden gäller för. Ange mängden i den måttenhet som har valts i fältet **Enhet**.
- **Till kvantitet** – Ange slutet för det intervall av kvantiteter som raden gäller för. Ange mängden i den måttenhet som har valts i fältet **Enhet**.
- **Enhet** – Välj måttenhet för artiklarna. Du kan ange en minsta kvantitet och en maximal kvantitet att direktivet bör gälla, och du kan ange att direktivet bör vara en viss lagerenhet. Fältet **Enhet** används *endast* för utvärdering av kvantitet. För att avgöra om en platsdirektivrad gäller alls använder systemet kvantiteten i enheten som anges på den raden. Varje gång den når platsdirektivrad har nåtts, görs försök att konvertera efterfrågeenheten till en enhet som har angetts på raden. Om måttenhetskonverteringen inte finns, kommer systemet att gå vidare till nästa rad.
- **Hitta kvantitet** – det här fältet används endast vid försök att placera eller lokalisera artiklar i lagerstället. (Därför gäller den endast om fältet **arbetstyp** är inställt på *placera*). Välj ett av följande värden för att ange den kvantitet som används för att utvärdera om en kvantitet ligger inom **från kvantitet** och **till kvantitet**:

    - **Kvantitet för ID-nummer** – Använd den kvantitet på ID-numret som tas emot.
    - **Kvantitet för enhet** – Använd den kvantitet som används under transaktionen. Du får t.ex. kvantiteten 1 000 i ett lagerställe och bryter den till 10 ID-nummer, som var och en har kvantiteten 100. I detta fall kan du använda en kvantitet på 1 000 artiklar i stället för antalet ID-nummer 100.
    - **Resterande kvantitet** – Använd den kvantitet som fortfarande måste inlevereras på inköpsorderraden som bearbetas.
    - **Förväntad kvantitet** – Använd den totala kvantiteten på inköpsorderraden, oavsett vad som redan har inlevererats.

- **Begränsa efter enhet** – den här kryssrutan låter dig göra platsdirektivraden specifik för en måttenhet eller flera måttenheter. Markera den om du vill begränsa vilka måttenheter som är giltiga urvalskriterier för platsdirektivraderna. Den här funktionen fungerar bara för platsdirektiv där fältet **Arbetstyp** är inställt på *Plocka*.

    När du t.ex. reserverar kvantiteter vill du bara reservera lastpallar från en viss uppsättning lagerställen. I det här fallet begränsar raderna den ordningsföljden till lastpallar på så sätt att en kvantitet som är mindre än en lastpall inte väljs för platsdirektivet.

    Observera att kryssrutan **begränsa efter enhet** styr inte enheten eller enheterna som används på arbetsraderna. Enhetsbegränsningen gäller endast de enheter som har gjorts tillgängliga via enhetsseriegruppen. Till exempel är ett objekt associerat med en enhetsseriegrupp som inkluderar båda enheterna *Lastpallar* och *styck*. En måttenhet har definierats där 1 lastpall = 100 st, och i platsdirektivet används endast funktionen **begränsa efter enhet** för lastpallar. Dessutom har en arbetsmall definierats som begränsar skapandet av arbetshuvud till 50 st. I det här fallet skapas arbetsrader på 50 stycken. Följ dessa steg för att specificera måttenheten för begränsning:

    1. På snabbfliken **Rader** välj **Begränsa per enhet** i verktygsfältet. (Den här knappen blir tillgänglig när du har markerat kryssrutan **begränsa per enhet** och sedan väljer **Spara**.)
    1. På sidan **Begränsa efter enheter** i fältet **Enhet**, välj den måttenhet som du vill begränsa med för plock och platsprocesserna.

- **Avrunda till enhet** – det här fältet fungerar tillsammans med kryssrutan **begränsa efter enhet**. T.ex. om **begränsa per enhet** och **avrunda uppåt till enhet** väljs på platsdirektivraden, ska arbetet som genereras från direktivet för råmaterialplockning avrundas upp till en multipel av en av hanteringsenheten som anges på sidan **begränsa per enhet**.

    > [!NOTE]
    > Den här inställningen **Avrunda uppåt till enhet** fungerar bara för arbetsordertypen *Råmaterialhämtning* och endast för platsdirektiv där fältet **Arbetstyp** anges till *Plocka*.

- **Placera förpackningskvantitet** – Om du anger en förpackningskvantitet på en försäljningsorder, överföringsorder eller produktionsorder, låter du denna kryssruta begränsa systemet så att det endast kan välja platser som har åtminstone den förpackningskvantiteten.

    > [!NOTE]
    > Denna funktion fungerar bara med platsdirektiv av typen *Plocka*.

- **Tillåt delning** – Ange om platsdirektivet kan dela upp kvantiteten som tas emot eller reserveras över flera lagerplatser, eller om hela kvantiteten måste placeras på en enda plats eller reserveras från en enda plats för att skapa arbete.
- **Mall för omedelbar lagerpåfyllnad** – Använd detta fält för att skapa en anslutning till en påfyllnadsmall för att starta påfyllnad omedelbart om artiklar inte har tilldelats. Om fältet är tomt startar inte artikelpåfyllnad förrän alla rader i platsdirektivet har körts klart.

    > [!NOTE]
    > Det här fältet är endast tillgängligt för de valda arbetsordertyperna där lagerpåfyllnad är tillåtet. En fullständig lista finns i [fält som är specifika för avsnittet arbetsordertyper](#fields-specific-types).

## <a name="location-directive-actions-fasttab"></a>Snabbfliken platsdirektivåtgärder

Du kan definiera flera plats direktiv åtgärder för varje linje. Återigen används ett ordningsnummer för att avgöra i vilken ordning åtgärderna bedöms. På den här nivån kan du skapa en frågeställning för att definiera hur du hittar den bästa platsen i lagerstället. Du kan också använda fördefinierade värden för **Strategi** för att finna en optimal placering.

- **Sekvensnummer** – Detta fält visar i vilken ordning som åtgärderna kommer att bearbetas i för den valda arbetstypen. Du kan ändra ordningsföljden genom att använda knapparna **Flytta upp** och **Flytta ned** i verktygsfältet.
- **Namn** – Ange namnet för platsdirektivsåtgärden. Var specifik så att åtgärden som utförs tas bort från namnet.
- **Användning av fast lagerplats** – Ange vilka platser som det här direktivet ska ta hänsyn till. Välj ett av följande värden:

    - **Fasta och inte fasta lagerplatser** – Platsdirektivet beaktar alla platser.
    - **Endast fasta lagerplatser för produkten** – Platsdirektivet beaktar endast fasta lagerplatser för produkter.
    - **Endast fasta lagerplatser för produktvarianten** – Platsdirektivet beaktar endast fasta lagerplatser för produktvarianter.

- **Tillåt negativt lager** – Markera denna kryssruta om du vill tillåta negativt lager på det angivna lagerstället i platsdirektiv.
- **Batchaktiverad** – Markera den här kryssrutan om du vill använda batchstrategier för artiklarna som är batchaktiverade. Det är viktigt att du markerar den här kryssrutan för processer som använder platsdirektiv för att hitta platser där du kan välja batchnummerspårade artiklar från. På det här sättet inkluderas sökningen efter platser som innehåller batchnummerspårade artiklar. Om den här kryssrutan är markerad och fältet **strategi** fältet är inställt på *ingen*, förs systemet vidare till nästa åtgärdsrad.
- **Strategi** – För att enklare och snabbare att definiera åtgärder som är knutna till varje platsdirektivrad genom att använda en av de fördefinierade strategierna.

    - **Ingen** – ingen strategi kommer att användas.
    - **Matcha förpackningskvantitet** – Denna strategi används för att verifiera att en plockplats har den angivna kvantiteten. Denna strategi är endast giltig om fältet **arbetstyp** är inställt på *plocka*.
    - **Konsolidera** – Denna strategi konsoliderar artiklar på en viss plats när andra artiklar redan är tillgängliga. Denna strategi är endast giltig om fältet **arbetstyp** är inställt på *placera*. En typisk inställning för placera försöker konsolidera på den första åtgärdsraden och sedan försöker den på den andra raden placera utan konsolidering. Konsolidera varor gör senare plockning effektivare.
    - **FEFO batchreservation** – Denna strategi använder FEFO-gruppreservationer (först utgått, först ut). Använd den när lagret lokaliseras med hjälp av en batch för utgångsdatum och allokeras för batchreservation. Du kan bara använda denna strategi för batchen aktiverade artiklar. Den är endast giltig om fältet **arbetstyp** är inställt på *plocka*.
    - **Avrunda till fullständigt LP och FEFO-batch** – den här strategin kombinerar elementen i *FEFO-batchreservation* och *avrundar upp till en fullständig LP* strategi. Det är bara giltigt för grupperade artiklar och platsdirektiv med jobbtypen *plocka*. Raden måste vara aktiverad för att använda strategin *FEFO-batchreservation* och strategin *avrundning till fullständig LP* kan bara användas för påfyllnad. Om den här strategin har konfigurerats tillsammans med en platsgräns för lager, kan det medföra att den valda arbetsplatsen för placering överbelastas och att gränsvärdena för lagring ignoreras.
    - **Avrunda uppåt till full LP** - Denna strategi avrundar lagerkvantiteten för att matcha den registreringsskyltskvantitet som tilldelas artiklarna som ska plockas. Du kan bara använda den här strategin för påfyllningsdirektiv av typen *Plocka*. Om den här strategin har konfigurerats tillsammans med en platsgräns för lager, kan det medföra att den valda arbetsplatsen för placering överbelastas och att gränsvärdena för lagring ignoreras.
    - **Guidat ID-nummer** – Använd denna strategi när du släpper ordern till lagret för att skapa plocka och inlagra arbete. Du kan använda denna metod för flera ID-nummer. Denna strategi kommer att försöka reservera och skapa plockningsarbete mot de platser som innehåller de begärda registreringsskylt som har associerats med överföringsorderraderna. Om dessa åtgärder inte kan slutföras men du ändå vill skapa plockningsarbete, bör du gå tillbaka till en annan strategi för platsdirektivåtgärder. Beroende på vilka affärsprocess behov du har kan du även söka efter lager i ett annat område i lagerstället.
    - **Tom plats utan inkommande arbetsuppgifter** – Använd denna strategi för att söka tomma platser. Platsen anses vara tom om den inte har något fysiskt lager och inget förväntat inkommande arbete. Du kan bara använda denna strategi för platsdirektiv som har en arbetstyp av *Placera*.
    - **Platsåldrande FIFO** – Använd strategin först in, först ut (FIFO) för att skicka både batchspårade artiklar och icke batchspårade artiklar, baserat på datumet då lagret kom in i distributionslagret. Den här funktionen kan vara särskilt användbar vid icke-spårade lager, där inget utgångsdatum kan användas för sortering. FIFO-strategin söker efter platsen som innehåller det äldsta åldersdatumet och allokerar plockning utifrån detta åldersdatum.
    - **Platsåldrande LIFO** – Använd strategin sist in, sist ut (LIFO) för att skicka både batchspårade artiklar och icke batchspårade artiklar, baserat på datumet då lagret kom in i distributionslagret. Den här funktionen kan vara särskilt användbar vid icke-spårade lager, där inget utgångsdatum kan användas för sortering. LIFO-strategin söker efter platsen som innehåller det nyaste åldersdatumet och allokerar plockning utifrån detta åldersdatum.

## <a name="example-using-location-directives"></a>Exempel: Använda platsdirektiven

I det här exemplet kommer vi att överväga en inköpsorder där placering direktiv måste hitta ledig kapacitet inom ett lager för inventarier som just registrerats vid mottagningsplatsen. Först måste du försöka hitta ledig kapacitet inom lagret genom att konsolidera med befintliga lagersaldot. Om konsolideringen är inte möjligt, då måste du hitta en tom plats.

För detta scenario, måste du definiera två platsdirektivåtgärder. Den första åtgärden i sekvensen måste *konsolidera* strategi, och den andra ska använda den *tomma platsen med några inkommande arbete* strategi. Om du definierar en tredje handlingsplan för att hantera ett överskott scenario två utfall är möjliga när det inte finns något mer kapacitet i lagret: arbete kan skapas även om inga lagerplatser definieras eller arbete processen kan misslyckas. Resultatet bestäms av inställningar på **plats direktiv fel** sida, där du kan bestämma om du vill välja **stopp på plats direktiv fel** alternativ för varje arbetsorder.

## <a name="next-step"></a>Gå vidare

När du har skapat platsdirektiv kan du associera varje direktivkod med en arbetsmallkod för att skapa arbete. Mer information finns i [Lagerpåfyllnad och Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](./control-warehouse-location-directives.md).

## <a name="additional-resources"></a>Ytterligare resurser

- Video: [konfiguration för lagerstyrning djupdykning](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Hjälpavsnitt: [Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]