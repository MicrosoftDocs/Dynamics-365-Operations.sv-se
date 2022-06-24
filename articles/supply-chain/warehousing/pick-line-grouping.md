---
title: Plockradsgruppering
description: Denna artikel ger en översikt över plockradsgruppering.
author: Mirzaab
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: f9e6cbf0f520f0f30c01cefba03689e9c119f2cb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890637"
---
# <a name="pick-line-grouping"></a>Plockradsgruppering

[!include [banner](../includes/banner.md)]

I plockradgruppering kan flera arbetsrader som har samma artikel och plats kombineras till en enda plockning som visas för användaren på en mobil enhet. Därför kan lagerarbetare få de mest effektiva instruktionerna, men nödvändig arbetsradeparation (för olika behållare, beställningar och så vidare) kan fortfarande bibehållas i systemet.

## <a name="turn-on-the-pick-line-grouping-feature"></a>Aktivera funktionen plockradsgruppering

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Plocka radgruppering*

## <a name="set-up-pick-line-grouping"></a>Ställ in plockradsgruppering

### <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Menyartikelnamn** ange *Plockning av försäljningsgrupprad*.
1. I fältet **Rubrik** ange *Plockning av försäljningsgrupprad*. Den här rubriken visas på menyn för den mobila enheten.
1. Välj **Arbete** i fältet *Läge*.
1. Ange alternativet **Använd befintligt arbete** till *Ja*.
1. Ange följande värden på snabbfliken **Allmänt**:

    - I fältet **Dirigerad av** välj *Användarstyrd*.
    - Ange det här alternativet **Generera registreringsskylt** till *Ja*.
    - Ge alternativet **Grupplockning** värdet *Ja*.
    - Acceptera standardvärden för kvarvarande alternativ.

1. Följ dessa steg för att konfigurera de giltiga arbetsklasserna för mobila enhetens menyalternativ:

    1. På snabbflikarna **Arbetsklasser** väljer du **Ny**.
    2. I fältet **Arbetsklass-ID** välj *Försäljning* eller *SO plocka*, beroende på vilket lagerställe du ska använda. För det här scenariot väljer du *SO plocka*.

        Fältet **Arbetsordertyp** anges automatiskt till *Försäljningsorder*.

### <a name="set-up-a-mobile-device-menu"></a>Ställ in mobil enhet för lagerställe

Följ dessa steg om du vill lägga till menyalternativet som du just skapade på **utgående** meny.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I listfönstret visas alla befintliga menyer för mobila enheter. Välj *utgående* i listan.
1. I rutnätet **Tillgängliga menyer och artiklar** hitta och välj menyalternativet *Plockning av försäljningsgrupprad* som du just skapat.
1. Klicka på högerpilen för att flytta menyalternativet *Plockning av försäljningsgrupprad* till listan **Menystruktur**.
1. Använd uppilen eller nedpilen om du vill flytta menyalternativet till önskad plats på menystrukturen.
1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-a-work-template"></a>Ställ in en arbetsmall

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.
1. I rutnätet **Översikt** välj arbetsmallen som ska användas med den här funktionen. För detta scenario, välj mallen *51 välj till fas*.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I frågerutan på fliken **Sortering** välj **Lägg till** för att lägga till en rad och ange sedan följande värden för den nya raden:

    - I kolumnen **Tabell** väljer du *Tillfälliga arbetstransaktioner*.
    - I kolumnen **Härlett register** väljer du *Tillfälliga arbetsstransaktioner*.
    - I kolumnen **Fält**, välj *Artikelnummer*.
    - I kolumnen **Sökriktning** välj *Stigande*.

1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.
1. Följande meddelande kan visas: "gruppering återställs, fortsätt?" Klicka på **Ja** när du vill fortsätta.

> [!IMPORTANT]
> För att funktionen plockradsgruppering ska fungera måste arbetsraderna sorteras efter artikel-ID. Om rader som har samma objekt inte sekvenseras en efter en grupperas de inte.

## <a name="example"></a>Exempel

### <a name="create-picking-work"></a>Skapa plockarbete

Innan du kan konfigurera plockradsgruppering måste du skapa vissa kvalificerade utgående arbete.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I fältet **kundkonto** välj *US-004*.
1. På snabbfliken **Allmänt** i fältet **Lagerställe**, välj *51*.
1. Välj **OK**.
1. På snabbfliken **Försäljningsorderrader**, lägg till följande sex rader:

    - **Rad 1:** I fältet **Artikelnummer** välj *M9200*. I fältet **Kvantitet**, ange *3*.
    - **Rad 2:** I fältet **Artikelnummer** välj *M9201*. I fältet **Kvantitet**, ange *3*.
    - **Rad 3:** I fältet **Artikelnummer** välj *M9202*. I fältet **Kvantitet**, ange *2*.
    - **Rad 4:** I fältet **Artikelnummer** välj *M9200*. I fältet **Kvantitet**, ange *1*.
    - **Rad 5:** I fältet **Artikelnummer** välj *M9200*. I fältet **Kvantitet**, ange *3*.
    - **Rad 6:** I fältet **Artikelnummer** välj *M9202*. I fältet **Kvantitet**, ange *7*.

    Här är en sammanfattning av de totala kvantiteterna för varje artikel:

    - **Artikel M9200:** *7* var
    - **Artikel M9201:** *3* var
    - **Artikel M9202:** *9* var

1. Innan du släpper order till distributionslagret måste du se till att plockplatserna har tillräckligt med lager för alla artiklar på alla order. Granska inställningen **platsdirektiv** för att avgöra vilka plockplatser som används för plockning av försäljningsorder. Om du använder Contoso-demodatamiljön för lagerställe *51* ska du bekräfta att det finns tillgängligt lager.

    Du måste nu reservera lagret för varje rad.

1. På snabbfliken **Försäljningsorderrader** välj en av raderna som måste reserveras.
1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att tillämpa reservationen. Stäng sidan.
1. Upprepa steg 8 till 10 för de rader som återstår att reservera.

    Du måste nu släppa försäljningsordern till lagret.

1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Du får ett meddelande om att en försändelse och en påfyllnad har skapats och att påfyllnad har skickats för körning i en batch.

    När påfyllnad och alla jobb som är lediga skapas ett arbets-ID för arbete som har sex rader. Raderna sorteras efter artikelnummer.

1. Gå till **Lagerstyrning \> Arbete \> Allt arbete** för att visa det arbete som har skapats. Anteckna värdet för **Arbets-ID** eftersom du behöver det i nästa procedur.

### <a name="initiate-picking-from-the-mobile-device"></a>Initiera plockning från den mobila enheten

1. Logga in på mobila enheten som en användare som är inställd på lagerstället *51*.
1. På den mobila enheten väljer du den meny som innehåller menyalternativet ny mobil enhet. För det här scenariot väljer du **Utgående**.
1. Välj menyalternativet **Plockning av försäljningsgrupprad** och initiera plockningen.
1. Ange värdet **arbets-ID** som du gjorde en notering i föregående procedur.

    Du bör se ett plockningssteg där alla plockrader för artikel *M9200* grupperas och du bör få en instruktion för att plocka *7* varje artikel *M9200*.

    > [!IMPORTANT]
    > På den mobila enheten har plockarbetet för de tre plockarbeteraderna aggregerats till ett plockningssteg för användaren.

1. Bekräfta plockningssteget.
1. Gå till arbetssidan för det arbets-ID som pågår och lägg märke till att alla tre plockningsrader för artikel *M9200* stängdes samtidigt.
1. Gå tillbaka till den mobila enheten och fortsätt att plocka. Arbetsrad 4 för artikel *M9201* ska presenteras. Eftersom det bara fanns en arbetsrad på ordern finns det inget att slå ihop.
1. Bekräfta plockningssteget.
1. Det sista plockningssteget på den mobila enheten sammanställer de två sista plockningsraderna från arbetsordern.
1. Slutför plockningssteget för *9* var och en av artikel *M9202*.
1. Bekräfta inlagringssteget och eventuella ytterligare utskriftssteget efter inlagringssteget för att slutföra arbetet.

> [!IMPORTANT]
>
> - Arbetsrader kan bara grupperas om de är i sekvens.
> - Följande funktioner stöds inte:
>
>   - Fångstviktartiklar
>
>    Om det finns några fångstviktartiklar i arbetet, visas ett felmeddelande innan du börjar plocka.
>
>   - Enhetsplockning
>   - Arbetsrader som har oavslutade lagerpåfyllnadsarbete
>   - Överplockning
>   - Kort plockning med omallokering av artiklar


[!INCLUDE[footer-include](../../includes/footer-banner.md)]