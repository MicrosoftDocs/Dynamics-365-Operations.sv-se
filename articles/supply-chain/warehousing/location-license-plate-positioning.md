---
title: Placering för plats-ID-nummer
description: Med hjälp av placering av ID-nummer kan du se var ett ID-nummer finns på en plats för flera lastpallar, t.ex. en plats där dubbel djupgående lastpall används.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 4dc084e4ef568d97912bfa22657b616fd6e493e03ad95703db66584f03e5381e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739692"
---
# <a name="location-license-plate-positioning"></a>Placering för plats-ID-nummer

[!include [banner](../includes/banner.md)]

Med hjälp av placering av ID-nummer kan du se var ett ID-nummer finns på en plats för flera lastpallar, t.ex. en plats där dubbel djupgående lastpall används.

Funktionen lägger till ett löpnummer för varje ID-nummer som placeras på en lagringsplats. Detta sekvensnumme används för att beställa ID-nummer på lagringsplatsen. Det innebär att funktionen intelligent stöder scenarier där kunder använder ett gravitations hyllsystem och måste känna till vilka ID-nummer som finns på framsidan.

Det här ämnet innehåller en sammanfattning av hur du ställer in och använder funktionen.

## <a name="turn-on-the-location-license-plate-positioning-feature"></a>Aktivera funktionen för placering av ID-nummer

Innan du kan använda positionering av ID-nummer måste funktionen aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Plats för positionering av ID-nummer*

## <a name="example-scenario"></a>Exempelscenario

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

För att arbeta igenom scenariot genom att använda värdena som föreslås här måste du arbeta på ett system där exempeldata är installerat. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

### <a name="set-up-the-feature-for-this-scenario"></a>Ställ in funktionen för det här scenariot

Slutför följande procedurer för att ställa in funktionen *Plats för positionering av ID-nummer* för det scenario som visas i det här avsnittet.

#### <a name="location-profiles"></a>Platsprofiler

Funktionen måste vara aktiverad i platsprofilen för varje plats där den ska användas.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. I listan över platsprofiler i det vänstra fönstret väljer du **BULK-06**.
1. På snabbfliken **Allmänt** har två nya alternativ lagts till av funktionen. Ange följande värden.

    - **Aktivera placering av ID-nummer:** *Ja*

        När det här alternativet är inställt på *Ja* placeringen av ID-nummer att behållas för ID-nummer på platsen.

    - **Visa mobila enhetens LP-position:** *Ja*

        När det här alternativet är inställt på *Ja* visas ID-numrets position för användare av mobila enheter vid justering och inventering. Du kan bara ändra inställningen för det här alternativet om funktionen är aktiverad.

1. Välj **Spara**.

#### <a name="location-directives"></a>Platsdirektiv

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I det vänstra fönstret kontrollerar du att fältet **Arbetsordertyp** är inställt på *försäljningsorder*.
1. I listan över platsdirektiv väljer du **61 SO plockningsorder**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Rader** markerar du raden som har ett **Löpnummer** värde på *2*.
1. På snabbfliken **Platsdirektivåtgärder** markerar du raden som har värdet **Namn** för *Plocka för mindre än lastpall* (den ska vara en enda rad) och ändra värdet för **löpnumret** till *2*.
1. Välj **Ny** ovanför rutnätet för att lägga till en rad för en ny platsdirektivåtgärd.
1. Ställ in följande värden på denna nya rad:

    - **Löpnummer:** *1*
    - **Namn:** *Välj position 1*

1. Medan den nya raden fortfarande är markerad väljer du **redigeringsfråga** ovanför rutnätet.
1. I frågeredigeraren, välj fliken **kopplingar**.
1. Expandera registerkoppling **Platser** för att visa kopplingen till registret **Lagerdimensioner**.
1. Expandera registerkoppling **Lagerdimensioner** för att visa kopplingen till registret **Lagerbehållning**.
1. Välj **Lagerdimensioner** och välj sedan **Lägg till registerkoppling**.
1. I listan över register som visas i kolumnen **Relation** välj **ID-nummer (ID-nummer)**. Välj sedan **Välj** för att lägga till **ID-nummer** i registerkoppling **Lagerdimensioner**.
1. När **ID-nummer** fortfarande är markerad väljer du **Lägg till registerkoppling**.
1. I listan över register som visas i kolumnen **Relation** välj **Plats för positionering av ID-nummer (ID-nummer)**. Välj sedan **Välj** för att lägga till **Plats för positionering av ID-nummer** i registerkoppling **Lagerdimensioner**.

    ![Tabellkopplingar.](media/LpTableJoin.png "Registerkopplingar")

1. Välj **OK** om du vill bekräfta de uppdaterade kopplade register och stäng frågeredigeraren.
1. På snabbfliken **Platsdirektivåtgärd**, välj **Redigera fråga** igen för att öppna frågeredigeraren igen.
1. På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Register:** *Plats för positionering av ID-nummer*
    - **Härlett register:** *Plats för positionering av ID-nummer*
    - **Fält:** *LP-position*
    - **Kriterier:** *1*

    ![Nytt område.](media/LpPositionCriteria.png "Nytt intervall")

1. Välj **OK** om du vill bekräfta dina ändringar fråga och stänga frågeredigeraren.

### <a name="set-up-sample-data-for-this-scenario"></a>Ställ in exempeldata för det här scenariot

I det här scenariot måste användaren logga in på mobilappen för lagerstyrning genom att använda en arbetare som har ställts in för lagerställe *61* för att utföra arbete. Användaren måste också genomföra transaktioner.

Eftersom funktionen *Plats för positionering av ID-nummer* lägger till en ny identifierare för ID-nummer på en plats måste du först skapa vissa data för att stödja scenariot.

#### <a name="spot-count-the-first-location"></a>Punktinventering för den första platsen

1. Öppna lagermobilappen och logga in på lagerställe *61*.
1. Gå till **Lager \> Punktinventering**.
1. På sidan **Punktinventering** ange fältet **Plats** till *01A01R1S1B*.
1. Välj **OK**.

    På sidan visas den plats du har angett. Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"

1. Välj **uppdatera** om du vill lägga till ett antal på platsen.
1. På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **artikel** och ange sedan värdet *A0001*.
1. Välj **OK**.
1. På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **LP** och ange sedan värdet *LP1001* (eller något annat alternativ för ID-numret som du väljer).

    Sidan **Rullande inventering: Lägg till ny LP eller artikel** visar **Placering av ID-nummer 1**.

1. Välj **OK**.

    Du måste nu ange kvantiteten för den artikel som räknas på ID-numret.

1. Ange fältet **Kvt** till *10*.
1. Välj **OK**.

    På sidan visas den plats du har angett. Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"

1. Välj **uppdatera** om du vill lägga till ett annat antal på platsen.
1. På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **artikel** och ange sedan värdet *A0002*.
1. Välj **OK**.
1. På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **LP** och ange sedan det värde *LP1002* (eller något annat ID-nummer som du har valt, förutsatt att det skiljer sig från det ID-nummer som du angav tidigare).
1. Ändra placeringen av ID-nummer genom att ställa in fältet **LP-position** på *2*.
1. Välj **OK**.
1. Ange kvantiteten för artikeln som inventeras på ID-numret genom att ställa in fältet **Kvt** på *10*.
1. Välj **OK**.

    På sidan visas den plats du har angett. Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"

1. Välj **OK**.

Arbetet har nu slutförts.

#### <a name="spot-count-the-second-location"></a>Punktinventering för den andra platsen

1. På sidan **Punktinventering** ange fältet **Plats** till *01A01R1S2B*.
1. Välj **OK**.

    På sidan visas den plats du har angett. Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"

1. Välj **uppdatera** om du vill lägga till ett antal på platsen.
1. På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **artikel** och ange sedan värdet *A0002*.
1. Välj **OK**.
1. På sidan **Rullande inventering: Lägg till ny LP eller artikel** välj fältet **LP** och ange sedan det värde *LP1003* (eller något annat ID-nummer som du har valt, förutsatt att det skiljer sig från de båda ID-nummer som du angav i den föregående proceduren).

    Sidan **Rullande inventering: Lägg till ny LP eller artikel** visar **Placering av ID-nummer 1**.

1. Välj **OK**.
1. Ange kvantiteten för artikeln som inventeras på ID-numret genom att ställa in fältet **Kvt** på *10*.
1. Välj **OK**.

    På sidan visas den plats du har angett. Följande meddelande visas: "platsen är klar, lägg till ny LP eller artikel?"

1. Välj **OK**.

Arbetet har nu slutförts.

#### <a name="work-details"></a>Information om arbete

> [!NOTE]
> Antalet inventeringar från mobilappen för att skapa rullande inventeringsarbete i Microsoft Dynamics 365. Arbetet kräver att antalet tas emot innan de bokförs i lagret.

1. Logga in på Dynamics 365 Supply Chain Management.
1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. På fliken **Översikt** tittar du på de rader som har följande värden:

    - **Arbetsordertyp:** *Rullande inventering*
    - **Lagerställe:** *61*
    - **Arbetsstatus:** *Väntar på granskning*

    Två arbets-ID ska ha skapats för dessa rader. Antalet för båda dessa arbets-ID måste accepteras.

1. I rutnätet väljer du det första arbets-ID:t för arbetsordertypen *Rullande inventering*.
1. I åtgärdsfönstret, på fliken **Arbete**, i gruppen **Arbete**, väljer du **Rullande inventering**.

    Två rader visas, en för varje artikel och ID-nummer. Värdena i fälten **Räknad kvantitet**, **Plats**, **ID-nummer** och **Artikel** bör matcha de inventeringsposter som du skapade på den mobila enheten. Om något av dessa fält inte visas väljer du **Visa dimensioner** i åtgärdsfönstret för att lägga till dem i rutnätet.

1. Markera båda raderna.
1. Välj **Godkänn inventering** i åtgärdsfönstret.
1. Meddelandet "bokföring – journal" visas. Välj **meddelandeinformation** om du vill visa det bokförda journalnumret.
1. Stäng meddelandeinformationen.
1. Uppdatera sidan **Arbete**.

    Det första arbets-ID:t har stängts och visas inte längre.

    > [!TIP]
    > Om du vill visa stängt arbete markerar du kryssrutan **Visa stängd** ovanför rutnätet.

    Du kommer nu att acceptera arbetet för ID-numret på plats *01A01R1S2B*.

1. På fliken **Översikt** väljer du det andra arbets-ID:t för arbetsordertypen *Rullande inventering*.
1. I åtgärdsfönstret, på fliken **Arbete**, i gruppen **Arbete**, väljer du **Rullande inventering**.

    En rad visas för artikeln och ID-numret. Värdena i fälten **Räknad kvantitet**, **Plats**, **ID-nummer** och **Artikel** bör matcha de inventeringsposter som du skapade på den mobila enheten.

1. Markera raden.
1. Välj **Godkänn inventering** i åtgärdsfönstret.
1. Meddelandet "bokföring – journal" visas. Välj **meddelandeinformation** om du vill visa det bokförda journalnumret.
1. Stäng meddelandeinformationen.
1. Uppdatera sidan **Arbete**.

    Det andra arbets-ID:t har stängts och visas inte längre.

    > [!TIP]
    > Om du vill visa stängt arbete markerar du kryssrutan **Visa stängd** ovanför rutnätet.

#### <a name="on-hand-by-location"></a>Behållning efter plats

1. Gå till **Lagerstyrning \> Förfrågningar och rapporter \> Behållning efter plats**.
1. Ange följande värden.

    - **Plats:** *6*
    - **Lagerställe:** *61*
    - **Uppdatera mellan platser:** *Ja*

1. Lägg märke till att platsen *01A01R1S1B* har två ID-nummer:

    - **A0001**, där fältet **LP-position** anges till *1*
    - **A0002**, där fältet **LP-position** anges till *2*

1. Lägg märke till att platsen *01A01R1S2B* har ett ID-nummer:

    - **A0002**, där fältet **LP-position** anges till *1*

### <a name="sales-order-scenario"></a>Scenario för försäljningsorder

Nu när funktionen *positionering av ID-nummer* har ställts in och lagret har mellanlagrats måste du skapa en försäljningsorder för att generera plockningsarbete som leder lagerarbetaren till att plocka artikeln *A0002* från lager platsen där lastpalls-ID finns i position *1*.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-004*
    - **Lagerställe:** *61*

1. Välj **OK**.
1. En ny rad läggs till i rutnätet på snabbfliken **försäljningsorderrader**. Ställ in följande värden på denna nya rad:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *1*

1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager för orderraden.
1. Stäng sidan **Reservation**.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.

    Du får ett informationsmeddelande som visar det påfyllnads-ID och leverans-ID som skapades för ordern.

1. På snabbfliken **Försäljningsorderrader** på menyn **Lagerställe** ovanför rutnätet, välj **Arbetsdetaljer**.
1. Sidan **arbete** visas och visar det arbete som har skapats för försäljningsraden. Anteckna de arbets-ID som har visats.

### <a name="sales-picking-scenario"></a>Scenario för försäljningsplockning

1. Öppna mobilappen och logga in på lagerställe *61*.
1. Gå till **Utgående \> Försäljningsplockning**.
1. På sidan **Skanna ett arbets-ID/ID-nummer** välj fältet **ID** och anger sedan arbets-ID:t från försäljningsraden.
1. Observera att plockningsarbetet styr att du kan välja artikel *A0002* från plats *01A01R1S2B*. Den här instruktionen visas eftersom objektet *A0002* finns på ett ID-nummer som finns på position *1* på den platsen.

    ![Plats för position 1.](media/LocationLicensePlatePositioning.png "Position 1 plats")

1. Ange det ID-nummer som du skapade för platsen och följ sedan instruktionerna för att plocka försäljningsordern.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]