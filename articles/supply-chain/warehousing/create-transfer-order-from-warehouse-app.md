---
title: Skapa överföringsorder från distributionslagerappen
description: I det här avsnittet beskrivs hur du skapar och bearbetar överföringsorder från funktionen för distributionslagerappen
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c30b0e74053480a08f84f4d7579021084ded5799
ms.sourcegitcommit: 286786445f72db20e993d37a63df0b886f8f5e99
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/12/2020
ms.locfileid: "3988401"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Skapa överföringsorder från distributionslagerappen

[!include [banner](../includes/banner.md)]

Denna funktion låter lagerarbetare skapa och bearbeta överföringsorder direkt från lagerställeappen. Lagerarbetarna börjar med att välja destinationslager stället och kan sedan skanna en eller flera licensskyltar med hjälp av appen för att lägga till registreringsskyltar till överföringsordern. När lagerarbetaren väljer **slutför order**, kommer ett batch-jobb att skapa de överföringsorder och orderrader som krävs baserat på den lagerbehållning som har registrerats för dessa registreringsskyltar.

## <a name="enable-the-create-transfer-orders-from-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Aktivera skapa överföringsorder från funktionen för distributionslagerappen

Innan du kan använda den här funktionen måste både den och dess förutsättningar aktiveras i ditt system. Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.

1. Aktivera först funktionen [bearbeta händelser i lagerställeapp](warehouse-app-events.md), som visas i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) som:
    - **Modul** – Lagerstyrning
    - **Funktionsnamn** - Bearbeta händelser för lagerställeapp
1. Aktivera sedan formuläret *skapa överföringsorder från funktionen lagerställeapp*, som visas som:
    - **Modul** – Lagerstyrning
    - **Funktionsnamn** - Skapa och bearbeta överföringsorder från lagerställeappen
1. Om du vill automatisera bearbetningen av utgående leveranser måste du också aktivera funktionen [Bekräfta utgående leveranser från batch-jobb](confirm-outbound-shipments-from-batch-jobs.md). Funktionen visas som:
    - **Modul** – Lagerstyrning
    - **Funktionens namn** - Bekräfta utgående leveranser från batchjobb

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Ställa in ett menyalternativ för mobila enheter för att skapa överföringsorder

Här följer allmänna riktlinjer för hur du skapar ett menyalternativ för mobila enheter för att skapa en överföringsorder. Beroende på vilka affärskrav som ställs in när användarna skapar överföringsorder från golvet, kommer olika konfigurationer att aktiveras. Scenariot i detta dokument kommer att beskriva en sådan konfiguration.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Välj **Nytt** för att lägga till ett nytt menyalternativ. Gör följande inställningar för att komma igång:

    - **Menyalternativnamn** - tilldela ett namn som det ska visas i Supply Chain Management.
    - **Titel** - tilldela ett menynamn som det ska visas för arbetare i distributionslagerappen.
    - **Läge** - inställt på *indirekt* (den här lagerställeappen kommer inte att skapa arbete).
    - **Aktivitetskod** - Ställ in *Skapa överföringsorder från registreringsskyltar* för att göra det möjligt för lagerarbetarna att skapa en överföringsorder baserat på en eller flera skannade registreringsskyltar.

1. Använd inställningen **Policy för skapande av överföringsrader** för att styra hur överföringsorderrader skapas av detta menyalternativ. Raderna skapas/uppdateras baserat på den registrerade lagerbehållningen för skannade registreringsskyltar. Välj ett av följande värden:

    - **Ingen reservation** - överföringsorderraderna kommer inte att reserveras.
    - **ID-nummer guidad med radreservation** – överföringsorderraderna kommer att reserveras och använda alternativet för interaktiv strategi för ID-nummer som lagrar relevanta ID-nummer som är kopplade till orderraderna. Värden för "Lokaliserat ID-nummer" kan därför användas som en del av arbetsprocessen för att skapa överföringar för överföringsorderraderna.

1. Använd inställningen **utgående leveransprincip** för att lägga till mer automatisering i den utgående leveransprocessen efter behov. När en arbetare väljer **Slutför beställning**-knappen skapar programmet den programhändelse för *Slutför beställning* som kommer att spara värdet som du väljer här i fältet **utgående leveransprincip** för varje rad i den aktuella överföringsordern. Senare, när händelsekön bearbetas av ett batchjobb för att skapa överföringsordern, kan värdet som lagras i det här fältet läsas av batch-jobbet och kan därför styra hur det här jobbet bearbetar varje rad. Välj en av följande:

    - **Ingen** - ingen automatisk bearbetning utförs.
    - **Släpp till lagerställe** - automatiserar utleveransen till lagerställeprocess.
    - **Leveransbekräftelse** - automatiserar leverans av bekräftelsen.
    - **Släpp- och levereransbekräftelse** - Automatisk automatiserar både frisläppningen till lagerställe och leveransbekräftelse processer.

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>Lägg till menykommandot för menyalternativ för mobila enheter

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**
1. Välj **Redigera**.
1. Välj en befintlig meny efter valet av menyalternativet ny under **tillgängliga menyer och menyalternativ**. Lägg till menyalternativet genom att välja knappen med högerpilen.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Skapa en överföringsorder baserat på registreringsskyltar

Distributionslagerappen har en enkel process för att skapa överföringsorder baserat på registreringsskyltar. För att du ska kunna göra detta gör arbetaren följande med hjälp av distributionslagerappen:

1. Skapa överföringsordern och identifiera lagerstället.
1. Identifiera varje registreringsskylt som ska levereras.
1. Välj **Slutför order**.

>[!NOTE]
> Det är möjligt för flera arbetare att tilldela registreringsskylt som är avsedda för samma överföringsorder genom använda knappen **Välj överföringsorder** för att välja ett befintligt, ej behandlat, överföringsordernummer från händelsekön för distributionslagerappen. Information om hur du hittar värden för överföringsordernumren finns i [fråga om lagerställeapp händelser](#inquire-the-warehouse-app-events).

## <a name="example-scenario"></a>Exempelscenario

Det här scenariot innehåller en översikt över processen för att hämta överföringsorder som skapats och automatiskt bearbetas baserat på den lagerbehållning som registreras på de valda registreringsskyltar.

Om du vill arbeta genom det här scenariot med hjälp av de föreslagna värdena måste du arbeta på ett system med demodata installerade och välja den *USMF* juridiska personen innan du börjar.

I det här scenariot förutsätts det att du redan har aktiverat både [skapa och bearbeta överföringsorder från funktionen för distributionslagerappar](#enable-create-transfer-order-from-warehouse-app)och [Händelsebearbetning i distributionslagerappen](warehouse-app-events.md).

Förutom att ställa in skapa överföringsordern i menyalternativen på den mobila enheten måste även ytterligare mallar, plats direktiv och batchjobb ställas in och aktiveras.

### <a name="example-scenario-blueprint"></a>Skiss över exempelscenario

Du är återförsäljare och har flera registreringsskyltar, där var och en innehåller en blandning av artiklar som placerats på en viss plats i ett av dina lagerställen (*lagerställe 51*). Du vill aktivera processen som gör att arbetare kan skapa en överföringsorder till ett annat lagerställe (*lagerställe 61*) för en samling skannade registreringsskyltar. Du kommer automatiskt att uppdatera överföringsordern så snart den sista registreringsskylten för beställningen har identifierats.

![Exempel på automatiserad överföringsorderprocess](media/create-transfer-order-from-app-example.png "Exempel på automatiserad överföringsorderprocess")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Skapa ett menyalternativ för mobila enheter för att skapa överföringsorder

Det här avsnittet innehåller information om hur du skapar ett nytt menyalternativ för mobila enheter för att skapa överföringsorder. Ställ in **läge** till *indirekt* och **aktivitetskod** för att *skapa överföringsorder från registreringsskyltar*.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Välj **Ny**.
1. I fältet **Menyalternativnamn** ange namnet *Skapa TO*.
1. I fältet **Rubrik** ange beskrivningen *Skapa TO*.
1. I fältet **Läge** välj *Indirekt*.
1. I **Aktivitetskod**, välj *Skapa överföringsorder från registreringsskyltar*
1. I **Policy för skapande av orderrader**, välj *ID-nummer guidad med radreservation*.
1. I **utgående leveransprincip**, välj *Släpp- och levereransbekräftelse*.
1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. Välj **Redigera**.
1. Välj befintlig meny för **Lager** och välj sedan det nya menyalternativet under **Tillgängliga menyer och menyalternativ**. Lägg till menyalternativet i menyn **Lager** genom att välja knappen med högerpilen.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Ställa in arbetstidsmallar för automatisk bearbetning och dela upp arbete efter placerad ID-nummer

Det här avsnittet innehåller information om hur du aktiverar en arbetsmall för automatisk bearbetning av det arbete som har skapats med mallen när en påfyllnad frisläpps.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. I fältet **Arbetsordertyp** välj *Överföringsproblem*.
1. Skapa en ny arbetsmall genom att välja **Nytt**.
1. I fältet **Arbetsmall** ange *51 automatisk bearbetning LP*.
1. I fältet **Beskrivning av arbetsmall** ange *51 automatisk bearbetning LP*.
1. Markera kryssrutan **bearbeta automatiskt**. Du måste välja det här alternativet för att automatiseringsstegen ska kunna bearbetas.
1. I demonstrationsdata finns redan en arbetsmall *51 överföring*, redigera fältet **sekvensnummer** så att den nya arbetsmallen har ett lägre sekvensnummer än den befintliga arbetsmallen *51 överföring*.
1. Välj **Spara** i verktygsfältet om du vill aktivera snabbfliken **Arbetsmallinformation**.
1. I snabbfliken **Arbetsmallinformation** välj **Ny** i verktygsfältet. Du kommer att lägga till två rader.
1. I fältet **Arbetstyp**, välj *Välj*.
1. I fältet **Arbetsklass-ID**, välj *TransfOut*.
1. Välj **Nytt** i verktygsfältet **Arbetsmallinformation**.
1. Välj **Placera** i fältet *Arbetstyp*.
1. I fältet **Arbetsklass-ID**, välj *TransfOut*.
1. Välj **Spara** för att aktivera fältet **Direktivkod**.
1. På raden **Arbetstyp** välj *Placera* välj **Direktivkod** *Baydoor*. Se till att den nya arbetsmallen får det lägsta **Sekvensnummer**.
1. I verktygsfältet, välj **Redigera fråga** för att öppna frågeredigeraren.
1. På fliken **Intervall** klickar du på **Lägg till**.
1. På den tillagda raden, i **fält** välj *lagerställe*.
1. I fältet **Kriterier** välj *51*.
1. Välj fliken **Sortera**.
1. Välj **Lägg till** och ställ in **fält** för att *Lokaliserat ID-nummer*. Om du markerar det här fältet aktiveras knappen **Arbetsuppgiftshuvudet delas**.
1. Välj **OK** följt av **Ja** för att återställa grupperingen och återgå till sidan **Arbetsmallar**.
1. Markera **Arbetsuppgiftshuvudet delas** och aktivera **Gruppera efter detta fält** för **Lokaliserat ID-nummer** och stäng.

> [!NOTE]
> Alla inställningar kan inte bearbetas automatiskt, till exempel artiklar med faktisk/nominell vikt och användning av blandade spårningsdimensioner.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Ställ in platsdirektiv för den guidade strategin för ID-nummer

Det här avsnittet innehåller information om hur du ställer in en plats för direktiv plockning så att du kan använda strategin **guidad registreringsskylt**.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. Välj **Redigera**.
1. I navigeringslistans rubrik, välj **Arbetsordertyp** *Överföringsproblem*.
1. I navigeringslistan väljer du befintligt platsdirektiv **51 för plockning**.
1. På snabbfliken **Rader** i kryssrutan **Tillåt delning**.
1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en ny åtgärdsrad.
1. Skriv **Dokument** i fältet *LP guidad*.
1. I fältet **Strategi** välj *guidat ID-nummer*. Den här åtgärden kräver det lägsta sekvensnumret.
1. Klicka på **Spara** i verktygsfältet.
1. Välj sidikonen **Uppdatera** från verktygsfältet.
1. På snabbfliken **Platsdirektivåtgärd** välj raden för åtgärden *Att plocka*.
1. I verktygsfältet **Platsdirektivåtgärder** välj **Flytta ned** för att ändra sekvensnumret så att det är större än sekvensnumret för åtgärden *LP guidad* som just har skapats.

> [!NOTE]
> Den guidade strategin för registreringsskylt kommer att försöka reservera och skapa plockningsarbete mot de platser som innehåller de begärda registreringsskylt som har associerats med överföringsorderraderna. Om detta inte är möjligt och du ändå vill skapa plockningsarbete, bör du gå tillbaka till en annan platsdirektiv åtgärdsstrategi och kanske även söka efter lager i en annan del av lagerstället, beroende på affärsprocessens behov.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Ställ in ett batchjobb för att bearbeta händelser för lagerställeapp

Det här avsnittet innehåller information om hur du ställer in ett schemalagt batchjobb för bearbetning av händelser för lagerställeapp.

1. Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta händelser för lagerställeapp**.
2. I dialogrutan aktiverar du **Batchbearbetning** under avsnittet **Kör i bakgrunden**.
3. Välj **återkommande** och ställ in batchjobbet på process baserat på det intervall som krävs för ditt företag.
4. Välj **OK** om du vill återgå till huvuddialogen.
5. Välj **OK** i huvuddialog om du vill lägga till jobbet i batchkön.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Ställa in ett batchjobb för att automatiskt frisläppa överföringsorder

Det här avsnittet innehåller information om hur du ställer in ett schemalagt batchjobb för att frisläppa överföringsorder som har markerats som "redo att frisläppa".

1. Gå till **Lagerstyrning \> Släpp till lagerställe \> Automatiskt släpp av transferorder**.
1. I dialogrutan expanderar du avsnitt **poster som ska inkludera**.
1. Välj **Filter** under avsnitten **Poster som ska ingå**.
1. I frågesida **WHSTransferAutoRTWQuery** fliken **Intervall** välj **Lägg till** för att ändra för att lägga till en ny rad i frågan.
1. I den nya raden i fältet **Tabell**, välj rullgardinsmenyn och välj tabellen **Frisläppning av överföringsrad till lagerställe**.
1. I din nedrullningsbara menyn **Fält** välj **Utgående leveransprincip**.
1. I fält **Kriterier** välj **Släpp- och levereransbekräftelse**.
1. I raden där **Fält** anges till *Från lagerställe*, i fältet **Kriterier** välj *51*.
1. Välj **OK** om du vill återgå till huvuddialogrutan.
1. Expandera avsnittet **Kör i bakgrunden** till att ange batchbearbetning.
1. Aktivera **Batchbearbetning** under avsnittet **Kör i bakgrunden**.
1. Välj **återkommande** och ställ in batchjobbet på process baserat på det intervall som krävs för ditt företag.
1. Välj **OK** om du vill återgå till huvuddialogen.
1. Välj **OK** i huvuddialog om du vill lägga till batchjobbet i batchkön.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>Ställ in batch-jobbet "behandla utgående leverans"

I det här avsnittet beskrivs hur du ställer in ett tidsplanerat batchjobb för att köra bekräftelse av utgående leverans för inläsningar som är relaterade till överföringsorderrader som är "klara att levereras".

1. Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta utgående leveranser**.
1. Expandera avsnittet **Poster som ska ingå**.
1. Välj **filter**.
1. I frågan **WHSLoadShipConfirm** välj fliken **Kopplingar**.
1. Expandera hierarkistrukturen så att **Laster** och **Lastinformation** har expanderats.
1. Välj tabellen **Lastinformation**.
1. Välj knappen **Lägg till registerkoppling**.
1. I listan med registerrelationer filtrerar eller söker du i kolumnen **Relation** för *Överföringsorderrader (referens)*.
1. Fokusera på register relationen i listan och klicka på knappen **Välj**.
1. Välj tabellen **Överföringsorderrader**.
1. Välj knappen **Lägg till registerkoppling**.
1. I listan med registerrelationer filtrerar eller söker du i kolumnen **Relation** för *Överför ytterligare fält för uppfinningar (post-ID)*.
1. Fokusera på register relationen i listan och klicka på knappen **Välj**.
1. Välj fliken **Intervall**.
1. I frågetabellen **område** kommer du att ställa in tre kriterier för frågevillkor. Välj knappen **Lägg till** för att lägga till en rad.
1. Lägg till ett intervall för registret som **Laster**. Ange **Fält** till *Last status* och ange **Villkor** till *Lastad*.
1. Lägg till ett annat intervall för tabellen **Överför ytterligare fält för överföring**. Ange **Fält** till *Utgående leveransprincip* och ange **Kriterier** till *Släpp- och levereransbekräftelse*.
1. Lägg till ett annat intervall för tabellen **Lastinformation**. Ange **Fält** till *Referens* och **Kriterier** till *Överföringsorderförsändelse*.
1. Välj **OK** om du vill återgå till huvuddialogrutan.
1. Expandera avsnittet **Kör i bakgrunden**.
1. Aktivera **Batchbearbetning**.
1. Välj **återkommande** och ställ in batchjobbet på process baserat på det intervall som krävs för ditt företag.
1. Välj **OK** om du vill återgå till huvuddialogen.
1. Välj **OK** i huvuddialog om du vill lägga till batchjobbet i batchkön.

> [!NOTE]
> Mer information finns i [Bekräfta utgående försändelser från batchjobb](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Bearbetar exemplet för "Skapa överföringsorder från lagerställeapp"

### <a name="add-on-hand-on-a-license-plate"></a>Lägga till behållning på en registreringsskylt

Som utgångspunkt för det här scenariot måste du ha en registreringsskylt som innehåller fysiskt tillgängligt lager.

| Artikel | Lagerställe | Lagerstatus | Plats | ID-nummer | Kvantitet |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Tillgängligt | LP-010 | LP10 | 1 |
| A0002 | 51 | Tillgängligt | LP-010 | LP10 | 2 |

Lägg till fysiskt lager i behållningskvantitet med hjälp av följande värden:

> [!NOTE]
> Du måste skapa en registreringsskylt och använda platser som gör att du kan överföra blandade artiklar, t.ex. LP-010.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Skapa och bearbeta överföringsorder från lagerställeappen

1. Öppna appen och logga in som användare *51*. Aktuellt användarlager kommer att vara 51.
1. Välj meny alternativet **skapa till** från den menyplats som du har lagt till det under installationen.
1. Skapa en överföringsorder genom att ange destinations lagerstället (till lagerstället) i fältet **lagerställe**, ange *61*. Den nya överföringsordern kommer från det aktuella lagerstället 51 (från lagerstället) till lagerstället *61*.
1. Välj **OK**.
1. Sök igenom ett ID-nummer i fältet **ID-nummer**. Ange ID-nummer för den nya inventeringen i ett tidigare steg, *LP10*.
1. Välj **OK**.
1. Välj menyknappen och välj sedan **Slutför order** för att slutföra skapandet av överföringsordern för distributionslagerappen.

För nämnda exempel två **Händelser för lagerställeapp** (*Skapa överföringsorder* och *Slutför överföringsorder*) används.

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Fråga om händelser i lagerställeapp

Du kan visa den händelsekön och de händelsemeddelanden som har genererats av lagerställeappen genom att gå till **Hantering av distributionslager \> Frågor och rapporter \> Loggar för mobil enhet \> Lagerställeapp händelser**.

Händelsemeddelandena *Skapa överföringsorder* kommer att få status *Vänta*, vilket innebär att batch-jobbet **Bearbeta lagerställeapp händelser** inte kommer att hämtas och bearbeta händelsemeddelandena. Så snart händelsemeddelandet uppdateringar till status *i kö* bearbetar batch-jobbet händelserna. Detta kommer att ske samtidigt som skapandet av händelsen *Slutför överföringsorder* (när en arbetare väljer knappen**Slutför order** på distributionslagerappen). När händelsemeddelandena *skapa överföringsorder* har bearbetats uppdateras statusen till *slutförd* eller *misslyckad*. När status *Slutför överföringsorder* uppdateras till *Slutförd* tas alla relaterade händelser bort från kön.

Eftersom **Händelser för lagerställeapp** för skapandet av överföringsorderdata kommer inte bearbetas av batchjobbet innan meddelandena uppdateras till status *I kö* måste du slå upp de begärda numren för överföringsorder som en del av fältet **Identifierare**. Fältet **Identifierare** finns i rubriken på sidan för **händelser för lagerställeapp**.

Som en del av bearbetning av händelser för lagerställe kan skapandet av överföringsorderraden misslyckas. I det här fallet uppdateras händelsemeddelandets tillstånd till *misslyckad* och du kan använda informationen **Batch-logg** för att lära dig varför och vidta åtgärder för att rätta till eventuella problem.

Typiska problem kan vara relaterade till saknad inställning för processen, t.ex. ett saknat transitlager för *Skapa överföringsorder*. I det här exemplet lägger du till ett transitlager i leveranslagret och använder alternativet **Återställ** om du vill ändra status för alla program händelse meddelanden från *Misslyckad* till *I kö*, vilket innebär att händelsemeddelandena kommer att bearbetas igen efter korrigeringen av inställningsdata.

Inom produktionsmiljöer är undantagen mer processrelaterade, t.ex. att ha en begärd registreringsskylt, som vid bearbetningen av tiden i batch-jobbet är tom och därmed skapas inga överföringsorderrader. Det här misslyckade händelsemeddelandet kan antingen tas bort med hjälp av alternativet **ta bort** eller så kan du lägga till nödvändig fysisk behållning på registreringsskylten och använda alternativet **återställning** för alla relaterade händelsemeddelanden.

Mer information finns i [händelsebearbetning för lagerställe](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>Följa upp exempel på scenariohantering

Under detta scenario inträffade följande:

1. Med lagerställeappen valde du ett menyalternativ som använder aktivitetskoden **skapa överföringsorder från registreringsskyltar**.
1. Appen ber dig välja destinations lagerställe för överföringsordern. Käll lagerstället är alltid det som du för närvarande är inloggat som arbetare.
1. På val av destination lagerställe reserverades ett ID-nummer för den kommande överföringsordern (baserat på nummerserien för överföringsorder som definierats i systemet) men det gick inte att skapa ännu en överföringsorder.
1. När du skannar registreringsskylt *LP10* som innehåller lagerbehållning som ska flyttas till det nya lagerstället, lades **händelse för lagerställeapp** i kön som bearbetas senare. Lagerställehändelsen innehöll meddelandeinformation om sökningen, inklusive det avsedda överföringsordernumret.
1. I lagerställeappen när knappen **Slutför order** är vald skapas en ny händelse för lagerställeapp **Slutför överföringsorder** skapas och relaterad befintlig händelse **Skapa överföringsorder**, ändra status till **I kön**.
1. I servern plockade **Bearbeta batch-jobb distributionslagerappen** upp händelsen **I kö** samlar den behållning som är relaterad till den skannade ID-nummer. Baserat på behållning den faktiska överföringsorder posten och tillhörande rader skapades. Jobbet fyllde också i fältet **Utgående leveransprincip** för överföringsorder med värdet baserat på konfigurerat *Släpp- och levereransbekräftelse* och länkade registreringsskylten mot linjerna för strategi **Registrerad skylt**.
1. Baserat på överföringsordern fältet **Utgående leveransprincip** värde resulterade nu frågan **Automatisk frisättning av överföringsorder batchjobb** i att släppa överföringsordern till leveranslagret. Och på grund av inställningarna för den använda **påfyllnadsmallen**, **arbetsmallen** och **platsdirektiven** beror automatiska processer på att **Laststatus** uppdaterades till *Lastad*.
1. **Batchjobbet för behandla utgående leverans** körs för lasten, vilket resulterar i att överföringsordern som levereras och leveransavisering (ASN) genereras.
1. Tidsinställningen för alla dessa händelser beror på inställningarna **upprepning** för de batchjobb som skapas.

## <a name="frequently-asked-questions"></a>Vanliga frågor

### <a name="mobile-device-menu-item-setup"></a>Inställning av menyalternativ för mobila enheter

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>Varför visas inte "skapa överföringsorder från ID-nummer" i listrutan för menyalternativ arbetsaktivitet?

Funktionen *Skapa och bearbeta överföringsorder från lagerställeappen* måste aktiveras. Mer information finns i [Aktivera skapa överföringsorder från lagerställeapp](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-app-processes"></a>Lagerställeappprocesser

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>Varför visas inte meny knappen "Slutför beställning"?

Du måste ha minst ett ID-nummer tilldelat till överföringsordern.

#### <a name="can-several-warehouse-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>Kan flera användare av lagerställeappen lägga till ID-nummer för samma överföringsorder samtidigt?

Ja, flera lagerarbetare kan skanna ID-nummer till samma överföringsorder.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>Kan samma ID-nummer läggas till på olika överföringsorder?

Nej, ett ID-nummer kan bara läggas till på en överföringsorder åt gången.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>När du har valt knappen Slutför beställning kan jag sedan lägga till fler ID-nummer för överföringsordern?

Nej, du kan inte lägga till fler ID-nummer till en överföringsorder som har en händelse för lagerställeapp **Slutförd överföringorder**.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>Hur söker jag efter befintliga överföringsorder som ska användas via knappen "Välj överföringsorder" i lagerställeappen om ordern ännu inte har skapats i serversystemet?

Du kan för närvarande inte söka efter överföringsorder i appen, men du hittar överföringsordernumren på sidan **händelser för lagerställeapp**. Mer information finns i [Fråga om händelser i lagerställeapp](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-app"></a>Kan jag manuellt välja överföringsordernumret som ska användas från lagerställeapp?

Det går bara att använda automatiskt genererade överföringsordernummer via nummerserier.

### <a name="background-processing"></a>Behandling i bakgrunden

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>Hur ska jag rensa poster i kön med händelsemeddelanden i mina lagerställeappar?

Du kan visa och underhålla detta på sidan **Händelser för lagerställeapp**. Mer information finns i [Fråga om händelser i lagerställeapp](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>Varför uppdateras inte inställningen "inleveransdatum" i överföringsordern enligt inställningen för "leveransdatumkontroll"?

Överföringsorder skapas utan att du använder funktionerna **leveransdatumkontroll**.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>Kan jag använda ett ID-nummer som har fysiskt negativt lagerbehållning?

Funktionen har endast stöd för positiva fysiska behållningsartiklar. Se till att du har positiva fysiska lagerbehållningar på lagerställe och lagerstatusnivå innan du tilldelar ID-nummer till en överföringsorder.
