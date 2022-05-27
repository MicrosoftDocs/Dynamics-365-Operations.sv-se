---
title: Frisläpp till regel för lagerställe
description: Det här ämnet ger information om funktionen frisläpp till regel för lagerställe, vilket ger flexibilitet vid frisläppning till lagerstället. Det lägger till ett konfigurationsalternativ som styr om systemet tillåter att delvis reserverade orderrader frisläpps.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5fef1d942f2e9d3467fb8a00c6d89cc5c018a5aa
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674629"
---
# <a name="release-to-warehouse-rule"></a>Frisläpp till regel för lagerställe

[!include [banner](../includes/banner.md)]

Funktionen *Frisläpp till regel för lagerställe* ger flexibilitet under frisläppning till lagerstället. Det lägger till ett konfigurationsalternativ för varje lagerställe. Du kan använda det här alternativet för att ange om delvis reserverade orderrader kan frisläppas för det lagerstället. Funktionen fungerar tillsammans med avancerad direktutleverans i situationer där en del av en order radkvantitet har markerats mot en leveranskälla, men den återstående delen kan bearbetas i lagerstället. Därför kan raden frisläppas så att lagerbearbetning för den tillgängliga lagerkvantiteten kan fortsätta.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>Aktivera och initiera funktionen Frisläpp till regel för lagerställe

### <a name="turn-on-the-feature"></a>Aktivera en funktion

Innan du kan använda funktionen *Frisläpp till regel för lagerställe* den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Frisläpp till regel för lagerställe*

### <a name="initialize-the-feature"></a>Initiera funktionen

När funktionen är aktiverad i systemet måste du initiera den för att ställa in regeln på rätt initial status för alla lagerställen.

- För lagerställen som inte aktiveras för lagerstyrning anges regeln ursprungligen till **ej tillämplig**.
- För lagerställen som aktiveras för lagerstyrning anges regeln ursprungligen till **Tillåt viss reservation**.

Om du vill initiera funktionen och ställa in frisläppning till regel för lagerställe för alla lagerställen följer du stegen nedan.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **Parametrar för lagerstyrning** på fliken **Allmänt** i avsnittet **Företagsinformation** väljer du länken för regeln **Initiera frisläppning till lagerställe**. (Om den här länken inte visas är funktionen antingen inte aktiverad eller också har den redan initierats.)
1. När du uppmanas att bekräfta åtgärden väljer du **Ja** för att initiera funktionen.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Ställ in regeln för frisläppning till lagerställe för varje lagerställe

När funktionen har aktiverats och initierats får alla lagerställen en initial inställning, enligt beskrivningen i föregående avsnitt. Du kan ändra inställningen för enskilda lagerställen genom att följa de här stegen.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
1. Välj vilket lagerställe du vill konfigurera.
1. Välj **Redigera** om du vill placera sidan i redigeringsläge.
1. På snabbfliken **Lagerställe** i avsnittet **Reservationer** kontrollerar fältet **Krav för lagerreservation** om delvis frisläppning av order är tillåten. Välj ett av följande värden:

    - **Ej tillämpligt** – När funktionen är aktiverad och initierad tilldelas detta värde automatiskt till alla lagerställen som inte är aktiverade för lagerstyrning. Värdet kan inte ändras. Det här värdet är inte tillgängligt för lagerställen som är aktiverade för lagerstyrning.
    - **Tillåt viss reservation** – Order kan frisläppas när en kvantitet har reserverats. Systemet kommer att utvärdera om den icke reserverade kvantiteten ska markeras för avancerad direktutleverans och den kvantitet som krävs markeras. Om det inte finns någon markering kommer systemet bara att skapa arbete för den reserverade kvantiteten. När funktionen är aktiverad och initierad tilldelas detta värde automatiskt till alla lagerställen som är aktiverade för lagerstyrning. Det här värdet är inte tillgängligt för lagerställen som inte är aktiverade för lagerstyrning.
    - **Kräv fullständig reservation** – Order kan bara frisläppas om hela kvantiteten är reserverad. De kan inte frisläppas om den totala kvantiteten varken är fysiskt reserverad eller planerad för direktleverans. Det här värdet är inte tillgängligt för lagerställen som inte är aktiverade för lagerstyrning.

1. Välj **Spara**.

## <a name="scenarios"></a>Scenarier

I det här avsnittet finns två scenarier som du kan arbeta igenom för att lära dig vad funktionen gör och hur du använder den.

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom dessa scenarier med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda dessa scenarier som vägledning för funktionen när du arbetar med ett produktionssystem. I så fall måste du emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>Scenario 1: Kräv fullständig frisläppning (ingen planerad direktleverans)

Det här scenariot visar hur funktionen fungerar för lagerställen som är inställda på att **kräva fullständig reservation**.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
1. För lagerställe _62_ ställer du in fältet **Krav för lagerreservation** till **Kräv full reservation** enligt beskrivningen i avsnittet [Ställ in regeln för frisläppning till lagerställe för varje lagerställe](#set-option-warehouse) tidigare i detta ämne.
1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på _US-004_.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till _62_.

1. Välj **OK** för att skapa den nya försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Den innehåller en tom rad i rutnätet i avsnittet **försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *2*

1. Välj **Lägg till rad** för att lägga till en nya rad och ställa in följande värden:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *2*

1. Markera den första orderraden och i menyn **Lager** ovanför rutnätet väljer du **Reservation**.
1. På sidan **Reservation** välj **Reservera parti** för att reservera den valda radens fullständiga kvantitet i lagerstället.
1. Stäng sidan **Reservation** om du vill återgå till försäljningsordern.
1. Reservera inte den andra orderraden.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.
1. Observera att följande felmeddelande visas: "den fullständiga kvantiteten måste vara fysiskt reserverad". Därför skapas inget arbete, en försändelse eller en belastning för ordern i systemet.

    > [!NOTE]
    > Samma felmeddelande visas om du delvis reserverar den andra raden.

### <a name="scenario-2-allow-partial-release"></a>Scenario 2: Tillåt delvis frisläppning

Det här scenariot visar hur funktionen fungerar för lagerställen som är inställda på att **Tillåt delvis frisläppning**.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
1. För lagerställe _62_ ställer du in fältet **Krav för lagerreservation** till **Tillåt delvis frisläppning** enligt beskrivningen i avsnittet [Ställ in regeln för frisläppning till lagerställe för varje lagerställe](#set-option-warehouse) tidigare i detta ämne.
1. På samma sätt som i [föregående scenario](#scenario1), gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder** och skapar en order för kundkonto _US-004_ från lagerställe _62_. Lägg till följande två orderrader:

    - **Rad 1:** Ställ in fältet **Artikelnummer** till _A0001_, fältet **Kvantitet** till _2_ och fältet **Enhet** till _Pcs_.
    - **Rad 2:** Ställ in fältet **Artikelnummer** till _A0002_, fältet **Kvantitet** till _2_ och fältet **Enhet** till _Pcs_.

1. Som du gjorde i [föregående scenario](#scenario1) reserverar du hela kvantiteten för orderrad 1, men reservera inte orderrad 2.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.
1. Observera att du inte får ett felmeddelande den här gången. I stället skapar systemet arbete, försändelser och laster efter behov och visar resultaten.
1. Om du vill visa leverans-, last- och arbetsinformation använder du alternativen på menyn **Lagerställe** ovanför rutnätet:

    - **Rad 1:** tre alternativ är tillgängliga: **Leveransdetaljer**, **Lastdetaljer** och **Arbetsuppgifter**. Välj varje alternativ om du vill visa information om leveransen, lasten och arbetet som skapades när ordern släpptes till lagerstället.
    - **Rad 2:** endast alternativet **Arbetsinformation** är tillgängligt. Markera den och lägg märke till att inget arbete har skapats eftersom inget lager har reserverats. Därför skapades ingen försändelse eller last för någon.

> [!NOTE]
> Samma resultat förväntas när den andra raden reserveras delvis. I det här fallet kommer arbetet att skapas för den reserverade radkvantiteten men inte för den icke reserverade kvantiteten.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]