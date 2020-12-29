---
title: Plockradsgruppering
description: Det här ämnet ger en översikt över plockradsgruppering.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438002"
---
# <a name="pick-line-grouping"></a>Plockradsgruppering

[!include [banner](../includes/banner.md)]

I plockradgruppering kan flera arbetsrader som har samma artikel och plats kombineras till en enda plockning som visas för användaren på en mobil enhet. Lagerarbetare kan därför få de mest effektiva instruktioner som är möjliga, men den nödvändiga uppdelningen av arbetsrader i systemet upprätthålls också (till exempel för olika behållare och order).

## <a name="set-up-pick-line-grouping"></a>Ställ in plockradsgruppering

### <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter

1. Gå till **Lagerstyrning \> Konfigurera \> Mobil enhet \> Menyalternativ på mobil enhet** och skapa ett nytt menyalternativ som heter **Plockning av försäljningsgrupprad - Användarriktad**.
2. Under **Menyalternativ på mobil enhet**, ange följande värden:

    - I fältet **Menyartikelnamn** ange **Försäljningsplockning - Grupprad**.
    - I fältet **Rubrik** ange **Försäljningsplockning - Grupprad**.
    - Välj **Arbete** i fältet **Läge**.
    - Ange alternativet **Använd befintligt arbete** till **Ja**.

3. Ange följande värden på snabbfliken **Allmänt**:

    - I fältet **Dirigerad av** välj **Användarstyrd**.
    - Ange det här alternativet **Generera registreringsskylt** till **Ja**.
    - Ge alternativet **Grupplockning** värdet **Ja**.

4. På snabbfliken **arbetsklasser** följer du dessa steg för att konfigurera de giltiga arbetsklasserna för mobila enhetens menyalternativ:

    1. Välj **Ny**.
    2. I fältet **Arbetsklass-ID** välj **Försäljning** eller **SO plocka**, beroende på vilket lagerställe du ska använda.
    3. Välj **Inköpsorder** i fältet **Försäljningsarbetsorder**.

### <a name="set-up-a-mobile-device-menu"></a>Ställ in mobil enhet för lagerställe

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**. 
1. Lägg till menyalternativet som du nyss skapade i önskad meny.

### <a name="set-up-a-work-template"></a>Ställ in en arbetsmall

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Leta reda på arbetsmallen som ska användas med den här funktionen. I det här exemplet väljer du standard **51 välj till fas** Contoso arbetsmallen.
1. Välj på menyn **redigera fråga**.
1. Välj **Sortering** välj **Lägg till** och ange sedan följande värden:

    - I fältet **Tabell** väljer du **Tillfälliga arbetsstransaktioner**.
    - I fältet **Härlett register** väljer du **Tillfälliga arbetsstransaktioner**.
    - I fältet **Fält**, välj **Artikelnummer**.
    - I fält **Sökriktning** välj **Stigande**.

> [!NOTE]
> För att funktionen plockradsgruppering ska fungera måste arbetsraderna sorteras efter artikel-ID. Om rader som har samma objekt inte sekvenseras en efter en grupperas de inte.

## <a name="example"></a>Exempel

### <a name="create-picking-work"></a>Skapa plockarbete

Innan du kan ställa in plockradsgruppering måste du skapa vissa kvalificerade utgående arbete.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
2. Skapa en försäljningsorder genom att välja **Ny**. 
3. Markera en kund i fältet **Kundkonto**. 
4. På snabbfliken **Allmänt** i fältet **Lagerställe**, välj **51**. Välj sedan **OK**.
5. Under **Försäljningsorderrader**, lägg till följande sex rader:

    - **Rad 1:** I fältet **Artikelnummer** välj **M9200**. I fältet **Kvantitet**, ange **3**.
    - **Rad 2:** I fältet **Artikelnummer** välj **M9201**. I fältet **Kvantitet**, ange **3**. 
    - **Rad 3:** I fältet **Artikelnummer** välj **M9202**. I fältet **Kvantitet**, ange **2**. 
    - **Rad 4:** I fältet **Artikelnummer** välj **M9200**. I fältet **Kvantitet**, ange **1**. 
    - **Rad 5:** I fältet **Artikelnummer** välj **M9200**. I fältet **Kvantitet**, ange **3**.
    - **Rad 6:** I fältet **Artikelnummer** välj **M9202**. I fältet **Kvantitet**, ange **7**. 

    Här är en sammanfattning av de totala kvantiteterna för varje artikel:

    - **Artikel M9200:** 7 var
    - **Artikel M9201:** 3 var
    - **Artikel M9202:** 9 var

6. Innan du släpper order till distributionslagret måste du se till att plockplatserna har tillräckligt med lager för alla artiklar på alla order. Granska inställningen **platsdirektiv** för att avgöra vilka plockplatser som används för plockning av försäljningsorder.
7. Reservera lagret och släpp det till lagerställe. Ett arbets-ID som har sex rader skapas. Raderna sorteras efter artikelnummer.

### <a name="run-the-mobile-device-flow"></a>Kör det mobila enhetsflödet

1. På den mobila enheten väljer du den meny som innehåller menyalternativet ny mobil enhet.
1. Välj menyalternativet **försäljningsplockning – grupprad** och initiera plockningen.

    När du har valt menyn och ange arbets-ID, visas plockningssteget där alla plockningsrader för artikel M9200 grupperas. Du får en instruktion att välja 7 var och en av artikel M9200.

1. Bekräfta plockningssteget. 
1. Gå till klientskärmen för det arbete som pågår och lägg märke till att alla tre plockningsrader för artikel M9200 stängdes samtidigt.

    Arbetsrad 4 presenteras.

1. Bekräfta plockningssteget.

    Det sista plockningssteget på den mobila enheten sammanställer de två sista plockningsraderna från arbetsordern.

1. Slutför plockningssteget för 9 var och en av artikel M9202.
1. Bekräfta inlagringssteget och eventuella ytterligare utskriftssteget efter inlagringssteget för att slutföra arbetet.

> [!NOTE]
> - Arbetsrader kan bara grupperas om de är i sekvens.
> - Följande funktioner stöds inte:
>
>    - Fångstviktartiklar. Om det finns några fångstviktartiklar i arbetet, visas ett felmeddelande innan du börjar plocka.
>    - Enhetsplockning.
>    - Arbetsrader som har oavslutade lagerpåfyllnadsarbete.
>    - Överplockning.
>    - Kort plockning med omallokering av artiklar
