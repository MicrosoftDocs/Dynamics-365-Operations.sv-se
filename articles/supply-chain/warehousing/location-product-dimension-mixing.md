---
title: Blandning av produktstorlekar på plats
description: Det här avsnittet innehåller information om hur du hanterar blandning av produktdimension för plats. Den här platsprofilfunktionen hjälper till att förbättra platshanteringen när produktvarianter eller produkter som har dimensioner används, t.ex. inom modebranschen. Med den kan du bestämma om konfigurationer, färger, utföranden och storlekar kan blandas för en viss platsprofil, eller om bara en av dessa dimensioner eller en kombination av dem kan placeras på samma plats.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437991"
---
# <a name="location-product-dimension-mixing"></a>Blandning av produktstorlekar på plats

[!include [banner](../includes/banner.md)]

Blandning av produktdimension för plats är en platsprofilfunktion som hjälper till att förbättra platshanteringen när produktvarianter eller produkter som har dimensioner används, t.ex. inom modebranschen. Med den kan du bestämma om konfigurationer, färger, utföranden och storlekar kan blandas för en viss platsprofil, eller om bara en av dessa dimensioner eller en kombination av dem kan placeras på samma plats.

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a>Aktivera funktionen för blandning av produktdimension för plats

Innan du kan använda funktionen blandning av produktdimension för plats måste den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *blandning av produktdimension för plats*

## <a name="setup"></a>Konfigurera

Varje plats på lagerstället måste ha en platsprofil associerad som beskriver egenskaperna för platsen. Därför kan alla platser som använder samma platsprofil tillåta blandning av produktdimensioner när den har ställts in.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>Konfigurera platsprofiler för att tillåta blandning av produktdimensioner

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. I listan över platsprofiler, välj **BULK**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Allmänt** ange alternativet **Aktivera blandning av produktdimension för plats** till *Ja*.

    > [!NOTE]
    > Du kan ange det här alternativet till *Ja* endast om alternativet **Tillåt blandade artiklar** är inställt på *Nej*.

1. På snabbfliken **Tillåten blandning av produktdimensioner** ange alternativet **storlek** till *Ja*. I det scenario som beskrivs i det här avsnittet kan blandning endast göras för produkter som har olika dimensioner för **storlek**. Andra alternativ är också tillgängliga.
1. Välj **Spara**.

### <a name="create-a-new-product-master-and-product-variants"></a>Skapa en ny produktmallar och produktvarianter

1. Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en produktmall.
1. I dialogrutan **Ny produkt** anger du följande värden:

    - **Produkttyp:** *Artikel*
    - **Delprodukttyp:** *Produktmall*
    - **Produknummer:** *B0001*
    - **Produktnamn:** *B0001 storlek*
    - **Produktdimensionsgrupp:** *Storlek*
    - **Konfigurationsteknik:** *fördefinierade varianten*

1. Välj **OK**.
1. På sidan **Produktinformation** på snabbfliken **Allmänt** anger du följande värden:

    - **Generera varianter automatiskt:** *Ja*
    - **Storleksgrupp:** *CASUALDHIR*

1. Om du vill visa de fördefinierade varianterna väljer du **produktvarianter** i åtgärdsfönstret.

    Sidan **Produktvarianter** visas och visar en lista med varianter från konfiguration av storleksgruppen.

### <a name="release-products-to-the-usmf-company"></a>Frisläpp produkter till USMF-företag

1. Välj **Frisläpp produkter** i åtgärdsfönstret.
1. På sidan **Välj produkter att frisläppa** bekräftar du att produktnumret *B0001* finns i listan och väljer **Nästa**.
1. Välj **Nästa** för att bekräfta de produktvarianter som ska frisläppas.
1. På sidan **Välj företag att frisläppa till**, välj *USMF* och sedan **Nästa** för att bekräfta valet.
1. På sidan **Bekräfta val** väljer du **slutför** för att slutföra frisläppandet.

    Du får ett meddelande Operationen är klar.

### <a name="update-a-released-product-in-the-usmf-company"></a>Uppdatera en frisläppt produkt i USMF företaget

1. Kontrollera att du är inloggad på **USMF**-företaget.
1. Gå till **produktinformationshantering \> produkter \> frisläppta produkter** för att avsluta skapa den frisläppta produkten.
1. Sök och välj artikelnummer *B0001* om du vill öppna sidan **information om frisläppta produkter**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Allmänt** ser du till att fältet **artikelmodellgrupp** är inställt på *FIFO*.
1. I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Dimensionsgrupper**.
1. Ange följande värden.

    - **Lagringsdimensionsgrupp:** *Lager*
    - **Spårningsdimensionsgrupp:** *Ingen*

1. Välj **OK**.
1. I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Reservationshierarki**.
1. Ställ in fältet **Reservationshierarki** till *Standard* och välj sedan **OK**.
1. På snabbfliken **Allmänt** i avsnittet **Administration** ser du att dina val har uppdaterats.
1. På snabbfliken **Inköp** i fältet **Pris** ange *10*.
1. På fliken **hantera kostnader** i fältet **artikelgrupp** anger du *Ljud*.
1. På snabbfliken **Inköp** i fältet **Pris** ange *10*.
1. På snabbfliken **lagerställe** i fältet **enhetssekvensgrupp- ID** anger du *ea*.
1. Välj **Spara**.

### <a name="create-a-location-directive"></a>Skapa ett platsdirektiv

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I vänstra fönstret i fältet **Typ av arbetsorder** väljer du *Inköpsorder*.
1. I listan väljer du platsdirektivet med namnet *24 PO direkt*.
1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Löpnummer:** *1*

        Den nya raden ska ligga framför den befintliga raden. Om du vill göra ändringen använder du knapparna **Flytta upp** och **Flytta ned** i verktygsfältet eller ändrar värdet för **löpnummer** för den befintliga raden till *2*.

    - **Namn:** *Placera i BULK platsprofil*
    - **Användning av fast lagerplats:** *Fasta och ej fasta platser*
    - **Tillåt negativt lager:** *Avmarkera den här kryssrutan (=Nej)*
    - **Batchaktiverad:** *Avmarkera den här kryssrutan (=Nej)*
    - **Strategi:** *ingen*

1. Medan den nya raden fortfarande är markerad väljer du **redigeringsfråga** ovanför rutnätet.
1. I dialogrutan fråga på fliken **Intervall** välj **Lägg till** om du vill lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Register:** *platser*
    - **Härlett register:** *platser*
    - **Fält:** *platsprofil-ID*
    - **Kriterier:** *BULK*

1. Välj **OK**.
1. På sidan **platsdirektiv** i åtgärdsfönstret, välj **Spara**.

> [!NOTE]
> På snabbfliken **Platsdirektivåtgärder** i fältet **Strategi** om du använder *Konsolidera* platsstrategi, kommer inställningen av snabbfliken **Tillåten blandning av produktdimensioner** i **Platsprofiler** kommer att åsidosättas och objekt kommer att placeras på samma plats även om detta beteende inte tillåts av installationen.

### <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I åtgärdsfönstret, välj **Ny** för att skapa ett menyalternativ som ska användas för sortering.
1. I rubriken anger du följande värden:

    - **Menyalternativnamn:** *Inleverans av inköpsorderrad*
    - **Rubrik:** *Inleverans av inköpsorderrad*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Nej*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Arbetsskapandeprocess:** *Inköpsorderrad har inlevererats och inlagrats*
    - **Generera ID-nummer:** *Ja*

1. Välj **Spara**.

### <a name="configure-the-mobile-device-menu"></a>Konfigurera mobilenhetsmeny

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. I listan över menyer, välj **Inkommande**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I listan **Tillgängliga menyer och artiklar** hittar du och väljer menyalternativet **Inleverans av inköpsorderrad**.
1. Klicka på högerpilen för att flytta menyalternativet **Inleverans av inköpsorderrad** till listan **Menystruktur**. På det här sättet lägger du till det nya menyalternativet på den valda menyn.
1. Välj **Spara**.

## <a name="scenario"></a>Scenario

Det här demoscenariot visar hur två olika produktvarianter kan placeras på samma plats när lagerställeprofilen inte tillåter blandade artiklar, men funktionen *blandning av produktdimension för plats* är aktiverad. I det här fallet ska du använda varianten **storlek** som kriterium.

Innan du börjar ska du kontrollera att det finns tomma platser i lagerstället *24* som använder platsprofil *BULK*.

### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

Du skapar en inköpsorder med tre rader: två rader för samma produktnummer men olika varianter av **storlek** och en tredje rad för en annan produkt utan varianter.

1. Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa inköpsorder** ställ in följande värden:

    - **Leverantörskonto:** *1001*
    - **Lagerställe:** *24*

1. Välj **OK**.
1. Inköpsordern skapas och en ny rad läggs till på snabbfliken **inköpsorderrader**. Anteckna inköpsordernumret.
1. Ställ in följande värden på denna nya rad:

    - **Artikelnummer:** *B0001*
    - **Storlek** *L*
    - **Kvantitet:** *2*

1. Välj **Lägg till rad** ovanför rutnätet för att lägga till en andra inköpsorderrad och ställa in följande värden:

    - **Artikelnummer:** *B0001*
    - **Storlek** *XL*
    - **Kvantitet:** *2*

1. Välj **Lägg till rad** för att lägga till en tredje inköpsorderrad och ställa in följande värden:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *1*

1. Välj **Spara**.

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a>Ta emot inköpsorderrader i lagerställeappen

1. Logga in på lagerställeappen som en användare som är aktiverad för lagerstället *24*.
1. Välj menyn **Inkommande**.
1. Välj **Inleverans av inköpsorderrad**.
1. Markera fältet **PONUM**, ange inköpsordernummer och bekräfta.
1. Bekräfta registreringen genom att välja knappen bekräfta (✔) längst ned på sidan.
1. Ange radnumret från inköpsordern som ska inlevereras. Markera fältet **LINENUM** och använd sedan det numeriska tangentbordet för att ange *1*.
1. Bekräfta din inmatning.
1. Ange den kvantitet som ska ta emot. Markera knappen plustecken (**+**) två gånger för att öka värdet i fältet **Kvt** till *2*.
1. Registrera din registrering genom att välja knappen (✔) längst ned på sidan och bekräfta registreringen genom att välja knappen (✔) igen.
1. Visa informationen på sidan **Inköpsorder: placera**. På den här sidan visas det arbete som har skapats för artikelinförseln (arbete 1).

    Platsen där den mottagna artikeln ska föras in, ID-nummer, artikeln, storleken och kvantiteten för **Inleverans av inköpsorderrad** som du just har slutfört visas.

1. Bekräfta artikelinförselarbetet.
1. Upprepa steg 4 till 11 för inköpsorderraden 2. I steg 8 ska du emellertid ange en kvantitet på *1*.

    Nytt artikelinförselarbete (arbete 2) skapas för samma plats som arbete 1.

1. Upprepa steg 4 till 11 för inköpsorderraden 2. I steg 8 ska du ange kvarvarande kvantitet på *1*.

    Nytt artikelinförselarbete (arbete 3) skapas för samma plats som arbete 1 och arbete 2. Det här problemet beror på att den *konsoliderade* platsens direktivstrategi används och snabbfliken **Tillåten blandning av produktdimensioner** i inställningen *Bulk* **Platsprofiler** tillåter att varianten **Storlek** blandas på plats.

1. Upprepa steg 4 till 11 för inköpsorderraden 3. I steg 8, ange kvantiteten *1* för artikelnummer *A0001*.

    Nytt artikelinförselarbete (arbete 4) skapas för en annan plats än den plats som används för inköpsorderraderna 1 och 2. Det här problemet beror på att platsprofilen inte tillåter blandade produkter, men den tillåter blandade dimensioner av samma produktmall.

1. Välj Meny-knappen överst på sidan (kallas ibland hamburger eller knappen hamburger) och välj sedan **Avbryt** för att avsluta **Inleverans av inköpsorderrad**.

> [!TIP]
> Du kan upprepa scenariot, men den här gången ändra **Storlek** - *Nej* under snabbfliken **tillåta blandning av produktdimensioner** på *BULK* **platsprofiler**, så att ingen av produkt dimensionerna kan blandas. I det här fallet, när du tar emot inköpsordern, kommer varje produktvariant att placeras på en ny plats.