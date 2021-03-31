---
title: Placera på vägg – placera i butik
description: Det här avsnittet innehåller information om funktionen Placera på vägg – placera i butik. Med den här funktionen kan du hantera situationer där du måste konsolidera en produkt till ett förpackat mellanlagringsområdet, baserat på konfigurerbara kriterier. Den hjälper till att minska plocktiden eftersom den möjliggör plockning på en målnummer-ID och kan använda fler befattningar än klusterplockning.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e2dcfa18af457ea21618704bafa2ed81c615d952
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228523"
---
# <a name="put-to-wall---put-to-store"></a>Placera på vägg – placera i butik

[!include [banner](../includes/banner.md)]

Med funktionen *Placera på vägg – placera i butik* kan du hantera situationer där du måste konsolidera en produkt till ett förpackat mellanlagringsområdet, baserat på konfigurerbara kriterier. Eftersom den här funktionen tillåter plockning på en enda målnummer-ID och kan använda fler positioner än för klusterplockning, kommer företag som levererar att lagra eller hantera små artiklar att dra nytta av minskad plockningstid.

Arbetsflödet för denna funktion riktar plockad produkt till en sorteringsplats för distribution i olika typer av behållare. Varje sorteringsplats innehåller i allmänhet flera sorteringspositioner. Varje sorteringsposition tilldelas enligt kriterierna som ställs in av affärsprocessen. Typiska kriterier är slutdestination, leverans eller last. När en produkt har inlevererats distribueras den till varje sorteringsposition, baserat på den kvantitet som är kopplad till ordern, destinationen, försändelsen eller lasten. När en behållare är full eller fullständig flyttas den till en mellanlagringsplats eller en leveransplats för ytterligare hantering, beroende på affärsprocessen.

Dessa lagerfunktioner kallas även andra namn, t.ex. placera i ljus och paus öppna.

## <a name="turn-on-the-outbound-sorting-feature"></a>Aktivera funktionen för utgående sortering

Innan du kan använda funktionen *Placera på vägg – placera i butik* måste funktionen *Utgående sortering* vara aktiverad i systemet. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *utgående sortering*

Funktionen *Utgående sortering* kan användas tillsammans med den funktionen *Påfyllnadsstegkod för hela organisationen* om den är aktiverad. Du måste också aktivera den här funktionen om du vill använda fördefinierade koder som har ställts in i koder för påfyllnadssteg. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Påfyllnadsstegkod för hela organisationen*

## <a name="setup"></a>Konfigurera

För denna demo används standard Contoso-data och lagerställe *62*. Vissa tillägg som anges senare används också.

### <a name="location-type"></a>Platstyp

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platstyper**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en platstyp som ska användas för sortering.
1. Ange följande värden.

    - **Platstyp:** *SORTERA*
    - **Beskrivning:** *Sortera*

1. Välj **Spara**.

### <a name="warehouse-management-parameters"></a>Parametrar för lagerstyrning

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **Allmänt** på snabbfliken **Platstyper** ange fältet **Sortera platstyp** till *SORT*.
1. Välj **Spara**.

### <a name="location-profile"></a>Platsprofiler

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en platsprofil som ska användas för sorteringsplats.
1. I rubriken anger du följande värden:

    - **Platsprofil-ID:** *Sortera*
    - **Namn:** *Sortera*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Platsformat:** *PACKET*
    - **Platstyp:** *SORTERA*
    - **Använd spårning av ID-nummer:** *Ja*
    - **Tillåt blandade artiklar:** *Ja*
    - **Tillåt blandade lagerstatusvärden:** *Ja*

1. Välj **Spara**.

### <a name="locations"></a>Platser

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.
1. Rensa kryssrutan **Generera kontrollsiffra för plats**.
1. I åtgärdsfönstret, välj **ny** och ange sedan följande värden:

    - **Lagerställe:** *62*
    - **Plats:** *Sortera*
    - **Platsprofil-ID:** *Sortera*

1. Välj **Spara**.

### <a name="packing-profiles"></a>Packprofiler

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Förpackningsprofiler**.
1. I åtgärdsfönstret, välj **ny** och ange sedan följande värden:

    - **Förpackningsprofil-ID:** *Sortera*
    - **Beskrivning:** *Sortera*
    - **Policyer för packning av behållare:** Lämna det här fältet tomt.
    - **Läge för behållar-ID:** *Auto*
    - **Behållartyp:** *LASTPALL 48X48*
    - **Skapa behållare automatiskt vid stängning av behållare:** Lämna det här fältet tomt.

1. Välj **Spara**.

### <a name="wave-step-codes"></a>Koder för påfyllnadssteg

Om du aktiverar funktioner *Påfyllnadsstegkod för hela organisationen* ange följande kod.

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Koder för påfyllnadssteg**.
1. I åtgärdsfönstret, välj **ny** och ange sedan följande värden:

    - **Kod för påfyllnadssteg:** *Sortera*
    - **Beskrivning för påfyllnadssteg:** *Sortera*
    - **Typ av påfyllnadssteg:** *Sortera mall*

1. Välj **Spara**.

### <a name="outbound-sorting-template"></a>Mall för utgående sortering

Sorterings mal len styr om sorteringsbefattningar skapas, vilka kriterier som används och andra attribut för sorteringsprocessen.

1. Gå till **Lagerstyrning \> Inställningar \> Förpackning \> Utgående sorteringsmallar**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en sorteringsmall.
1. Ange följande värden i nya mallens rubrik:

    - **Mall för utgående sorterings-ID:** *påfyllnadsortering*
    - **Beskrivning:** *påfyllnadsortering*
    - **Sortera malltyp:** *Lagerpåfyllnad*

        Det här fältet definierar den process som sorteringsmallen används för. Följande värden finns:

        - **Lagerpåfyllnad** – sorteringsmallen används för processen *Placera på vägg*. Denna malltyp används för att kringgå packstationen och bearbeta inventeringen direkt ur påfyllnad. Du kan bara använda den här typen om **sortering** påfyllnadsmetod ingår i påfyllnadsmallen.
        - **Behållare** – sorteringsmallen används för processen *lastpallbyggnad efter förpackning*. Malltyp används för bearbetning av behållare som stängs vid packningsstationen och behöver sorteras på lastpallar.

    - **Lagerställe:** *62*
    - **Plats:** *Sortera*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Sortera verifieringstyp:** *positionsskanning*

        Det här fältet definierar den verifiering som krävs vid sorteringen. Följande värden finns:

        - None
        - Skanna ett ID-nummer
        - Platsskanning

    - **Skapa arbete vi positionsstängning:** *Ja*

        Om detta alternativ är inställt på *Ja*, när positionen är stängd kommer arbetet att skapas för att flytta lager till den slutliga leveransplatsen. Om den är inställd på *Nej*, lager kommer omedelbart att väljas till beställningen när positionen är stängd.

    - **Befattningstilldelning:** *manuell*

        Det här fältet definierar typen av befattningstilldelning. Följande värden finns:

        - **Manuell** – användaren måste ange vilken plats som lagret sorteras till.
        - **Automatisk** – System kommer automatiskt att leda lagret till en plats som när det är möjligt baseras på sorteringsmallens uppdelningar.

    - **Tilldela sorteringsvillkor för position:** *Använd endast tom position*

        Detta fält kontrollerar om inventarier som redan finns på sorteringspositioner beaktas när en position tilldelas för efterfrågan. Följande värden finns:

        - **Använd endast tom befattning** – befattningar som redan har lagret kopplat till dem kommer att tas med i beräkningen
        - **Anta befattning tom** – alla lager som redan finns på befattningen ignoreras under tilldelningen. Alla tillgängliga befattningar kommer att användas.

    - **Kod för påfyllnadssteg:** *Sortera*

        Om funktionen *Påfyllnadsstegkod för hela organisationen* är aktiverad måste påfyllnadsstegkoden *Sortera* också aktiveras i påfyllnadsstegkoder.

    - **Automatiskt stängning av sorteringsordning:** *Ja*

        Om det här alternativet ställs in på *Ja* stängs sorteringspositionen automatiskt när allt arbete som kommer till positionen har slutförts.

    - **Antal nya sorteringspositioner:** *3*

        Det här fältet definierar det maximala antalet sorteringspositioner som systemet skapar.

    - **Prefix för sorteringsposition:** *SP-*

        Det här fältet definierar det prefix som systemet tilldelar före befattningsnumret.

    - **Automatiskt packning av sorteringsordning:** *Ja*

        Om det här alternativet ställs in på *Ja* kommer lagret på sorteringsposition att packas in i en behållare när positionen är stängd.

    - **Förpackningsprofil-ID:** *Sortera*

        Det här fältet definierar den packprofil som ska användas när sorteringspositionen packas i en behållare.

1. I åtgärdsfönstret, välj **Redigera fråga** för att ange de kriterier som används för den här sorteringsmallen.
1. I frågerutan på fliken **Sortering** välj **Ny** för att lägga till en rad och ange sedan följande värden:

    - **Register:** *Lastinformation*
    - **Härlett register:** *Lastinformation*
    - **Fält:** *leverans-ID*
    - **Sökriktning:** *Stigande*

1. Välj **OK**.
1. Följande meddelande kan visas: "gruppering återställs, fortsätt?" Välj **Ja**.

    Knappen **utgående sorterings sorteringsmallens uppdelningar** i åtgärdsfönstret blir tillgänglig.

1. I åtgärdsfönstret väljer du **utgående sorterings sorteringsmallens uppdelningar**.
1. Välj kryssrutan **Gruppera efter fält** till grupp genom leverans-ID.

    Med den här inställningen skapas en sorteringsposition per försändelse som är en behållare i påfyllnaden.

1. Välj **OK**.

### <a name="wave-process-methods"></a>Metoder för bearbetning av påfyllnad

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Metoder för påfyllnadsprocess**.
1. Klicka på **återskapa metoder** i åtgärdsfönstret.

    Metoden **Sortering** läggs till i listan över tillgängliga metoder och påfyllnadsmallstypen *leverans* har valts.

### <a name="wave-templates"></a>Påfyllnadsmallar

Redigera påfyllnadsmallen som används för att sortera om påfyllnadsbegäran.

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. Ställ in fältet **Malltyp för påfyllnad** som *Levereras*.
1. Välj den befintliga mallen **62 leveransstandard**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Ange följande ändringar på snabbfliken **Allmänt**:

    - Ange alternativet **Bearbeta påfyllnad vid släpp till lagerställe** som *Nej*.
    - Ange alternativet **Automatisera släpp av påfyllnad** till *Ja*.

1. På snabbfliken **metoder** ställer du in metoden **sortering**:

    1. I rutnätet **återstående metoder** välj **sortering**.
    2. Välj höger pil för att flytta **sortering** till rutnätet **Valda metoder**.
    3. I rutnätet **valda metoder** välj **sortering**.
    4. Ange fältet **Kod för påfyllnadssteg** till *Sortera*.

1. Välj **Spara**.

### <a name="mobile-device-menu-items"></a>Menyalternativ på mobil enhet

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Menyalternativnamn:** *Sortera*
    - **Rubrik:** *Sortera*
    - **Läge:** *Indirekt*
    - **Använd befintligt arbete:** *Nej*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Aktivitetskod:** *Utgående sortering*
    - **Använd processguide:** *Ja* (standardvärde)
    - **Mall för utgående sorterings-ID:** *påfyllnadsortering*

1. Välj **Spara**.

### <a name="mobile-device-menu"></a>Meny på mobil enhet

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. I listan över menyer, välj **Utgående**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I rutnätet **Tillgängliga menyer och artiklar** hitta och välj menyalternativet **Sortera** som du just skapat.
1. Klicka på högerpilen om du vill flytta **Sortera** till rutnätet **Menystruktur**. På det här sättet lägger du till det nya menyalternativet på menyn **Utgående**.
1. Välj **Spara**.

### <a name="location-directives"></a>Platsdirektiv

Du måste skapa platsdirektiv för att vägleda arbetet som skapas efter att sorteringen slutförts.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. Välj **Sorterad lagerplockning** i fältet *Typ av arbetsorder*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Sekvens:** *1*
    - **Namn:** *Placera på Baydoor*

1. Ange följande värden på snabbfliken **Platsdirektiv**:

    - **Arbetstyp:** *Placera*
    - **Plats:** *6*
    - **Lagerställe:** *62*
    - **Direktivkod:** Lämna det här fältet tomt.
    - **Flera SKU:** *Nr*

1. Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.
1. På snabbfliken **Rader** välj **Ny** och ange sedan följande värden. Acceptera standardvärden i alla andra fält.

    - **Löpnummer:** *1*
    - **Från kvantitet:** *0*
    - **Till kvantitet:** *1000000*

1. Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.
1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** och ange sedan följande värden. Acceptera standardvärden i alla andra fält.

    - **Löpnummer:** *1*
    - **Namn:** *Baydoor*

1. Välj **Spara** så att knappen **Redigera fråga** i snabbfliken **Platsdirektivåtgärder** är tillgänglig.
1. På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.
1. I dialogrutan för fråga på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Plats*. Ställ in fältet **villkor** för den här raden till *Baydoor*.
1. Bekräfta redigeringen genom att välja **OK**.

### <a name="work-classes"></a>Arbetsklasser

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsklasser**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken anger du följande värden:

    - **Arbetsklass-ID:** *Sortera*
    - **Beskrivning:** *Sortera*
    - **Arbetsordertyp:** *Sorterad lagerplockning*

1. Välj **Spara**.

### <a name="work-templates"></a>Arbetsmallar

1. Gå till **Lagerstyrning \> Arbete \> Arbetsmallar**.
1. Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.
1. I rutnätet väljer du arbetsmallen **62 välj för packa**.
1. Klicka på **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På raden där fältet **Fältnamn** anges till *Leverans-ID*, rensa kryssrutan **Gruppera efter detta fält**.
1. Välj **Spara** och stäng sedan dialogrutan **Arbetsuppgiftshuvudet delas**.
1. Välj **Sorterad lagerplockning** i fältet *Typ av arbetsorder*.
1. Skapa en ny arbetsmall genom att välja **Nytt**.
1. Ange följande värden i avsnittet **Översikt**. Acceptera standardvärden i alla andra fält.

    - **Arbetsmall:** *sorterad plockning*
    - **Arbetsmallbeskrivning:** *sorterad plockning*

1. Välj **Spara** om du vill göra avsnittet **Arbetsmallinformation** tillgänglig.
1. I avsnittet **Arbetsmallinformation** skapar du två rader. Välj **ny** och ange sedan följande värden för rad 1:

    - **Arbetstyp:** *plockning*
    - **Obligatorisk:** markerad (= *Ja*)
    - **Arbetsklass-ID:** *Sortera*

1. Välj **ny** igen och ange sedan följande värden för rad 2:

    - **Arbetstyp:** *Placera*
    - **Obligatorisk:** markerad (= *Ja*)
    - **Arbetsklass-ID:** *Sortera*

1. Välj **Spara**.

## <a name="example-scenario"></a>Exempelscenario

Det här scenariot simulerar en situation där lagerställen lagras i mindre artiklar och måste packas in i rutor innan de skickas, och där funktionerna för förpackningsstationen egentligen inte är lämpliga. Arbetare plockar order för flera kunder och olika adresser samtidigt för att öka plockningshastigheten. När plockningen har slutförts kommer arbetare till sorteringsplatsen där de plockade artiklarna kan sorteras i rätt ruta utifrån de kriterier som krävs. I det här exemplet används leverans-ID för att bestämma rätt låda, eftersom varje leverans har en annan adress. När alla artiklar från lasten har packats och sorterats efter leverans, flyttas lådorna till mellanlagringsområdet och slutligen till lastbil.

Innan du startar scenariot ska du se till att alla standardfunktioner för lagerställe är korrekt inställda för lagerstället. Standard Contoso-lagerstället *62* används för detta syfte. Standardkonfigurationer har inte ändrats, förutom vad som beskrivs i inställningarna.

### <a name="create-demand"></a>Skapa efterfrågan

Innan du kan visa funktionerna måste du skapa vissa behov. I det här scenariot skapar du tre försäljningsorder för tre olika kunder för att simulera olika leveransadresser. På det här sättet skapar du tre separata försändelser.

Innan du skapar försäljningsorder och leveranser måste du se till att plockplatserna har tillräckligt med lager för alla objekt på ordern. Granska inställningen platsdirektiv för att bekräfta vilka plockplatser som används för plockning av försäljningsorder. Om du måste justera inventeringen kan du skapa manuella rörelser, använda påfyllning eller använda något annat flöde. Reservera sedan lagerkvantiteter.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder för order 1 genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kund:** *US-001*
    - **Lagerställe:** *62*

1. Välj **OK**.
1. En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**. Ange följande värden.

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *5*

1. Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *10*

1. Upprepa följande steg för varje försäljningsrad på ordern för att reservera lager för den:

    1. På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.
    1. På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.
    1. Välj **Spara**.

1. Skapa en försäljningsorder för order 2 genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kund:** *US-004*
    - **Lagerställe:** *62*

1. Välj **OK**.
1. En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**. Ange följande värden.

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *7*

1. Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *3*

1. Upprepa följande steg för varje försäljningsrad på ordern för att reservera lager för den:

    1. På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.
    1. På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.
    1. Välj **Spara**.

1. Skapa en försäljningsorder för order 3 genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kund:** *US-007*
    - **Lagerställe:** *62*

1. Välj **OK**.
1. En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**. Ange följande värden.

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *8*

1. Följ dessa steg för att reservera lager för försäljningsraden:

    1. På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.
    1. På sidan **Reservation**, välj **Reservera parti** och stäng sedan sidan.
    1. Välj **Spara**.

Slutför följande procedur för att frisläppa varje försäljningsorder till lagerstället. Tre olika försändelser kommer att skapas. Du kommer sedan att lägga till alla tre försändelser till en ny påfyllnad.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. I rutnätet väljer du den första försäljningsorder som du skapade.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades.

1. Upprepa de föregående stegen för att frisläppa försäljningsorder 2 och 3 till lagerstället. Observera att det informationsmeddelande som visas anger att en leverans har lagts till i påfyllnaden som skapades när du släppte försäljningsorder 1.
1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj påfyllnads-ID som skapades från frisläppandet av försäljningsorder för att öppna sidan **påfyllnad**. På den här sidan visas påfyllnadsdetaljerna. Snabbfliken **påfyllnadsrader** visar de försändelser som har skapats.

    Du måste nu skapa arbete för att hämta artiklar från plockplatserna till sorteringsplatsen.

1. Välj **Process** i åtgärdsfönstret.

    Under påfyllnadsbearbetning använder sorteringsmetoden sorteringsmallen för att tilldela lagret att sortera positioner. När påfyllnadsbearbetning är klar får du ett informationsmeddelande som säger att påfyllnaden har publicerats och arbete har skapats.

1. I åtgärdsfönstret på fliken **Påfyllnad** i gruppen **Relaterad information** välj **Arbete** om du vill visa det arbete som har skapats. Gör en notering av arbets-ID.
1. Gå till **Lagerhantering \> Förpackning och skapande av behållare \> Positionstilldelningar för utgående sortering**.
1. I den vänstra kolumnen kan du visa den avgående sorteringsposition som har skapats för varje leverans.
1. På snabbfliken **Sorteringsvillkor för position** kan du visa leverans-ID för den positionen.

Ett arbets-ID har skapats för att hämta artiklar från plockplatserna till sorteringsplatsen. För att slutföra arbetet måste du ha det arbets-ID som skapades under påfyllnadsbearbetningen.

### <a name="sales-order-picking-to-the-sorting-location"></a>Försäljningsorder som plockas till sorteringsplatsen

1. Logga in på den mobila appen som en arbetare i lagerställe *62*.
1. I huvudmenyn, välj **utgående**.
1. I menyn **utgående** välj **försäljningsplockning**.
1. Markera fältet **ID** och ange sedan arbets-ID från påfyllnadsbearbetningen.
1. Bekräfta din inmatning.

    Sedan uppmanas du att ange ett målnummer-ID (LP). Observera att rad 1 från försäljningsorder 1 är vad som måste plockas och läggas till målnummer-ID. Artikelnummer, kvantitet, artikelbeskrivning och plockningsplats visas.

1. I fältet **Mål-LP** ange ID-nummer.

    Du ska välja alla rader som har skapats från den bearbetade påfyllnaden på samma målnummer-ID.

1. Bekräfta din inmatning.

    I mobilappen visas nu en serie sidor **Plocka** som pekar dig till plockningsplatsen och till objektet och mängden som måste väljas. När den plockade artikeln har lagts till i ID-nummer ska du bekräfta plockningsarbetet. Den sista sidan är arbetet där de plockade artiklarna placeras på sorteringsplatsen.

1. Bekräfta det första plockningsarbetet.
1. Nästa plockningsarbete visas. Bekräfta plockning.
1. Fortsätt att bekräfta resten av plockningsarbetet.
1. Det sista steget är att slutföra det införda arbetet. Bekräfta artikel införseln på sorteringsplatsen.

    Du får ett meddelande arbetet är slutfört.

1. Avsluta **försäljningsplockningen** i mobilappen.

### <a name="sortingput-to-wall"></a>Sortering/placera på vägg

Nu när hela lagret har placerats på sorteringsplatsen måste det vara sorterat på rätt sorteringsposition.

1. Logga in på mobilappen.
1. I huvudmenyn, välj **utgående**.
1. I menyn **Utgående** väljer du **Sortera** för att börja sortera objekten.
1. I fältet **LP/CON** anger du målregistreringsskylt för den plockade försäljningsordern.
1. Bekräfta din inmatning.
1. Ange det artikelnummer som ska sorteras först.
1. Systemet bestämmer den första sorteringsposition som ska visas. Bekräfta sorteringspositionen.
1. Du uppmanas att tilldela ett ID-nummer till sorteringsplatsen. Välj fältet **LP** ange ett ID-nummer och bekräfta din registrering.

    Eftersom sorteringsposition är relaterad till leverans-ID sorteras de plockade artiklarna i ett ID-nummer som är specifik för den utgående leveransen och försäljningsordern.

    På nästa sida visas artikel-ID, kvantitet, sorteringspositions-ID och "från" (plockning) och "till"-licensens ID-nummer (sortering). Informationen på den här sidan instruerar dig att sortera den angivna artikeln och kvantiteten från plockningens ID-nummer till sorteringens ID-nummer.

1. Bekräfta sorteringspositionen.
1. Sortera posterna på den första sorteringsplatsen. När du är klar dirigerar systemet dig till nästa sorteringsposition.
1. Upprepa den här processen för alla plockade rader på arbetsordern. Du bör även använda den här processen när det finns flera plockrader med samma artikelnummer.

    När du upprepar den här processen för alla artiklar utvärderas villkoren från nästa skannade artikel (arbetsraden) och avgör vilken sorteringsplats som den ska sättas på. Du dirigeras automatiskt om till rätt sorteringsposition. Beroende på bekräftelseinställningen måste du också bekräfta åtgärden genom att ange positionsnummer eller ID-nummer.

    > [!NOTE]
    > Om automatisk sortering har aktiverats är manuell åsidosättning inte tillgängligt.

1. När du är klar öppnas i Microsoft Dynamics 365 Supply Chain Management sidan **Positionstilldelningar för utgående sortering** för att granska status för positioner.

    - Om positionerna stängs automatiskt väljer du **Visa stängd** för att visa stängda positioner.
    - Observera att transaktioner för sorteringspositioner visas. Artikeln och kvantiteten som bearbetades genom positionen visas.

    När du ställer in mallen för utgående sortering ställer du in alternativet **Automatiskt stängning av sorteringsordning** till *Ja*. Därför stängs positionen automatiskt när den sista förväntade lagerstället har placerats där. Sorteringspositionerna har statusen **stängd** och arbetet har skapats för att flytta det sorterade lagret till platsen *Baydoor*.

1. Slutför det sorterade lagerplockningsarbetet för att flytta lagret till leveransplatsen. När lagret är klart kan du bekräfta det för leverans.

> [!NOTE]
> För att sorterat lagerplockningsarbete ska bearbetas korrekt, ska en menyartikel för mobila enheter med arbetsklasss-ID där fältet **arbetsordertyp** tälls in för *sorterad lagerplockning* användas för transport och lastningsprocess.

### <a name="manually-close-a-position-optional"></a>Avsluta en position manuellt (valfritt)

Om sorteringspositionerna ska stängas manuellt måste alternativet **Automatiskt stängning av sorteringsordning** för mallen för utgående sortering ställas in på *Nej* och stängning måste göras innan lagret kan flyttas till vikdörren. Positioner kan stängas på olika sätt:

- Via lagerställeappen:

    - Användaren kan skanna ett av artiklarna som redan finns på befattningen och sedan välja **Stäng** för att stänga position.
    - Om användaren skannar en behållare som redan har sorterats som behållare visas ett felmeddelande. Användaren kan dock fortfarande fortsätta att stänga positionen.

- Från sidan Microsoft Dynamics 365 Supply Chain Management sidan **Positionstilldelningar för utgående sortering**:

    - Användaren kan välja posten för den utgående sorteringspositionen och sedan välja **stängningsposition** i åtgärdsfönstret.

## <a name="tips"></a>Tips:

- Objekt kan inte flyttas mellan positioner när de har tilldelats en. Systemet utvärderar hur många av varje objekt som ska gå till en viss position.
- Sorteringsmallen kan konfigureras så att behållare skapas automatiskt när positioner stängs. Den här metoden skapar ett standardbehållar-ID som baseras på den angivna förpackningsprofilen.

> [!IMPORTANT]
> När du har skapat rörelsearbete från sorteringsplatsen, får du inte avbryta arbetet. I annat fall kommer positionen och behållarna i den att tas bort från systemet och inte användas för vidare behandling. Även lagret tas bort.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]