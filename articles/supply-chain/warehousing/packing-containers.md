---
title: Packa behållare för leverans
description: Den här artikeln beskriver förpackningsprocessen som gör att du kan validera lagerartiklar och packa dem i behållare.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 171b9f1dcb1d4ece63bc0beeb71f45b9f8ae7bba
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220618"
---
# <a name="pack-containers-for-shipment"></a>Packa behållare för leverans

[!include [banner](../../includes/banner.md)]

Behållarens packningsprocess beskriver förpackningsprocessen som gör att du kan validera lagerartiklar och packa dem i behållare. Under den här processen plockar lagerarbetare vanligtvis lagerartiklar från lagringsområden i bulk och flyttar dem till ett förpackningsområde. Där kontrollerar flera lagerarbetare artikelkvantiteterna och typerna och tilldelar dem till lämpliga behållarstorlekar. När en behållare är fullpackad stängs den och flyttas till det utgående hamnområdet, där den görs redo för leverans.

Behållare representerar fysiska strukturer som artiklar är förpackade i och du kan spåra information om behållare i systemet. Den här informationen kan vara användbar under transportplanering, särskilt om du beräknar leveransavgifter baserat på behållare. Innan du levererar kan du visa antalet behållare som används i en leverans, typerna av behållare som används och de fysiska dimensionerna för varje behållare (till exempel total volym och vikt).

Flera relaterade utgående lagerställefunktioner kan användas med behållare. Mer information finns i följande artiklar:

- [Påfyllnad vid skapande av behållare](wave-containerization.md)
- [Utgående sortering](outbound-sorting.md)
- [Leverans av små paket](small-parcel-shipping.md)
- [Bekräfta och överföra](confirm-and-transfer.md)
- [Ställ in olika dimensioner för förpackning och lagring](packing-vs-storage-dimensions.md)
- [Förpackningsarbete för att packa utgående behållare och bearbeta försändelser](packing-work.md)
<!-- KFM: Add link to upcoming topic when available (10.0.31): [Manual packing on the Warehouse management mobile app](manual-packing-on-the-warehouse-management-mobile-app.md) -->

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Ställ in lagerstället så att manuella förpackningsoperationer används

Du kan organisera dina utgående operationer på två grundläggande sätt:

- **Skapa och bearbeta påfyllnad** – Arbetarna plockar artiklar baserat på utgående lagerställearbete. Artiklarna placeras sedan direkt på en utlastningsplats, där de är klara för omedelbar leverans. Mer information om hur du konfigurerar och använder denna process finns i [Skapa och bearbeta påfyllnad](wave-processing.md).
- **Manuell förpackning vid förpackning** – Den här processen innebär en extra operation mellan plocknings- och leveransoperationerna. I stället för att placera lagret på en *vikdörr som leveransplatsen* kan medarbetare placera det på en *förpackningsplats*. De hanterar sedan förpackningsprocessen vid förpackningsprocessen genom att använda sidan **packa** i webbklienten. För att aktivera denna process måste du konfigurera systemet så som beskrivs i det här avsnittet.

### <a name="set-up-warehouse-locations-for-packing"></a>Ställ in lagerplatser för packning

Du måste ha minst en förpackningsplats där arbetare ska placera lagerartiklar så att de kan packas i behållare. För mer information om hur du skapar lagerplatser, se [Konfigurera platser i ett WMS-aktiverat distributionslager](tasks\configure-locations-wms-enabled-warehouse.md). I följande underavsnitt beskrivs hur du skapar och anger förpackningsplatser.

#### <a name="set-up-location-types-for-packing"></a>Ställ in platstyper för packning

Du måste ange en *platstyp* för förpackningsplatserna. Platstyper kan användas som filtreringsalternativ för att styra de olika lagerstyrningsprocesserna. Namnet på varje platstyp beskriver vanligtvis något om hur den platstypen ska användas. Platstypen som du ställer in här måste associeras med varje plats som används för förpackningsoperationer.

Följ dessa steg för att ställa in en platstyp.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platstyper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till ett platstyp i rutnätet.
1. Ställ in följande fält för den nya platstypen:

    - **Platstyp** – Ange ett namn på platstypen. Varje namn måste vara unikt och bör beskriva något om hur platstypen är avsedd att användas.
    - **Beskrivning** – Ange en kort beskrivning av platstyp.

#### <a name="inform-the-system-about-the-packing-location-type"></a>Informera systemet om förpackningsplatstypen

När du har skapat en platstyp måste du ställa in systemet för att känna igen den som platstypen som ska användas för förpackningsoperationer.

Följ dessa steg om du vill ställa in den platstyp som används för förpackningsoperationer.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**
2. På fliken **Allmänt** på snabbfliken **Platstyper** ange fältet **Typ av packningsplats** till den platstyp som du ska använda för att identifiera packstationer.

> [!NOTE]
> Om du uppgraderar från en version av Microsoft Dynamics AX har statusen *förpackas* tagits bort från försändelser och lastning eftersom den inte fungerar konsekvent och orsakade redundanta data. Därför är listsidorna **I leveranser** och **Last som packas** inaktuella. Behållare som måste packas spåras på platsnivå.
>
> I tidigare versioner definierade du packningsplatsen med hjälp av **Profil-ID för packplats** på fliken **Förpackning** på **Parametrar för lagerstyrning** för att ange en *platsprofil*. I den aktuella versionen använder du fältet **Typ av packningsplats** på fliken **Allmänt** på sidan **Parametrar för lagerstyrning** för att ange *platstyp*, enligt beskrivningen i den här artikeln. Det nya fältet anpassas bättre efter processen för identifiering av mellanlagringsplatser och slutliga leveransplatser.
>
> Även om du kan fortsätta använda det gamla **Profil-ID för packplats** rekommenderar vi att du börjar använda det nya fältet **Typ av packningsplats** istället eftersom det gamla fältet så småningom kommer att fasas ut.
>
> Om du rensar inställningen för den gamla fältet **Profil-ID för packplats** och sedan spara sidan, kommer fältet att inaktiveras permanent. För installationer där fältet **Profil-ID för packplats** aldrig har använts, kommer det alltid att vara inaktiverat. När du har avmarkerat inställningen av fältet **Profil-ID för packningsplats** använd inställningarna som beskrivs i den här artikeln för att ställa in och identifiera din packningsplats.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Ställ in platsprofiler för packningsplatser

Varje *platsprofil* innehåller information om respektive platsprofil och regler som gäller för de associerade platserna. Eftersom du behöver minst en plats för att kunna använda i förpackningsåtgärder måste du skapa en platsprofil för den, utöver platstypen. Varje profil kan användas av ett valt antal platser. Platser som används för packning måste ställas in för att spåra registreringsskyltar.

Följ dessa steg om du vill ställa in en platsprofil för en förpackningsplats.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. Välj antingen en befintlig profil i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny.
1. Ange följande fältvärden i den valda profilen:

    - **Platsprofil-ID** – Ange ett unikt ID för profilen.
    - **Namn** – Ange ett beskrivande namn för profilen.

1. På snabbfliken **Allmänt** ange följande fält:

    - **Platsformat** – Välj det platsformat som ska användas för den aktuella platsen. Platsformat är ett namnhanteringssystem som används för att skapa unika och konsekventa unika namn för de olika platsbingepositioner som används inom ett lagerställe. Om du inte redan har formatet du behöver kan du skapa det genom att gå till **Lagerstyrning \> Inställningar \> Lagerställeplats \> Platsformat**. Mer information finns i [Konfigurera platser i ett WMS-aktiverat lagerställe](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Platstyp** – Välj den platstyp som har ställts in som förpackningsplatstyp på sidan **Lagerstyrningsparametrar**, enligt beskrivningen tidigare i den här artikeln.
    - **Använd licensspårning** – Ställ in det här alternativet på *Ja* för förpackningsplatser. Systemet måste kunna spåra registreringsskylt-ID på förpackningsplatser, så att det kan styra packningsprocessen.
    - **Tillåt negativt lager** – Ange det här alternativet till *Nej* för förpackningsplatser.
    - **Tillåt blandade artiklar** – Ange det här alternativet till *Ja* för förpackningsplatser. Den här inställningen är obligatorisk eftersom många olika artikelnummer vanligtvis tas till förpackningsplatserna samtidigt.
    - **Tillåt blandade lagerstatusar** – Ange det här alternativet till *Ja* för förpackningsplatser. Den här inställningen krävs eftersom artiklar som har olika lagerstatus tas vanligtvis till förpackningsplatserna samtidigt.
    - **Tillåt blandade lagerbatchar** – Ange det här alternativet till *Ja* för förpackningsplatser. Det här alternativet ställs automatiskt in på *Ja* närhelst alternativet **Tillåt blandade artiklar** anges till *Ja*.

#### <a name="set-up-packing-locations"></a>Ställ in packplatser

Du måste ha minst en *plats* där arbetare ska placera lagerartiklar så att de kan packas i behållare.

Följ dessa steg för att lägga till en packningsplats.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till ett plats.
1. Ställ in följande fält för den nya plats:

    - **Distributionslager** – Ange det distributionslager där förpackningsplatsen måste vara.
    - **Plats** – Ange ett namn för den nya platsen.
    - **Platsprofil-ID** – Se till att ange det ID som du skapade i det föregående avsnittet.

## <a name="set-up-the-packing-process"></a>Ställa in packingsprocess

Det här avsnittet beskriver hur man konfigurerar inställningar som aktiverar förpackningsprocessen och låter arbetare packa lager i behållare.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Ställa in policyer för packning av behållare

Varje *packning av behållare* definierar hur en behållare ska behandlas. Varje gång du skapar en ny behållare väljer du också en förpackningspolicy för behållare som ska användas för den.

Följ dessa steg för att konfigurera en policy för packning av behållare.

1. Gå till **Lagerstyrning \> Inställningar \> Behållare \> Policyer för packning av behållare**.
1. Välj antingen en befintlig policy i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny.
1. Ange följande fältvärden i den nya eller valda policyns rubrik:

    - **Förpackningspolicy för behållare** – Ange ett unikt namn för policyn.
    - **Beskrivning** – Ange ett beskrivande namn för policyn.

1. Ange följande fält på fliken **Översikt**: I dessa fält kan du ange vilka åtgärder som ska vidtas när behållaren är stängd, om du vill använda den med eller utan att skapa arbete och när behållaren ska frisläppas från förpackningsbehållaren.

    - **Distributionslager** – Välj det distributionslager där packningspolicy gäller.
    - **Standardplats för slutlig leverans** – Ange önskad plats för behållaren efter att den har stängts. Detta fält är endast tillgängligt när fältet **Frisläppningspolicy för behållare** ange *Gör tillgänglig vid slutlig leveransplats*.
    - **Standardplats för sortering** – Det här fältet används med den [utgående sortering](outbound-sorting.md) kapaciteten.
    - **Viktenhet** – Välj standardmåttenheten som ska användas när en behållare stängs och blir nedsvald. Denna måttenhet är vanligtvis den måttenhet som används av en våg vid förpackningsapparaten. Det här fältet gäller för policyer med eller utan att skapa arbete.
    - **Policy för stängning av behållare** – Välj ett av följande alternativ för att definiera vad som ska hända när behållaren är stängd:

        - *Automatisk frisläppning* – Behållaren betraktas som frisläppt från förpackningsåtgärden och åtgärden som anges i fältet **Frisläppningspolicy för behållare** utlöses.
        - *Försenad frisläppning* – Behållaren kommer inte omedelbart att frisläppas från förpackningsbehållaren. En lagerarbetare måste manuellt frisläppa det senare.
        - *Valfritt* – Även om en medarbetare stänger behållaren kan de välja om behållaren ska frisläppas.

        Om förpacknings- och förpackningsbehållare hanterar framförallt enstaka behållare som levereras direkt till kunder är det vanligaste sättet att frisläppa behållare omedelbart. Om packstationen hanterar försändelser som består av flera behållare eller till och med lastpallar, är det förmodligen bäst att skjuta upp frisläppandet tills hela försändelsen eller pallen har packats och är klar för avhämtning.

    - **Frisläppningspolicy för behållare** – Välj ett av följande alternativ för att definiera vad som ska hända när behållaren frisläpps från packningsplatsen:

        - *Gör tillgänglig vid slutlig leveransplats* – Uppdatera behållaren till den slutliga leveransplatsen. Om du väljer det här alternativet använder du fältet **Standardplats för slutgiltig leverans** för att ange en föredragen plats för behållaren efter att den har stängts.
        - *Skapa arbetsuppgift för förflyttning av behållaren från förpackningsstationen* – Skapa arbete för att flytta containern från packstationen till uppställningsplatsen eller direkt till vikdörren. Använd fältet **Arbetsmall** för att ange arbetsmallen som ska användas när arbete skapas för behållaren.
        - *Tilldela behållare till utgående sorteringsposition* – Det här alternativet används med den [utgående sorterings](outbound-sorting.md) kapaciteten.

        I de flesta fall rekommenderar vi att du skapar arbete för att flytta behållare, eftersom det här sättet bättre representerar de faktiska manuella processerna i lagerstället. För enkla scenarier, eller situationer där förpackningsbehållaren finns direkt i leveransområdet, kan det dock vara bättre att behållaren omedelbart blir tillgänglig vid den slutliga leveransplatsen.

    - **Arbetsmall** – Välj arbetsmallen som ska användas när arbete skapas för behållaren. Det här fältet är endast tillgängligt om fältet **Frisläppningspolicy för behållare** anges till *Skapa arbetsuppgift för förflyttning av behållaren från förpackningsstationen* och relaterad till en arbetsordertyp som är namngiven *Plockning för packad behållare*. Mer information finns i [Arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).

    I de återstående stegen kommer du att konfigurera inställningar som är relaterade till *manifestering*. Manifestering är processen att specificera vikten på en behållare, behållargrupp eller försändelse, tillsammans med spårnings-ID som tas emot från en transportleverantör. Dynamics 365 Supply Chain Management integreras inte med externa transportleverantörssystem. Istället måste lagerarbetare skriva ut etiketter som tas emot från transportleverantören och sedan skanna ett spårningsnummer när de har slutfört proceduren.

    Eftersom behoven varierar mellan kunder och även mellan försändelser innebär förpackningspolicyn att arbetsflödet blir mer flexibelt. Du kan ställa in manifest för behållare, behållargrupper och försändelser i alla kombinationer.

    Om du använder en flernivåprocess, måste arbetarna få alla behållare innan de kan använda den relaterade behållargruppen och de måste dock använda alla behållargrupper innan de använder den relaterade leveransen.

1. Ange följande fält på snabbfliken **Behållarmanifest**:

    - **Manifestera automatiskt när behållare stängs** – Ange det här alternativet till *Ja* för att använda manifestinformation som en del av stängningsprocessen för behållare. Om du inte använder transportintegrering måste informationen registreras manuellt.
    - **Manifestkrav för behållare** – Välj ett av följande alternativ:

        - *Ingen* – Ingen manifestationsprocess kommer att användas.
        - *Manuell* – Ett arbete krävs i förpackningsarbetsflödet. Systemet tillåter inte att en behållare stängs eller frisläpps innan den är färdig.
        - *Transporthantering* – Manifestering kommer att göras genom transporthanteringsmotorer (TMS). Eftersom det här alternativet kräver anpassad utveckling för att en viss motor ska implementeras för transportprovidern fungerar det inte i rutan i den aktuella versionen.

    - **Skriv ut behållarinnehåll** – Ange det här alternativet till *Ja* om rapporten över behållarens innehåll automatiskt ska skrivas ut när en behållare registreras som stängd. Rapporten kan även skrivas ut på begäran.

1. På snabbfliken **Behållargruppmanifest** i fältet **Krav på manifest för behållargrupp** väljer du ett av följande alternativ:

    - *Ingen* – Behållargruppens manifest går inte att inkludera som ett krav i arbetsflödet.
    - *Manuell* – Behållargruppens manifest går inte att inkludera som ett krav i arbetsflödet. Alla behållare som inkluderas i gruppen måste manifesteras och stängas innan det går att manifestera gruppen. Välj det här alternativet om du måste fylla i en kartong för varje behållargrupp som är förpackad på förpackningsbehållaren. Du väljer vanligtvis det här alternativet om behållare packas på en lastpall och hela lastpallen blir förpackad.

    > [!NOTE]
    > Den aktuella versionen stöder inte manifestrapporter för behållargrupper och det finns inget stöd för TMS-motorer för behållargrupper.

1. Ange följande fält på snabbfliken **Leveransmanifest**:

    - **Manifestkrav för leverans** – Välj ett av följande alternativ:

        - *Ingen* – Leveransgruppens manifest går inte att inkludera som ett krav i arbetsflödet.
        - *Manuell* – Leveransgruppens manifest kommer att inkluderas som ett krav i arbetsflödet. Inga behållare för en försändelse kan frisläppas förrän manifestering slutförs.
        - *Transporthantering* – Manifestering kommer att göras genom TMS tariffmotorer. Eftersom det här alternativet kräver anpassad utveckling för att en viss motor ska implementeras för transportprovidern fungerar det inte i rutan i den aktuella versionen.

        Leveransmanifestering bör vara aktiverat om du måste fylla i ett manifest för hela försändelsen som packas vid packningsstationen. Den används vanligtvis när ett konsoliderat manifest behövs även om försändelsen består av flera behållare eller behållargrupper.

    - **Skriv ut följesedel** – Ställ in detta alternativ till *Ja* om du automatiskt vill skriva ut följesedeln som en del av leveransmanifestet. Följesedeln kan även skrivas ut på begäran.

### <a name="set-up-container-types"></a>Ställ in behållartyper

Under den manuella förpackningsprocessen måste behållare skapas innan artiklar kan packas i dem. Varje behållare måste baseras på en *behållartyp* som definierar en behållares maximala fysiska volym och viktkapacitet.

Följ dessa steg för att skapa en behållartyp.

1. Gå till **Warehouse Management \> Inställningar \> Behållare \> Behållartyper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till behållartyp.
1. Ställ in följande fält för den nya behållartypen:

    - **Kod för behållartyp** – Ange ett unikt ID för behållartypen.
    - **Beskrivning** – Ange en beskrivning av den nya behållartypen.
    - Ange behållarens verkliga eller beräknade vikt i fältet **Taravikt**.
    - **Högsta nettovikt** – Ange den maximala vikt som behållaren kan hålla.

1. I avsnittet **Behållardimensioner** i fälten **Längd**, **Bredd**, **Höjd** och **Volym**, ange de fysiska dimensionerna för själva behållaren.
1. I avsnittet **Maximala** i fälten **Längd**, **Bredd**, **Höjd** och **Volym**, ange de maximala fysiska dimensionerna som behållaren kan hantera.
1. Du kan definiera ytterligare attribut för behållartyper som är associerade med andra operationer som använder behållare. Mer information finns i [Skapande av behållare](wave-containerization.md).

> [!NOTE]
> För den manuella packningsprocessen använder systemet endast värdet av **Maximal nettovikt** och värdet för fältet **Volym** i avsnittet **Maximala**.

### <a name="set-up-packing-profiles"></a>Ställa in förpackningsprofiler

*Förpackningsprofiler* är nödvändiga för förpackningsprocessen. De kan väljas eller ställas in som standard när du startar en förpackningsoperation på sidan **Packa**.

Följ dessa steg för att skapa en förpackningsprofil.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.
1. Välj antingen en befintlig profil i listvyn eller **Ny** i åtgärdsfönstret för att skapa en ny.
1. Ange följande fältvärden i den valda profilen:

    - **Packningsprofil-ID** – Ange ett kort ID för profilen.
    - **Beskrivning** – Ange en beskrivning av förpackningsprofilen.
    - **Förpackningspolicy för behållare** – Välj den förpackningspolicy som gäller för profilen. För mer information, se avsnittet [Konfigurera packningspolicyer för behållare](#packing-policy) i denna artikel.
    - **Läge för behållar-ID** – Välj om ett behållar-ID ska genereras automatiskt när en behållare skapas, eller om det måste skapas manuellt.
    - **Behållartypen** – Välj den behållartyp som används som standard när en ny behållare skapas.
    - **Skapa behållare automatiskt när behållare stängs** – Markera den här kryssrutan för att automatiskt skapa en ny behållare om den tidigare behållaren är stängd och en eller flera rader finns kvar i den aktuella försändelsen.

### <a name="set-up-warehouse-workers"></a>Ställ in lagerarbetare

Varje användare eller arbetare som packar containrar genom att använda sidan **Packa** för webbklienten eller aktivitetskoden *Förpackning* i mobilappen Hantering av distributionslager måste ha ett användarkonto som är associerat med posten *arbetare/person* för att de nödvändiga säkerhetsrättigheterna tilldelas. (För mer information om hur du konfigurerar användare, se [Skapa nya användare](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md).)

Följ dessa steg för att ställa in posten *arbetare/person* för förpackningsprocessen.

1. Gå till **Warehouse management \> Inställningar \> Arbetare**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till en arbetsanvändare.
1. Ställ in fältet **Arbetare** till den befintliga arbetarposten som är definierad i modulen **personal** för användaren som ska slutföra packningsprocessen.
1. På snabbfliken **Profil** anger du följande fält:

    - **Förpackningspolicy för behållare** – Välj en förpackningspolicy för behållare som definierar hur behållare vid förpackningsenheten ska bearbetas. Förpackningspolicyn för behållare som har valts här väljs för arbetaren när han eller hon öppnar förpackningsbehållaren. Mer information finns i följande blogginlägg: [Förbättrad förpackningsfunktion](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **Förpackningsprofil-ID** – Välj ett förpackningsprofil-ID som definierar de förpackningspolicy- och behållarinställningar som bör användas. Om det valda förpackningsprofil-ID:t är kopplat till en förpackningspolicy för behållare kan du inte ändra inställningen för fältet **förpackningspolicy för behållare** på den här sidan.

1. På snabbfliken **Standardförpackningsstation**, välj standardplats, lager och plats som gäller för arbetaren.
1. Om arbetaren ska använda mobilappen Lagerstyrning för att hantera och registrera förpackningsarbete i behållare ställer du på snabbflikarna **användare** in ett eller flera konton som arbetaren kan använda när han eller hon loggar in på programmet. Mer information finns i [användarkonton för mobil enhet](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Exempelscenario

I det här avsnittet ges ett exempelscenario som visar hur du skapar en order och paketar artiklarna.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda dessa scenarier som vägledning för funktionen när du använder ett produktionssystem. I så fall måste du dock ersätta dina egna värden för varje inställning som beskrivs här.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Logga in som en användare som kan göra förpackningsarbete

Logga in i Supply Chain Management med ett användarkonto som har den behörighet som krävs för att packa behållare. Användaren *Julia Funderburk* ingår som en del av demodata och har nödvändiga behörigheter. Användaren har användar-ID:t *Admin*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Skapa en försäljningsorder och slutför arbetet

Följ dessa steg om du vill skapa en försäljningsorder och slutföra arbetet med att flytta de beställda artiklarna till förpackningsordern.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj *US-005*.
1. Välj **OK** för att stänga dialogrutan.
1. Den nya försäljningsordern öppnas och omfattar en enda, tom rad på snabbfliken **Försäljningsorderrader**. Ställ in följande värden på den nya orderraden:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *2*
    - **Plats:** *6*
    - **Lagerställe:** *62*

1. Medan beställningsraden fortfarande är vald, välj **Lager \> Reservation** i verktygsfältet på snabbfliken **Försäljningsorderrader**.
1. På sidan **Reservation** i åtgärdsfönstret väljer du **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Ett meddelande visar leverans- och våg-I:erna för ordern.

1. Medan beställningsraden fortfarande är vald, välj **Lagerställe** \> **Information om arbete** i verktygsfältet på snabbfliken **Försäljningsorderrader**. Om du använder batchbearbetning för att köra dina påfyllningar, kan du behöva vänta en kort tid för att arbete ska skapas.
1. På sidan **Arbete** i åtgärdsfönstret på fliken **Arbete**, välj **Slutfört arbete**.
1. På sidan **Arbetet slutförs** ange fältet **Användar-ID** till *62*.
1. I åtgärdsfönstret, välj **Validera arbete**.
1. När du får ett meddelande om att ditt arbete är giltigt väljer du **Slutför arbetet** med att plocka lagerartiklarna och placera dem på *pack* platsen.
1. Notera det värde för **försändelse-ID** som visas för arbetet i det övre rutnätet.

### <a name="pack-the-ordered-items-into-a-container"></a>Packa de beställda artiklarna i en behållare

Lagerartiklarna har nu förts in i förpackningsområdet och är klara att packas i behållare. Följ dessa steg för att skapa en ny behållare i systemet och packa den.

1. Gå till **lagerstyrning \> packa och skapa behållare \> packa**.
1. I dialogrutan **Välj packningsstation** ställ in följande värden:

    - **Plats:** *6*
    - **Lagerställe:** *62*
    - **Plats:** *Packa*
    - **Packprofil-ID:** *WH62*

1. Välj **OK**.
1. På sidan **Packa** i fältet **ID-nummer eller leverans** ange det leverans-ID som du noterade tidigare. Du bör nu se de återstående oförpackade artiklarna på snabbflikarna **Öppna rader**.
1. I åtgärdsfönstret, välj **Ny behållare** för att skapa en behållare i systemet.
1. I dialogrutan **ID för den nya fraktbehållaren** ange fältet **Behållartyp** till *SmallBox*.
1. Skapa behållare genom att välja **OK**.
1. Välj **OK** om du vill återgå till sidan **Packa**. Snabbflikarna **Öppna behållare** visar nu värdet för **Behållar-ID** för den behållare som du har skapat.
1. I det här scenariot packas bara en av de beställda artiklarna för nu. Ange därför följande värden på snabbfliken **artikelpackning**:

    - **Kvantitet:** *1.00*
    - **Identifierare:** *A0001*

    Omedelbart efter att du valt värdet **Identifierare** uppdaterar sidan snabbflikarna **Öppna rader** och **Alla rader** för att visa att en artikel har packats. Du bör nu ha packat en av de två delarna av artikel *A0001*.

1. Klicka på **Stäng behållare** i åtgärdsfönstret.
1. I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill fylla i standardvärdet **bruttovikt**.
1. Välj **OK** om du vill stänga behållaren.

> [!TIP]
> Det finns olika sätt att visa behållare baserat på kontext. När du till exempel förpackar en försändelse är det ofta praktiskt att visa antingen behållare som ingår i försändelsen eller alla behållare som är fysiskt på en förpackning. På sidan **Förpackningsstation** har du knappar som du kan använda för att visa alla öppna och stängda behållare i en förpackningsbehållare. Dessa vyer begränsas inte till en viss försändelse. De kan vara till stor hjälp i situationer där en arbetare packar en behållare, och en annan arbetare använder och frisläpper behållaren.
>
> En konsoliderad vy över alla behållare är också tillgänglig. Den här vyn är oftast användbar för användare som arbetar utanför ett enda förpackningsmaterial. För att se den går du till **Lagerstyrning \> Packning och skapande av behållare \> Behållare**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
