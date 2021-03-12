---
title: Systemdirigerad klusterplockning
description: Det här avsnittet innehåller en översikt över systemstyrd klusterplockning i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: fa737f61bfd5bd71ba6d76e75e57c8e2d682cda3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965687"
---
# <a name="system-directed-cluster-picking"></a>Systemdirigerad klusterplockning

[!include [banner](../includes/banner.md)]

Klusterplockning är en del plockningsprocess som låter dig plocka artiklar för flera order samtidigt genom att klustra dem i plockningskluster. Du måste sedan besöka plockplatsen bara en gång. Den här funktionen används vanligtvis med små orderplockning eller kvantiteter som är mindre än antalet fall.

När Systemstyrd klusterplockning har ställts in kan du klusterplocka arbetshuvuden baserat på ett systemgenererat kluster. Systemet klusterplockar order upp till antalet befattningar som anges i klusterprofilen. Därför kan du plocka flera order samtidigt utan att manuellt skapa ett kluster.

Systemstyrd klusterplockning erbjuder ett alternativ till manuell klusteruppbyggnad, där en klusterprofil används för att skapa ett kluster. Flera installationsrelaterade rader måste definieras i klusterprofilen innan de används:

- **Antal positioner** motsvarar antalet order som ska placeras i ett kluster. Därför motsvarar antalet last.
- **Bryt kluster** avgör när klustret ska brytas.
- **Generera kluster-ID** styr om kluster-ID kommer att genereras av systemet eller anges av användaren.
- **Sortera verifieringstyp** avgör om positionsverifiering krävs.

Ett nytt menyalternativ för mobila enheter används för systemstyrd klusterplockning. **Klusterprofil-ID** måste anges för alternativet **dirigerad av**. Dessutom kan den systeminriktade arbetsordningsfrågor kan gruppera order, baserat på företagsspecifika kriterier. Därför kan du ytterligare optimera tilldelningen av arbetsorder genom att ange anpassade sorteringskriterier med den systeminriktade arbetsordningsfrågorna.

När systemstyrd klusterplockning aktiveras, visas lagerarbetare med ett kluster där plockorder har förtilldelats till klusterbefattningar. Därför kan arbetstagarna börja plocka en artikel för flera arbetsorder genom att besöka plockplatsen bara en gång. Plockningsprocessen för systemstyrd klusterplockning är densamma som processen för användarstyrd klusterplockning.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>Aktivera funktionen för systemstyrd klusterplockning

Innan du kan använda den här funktionen måste du aktivera den i ditt system. Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Här visas funktionen i listan:

- **Modul** – Lagerstyrning
- **Funktionsnamn** – Systemstyrd klusterplockning

Den här funktionen kräver också att du aktiverar en beroende funktion. Den beroende funktionen är:

- **Modul** – Lagerstyrning
- **Funktionsnamn** – systemstyd arbetsordning på organisationsnivå

## <a name="set-up-system-directed-cluster-picking"></a>Ställ in systemdirigerad klusterplockning

### <a name="create-cluster-profiles"></a>Skapa klusterprofiler

Klusterprofiler styr hur systemet skapar varje kluster. Om det krävs olika kluster bör en annan klusterprofil skapas för varje menyalternativ för mobila enheter.

1. Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.
2. Välj **Ny**.
3. I fältet **Klusterprofil-ID** ange **2 position**.
4. Skriv **2 position** i fältet **Namn**.
5. På snabbfliken **Allmänt** anger du följande information:

    - **Generera kluster-ID** – Välj **Ja**. Det här alternativet avgör om kluster-ID skapas automatiskt av systemet eller om användaren ska skapa den i början av plockning. 
    - **Aktivera befattningar** – Välj **Ja**. Det här alternativet avgör om positionsnamnen genereras automatiskt baserat på inställningen av positionsnamn. Om den här alternativet är inställt på **Nej** används registreringsskylt-ID för positionen.
    - **Antal positioner:** – Välj **2**. Det här fältet bestämmer det maximala antalet positioner som klustret kan ha (det vill, det maximala antalet rutor, laster och så vidare).
    - **Positionsnamn:** – Välj **numeriskt**, så att befattningar namnges med hjälp av kontinuerliga tal. Om du väljer **alfabetiskt** namnges positionerna i alfabetisk ordning.
    - **Bryt kluster på:** – Välj **placera**. Det här fältet avgör när klustret bryts. 
    - **Sortera verifieringstyp:** – Välj **positionsskanning**. Det här fältet bestämmer om sätta i position-steget verifieras.
        
6. På snabbfliken **klustersortering** kan du definiera sorteringskriterier genom att skapa en ny rad och ange följande information:

    - **Serienummer** – Välj **1**. Det här fältet bestämmer den ordning som systemet sorterar efter. Ett värde anges automatiskt, men du kan ändra det som du behöver.
    - **Fältnamn:** – Ange **WMSLocationId**. Det här fältet bestämmer det fält som raden använder för sorteringskriterier.
    - **Sortering** – Välj **stigande**. Det här fältet anger om sorteringen görs i stigande eller fallande ordning.

### <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter

Gör så här om du vill skapa ett nytt menyalternativ för mobila enheter för systemstyrd klusterplockning och länka klusterprofil-ID till menyalternativet mobil enhet.

1. Gå till **Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet**.
1. Välj **Ny**.
1. I rubrikavsnittet anger du följande information:
    - **Menyalternativnamn** – SD-kluster
    - **Titel** – SD-kluster
    - **Läge** – Arbete
    - **Använd befintligt arbete** – Ja

1. På snabbfliken **Allmänt** anger du följande information:
    - **Dirigerad av** – Systemdirigerad klusterplockning
    - **Generera ID-nummer** – Ja
    - **Klusterprofil-ID** – 2 Position

1. På snabbfliken **arbetsklasser** ställer du in den giltiga arbetsklassen för den här mobila enhetens menyalternativ genom att ange följande fält:
    - **Arbetsklass-ID** – Försäljning
    - **Typ av arbetsorder** – försäljningsorder

1. I åtgärdsfönstret **Menyalternativ på mobil enhet** välj **Systeminriktade arbetsordningsfrågor** och följ dessa steg för att ange en ny systeminriktade arbetsordningsfråga:
    - Välj **Ny** i åtgärdsfönstret.
    - **Löpnummer** - 1
    - **Beskrivning** – arbetsprioritet – arbets-ID

1. I åtgärdsfönstret väljer du **Redigera fråga**
1. Välj fliken **Sortera**.
1. Välj **Lägg till** för att lägga till en ny rad och ange sedan följande:
    - **Register** – arbete
    - **Härlett register** – Arbete
    - **Fält** – arbetsprioritet
    - **Sökriktningarna** – Stigande
1. Välj **Lägg till** för att lägga till en andra rad och ange sedan följande:
    - **Register** – arbete
    - **Härlett register** – Arbete
    - **Fält** – Arbets-ID
    - **Sökriktningarna** – Stigande

1. Systemet sorterar nu arbets-ID:n i klustret, först efter arbetsprioritet och sedan efter arbets-ID.

### <a name="set-up-a-mobile-device-menu"></a>Ställ in mobil enhet för lagerställe

1. Gå till **Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet**.
1. Lägg till menyalternativet **SD-kluster** som du precis har skapat till en meny på mobil enhet.
1. Välj menyn **Utgående**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Bläddra tills du hittar **SD-kluster**.
1. Välj **SD-kluster** kommer den pil som pekar på listan **Menystruktur** kommer att aktiveras.
1. Välj **pilknappen** om du vill flytta menyalternativet **SD-kluster** till den **utgående** menystrukturen.
1. Välj **SD-kluster** från listan **Menystruktur** och välj sedan **UPP**- eller **NED**-pilarna för att flytta menyalternativet till önskad plats på menyn för den mobila enheten.

## <a name="scenario"></a>Scenario

### <a name="create-picking-work"></a>Skapa plockarbete

Innan du kan ställa in systemstyrd klusterplockning måste du skapa kvalificerade utgående arbete. Den klusterprofil som du skapade tidigare anger två klusterpositioner. Därför måste du skapa minst två arbets-ID. I det här scenariot ska du skapa två försäljningsorder, reservera lager, frisläppa försäljningsorder till lagerstället och sedan bearbeta vågen manuellt.

1. Gå till **Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
1. Välj **Ny** i åtgärdsfönstret för att skapa den första försäljningsordern.
    - Menyn **Skapa försäljningsorder** öppnas och ange följande information:
        - Gå till snabbfliken **Kund**, ange **Kundkonto** - **US-004**.
        - Gå till snabbfliken **Allmänt** och ange **Lagerställe** - **62**.
        - Välj **OK** för att stänga menyn och skapa försäljningsordern.
    - På snabbfliken **försäljningsorderrader**, välj **Lägg till rad** om en ny rad inte läggs till automatiskt och ange följande:
        - **Artikelnummer** - A0001
        - **Kvantitet** - 1
        - Välj **Lägg till rad** för att lägga till en andra rad.
        - **Artikelnummer** - A0002
        - **Kvantitet** - 3
    - Reservera lager för båda raderna som du just har skapat.
        - Markera **rad 1**.
        - I åtgärdsfönstret **Försäljningsorderrader**, välj **Lager** och sedan **Reservation** från listan.
        - I formuläret **Reservation**, välj **Reservera parti** för att reservera lager.
        - Stäng formuläret **Reservation** när reservationen är klar.
        - Upprepa dessa steg för att reservera lager för **rad 2**.
1. Välj **Ny** i åtgärdsfönstret för att skapa den andra försäljningsordern
    - Menyn **Skapa försäljningsorder** öppnas och ange följande information:
        - Gå till snabbfliken **Kund**, ange **Kundkonto** - **US-005**.
        - Gå till snabbfliken **Allmänt** och ange **Lagerställe** - **62**.
        - Välj **OK** för att stänga menyn och skapa försäljningsordern
    - På snabbfliken **försäljningsorderrader**, välj **Lägg till rad** om en ny rad inte läggs till automatiskt och ange följande information:
        - **Artikelnummer** - A0001
        - **Kvantitet** - 4
        - Välj **Lägg till rad** för att lägga till en andra rad.
        - **Artikelnummer** - A0002
        - **Kvantitet** - 2
    - Reservera lager för båda raderna som du just har skapat.
        - Markera **rad 1**.
        - I åtgärdsfönstret **Försäljningsorderrader**, välj **Lager** och sedan **Reservation** från listan.
        - I formuläret **Reservation**, välj **Reservera parti** för att reservera lager.
        - Stäng formuläret **Reservation** när reservationen är klar.
        - Upprepa dessa steg för att reservera lager för **rad 2**.
    - Stäng försäljningsordern och returnera till listsidan **Alla försäljningsorder**.
1. Hitta de två försäljningsorder som du just skapade (du kanske måste uppdatera sidan). I registret markerar du både försäljningsorder med hjälp av avsnittets kryssruta.
    - I åtgärdsfönstret **Alla försäljningsorder**, välj fliken **lagerställe**.
    - I gruppen **Åtgärder** väljer du **Frisläpp till lager** för att frisläppa både försäljningsorder till lagerstället.
1. När frisläppningen till lagerställeprocessen har slutförts visas ett informationsmeddelande.
    - Leveranser skapas för varje försäljningsorder.
    - En våg skapas och båda utleveranserna kommer att tilldelas vågen. Gör en notering av **Påfyllnads-ID**.
1. Gå till **lagerstyrning > utgående påfyllningar > leveranspåfyllningar > alla påfyllningar**.
    - I listan **Alla påfyllningar** hitta och välj det **Påfyllnings-ID** som du skapade i föregående steg.
    - I åtgärdsfönstret, klicka på fliken **Påfyllnad**,
    - I gruppen **Påfyllnad**, välj **Bearbeta** om du vill bearbeta påfyllnad och skapa **Arbete**.
    - Informationsmeddelanden genereras när bearbetningen har slutförts, vilket anger att arbetet har skapats och att påfyllnaden har bokförts.
1. **Valfritt**: Gå till **Lagerstyrning > Arbete > Arbetsuppgifter** för att visa det arbete som har skapats. Två olika arbets-ID skapas. Varje arbets-ID har två plockningsrader.

### <a name="run-the-mobile-device-flow"></a>Kör det mobila enhetsflödet

1. Logga in på den mobila enheten för en användare i lager ställe **62**.
1. I **huvudmenyn**, välj **utgående**.
1. I menyn **utgående** välj **SD-kluster** för att initiera plockningen.
    - Ett kluster skapas och de två arbets-ID:n som du skapade tidigare är kopplade. Om du har skapat fler än två arbets-ID:n läggs bara de första två till i klustret. Observera att arbets-ID:n läggs till i klustret i stigande ordning, som du angav i frågeinstallationen.

    > [!NOTE]
    > Det nya klustret skapas automatiskt endast om tillräckligt med ytterligare arbets-ID har skapats tidigare. I annat fall visas följande meddelande: "det går inte att hitta tillräckligt med arbete för klustret."

    - När du har valt menyn visas den första plockskärmen. Systemet sammanställer alla matchande plockningsrader från de två arbets-ID:n och dirigerar dig att besöka plockplatsen en gång, så att du kan tillfredsställa båda ordrarna genom att använda en plockning. Den här processen görs på samma sätt som process för användarstyrd klusterplockning.

1. Bekräfta den första plockplatsen och artikeln genom att välja **OK**.
    - Kvantiteten för plockningen är summan av den artikel som visas på försäljningsorder i klustret.
1. Ange positionsnamnet (numeriskt eller alfabetiskt) om du vill bekräfta att artikelkvantiteten som plockats för befattningen placerades i rätt position.
1. Upprepa den här processen tills alla artikelkvantiteter har plockats och satts till rätt position.
1. Det sista steget på den mobila enheten är att **placera** klustret till den sista platsen. Välj **OK**
    - När den här placeringsoperationen bekräftas stängs klustret och bryts, baserat på det värde som du anger för fältet **Bryt kluster vid** i klusterprofilen. Arbets-ID:n är också stängda.
1. Ett meddelande om att "klustret har slutförts" visas på den mobila enheten.
