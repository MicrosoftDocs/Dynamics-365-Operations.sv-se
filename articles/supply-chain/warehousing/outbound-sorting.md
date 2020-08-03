---
title: Utgående sortering
description: Den här ämnet innehåller information om utgående sortering. Den här funktionen gör det enklare att hantera små behållare och hjälper lagerarbetarna bättre att planera och organisera lastpallkapaciteten i lastbilen.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e72249e26fb8f291f804cf5f2e4ce98bf88cd5bf
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596276"
---
# <a name="outbound-sorting"></a>Utgående sortering

[!include [banner](../includes/banner.md)]

Den här funktionen gör det enklare att hantera små behållare och hjälper lagerarbetarna bättre att planera och organisera lastpallkapaciteten i lastbilen. När du använder utgående sortering kan du sortera packade behållare efter rätt lastpall efter att ha varit på en förpackningsstation. Du kan också skapa en packningshierarki.

Med den här funktionen kan du bygga lastpallar från behållare som är förpackade via packningsfunktionen. Behållaren skickas inte till den slutgiltiga leveransplatsen som den befinner sig i det ursprungliga förpackningsflödet. I stället kan arbetare stänga behållaren och flytta den till en sorteringstypplats. De kan sedan sortera behållare efter befattningar, som var och en har ID-nummer (LP). När behållarna har sorterats kan arbete skapas för att skicka hela LP till de slutliga leveransplatserna eller fasplatser, baserat på platsdirektiv eller dina egna krav. Dessutom kan lagrets stängningsposition omedelbart flytta lagret till den slutgiltiga leveransplatsen och plocka det till ordern.

## <a name="turn-on-the-outbound-sorting-feature"></a>Aktivera funktionen för utgående sortering

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *utgående sortering*

## <a name="setup"></a>Konfigurera

I det här scenariot måste du använda standard **USMF** för demodata och lagerställe *62*. Du måste också slutföra inställningarna som beskrivs i följande underavsnitt.

### <a name="set-up-a-wave-template"></a>Ställa in en påfyllnadsmall

Den här inställningen kommer automatiskt bearbeta påfyllnaden och skapa arbete när en rad frisläpps till lagerstället.

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. I mallistan välj **lagerställe 62**.
1. På snabbfliken **Allmänt** ser du till att alternativet **Bearbeta påfyllnaden vid släpp till lager** anges till *Ja*.

### <a name="set-up-a-worker"></a>Skapa en arbetare

Förpackningsstationen anses vara en plats. Lagerarbetare som loggar in på förpackningsstationen kan se och arbeta på endast försändelser och behållare som planeras vid den specifika förpackningsplatsen. En användare som loggar in på Microsoft Dynamics 365 måste ställas in som arbetare i lagerstyrning. Om användarens namn inte visas i listan över arbetsuppgifter lägger du till det med hjälp av följande procedur.

> [!NOTE]
> Dessa steg utgår från att användaren redan finns i systemet och att den har associerats med en medarbetare eller arbetare i modulen **personal**.

1. Gå till **Lagerstyrning \> Inställningar \> Arbetare**.
1. Välj **Ny**.
1. I fältet **Arbetare** väljer du målanvändaren i listan med medarbetare.
1. Välj **Välj**.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Användare** väljer **Ny** för att skapa ett mobilenhetskonto och anger följande värden:

    - **Användar-ID:** Ange ett unikt ID.
    - **Användarnamn:** Ange ett namn på ID.
    - **Standardlagerställe:** *62*
    - **Menynamn:** *huvud*

1. Klicka på **Spara** i åtgärdsfönstret.
1. Dialogrutan **Ange lösenord** visas, där du kan skapa ett enkelt lösenord som användaren kan använda för att logga in på mobilappen. Ange följande värden.

    - **Lösenord:** Ange ett enkelt lösenord.
    - **Bekräfta lösenord:** Ange samma lösenord igen.

1. Välj **Ange lösenord**.

    Ett meddelande i åtgärdscentret meddelar att lösenordet har ställts in för den användare som du har skapat.

### <a name="create-a-location-type"></a>Skapa en platstyp

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platstyper**.
1. I åtgärdsfönstret väljer du **Ny** för att skapa en platstyp och anger följande värden:

    - **Platstyp:** *SORTERA*
    - **Beskrivning:** *Sortera*

1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-warehouse-management-parameters"></a>Ställ in parametrar för lagerstyrning

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **Allmänt** på snabbfliken **Platstyper** ange fältet **Sortera platstyp** till *SORTERA*.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-a-location-profile"></a>Konfigurera en platsprofil

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Platsprofil-ID:** *sortering*
    - **Namn:** *sortering*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Platsformat:** *ASRB* (gång-rack-hylla-fack)
    - **Platstyp:** *SORTERA*
    - **Använd spårning av ID-nummer:** *Ja*
    - **Tillåt blandade artiklar:** *Ja* (om du ställer in det här alternativet till *Ja* kommer alternativet**Tillåt blandade lagerbatchar** automatiskt till *Ja* och kan inte ändras separat.)

1. Välj **Spara**.

### <a name="set-up-a-location"></a>Konfigurera en profil

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.
1. I rubriken, rensa kryssrutan **Generera kontrollsiffra för plats**.
1. I åtgärdsfönstret väljer du **Ny** för att skapa en plats och anger följande värden:

    - **Lagerställe:** *62*
    - **Plats:** *SORT*
    - **Platsprofil-ID:** *SORTERAERING*

1. Välj **Spara**.

### <a name="set-up-an-outbound-sorting-template"></a>Ställa in en mall för utgående sortering

Mallen för utgående sortering avgör om arbetet skapas utanför sorteringsplatsen och om sortering utförs manuellt eller automatiskt.

I det här scenariot ska du skapa en mall för utgående sortering för att skapa lastpallar efter förpackningsstationen.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange följande värden i nya mallens rubrik:

    - **Mall för utgående sorterings-ID:** *AutoWork*
    - **Beskrivning:** *Skapa automatiskt arbete*
    - **Malltyp för utgående sortering:** *Behållare*
    - **Lagerställe:** *62*
    - **Plats:** *SORT*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Sortera verifieringstyp:** *positionsskanning*
    - **Skapa arbete vi positionsstängning:** *Ja*

        Om detta alternativ är inställt på *Ja*, när positionen är stängd kommer arbetet att skapas för att flytta lager till den slutliga leveransplatsen. Om den är inställd på *Nej*, lager kommer omedelbart att väljas till beställningen när positionen är stängd.

    - **Befattningstilldelning:** *Automatisk*

        I detta fält anges till *Manuell*, måste användaren ange vilken plats som lagret sorteras till. Om detta anges till *automatisk* kommer systemet automatiskt att leda lagret till en plats som när det är möjligt baseras på sorteringsmallens uppdelningar.

1. Välj **Spara** för att göra knappen **Redigera fråga** i åtgärdsfönstret tillgängligt.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I frågeredigeraren, på fliken **Sortering** lägg till en rad med följande värden:

    - **Register:** *försändelser*
    - **Härlett register:** *försändelser*
    - **Fält:** *Transportföretag*

        När du har valt det här värdet kan följande meddelande visas: "fältet transportföretagstjänst är inte ett indexfält. Vill du lägga till sortering i det här? " Välj **Ja**.

    - **Sökriktning:** *Stigande*

1. Välj **OK**.
1. Följande meddelande kan visas: "gruppering återställs, fortsätt?" Välj **Ja**.

    Knappen **utgående sorterings sorteringsmallens uppdelningar** i åtgärdsfönstret blir tillgänglig.

1. I åtgärdsfönstret väljer du **utgående sorterings sorteringsmallens uppdelningar**.
1. I dialogrutan **Utgående sorteringskriterier** ställ in följande värden:

    - **Referensregisternamn:** *försändelser*
    - **Referensfältnamn:** *Transportföretag*
    - **Gruppera efter fält:** Markera den här kryssrutan om du vill gruppera försändelser per transportföretag.

1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.

### <a name="set-up-container-packing-policies"></a>Ställa in policyer för packning av behållare

1. Gå till **Lagerstyrning \> Inställningar \> Behållare \> Policyer för packning av behållare**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange följande värden i nya policyns rubrik:

    - **Policyer för packning av behållare:** *Sortera*
    - **Beskrivning:** *Sortera*

1. Ange följande värden på snabbfliken **Översikt**:

    - **Lagerställe:** *62*
    - **Standardplats för sortering:** *SORTERA*
    - **Viktenhet:** *kg*
    - **Policyn för stängning av behållare:** *Automatiskt släpp*
    - **Policyn för stängning av behållare:** *Tilldela behållare till utgående sorteringsposition*

1. Välj **Spara**.

### <a name="set-up-packing-profiles"></a>Ställa in förpackningsprofiler

Skapa en ny förpackningsprofil som ska användas tillsammans med sorteringsfunktionen.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.
1. I åtgärdsfönstret väljer du **Ny** för att skapa en rad och anger följande värden:

    - **Förpackningsprofil-ID:** *Sortera*
    - **Beskrivning:** *Sortera*
    - **Policyer för packning av behållare:** *Sortera*
    - **Läge för behållar-ID:** *Auto*
    - **Behållartyp:** *Kartong-stor*
    - **Skapa behållare automatiskt när behållare stängs:** avmarkerad (= *Nr*)

1. Välj **Spara**.

### <a name="set-up-work-classes"></a>Ställa in arbetsklasser

Skapa en arbetsklass som ska användas tillsammans med sortering.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.
1. I åtgärdsfönstret väljer du **Ny** för att skapa en arbetsklass för sortering och anger följande värden:

    - **Arbetsklass-ID:** *Sortera*
    - **Beskrivning:** *Sortera*
    - **Arbetsordertyp:** *Sorterad lagerplockning*

1. Välj **Spara**.

### <a name="set-up-mobile-device-menu-items"></a>Ställ in menyalternativ för mobila enheter

#### <a name="set-up-a-new-pallet-menu-item"></a>Ställ in menyalternativ för ny lastpallen

Skapa en menyartikel för mobila enheter för att skapa lastpallar under sortering.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Menyalternativnamn:** *Lastpallsversion*
    - **Rubrik:** *Lastpallsversion*
    - **Läge:** *Indirekt*
    - **Använd befintligt arbete:** *Nej*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Aktivitetskod:** *Utgående sortering*

        När det här fältet är inställt på *Utgående sortering* visas fältet **Mall för utgående sorterings-ID** visas.

    - **Använd processguide:** *Ja*

        När fältet **Aktivitetskod** anges till *Utgående sortering* anges det här alternativet automatiskt till *Ja*.

    - **Mall för utgående sorterings-ID:** *AutoWork*

1. Välj **Spara**.

#### <a name="set-up-a-new-loading-menu-item"></a>Ställ in menyalternativ för ny lastning

Skapa sedan ett menyalternativ där användarna kan flytta de sorterade lagerartiklarna till leveransplatsen.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Menyalternativnamn:** *Lasta från sortering*
    - **Rubrik:** *Lasta från sortering*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*

1. På snabbfliken **Allmänt** ska fältet **Dirigerad av** bör ställas in på *Användardirigerat*.
1. På snabbfliken **Arbetsklasser** välj **Ny** och ange sedan följande värden:

    - **Arbetsklass-ID:** *SORTERA*
    - **Arbetsordertyp:** *Sorterad lagerplockning*

1. Välj **Spara**.

### <a name="set-up-the-mobile-device-menu"></a>Ställ in meny för mobila enheter

Nu måste du lägga till nya menyalternativ på menyn för mobila enheter.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. Välj menyn **Utgående**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I kolumnen **Tillgängliga menyer och artiklar** hitta och välj **Lastpallsversion**.
1. Klicka på högerpilen om du vill flytta **Lastpallsversion** till en kolumn **Menystrukturen**.
1. Använd pil upp och pil ned för att sätta menyalternativet **Lastpallsversion** i önskad position på menyalternativ för mobil enhet.
1. Välj **Spara**.
1. Upprepa den här proceduren om du vill lägga till menyalternativet **Lasta från sortering** till menyn **Utgående**.

### <a name="set-up-location-directives"></a>Ställ in platsdirektiv

*Placering av direktiven* är regler som hjälper till att identifiera och sätta platserna för lager. Du måste nu skapa en regel för att hantera sorteringsarbetet.

#### <a name="set-up-a-single-sku-directive"></a>Ställa in ett SKU-direktiv

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I den vänstra rutan, ändra fältet **Arbetsordertyp** till *Sorterad lagerplockning*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Sekvens:** *1*
    - **Namn:** *Baydoor*

1. Ange följande värden på snabbfliken **Platsdirektiv**:

    - **Arbetstyp:** *Placera*
    - **Plats:** *6*
    - **Lagerställe:** *62*
    - **Flera SKU:** *Nr*

1. Välj **Spara** om du vill göra verktygsfältet för snabbfliken **Rader** tillgänglig.
1. På snabbfliken **Rader** välj **Ny** och ange sedan följande värden på den nya raden. Acceptera standardvärden i alla andra fält.

    - **Sekvens:** *1*
    - **Från:** *0*
    - **Till:** *1 000 000*

1. Välj **Spara** om du vill göra verktygsfältet på snabbfliken **Platsdirektivåtgärd** tillgänglig.
1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** och ange sedan följande värden på den nya raden. Acceptera standardvärden i alla andra fält.

    - **Sekvens:** *1*
    - **Namn:** *Baydoor*

1. Välj **Spara**.
1. På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.
1. I frågeredigeraren på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Plats*. Ställ in fältet **villkor** för den här raden till *Baydoor*.
1. Välj **OK** om du vill spara dina inställningar och stänga frågeredigeraren.

#### <a name="set-up-a-multiple-sku-directive"></a>Ställa in flera SKU-direktiv

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I den vänstra rutan, ändra fältet **Arbetsordertyp** till *Sorterad lagerplockning*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Sekvens:** *2*
    - **Namn:** *Baydoor Multi*

1. Ange följande värden på snabbfliken **Platsdirektiv**:

    - **Arbetstyp:** *Placera*
    - **Plats:** *6*
    - **Lagerställe:** *62*
    - **Flera SKU:** *Ja*

1. Välj **Spara** om du vill göra verktygsfältet för snabbfliken **Rader** tillgänglig.
1. På snabbfliken **Rader** välj **Ny** och ange sedan följande värden på den nya raden. Acceptera standardvärden i alla andra fält.

    - **Sekvens:** *1*
    - **Från:** *0*
    - **Till:** *1 000 000*

1. Välj **Spara** om du vill göra verktygsfältet på snabbfliken **Platsdirektivåtgärd** tillgänglig.
1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** och ange sedan följande värden på den nya raden. Acceptera standardvärden i alla andra fält.

    - **Sekvens:** *1*
    - **Namn:** *Baydoor Multi*

1. Välj **Spara**.
1. På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.
1. I frågeredigeraren på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Plats*. Ställ in fältet **villkor** för den här raden till *Baydoor*.
1. Välj **OK** om du vill spara dina inställningar och stänga frågeredigeraren.

### <a name="set-up-work-templates"></a>Ställ in arbetsmallar

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Ändra fältet **Arbetsordertyp** till *Sorterad lagerplockning*.
1. I åtgärdsfönstret, välj **Ny** för att skapa en arbetsmall.
1. Ange följande värden på fliken **Översikt**:

    - **Sekvens:** *1*
    - **Kod för arbetsmall:** *Sortera*
    - **Arbetsmallbeskrivning:** *Sortera*

1. Välj **Spara** om du vill göra snabbfliken **Arbetsmallinformation** tillgänglig.
1. På snabbfliken **Arbetsmallinformation** välj **Ny** för att lägga till en rad och anger sedan följande värden:

    - **Arbetstyp:** *plockning*
    - **Arbetsklass-ID:** *SORTERA*

1. Välj **Ny** igen för att lägga till en andra rad och ställa sedan in följande värden för den:

    - **Arbetstyp:** *Placera*
    - **Arbetsklass-ID:** *SORTERA*

1. Välj **Spara**.

## <a name="scenario"></a>Scenario

Det här scenariot simulerar en situation där packade behållare automatiskt ska sorteras mot olika positioner (lastpallar) efter förpackningsstationen, beroende på transportföretagets tjänst. När alla artiklar från lasten har packats upp och sorterats efter adress, flyttas lastpallarna till vikdörren.

### <a name="create-sales-orders-and-picking-work"></a>Skapa försäljningsorder och plockningsarbete

#### <a name="create-sales-order-1"></a>Skapa försäljningsorder 1

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-005*
    - **Lagerställe:** *62*

1. Välj **OK** för att stänga dialogrutan.

    Den nya försäljningsordern öppnas.

1. Växla till vyn **Rubrik**.
1. På snabbfliken **Leverans** i avsnittet **Transport** anger du följande värden:

    - **Transportföretag:** *Luftfrakt*
    - **Transportföretag:** *Flyg*

1. Växla till vyn **Rader**.
1. Om en ny rad inte läggs till automatiskt till rutnätet på snabbfliken **försäljningsorderrader** välj **lägg till rad** för att lägga till en.
1. Ställ in följande värden på den nya orderraden:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *2*

1. Medan den nya orderraden fortfarande är markerad på snabbfliken **försäljningsorderrader** väljer du menyn **lager** och **Reservation**.
1. På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern. Anteckna påfyllnadens ID och försändelsens ID-nummer.

#### <a name="sales-order-2"></a>Försäljningsorder 2

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-006*
    - **Lagerställe:** *62*

1. Välj **OK** för att stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**. Ställ in följande värden på denna orderrad:

    - **Artikel:** *A0001*
    - **Kvantitet:** *1*

1. På snabbfliken **Raddetaljer** på fliken **leverans**, ange fältet **Leveranssätt** till *Flowe-ST*.
1. På snabbfliken **Försäljningsorderrader** välj **Lägg till rad** och ange sedan följande värden på den andra raden:

    - **Artikel:** *A0002*
    - **Kvantitet:** *1*

1. På snabbfliken **Raddetaljer** på fliken **leverans**, ändra värdet för fältet **Leveranssätt** till *Air C-Air*.
1. På snabbfliken **Försäljningsorderrader** välj den första orderraden. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. På snabbfliken **Försäljningsorderrader** välj den andra orderraden. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. Du får ett informationsmeddelande som visar försändelsen och påfyllnad för ordern. Observera att två påfyllnads-ID-nummer och två leverans-ID-nummer har skapats, ett för varje leverans sätt för försäljningsorderraderna.

#### <a name="get-the-work-ids-from-the-work-details"></a>Hämta arbets-ID från arbetsinformationen

1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. På sidan visas de arbets-ID som har skapats från försäljningsorder. Använd påfyllnads-ID och leverans-ID från försäljningsorder som du har skapat för att hitta arbets-ID för varje påfyllnad och leverans. Anteckna dessa arbets-ID eftersom du kommer att behöva dem i nästa steg. Observera att två arbets-ID:n har skapats för den andra försäljningsordern. Om olika artiklar plockas från olika platser genereras separata ord-ID:n.

### <a name="pick-items-for-the-sales-orders"></a>Plocka artiklar för försäljningsorder

Slutför det skapade arbetet genom att flytta dem till paketstationen med hjälp av den mobila enheten.

1. Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **försäljningsplockning**.
1. I fältet **ID** anger du det arbets-ID som skapades för försäljningsorder 1.
1. Välj **OK**.
1. På sidan **försäljningsorder – plocka** anger du en mål LP som skapades för försäljningsorder 1. Observera att plockplatsen (*bulk-001*), artikel (*A0001*) och kvantitet (*2 stycken*) visas.
1. Välj **OK**.
1. Granska informationen på sidan **Inköpsorder – placera**. Fältet **Loc** ska visa att de plockade artiklarna kommer till platsen *Packa*.
1. Välj **OK**.

    På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete", vilket anger att arbets-ID från försäljningsorder 1 har slutförts.

    Du kommer nu att välja försäljningsorder 2.

1. I fältet **ID** anger du det arbets-ID som skapades för försäljningsorder 2 där rad 1 har artikel *A0001*.
1. Välj **OK**.
1. På sidan **Försäljningsorder – Placera** anger du mål-LP. Observera att plockplatsen (*bulk-001*), artikel (*A0001*) och kvantitet (*1 stycken*) visas.
1. Välj **OK**.
1. Granska informationen på sidan **Inköpsorder – placera**. Fältet **Loc** ska visa att de plockade artiklarna kommer till platsen *Packa*.
1. Välj **OK**.

    På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete". Det här meddelandet anger att arbets-ID från rad 1 för försäljningsorder 2 har slutförts.

1. I fältet **ID** anger du det arbets-ID som skapades för försäljningsorder 2 där rad 2 har artikel *A0002*.
1. Välj **OK**.
1. På sidan **Försäljningsorder – Placera** anger du mål-LP. Observera att plockplatsen (*bulk-002*), artikel (*A0001*) och kvantitet (*1 stycken*) visas.
1. Välj **OK**.
1. Granska informationen på sidan **Inköpsorder – placera**. Fältet **Loc** ska visa att de plockade artiklarna kommer till platsen *Packa*.
1. Välj **OK**.

    På sidan **Skanna ett arbets-ID/ID-nummer** visas meddelandet "färdigt arbete". Det här meddelandet anger att arbets-ID från rad 2 för försäljningsorder 2 har slutförts.

### <a name="pack-sales-orders-into-containers"></a>Packa försäljningsorder i behållare

#### <a name="pack-sales-order-1-into-containers"></a>Packa försäljningsorder 1 i behållare

1. Gå till **lagerstyrning \> packa och skapa behållare \> packa**.

    Dialogrutan **Välj packningsstation** visas. Som standard ska fältet **arbetare** vara inställt på namnet på den arbetare som du ställer in tidigare.

1. Ställ in följande värden för att visa och arbeta med försändelser och behållare som planeras på den specifika förpackningsplatsen:

    - **Plats:** *6*
    - **Lagerställe:** *62*
    - **Plats:** *Packa*
    - **Förpackningsprofil-ID:** *Sortera*

1. Välj **OK** för att stänga dialogrutan.
1. På sidan **Packa** i fältet **ID-nummer eller leverans** ange mål-LP för försäljningsorder 1. Markera sedan **tabb** eller **retur** på tangentbordet för att flytta från fältet.
1. Klicka på **Ny behållare** i åtgärdsfönstret.
1. Godkänn alla standardinställningar och välj **OK**. Gör en notering av behållar-ID.
1. Ange följande värden på snabbfliken **artikelpackning**:

    - **Kvantitet:** *1*
    - **Identifierare:** Artikel *A0001*

1. Klicka på **Stäng behållare** i åtgärdsfönstret.
1. I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.
1. Välj **OK**. Behållaren flyttas till platsen *SORTERA* och är klar för sortering.
1. Skapa en andra behållare för att lägga till den andra artikeln från LP för försäljningsorder 1 till en ny behållare.
1. Klicka på **Ny behållare** i åtgärdsfönstret.
1. Godkänn alla standardinställningar och välj **OK**. Gör en notering av behållar-ID.
1. Ange följande värden på snabbfliken **artikelpackning**:

    - **Kvantitet:** *1*
    - **Identifierare:** Artikel *A0001*

1. Klicka på **Stäng behållare** i åtgärdsfönstret.
1. I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.
1. Välj **OK**. Behållaren flyttas till platsen *SORTERA* och är klar för sortering.

#### <a name="pack-sales-order-2-into-containers"></a>Packa försäljningsorder 2 i behållare

1. På sidan **Packa** i fältet **ID-nummer eller leverans** ange mål-LP för rad 1 i försäljningsorder 2. Markera sedan **tabb** eller **retur** på tangentbordet för att flytta från fältet.
1. Klicka på **Ny behållare** i åtgärdsfönstret.
1. Godkänn alla standardinställningar och välj **OK**. Gör en notering av behållar-ID.
1. Ange följande värden på snabbfliken **artikelpackning**:

    - **Kvantitet:** *1*
    - **Identifierare:** Artikel *A0001*

1. Klicka på **Stäng behållare** i åtgärdsfönstret.
1. I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.
1. Välj **OK**. Behållaren flyttas till platsen *SORTERA* och är klar för sortering.
1. I fältet **ID-nummer eller leverans** ange mål-LP för rad 2 i försäljningsorder 2. Markera sedan **tabb** eller **retur** på tangentbordet för att flytta från fältet.
1. Klicka på **Ny behållare** i åtgärdsfönstret.
1. Godkänn alla standardinställningar och välj **OK**. Gör en notering av behållar-ID.
1. Ange följande värden på snabbfliken **artikelpackning**:

    - **Kvantitet:** *1*
    - **Identifierarfält:** artikel *A0002*

1. Klicka på **Stäng behållare** i åtgärdsfönstret.
1. I dialogrutan **Stäng behållare** välj **Hämta systemvikt** om du vill att systemet ska uppdatera fältet **bruttovikt**.
1. Välj **OK**. Behållaren flyttas till platsen *SORTERA* och är klar för sortering.

Om du vill visa behållardetaljer går du till **Hantering av distributionslager \> Förpackning och skapande av behållare \> behållare** och söker efter de behållar-ID:n som skapades under packningen.

### <a name="sort-the-containers"></a>Sortera behållarna

> [!IMPORTANT]
> När du öppnar menyalternativet **Lastpallsversion** på mobilappen för att utföra utgående sortering visas en knapp har etiketten **Full**. *Använd inte knappen **Full** för att sortera eller stänga positionen.*
>
> Knappen **Full** tillhandahålls som standard och kan inte inaktiveras eller tas bort från sidan. Den används inte för funktionen *Utgående data*.

#### <a name="sort-the-first-container"></a>Sortera den första behållaren

1. Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **Lastpallsversion**.
1. I fältet **LP/Con** ange det första behållar-ID som är associerat med försäljningsorder 1.
1. Välj **OK**.
1. Eftersom det inte finns några sorteringspositioner för närvarande måste du ange en. I fältet **Sorteringsposition-ID** ange *SP01*.
1. Eftersom ingen LP för närvarande är associerad med sorteringspositionen *SP01*, måste du ange ett. I fältet **LP** anger du *PLP01*.
1. Välj **OK**.
1. Eftersom valideringen av sorteringsposition är aktiverad måste du ange sorteringspositionens ID igen. I fältet **Sorteringsposition-ID** ange *SP01*.
1. Välj **OK**.

    Du får ett meddelande arbetet är slutfört.

> [!TIP]
> Om du vill visa sorteringspositionen och LP i den går du till **Lagerhantering \> Förpackning och skapande av behållare \> Positionstilldelningar för utgående sortering**.
>
> På sidan **Positionstilldelningar för utgående sortering** visas alla aktiva sorteringspositioner. Fältet **Sortera positionstransaktioner** visar det LP som är kopplat till varje sorteringsposition och de behållare som finns i sorteringspositionen. Lägg märke till att en sorteringsposition finns för närvarande och att snabbfliken **Sortera positionskriterier** visar ett villkor för **Leverans – Transportföretag - flyg**.

#### <a name="sort-the-remaining-containers"></a>Sortera de kvarvarande behållarna

1. Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **Lastpallsversion**.
1. I fältet **LP/Con** ange det andra behållar-ID som är associerat med försäljningsorder 1.
1. Välj **OK**. Eftersom sorteringsmallen är inställd på att sortera automatiskt och det redan finns en sorteringsposition som har matchande kriterier, dirigeras du automatiskt till rätt sorteringsposition.
1. Välj **OK**.
1. Bekräfta sorteringspositionens ID för att ange att lagret är på rätt plats. I fältet **Sorteringsposition-ID** ange *SP01*.
1. Välj **OK**.

    Arbetet har slutförts på den andra behållaren från försäljningsorder 1. Du kommer nu att sortera resten av behållarna från försäljningsorder 2.

1. I fältet **LP/Con** ange behållar-ID för behållaren från försäljningsorder 2 som innehåller artikel *A0001*. Eftersom transportföretaget skiljer sig åt, uppmanas du att ange en ny sorteringsposition och tilldela en LP till den positionen. Använd sorteringsposition *SP02* och LP *PLP02*.
1. Välj **OK**.
1. Bekräfta sorteringspositionen genom att ange *SP02* i fältet **sorteringspositions-ID**.
1. Välj **OK**.

    Arbetet har slutförts på behållaren.

1. I fältet **LP/Con** ange behållar-ID för behållaren från återstående försäljningsorder 2 som innehåller artikel *A0002*. Eftersom transportföretaget är samma som transportföretaget för försäljningsorder 1, visar systemet den befintliga sorteringsposition som har matchande kriterier.
1. Välj **OK**.
1. Bekräfta sorteringspositionen genom att ange *SP01* i fältet **sorteringspositions-ID**.
1. Välj **OK**.

    Arbetet har slutförts på behållaren.

### <a name="close-the-outbound-sorting-positions"></a>Stäng de utgående sorteringspositionerna

När alla lager har sorterats måste positionen stängas innan arbetet kan skapas. Sorterat lagerplockningsarbete kommer att skapas för att ta lagret till vikdörren.

#### <a name="close-a-position-from-the-mobile-device"></a>Avsluta en position från den mobila enheten

1. Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **Lastpallsversion**.
1. I fältet **LP/Con** anger du ett behållar-ID som har sorterats för att sortera positionen *SP01*.
1. Välj **OK**.
1. Följande meddelande visas: "behållaren har redan sorterats för att position SP01. Stäng den här positionen?" Välj **Nära**.

    Arbetet har slutförts.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Stäng en position från positionstilldelningar för utgående sortering

1. Gå till **Lagerhantering \> Förpackning och skapande av behållare \> Positionstilldelningar för utgående sortering**.
1. I den vänstra kolumnen, välj **SP02**. Den här utgående sorteringspositionsraden är den som du kommer att stänga.
1. Klicka på **Stäng position** i åtgärdsfönstret. Den sorteringspositionens post är stängd och visas inte längre.

    > [!TIP]
    > Om du vill visa alla poster med stängda positioner markerar du kryssrutan **Visa stängda**.

### <a name="sorted-inventory-picking"></a>Plockning i sorterat lager

Du måste slutföra det sorterade lagerplockningsarbetet. När den är avslutad plockas lagret till försäljningsordern. Vid den punkten gäller alla andra lagerprocesser.

1. Logga in på lager på mobilenheten *62* genom att använda det användar-ID som du skapade för det här scenariot (eller användar-ID för en befintlig demodatanvändare).
1. I huvudmenyn, välj **utgående**.
1. I menyn **Utgående** välj **Lasta från sortering**.
1. Ange mål-LP-ID från den första sorteringspositionen, *SP01*. Ange fältet **ID** till *PLP01*.
1. Välj **OK**.
1. På sidan **Sorterad lagerplockning: Plocka** visas det plockningsarbete som måste utföras. Plocka från platsen *SORTERA* och mål-LP *PLP01*, som har flera artiklar och kvantiteten *3*.
1. Välj **OK**.
1. På sidan **Sorterad lagerplockning: Placera** visas det placeringsarbete som måste utföras. Placera på platsen *Vikdörr* och mål-LP *PLP01*, som har flera artiklar och kvantiteten *3*.
1. Välj **OK**.

    Arbetet har slutförts.

1. Ange målnummer-ID från den andra sorteringspositionen *SP02*. Ange fältet **ID** till *PLP02*.
1. Välj **OK**.
1. På sidan **Sorterad lagerplockning: Plocka** visas det plockningsarbete som måste utföras. Plocka från platsen *SORTERA* och mål-LP *PLP02*, som har flera artiklar och kvantiteten *1*.
1. Välj **OK**.
1. På sidan **Sorterad lagerplockning: Placera** visas det placeringsarbete som måste utföras. Placera på platsen *Vikdörr* och mål-LP *PLP02*, som har flera artiklar och kvantiteten *1*.
1. Välj **OK**.

    Arbetet har slutförts.

Från och med denna punkt gäller alla andra lagerprocesser.
