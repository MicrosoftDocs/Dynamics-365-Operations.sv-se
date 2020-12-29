---
title: Artikelkonsolidering – platsutnyttjande
description: I det här avsnittet finns information om funktioner som gör det enkelt för lagerchefer att visa och filtrera platsens användning över hela lagerstället. Chefer kan välja platser och skapa lagerförflyttningar direkt från sidan artikelkonsolidering för att konsolidera artiklar och därmed bättre utnyttja lagerställets utrymme.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437993"
---
# <a name="item-consolidation---location-utilization"></a>Artikelkonsolidering – platsutnyttjande

[!include [banner](../includes/banner.md)]

I det här avsnittet finns information om funktioner som gör det enkelt för lagerchefer att visa och filtrera platsens användning över hela lagerstället. Chefer kan välja platser och skapa lagerförflyttningar direkt från sidan **artikelkonsolidering** för att konsolidera artiklar och därmed bättre utnyttja lagerställets utrymme.

## <a name="turn-on-the-features"></a>Aktivera en funktioner

Innan du kan använda funktionerna som beskrivs i det här avsnittet måste du aktivera dem i systemet. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs. Aktivera båda följande funktioner i angiven ordning. (Båda funktionerna gäller för modulen **Lagerstyrning** .)

1. Distributionslagrets platsstatus
2. Utnyttjande av artikelns konsolideringsplats

## <a name="warehouse-location-status"></a>Distributionslagrets platsstatus

Funktionen *platsstatus för lagerställe* lägger till fyra nya fält på sidan **Platser** för att spåra ytterligare information om platsens aktuella status:

- **Artikelnummer** – Den artikel som för närvarande finns på platsen. Om lagerstället innehåller flera artiklar är det här fältet tomt.
- **Datum och tid för senaste aktivitet** – Tidsstämpeln för den senaste lagertransaktion som har utförts mot platsen.
- **Åldersdatum** – Det datum då lagret på platsen förts in i lagerstället. Det här datumet beräknas utifrån ID-numrets åldersdatum. Även om detta datum är korrekt för platser som är ID-nummerspårade, men är kanske inte korrekt för platser som inte är ID-nummerspårade.
- **Platsstatus** – platsens status. Fyra värden är tillgängliga:

    - **Obestämd** – Platsprofilen kan inte spåra status. Därför är aktuell status okänd.
    - **Tom** – Det finns för närvarande inga lager på platsen.
    - **Plockning** – Utgående transaktioner har utförts mot platsen efter den senast var tom.
    - **Lagring** – Endast ingående transaktioner har utförts sedan platsen senast var tom.

De här fälten gör det möjligt för lagerställechefer att få en bättre översikt över statusen för lagerstället. De möjliggör även mer avancerad rapportering och filtrering.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Ställ in artikelkonsolidering och platsutnyttjande

I det här avsnittet beskrivs hur du förbereder systemet för att använda artikelkonsolidering och platsanvändning. Procedurerna använder exempelvärden från standard demodata. Om du planerar att arbeta genom det exempelscenario som finns senare i det här avsnittet väljer du den **USMF** juridiska personen (som innehåller standard demodata) och skapar varje post som beskrivs i det här avsnittet. Om du inte planerar att arbeta genom exempelscenariot, kan de värden som anges här beaktas som exempel på de typer av inställningar som du måste slutföra för att kunna använda funktionerna.

### <a name="released-product"></a>Frisläppt produkt

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. I fältet **artikelnummer** välj *M9201* och öppna informationssidan.
1. I åtgärdsfönstret, på fliken **Hantera lager**, i gruppen **Lagerställe**, väljer du **Fysiska dimensioner**.
1. På sidan **fysiska dimensioner** i åtgärdsfönstret väljer du **Ny**.

    En ny rad läggs till i rutnätet. Fältet **artikelnummer** är förval.

1. Välj *ea* i fältet **Enhet**. De återstående fälten på raden ställs in automatiskt.
1. Markera **Spara** och stäng sedan sidan.

### <a name="location-profile"></a>Platsprofiler

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. I listan över platsprofiler, välj **FLOOR-05**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Allmänt** ser du till att båda följande alternativ är inställda på *Ja*:

    - Aktivera artikel på plats
    - Aktivera platsens status

1. Välj **Spara**.

    > [!IMPORTANT]
    > Om alternativen **Aktivera artikel på plats** och **Aktivera platsstatus** redan har ställts in på *Ja* går du vidare till anvisningarna för att ställa in snabbfliken **Dimensioner** i steg 10. Om alternativen inte redan har ställts in på *Ja* måste du köra en konsekvenskontroll för modulen **Lagerstyrning** när du har ställt in dem manuellt. Fortsätt i så fall till nästa steg.

1. Kör konsekvenskontrollen genom att gå till **Systemadministration \> periodiska uppgifter \> databas \> konsekvenskontroll**.
1. I dialogrutan **konsekvenskontroll** anger du följande värden:

    - **Modul:** *Lagerstyrning*
    - **Kontrollera/korrigera:** *Kontrollera*
    - **Från datum:** Lämna det här fältet tomt.
    - **Konsekvenskontroll för lagerplatsstatus:** Markera den här kryssrutan.

1. Välj **OK**.

    > [!TIP]
    > Ett meddelande visas när konsekvenskontrollen är slutförd. Öppna [Åtgärdscenter](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) för att visa meddelandet. Välj **Meddelandedetaljer** om du vill visa detaljerna.
    >
    > Om meddelandet om konsekvenskontroll anger "felaktig platsstatusinformation hittades för plats XXXX i lagerställe XX" måste du köra konsekvenskontrollen igen. Den här gången anger du fältet **Kontrollera/åtgärda** för att *åtgärda felet*. Visa meddelandena och se till att inga fel hittades.

1. Du måste nu slutföra konfigurationen av platsprofilen. Gå tillbaka till **lagerstyrning \> inställningar \> lager \> platsprofiler**, välj platsprofil **FLOOR-05** och välj sedan **Redigera** i åtgärdsfönstret.
1. Ange följande värden på snabbfliken **Dimensioner**:

    - **Volymutnyttjandeprocent:** *100*
    - **Volymmetod som används för lagerställe:** *Använd platsvolym*
    - **Faktisk platshöjd:** *10*
    - **Faktisk platsbredd:** *10*
    - **Faktiskt platsdjup:** *10*
    - **Högsta vikt:** *100*

1. Välj **Spara**.

### <a name="mobile-device-menu-items"></a>Menyalternativ på mobil enhet

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I åtgärdsfönstret, välj **Ny** för att skapa ett menyalternativ som ska användas för sortering.
1. I rubriken anger du följande värden:

    - **Menyalternativnamn:** *Justera i*
    - **Rubrik:** *Justera i*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Nej*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Arbetsskapandeprocess:** *justering i*
    - **Lagerjusteringstyper:** *Justera i*

1. Välj **Spara**.

### <a name="mobile-device-menu"></a>Meny på mobil enhet

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. I listan över menyer, välj **Lager**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I listan **Tillgängliga menyer och artiklar** hittar du och väljer menyalternativet **Justera i**.
1. Klicka på högerpilen om du vill flytta **Justera i** till listan **Menystruktur**. På det här sättet lägger du till det nya menyalternativet på den valda menyn.
1. Välj **Spara**.

### <a name="movement-types"></a>Rörelsetyper

1. Gå till **Lagerstyrning \> Inställningar \> Lager \> Rörelsetyper**.
1. I åtgärdsfönstret, välj **ny** och ange sedan följande värden:

    - **Rörelsetypkod:** *KONSOLIDERA*
    - **Beskrivning:** *konsolidera platser*
    - **Arbetsklass-ID:** *InvMov*

1. Välj **Spara**.

## <a name="example-scenario"></a>Exempelscenario

I följande scenario används lagerställeappen på en mobil enhet för att göra en lager *justering in* på två platser i lagerstället.

### <a name="add-inventory-to-locations"></a>Lägg till lager till platser

1. Logga in på mobila enheten som en användare som är inställd på lagerstället *51*.
1. Gå till **lager \> Justera i**.

    Nu ska du ange den första platsjusteringen.

1. I uppgiften **Justera i** välj den plats som lagerjusteringen ska göras för. I fältet **LOC** välj *LP-001*.
1. Bekräfta platsen.
1. Skapa ett ID-nummer för den artikel som ska läggas till på platsen. I fältet **LP** anger du *LP00101*.
1. Bekräfta ID-numret.
1. Ange den artikel som ska läggas till i ID-numret. I fältet **ITEM** anger du *M9201*.
1. Bekräfta artikeln.
1. Ange kvantiteten av den artikel som ska läggas till. I fältet **QTY** ange *10*.
1. Bekräfta kvantiteten.

    Du får ett meddelande arbetet är slutfört. Nu ska du ange den andra platsjusteringen.

1. I uppgiften **Justera i** välj den plats som lagerjusteringen ska göras för. I fältet **LOC** välj *LP-002*.
1. Bekräfta platsen.
1. Skapa ett ID-nummer för den artikel som ska läggas till på platsen. I fältet **LP** anger du *LP00201*.
1. Bekräfta ID-numret.
1. Ange den artikel som ska läggas till i ID-numret. I fältet **ITEM** anger du *M9201*.
1. Bekräfta artikeln.
1. Ange kvantiteten av den artikel som ska läggas till. I fältet **QTY** ange *15*.
1. Bekräfta kvantiteten.

    Du får ett meddelande arbetet är slutfört.

1. Välj Meny-knappen (kallas ibland hamburger eller knappen hamburger) och välj sedan **Avbryt** för att avsluta uppgiften **Justering**.

### <a name="consolidate-locations"></a>Konsolidera platser

1. Gå till **lagerstyrning \> periodiska uppgifter \> artikelkonsolidering**.
1. Välj ett lagerställe att konsolidera för i huvudet. I fältet **Lagerställe**, ange *51*.

    En post visas för varje plats där artikel *M9201* justeras. Kolumnen **användningsprocent** visar den tillåtna platsens volymetriska utnyttjande.

1. Om du vill konsolidera lager markerar du alla lagerställen som måste konsolideras och väljer **konsolidera lager** i åtgärdsfönstret.
1. I dialogrutan **konsolidera lager** anger du plats och rörelsetyp som ska användas för att skapa arbetet för lagerförflyttning. Ange följande värden.

    - **Plats:** *LP-001*
    - **Rörelsetypkod:** *KONSOLIDERA*

1. Välj **OK**.
1. Du får ett informationsmeddelande som visar rörelsearbete som skapades. Gör en notering av rörelsens arbets-ID.

### <a name="view-movement-work"></a>Visa rörelsens arbete

1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. Visa det arbete som har skapats. Använd arbets-ID för transport från lagerkonsolideringen om du vill filtrera eller söka i arbetsrutnätet.

    I det här scenariot användes en befintlig plats som hade lagret som lager konsolideringsplats. Därför har endast ett arbets-ID skapats.

    > [!NOTE]
   > Systemet skapar ett arbets-ID för varje förflyttning som måste slutföras. Om du anger en plats som redan innehåller lager, skapas bara ett arbets-ID. Om du anger en ny plats skapas två arbets-ID:n.
