---
title: Systemstyrd arbetssekvensering
description: I det här avsnittet finns information om hur du dirigerar arbetssekvensering. Med den här funktionen kan du sortera och filtrera arbetsorder som systemet visar för användare för körning. Det är praktiskt i scenarier där det krävs fler kriterier för att köra plockningsprocessen för lager.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 2884c480d20090266f7cffb5e7d0aca58c1174f0
ms.sourcegitcommit: edb46dce498df42b09e8f5ad6de00f86c8022dfa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2020
ms.locfileid: "3534860"
---
# <a name="system-directed-work-sequencing"></a>Systemstyrd arbetssekvensering

[!include [banner](../includes/banner.md)]

Systemstyrd arbetssekvensering låter dig sortera och filtrera arbetsorder som systemet visar för användare för körning. Det är praktiskt i situationer där ytterligare kriterier (t.ex. leveranstid, plockningszon, platsprofil eller en kombination av olika kriterier) krävs för att köra lagerplockningsprocessen.

Den här funktionen utökar den aktuella systembaserade plockningsfunktionen genom att lägga till en systemriktad frågeorder där användarna kan ställa in en sekvens och en eller flera frågor som ska utvärdera alla arbetsorder som skapas. Endast arbetsorder som uppfyller de kriterier som anges i inställningarna för menyalternativet för mobil enhet hämtas och presenteras.

Denna funktion gör det enklare att optimera lagerplockningsprocesserna när de identifierar arbetsorder som matchar de angivna villkoren, tilldelar dem till rätt menyalternativ för mobila enheter och visar dem sedan till en arbetare, baserat på en viss färdighetsuppsättning, plockningsutrustning eller annat behov.

> [!NOTE]
> Om det behövs andra kriterier måste flera menyalternativ på mobil enhet användas.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Aktivera funktionen för systemstyrd arbetssekvensering på organisationsnivå

Innan du kan använda funktionen systemstyrd arbetssekvensering måste den aktiveras i ditt system. Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *systemstyrd arbetssekvensering på organisationsnivå*

## <a name="setup"></a>Konfigurera

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

För att arbeta igenom scenariot genom att använda värdena som presenteras i det här ämnet måste du arbeta på ett system där standarddemodata är installerat. Dessutom måste du välja den **USMF** juridiska personen. Scenariot använder lagerställe *51* från demodata.

> [!IMPORTANT]
> Innan du släpper order till distributionslagret måste du se till att plockplatserna har tillräckligt med lager för alla artiklar på order.
>
> Standard USMF-data bör stödja det här scenariot. Om du inte använder demodata, granska inställningen **platsdirektiv** för att lära dig vilka plockplatser som används för plockning av försäljningsorder. Om du måste justera inventeringen kan du skapa manuella rörelser, använda påfyllning eller använda något annat flöde.

### <a name="set-up-a-mobile-device-menu-item"></a>Ställ in menyalternativ för mobila enheter

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I listan menyalternativ för mobila enheter, välj **Försäljningsplockning – System**. Det menyalternativ som krävs ska redan finnas. 
1. Bekräfta följande inställning:

    - På snabbfliken **Allmänt** ska fältet **Dirigerad av** bör ställas in på *Systemdirigerat*.
    - Snabbfliken **arbetsgrupper** ska innehålla följande inställningar.

        | Arbetsklass-ID | Typ av arbetsorder |
        |---|---|
        | Försäljning | Försäljningsorder |
        | SÅ välj | Försäljningsorder |

1. I åtgärdsfönstret väljer du **Systeminriktade arbetsordningsfrågor**.
1. Välj **Redigera**.
1. Ta bort den befintliga raden och bekräfta sedan åtgärden genom att välja **Ja**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en rad.
1. Ställ in följande värden på denna nya rad:

    - **Löpnummer:** *1*
    - **Fältet Beskrivning:** *Arbetskvantitet mindre än 20 och fallande*

1. Välj **Spara**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. På fliken **Kopplingar** expanderar du kopplingshierarkin för att visa tabellen **Arbetsrader**.
1. Välj tabellen **Arbetsrader**.
1. Välj **Lägg till registerkoppling**.
1. Leta upp och markera den rad som har följande inställningar i listan som visas:

    - **Kopplingsläge:** *n:1*
    - **Relation:** *Platser (plats)*

1. Välj **Välj**.

    Platser läggs till i registerkoppling.

1. På fliken **Sortering**, välj **Lägg till** om du vill lägga till en rad.
1. Ställ in följande värden på denna nya rad:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *Arbetskvantitet* (i meddelanderutan som visas väljer du **Ja** om du vill lägga till sortering i det här fältet.)
    - **Sökriktning:** *Fallande*

1. Välj fliken **Intervall**.

    Om bara specifika arbetskriterier ska inkluderas i ordningsföljden kan du ange dem på fliken **Intervall**. I det här exemplet vill du bara inkludera arbete där kvantiteten är mindre än 20 ea (den lägsta måttenheten).

    Lägg märke till att vissa rader redan ingår. Dessa rader bör inte tas bort.

1. Välj **Lägg till** för att lägga till en rad.
1. Ställ in följande värden på denna nya rad:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *Inventarisk arbetskvantitet*
    - **Kriterier:** *\<20* (mindre än 20)

1. Välj **Lägg till** för att lägga till en annan rad.
1. Ställ in följande värden på denna nya rad:

    - **Tabell:** *Arbetsrader*
    - **Härlett register:** *Arbetsrader*
    - **Fält:** *arbetstyp*
    - **Kriterier:** *Plocka*

1. Välj **Lägg till** för att lägga till en annan rad.
1. Ställ in följande värden på denna nya rad:

    - **Register:** *platser*
    - **Härlett register:** *platser*
    - **Fält:** *platsprofil-ID*
    - **Villkor:** *!FAS*

        > [!IMPORTANT]
        > Se till att du tar med utropstecknet (*!*) framför *FAS*.

1. Välj **OK** om du vill spara och stänga frågan.
1. Välj **Spara**.
1. Stäng sidan och gå tillbaka till sidan **Menyalternativ på mobil enhet**.

> [!NOTE]
> Inställningen definierar de kriterier som används för att mata berättigat arbete till menyalternativet på mobila enheter. Om du lägger till fler villkorsrader i frågan använder systemet först den orderrad som har lägst serienummer. Med andra ord visas först alla stödberättigande arbeten för löpnummer 1 för användaren och sedan allt arbete för löpnummer 2. Om ett visst intervall och sortering måste användas tillsammans, ska detta därför anges i samma systemstyrda arbetssekvensfråga.
>
> Med den här inställningen sparas alla arbeten som har minst en rad där kvantiteten är mindre än 20 ea. Om arbetet har en rad där kvantiteten är exakt 20 ea eller mer än 20 ea, blir den därför giltig, förutsatt att den också har minst en rad där kvantiteten är mindre än 20 ea.

### <a name="location-directives"></a>Platsdirektiv

Om du använder Contoso-standarddata behöver frågan för åtgärdsrad för platsdirektiv inte ändras. Om du vill vara säker på att platsdirektiven kommer att fånga in artiklarna på försäljningsordern när du tillämpar funktionen i en icke-Contoso-miljö, ska du dock skapa ett nytt lokaliseringsdirektiv. Kontrollera inställningarna i demomiljön enligt följande instruktioner.

1. Gå till **Lagerstyrning** \> **Ställ in** \> **Platsdirektiv**.
1. Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.
1. Välj platsdirektivet med namnet *51 plockning*.
1. På snabbfliken **Platsdirektivåtgärd** välj raden för åtgärden **Plocka**.
1. Välj **redigeringsfråga** ovanför rutnätet.
1. Kontrollera frågan **Intervall**.

    1. Hitta raden där fältet **Fält** är inställt på *Plats*.
    2. Kontrollera att fältet **Kriterier** är tomt (dvs. det finns inga begränsningar).

## <a name="scenario"></a>Scenario

### <a name="create-sales-order-picking-work"></a>Skapa plockningsarbete för försäljningsorder

Innan systembaserade plockningen bör en del utgående arbete skapas. I det här scenariot skapar du fyra försäljningsorder som baseras på angivna systeminriktade arbetsordningsfrågor.

Du kommer att reservera lagerkvantiteter för varje försäljningsorder. Detta innebär att reserverade lager inte kan hämtas från lagerstället för andra order om inte lagerreservationen, eller delar av den, annulleras.

Därefter frigörs varje försäljningsorder till lagerstället så att det utgående arbetet skapas.

#### <a name="sales-order-1"></a>Försäljningsorder 1

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 1.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - I avsnittet **Kund** ställer du in fältet **Kundkonto** på *US-004*.
    - I avsnittet **Allmänt** anger du fältet **Lagerställe** till *51*.

1. Välj **OK** för att stänga dialogrutan. Anteckna försäljningsordernumret.
1. Lägg till en rad till den nya försäljningsorden och ange följande värden:

    - **Artikelnummer:** *M9200*
    - **Kvantitet:** *20*

1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation**, välj **Reservera parti** för att reservera lager.
1. Stäng sidan **Reservation**.
1. I åtgärdsfönstret på fliken **Lagerställe** väljer du **Släpp till lagerställe** för att skapa arbete för lagerstället.

    Du får informationsmeddelanden som visar det påfyllnads-ID och leverans-ID som skapades för försäljningsorder.

#### <a name="sales-order-2"></a>Försäljningsorder 2

1. I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 2.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-007*
    - **Lagerställe:** *51*

1. Välj **OK** för att stänga dialogrutan. Anteckna försäljningsordernumret.
1. Lägg till en rad till den nya försäljningsorden och ange följande värden:

    - **Artikelnummer:** *M9200*
    - **Kvantitet:** *5*

1. Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:

    - **Artikelnummer:** *M9201*
    - **Kvantitet:** *1*

1. Reservera lager för båda raderna.
1. Släpp order till lagerställe.

#### <a name="sales-order-3"></a>Försäljningsorder 3

1. I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 3.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-009*
    - **Lagerställe:** *51*

1. Välj **OK** för att stänga dialogrutan. Anteckna försäljningsordernumret.
1. Lägg till en rad till den nya försäljningsorden och ange följande värden:

    - **Artikelnummer:** *M9200*
    - **Kvantitet:** *7*

1. Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:

    - **Artikelnummer:** *M9202*
    - **Kvantitet:** *8*

1. Reservera lager för båda raderna.
1. Släpp order till lagerställe.

#### <a name="sales-order-4"></a>Försäljningsorder 4

1. I åtgärdsfönstret, välj **Ny** för att skapa försäljningsorder 4.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-010*
    - **Lagerställe:** *51*

1. Välj **OK** för att stänga dialogrutan. Anteckna försäljningsordernumret.
1. Lägg till en rad till den nya försäljningsorden och ange följande värden:

    - **Artikelnummer:** *M9200*
    - **Kvantitet:** *25*

1. Välj **Lägg till rad** för att lägga till en andra rad och ställa in följande värden:

    - **Artikelnummer:** *M9202*
    - **Kvantitet:** *10*

1. Reservera lager för båda raderna.
1. Släpp order till lagerställe.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Hämta arbets-ID för det arbete som har skapats

1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. Filtrera i fältet **lagerställe** så att endast arbete för lagerställe *51* visas.
1. Fyra arbets-ID bör ha skapats. Anteckna arbets-ID:t för varje försäljningsorder.

    | ID för försäljningsorder | Arbets-ID | Arbetskvantitet |
    |---|---|---|
    | Försäljningsorder 1 | Arbets-ID 1 | 20 ea |
    | Försäljningsorder 2 | Arbets-ID 2 | 6 ea (summan av båda raderna) |
    | Försäljningsorder 3 | Arbets-ID 3 | 15 ea (summan av båda raderna) |
    | Försäljningsorder 4 | Arbets-ID 4 | 35 ea (summan av båda raderna) |

Innan du kör flödet på den mobila enheten ska du kontrollera att endast det arbete som du just skapade är status *Öppna* för lagerställe *51* och arbetsordertyp *Försäljningsorder*. I annat fall kan testresultatet variera, eftersom systemdirekt plockning kommer att inkludera allt kvalificerat arbete.

1. Gå till **Lagerstyrning \> Arbeta \> Utgående \> Öppet försäljningsarbete**.
1. I rutnätet **Öppet försäljningsarbete** filtrera fältet **Lagerställe** så att endast arbete för lagerställe *51* visas.
1. Kontrollera att endast de fyra arbets-ID:n som du skapade tidigare visas.
1. Stäng sidan **Arbete**.

### <a name="mobile-device-flow-execution"></a>Flödeskörning för mobil enhet

Baserat på inställningarna kommer systemet att mata in det användararbete som är sorterat från den högsta kvantiteten för arbetsraden till den lägsta. Kvantiteten på varje rad är mindre än 20 ea.

Kom ihåg att den här inställningen sparas alla arbeten som har minst en rad där kvantiteten är mindre än 20 ea. Om arbetet har en annan rad där kvantiteten är exakt 20 ea eller mer än 20 ea kommer den också att vara giltig.

#### <a name="mobile-app"></a>Mobilapp

1. Logga in på lagerstyrningsappen en användare i lager ställe *51*.
1. Gå till **Utgående \> Försäljningsplockning - System**.

    Plockningssteget för arbets-ID *4* visas. Detta arbets-ID visas först på grund av inställningarna i systemriktad frågeordning, där du har angett att arbetet ska ordnas baserat på arbetsradens kvantitet i fallande ordning.

1. Slutför den begärda plockningen och sätt att stänga arbets-ID:t.

    Sedan visas arbets-ID *3*. En av dess arbetsrader ligger härnäst i sekvensen, baserad på arbetsradens kvantitet.

1. Slutför plockningen och sätt att stänga arbets-ID:t.

    Sedan visas arbets-ID *2*. Det här arbetets plockningsrad är härnäst i sekvensen.

1. Slutför plockningen och sätt att stänga arbets-ID:t.

    Inget ytterligare arbete kan presenteras för dig. Arbets-ID *1* är inte berättigat till menyalternativet för den mobila enheten eftersom frågan anger att arbetsrubrikerna endast ska beaktas om kvantiteten på arbetsraderna är mindre än 20 ea.

## <a name="tips"></a>Tips:

Systemstyrda frågor för arbetsserier *inkluderar*. Det är viktigt att du minns detta faktum för vissa inställningar. Du vill till exempel att en viss menyartikel endast ska behandla arbete där arbetsenheten är *ea* och du anger denna begränsning på fliken **intervall** i frågan. I det här fallet skickas alla arbeten där minst en arbetsrad har inställningen för arbetsenhet inställd på *ea* till arbetare. Därför kan det här arbetet även omfatta arbete där arbetsenheten har en annan arbetsenhet än *ea* (t.ex. *ruta* eller *lastpall*). Frågan utesluter endast arbete där arbetsenheten inte har satts till *ea*.

I exemplet från det här scenariot har arbets-ID *4* också fångats in av frågan. När den skapades lades två rader till: en för 25 ea och en annan för 10 ea. Arbetet uppvisades fortfarande för användaren, eftersom minst en arbetsrad har en kvantitet som är mindre än 20 ea.

Beroende på scenariot kan du förhindra detta genom att använda arbetsavbrott.
