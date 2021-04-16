---
title: Kluster för artikelinförsel
description: Kluster för artikelinförsel erbjuder ett sätt att välja flera ID-nummer samtidigt och sedan ta dem till artikelinförsel på olika platser. De kan vara mycket användbara för butiker, där ID-nummer vanligtvis inte är fullständiga lastpallar med lager.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: b3a7d1b7109b83b26c8187a7f0d271f1c82f6d63
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840375"
---
# <a name="putaway-clusters"></a>Kluster för artikelinförsel

[!include [banner](../includes/banner.md)]

Kluster för artikelinförsel erbjuder ett sätt att välja flera ID-nummer samtidigt och sedan ta dem till artikelinförsel på olika platser. Den här processen kalla ofta en *slinga*. Kluster för artikelinförsel kan vara mycket användbara för butiker, där ID-nummer vanligtvis inte är fullständiga lastpallar med lager. 

## <a name="turn-on-the-cluster-putaway-feature"></a>Aktivera funktionen för kluster för artikelinförsel

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Funktion för kluster för artikelinförsel*

## <a name="setup-for-the-example-scenario"></a>Ställ in exempelscenario

### <a name="cluster-profiles"></a>Klusterprofiler

Profilen kluster för artikelinförsel avgör var ett objekt ska placeras, baserat på platsen som objektet har tilldelats vid tiden för inleverans. Om det krävs olika kluster bör ett annat kluster för artikelinförsel skapas, en för varje menyalternativ för mobila enheter.

1. Gå till **lagerstyrning \> inställningar \> mobiltelefon \> klusterprofiler**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I vyn **Rubrik** anger du följande värden:

    - **Profil-ID för kluster för artikelinförsel:** *Kluster för artikelinförsel*
    - **Profil-ID-namn för kluster för artikelinförsel:** *Kluster för artikelinförsel*
    - **Klustertyp:** *artikelinförsel*
    - **Löpnummer:** Acceptera standardvärdet.

1. Välj **Spara** om du vill göra krävda fälten på fliken **Allmänt** tillgänglig.
1. Ange följande värden på snabbfliken **Allmänt**:

    - **Tidsgränsen för klustertilldelning:** *Vid inleverans*

        I det här fältet definieras om kluster för artikelinförsel ska tilldelas direkt när lagret tas emot, eller om det ska sorteras senare.

    - **Regel för klustertilldelning:** *manuell*

        Fältet definierar om klustertilldelningen ska bestämmas automatiskt av systemet eller manuellt av användaren.

    - **Direktivkod:** Lämna det här fältet tomt.
    - **Lokalisera kluster för artikelinförsel:** *Inleverans*

        Följande värden finns:

        - **Inleverans** – En plats hittades omedelbart under inleveransen.
        - **Klusterstängning** – En plats hittades när klustret är stängt.
        - **Användarriktad** – en plats hittas när ID-numret plockas från klustret för artikelinförsel. I det här fallet anges ingen plats när artikelinförselarbete skapas. Under själva artikelinförseln måste användaren söka igenom ID-numret eller arbets-ID för att initiera steget. Systemet söker sedan efter platsen igen och talar om för användaren var den plockade kvantiteten ska placeras.

    - **Kluster för artikelinförsel:** *Nej*

        I det här fältet anges om varje kluster måste vara unikt för varje användare när kluster tilldelas automatiskt. Den är bara tillgänglig när fältet **Klustertilldelningsregel** anges till *automatisk*.

    - **Enhetsbegränsning:** lämna det här fältet tomt.

        I det här fältet definieras den enhet som måste inlevereras för att profilen ska gälla. Om den lämnas tom är alla enheter giltiga.

    - **Arbetsenhetsavbrott:** *individuell*

        I det här fältet anges om alla lager ska konsolideras (med hjälp av kluster-ID och ID-nummer) till ett ID-nummer när ett kluster stängs och om det ska föras in som en enskild ID-nummer eller separat på ID-numren som togs emot. Det här fältet är inte tillgängligt om fältet **Lokalisera kluster för artikelinförsel** anges till *Inleverans*.

    - **Kluster finns kvar som överordnat ID-nummer:** *Nej*

        Om det här alternativet är inställt på *Ja*, när inlagringssteget är slutfört blir kluster-ID ett överordnat ID-nummer och alla artiklar på kluster-ID kommer att länkas till det överordnade ID-numret.

1. På snabbfliken **klustersortering** kan du definiera sorteringskriterier för artikelinförsel. Välj **Ny** på verktygsfältet för att lägga till en andra rad och ställa sedan in följande värden för den:

    - **Löpnummer:** Acceptera standardvärdet.
    - **Fältnamn:** *WMSLocationId*

        Det här fältet definierar det fält som den här raden ska använda som ett sorteringskriterium.

    - **Sortera:** *stigande*

        Det här fältet anger om sorteringen görs i stigande eller fallande ordning.

1. På snabbfliken **Arbetsmallar för kluster** välj **Ny** på verktygsfältet för att lägga till en rad och anger sedan följande värden:

    - **Arbetsordertyp:** *inköpsorder*
    - **Arbetsmallen:** *61 PO direkt*

1. I åtgärdsrutan väljer du **Spara** och välj sedan **Redigera fråga**.
1. I dialogrutan **kluster för artikelinförsel** på fliken **Intervall**, välj **Lägg till** om du vill lägga till en andra rad i frågan. Uppdatera sedan raderna som visas i följande tabell.

    | Register | Härlett register | Fält | Villkor |
    |---|---|---|---|
    | Arbete | Arbete | Lagerställe | *61* |
    | Arbete | Arbete | Arbets-ID | Lämna det här fältet tomt. |

1. Välj **OK** om du vill spara frågan och stänga dialogrutan.
1. Välj **Spara** i åtgärdsfönstret och stäng sidan.

> [!IMPORTANT]
> Fält i klusterprofilen som är nedtonade när **Genera kluster-ID** anges till *Ja* är inte tillgängligt och kommer inte att beaktas när den här funktionen används.

### <a name="mobile-device-menu-items"></a>Menyalternativ på mobil enhet

Det finns två nya menyartiklar för mobila enheter för den här funktionen. Menyalternativet **Inleverera och sortera kluster** används för att inleverera lager i ett kluster för artikelinförsel vid mottagning. Menyartikeln **kluster för artikelinförsel** används för att placera klustret efter att det har tilldelats.

#### <a name="receive-and-sort-cluster"></a>Ta emot och sortera kluster

Skapa ett nytt menyalternativ för mobil enhet för mottagning av lager och sortering i ett kluster. Det här menyalternativet skapar inkommande arbete efter att lagret mottagits, vilket anger att det mottagande menyobjektet ska användas för kluster för artikelinförsel.

> [!NOTE]
> Menyalternativet **ta emot och sortera kluster** kan användas med följande menyalternativ för mottagning:
>
> - Inleverans av inköpsorderrad
> - Inleverans av inköpsorderartikel
> - Mottagande av lastartikel

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I vyn **Rubrik** anger du följande värden:

    - **Menyalternativnamn:** *ta emot och sortera kluster*
    - **Titel:** *Ta emot och sortera kluster*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Nej*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Arbetsskapandeprocess:** *Inköpsorderpost har inlevererats*
    - **Generera ID-nummer:** *Ja*
    - **Tilldela kluster för artikelinförsel:** *Ja*

        > [!NOTE]
        > Alternativet **Tilldela kluster för artikelinförsel** är bara tillgängligt för aktiviteten skapa ett steg i *Arbetsskapandeprocess* för mottagning.

    Acceptera standardvärden för kvarvarande fält.

1. Klicka på **Spara** i åtgärdsfönstret.

#### <a name="cluster-putaway"></a>Klusterplats

Skapa ett nytt menyalternativ för mobila enheter för att sätta klustret i en annan plats efter att det har tilldelats.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I vyn **Rubrik** anger du följande värden:

    - **Menyalternativnamn:** *kluster för artikelinförsel*
    - **Titel:** *kluster för artikelinförsel*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*

1. På snabbfliken **Allmänt** ska fältet **Dirigerad av** bör ställas in på *kluster för artikelinförsel*. Acceptera standardvärden för kvarvarande fält.
1. På snabbfliken **Arbetsklasser** ställer du in den giltiga arbetsklassen för denna menyartikel för mobila enheter:

    - **Arbetsklass-ID:** *Inköp*
    - **Arbetsordertyp:** *inköpsorder*

1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="mobile-device-menu"></a>Meny på mobil enhet

Lägg till de menyalternativ som du just har skapat på inkommande menyn för mobilappen.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I menylistan, välj **Inkommande**.
1. I listan **Tillgängliga menyer och menyartiklar** hittar du och väljer menyalternativet **Ta emot och sortera kluster**.
1. Klicka på högerpilen för att flytta det valda menyalternativet till listan **Menystruktur**.
1. Använd uppilen eller nedpilen om du vill flytta menyalternativet till önskad plats på menyn.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Upprepa steg 4 till och med 7 om du vill lägga till resterande menyartiklar.

    - Tilldela kluster
    - Klusterplats

## <a name="example-scenario"></a>Exempelscenario

Det här scenariot simulerar bearbetning av kluster för artikelinförsel.

### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa inköpsorder** ställ in följande värden:

    - **Leverantörskonto:** *1001*
    - **Lagerställe:** *61*

1. Välj **OK**.

    Sidan **Alla försäljningsorder** visas.

1. På sidan **Alla inköpsorder** på snabbfliken **Inköpsorderrader** använder du knappen **Lägg till rad** för att lägga till följande rader:

    - Inköpsorderrad 1:

        - **Artikelnummer:** *A0001*
        - **Kvantitet:** *10*

    - Inköpsorderrad 2:

        - **Artikelnummer:** *A0002*
        - **Kvantitet:** *20*

    - Inköpsorderrad 3:

        - **Artikelnummer:** *M9215*
        - **Kvantitet:** *30*

1. Klicka på **Spara** i åtgärdsfönstret.
1. Anteckna inköpsordernumret.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Ta emot lager och placera det utanför den mobila enheten

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>Ta emot och sortera lagret i ett kluster

1. Logga in på mobilappen för distributionslagerhantering som en användare som är konfigurerad för lagerstället *61*.
1. I huvudmenyn, välj **ingående**.
1. I menyn **Ingående** välj **Ta emot och sortera kluster**.
1. I fältet **Ponum** anger du inköpsordernummer.
1. Välj **OK** (bockmarkeringsknappen).
1. Markera fältet **Artikel** ange artikelnummer *A0001* och välj sedan **OK**.
1. Markera fältet **Kvt** ange *10* med hjälp av det numeriska tangentbordet och sedan bockmarkeringsknappen.
1. På sidan **Kvt** välj **OK** (bockmarkeringsknappen) för att bekräfta kvantiteten som du har angett.
1. På sidan **artikel** välj **OK** för att bekräfta att artikeln *A0001* har registrerats.
1. Markera fältet **kluster-ID** och ange ett ID för klustret som du ska skapa.

    Det ID som du anger här kommer att användas när de två återstående artiklarna på inköpsordern inlevereras.

1. Välj **OK**.

    Uppgiftssidan **Ponum** visas och visar meddelandet "Arbetet slutfört".

    Artikeln *A0001* har nu tagits emot på platsen *RECV* och tilldelats det kluster-ID som du angav i steg 10.

1. Upprepa steg 4 till 11 om du vill ta emot de återstående två artiklarna från inköpsordern och tilldela dem till kluster-ID:

    - En kvantitet på *20* för artikel *A0002*
    - En kvantitet på *30* för artikel *M9215*

#### <a name="close-the-cluster"></a>Stäng klustret

Klustret måste vara stängt innan artiklarna i klustret kan föras in.

1. I Supply Chain Management, gå till **Lagerhantering \> Arbete \> Utgående \> Arbetskluster**.
1. På sidan **Arbetskluster** i avsnittet **Arbetskluster**, sök fältet **Kluster-ID** för det kluster-ID som du angav tidigare.
1. Om klustret inte visas kan det redan ha stängts. Om du vill ta reda på om klustret har stängts markerar du kryssrutan **Visa stängt arbete** och söker efter det kluster-ID som du angav tidigare. Gör sedan något av följande:

    - Om klustret har stängts hoppar du över de återstående stegen för den här proceduren och går vidare till nästa procedur, [placera klustret](#put-the-cluster-away).
    - Om klustret inte har stängts följer du de återstående stegen i den här proceduren för att stänga klustret manuellt. Gå sedan vidare till nästa procedur.

1. I avsnittet **Arbetskluster** väljer du det kluster-ID som du angav tidigare.
1. Klicka på **Stäng kluster** i åtgärdsfönstret.

    När klustret har stängts visas det inte längre i avsnittet **Arbetskluster** (om inte kryssrutan **Visa stängt arbete** är markerad).

#### <a name="put-the-cluster-away"></a>Placera klustret

1. Logga in på mobilappen för distributionslagerhantering som en användare som är konfigurerad för lagerstället *61*.
1. I huvudmenyn, välj **ingående**.
1. I menyn **ingående** välj **kluster för artikelinförsel**.
1. Välj **kluster-ID** och ange det kluster-ID som du angav tidigare för det stängda klustret.
1. Välj **OK**.

    Sidan **kluster för artikelinförsel: plocka** visas. Det visar kluster-ID, plockplatsen, artiklarna (värdet *Flera* visas) och den totala kvantiteten i klustret som måste plockas.

1. Välj **OK**.

    Sidan **kluster för artikelinförsel: placera** visas. Instruktionerna för **Placera** identifierar kluster-ID, plats, artiklar, total kvantitet och ID-nummer för de artiklar som har tagits emot i klustret.

    Du har standardalternativen för att åsidosätta eller godkänna det här steget.

    ![Kluster för artikelinförsel: sidan placera](media/Cluster_putaway-Put.png "Kluster för artikelinförsel: sidan placera")

1. Välj **OK** för att bekräfta placering av kluster.

    Du får ett meddelande att "klustret är slutfört".

## <a name="notes-and-tips"></a>Anteckningar och tips

För fall där kluster-ID blir det överordnade ID-numret för en kapslad lastpall, anges automatiskt placeringspositionen när kluster-ID skannas. Inget ytterligare ID-nummer måste skannas, även om ID-numren generation är inställd på manuell.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]