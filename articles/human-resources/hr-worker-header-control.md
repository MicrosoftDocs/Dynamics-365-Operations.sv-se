---
title: Huvudkontroll för arbetare
description: I den här artikeln finns information om huvudkontrollen som kan anpassa i Medarbetarens självbetjäning, i Personer och på sidan Arbetare i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445955"
---
# <a name="worker-header-control"></a>Huvudkontroll för arbetare

Microsoft Dynamics 365 Human Resources ger en personanpassad huvudkontroll i navet **Medarbetarens självbetjäning**, i **Personer** och på den strömlinjeformade sidan **Arbetare**. Huvudet innehåller nyckelinformation om arbetaren och åtgärder som t.ex. e-post, samtal eller meddelanden med enkla klick. Huvudet kan ändras genom att fält tas bort eller fält läggs till, inklusive anpassade fält, så att ytterligare information visas. Du använder den nya huvudkontrollen genom att gå till **Funktionshantering** och aktivera funktionen **Arbetshuvudkontroll**.

## <a name="personalization"></a>Anpassning

En av de viktigaste fördelarna med arbetsstyrningen är möjligheten att personanpassa information som visas i huvudet.

I rubrikens övre högra del finns en grupp med tre fält som visar olika data, beroende på medarbetarens status. Den här gruppen av fält kallas för Spotlight-delen av sidhuvudet. Du kan anpassa Spotlight-delen av rubriken genom att ta bort de aktuella fälten eller lägga till fält. Fälten som kan läggas till i Spotlight-delen i rubrikkontrollen skiljer sig åt för navet **Självbetjäning för medarbetare**, **Personer** och **Arbetare**.

## <a name="employee-self-service"></a>Självbetjäning för medarbetare

Arbetsrubriken på sidan **Självbetjäning för medarbetare** innehåller följande information:

- Arbetares namn
- Anställningsnummer
- Befattningstitel
- Avdelningar
- Typ av arbetare
- Juridisk person för anställningen
- Antal tjänsteår
- Rapporterar till (chef)
- Befattningstyp

Rubriken innehåller också en åtgärd med ett klick som gör att personens personuppgifter kan redigeras. Markera **Redigera personuppgifter** för att öppna sidan **Personuppgifter** i **Självbetjäning för medarbetare**.

## <a name="people-hub"></a>Personnav

Arbetarrubriken i **Personer** (sidan **arbetsytan personer**) innehåller följande information:

- Arbetares namn
- Anställningsnummer
- Befattningstitel
- Avdelningar
- Typ av arbetare
- Juridisk person för anställningen
- Antal tjänsteår
- Rapporterar till (chef)
- Befattningstyp

Rubriken innehåller också åtgärder som t.ex. e-post, samtal eller meddelanden med ett enda klick. Om en användare visar sin egen information på **arbetsytan Personer**, innehåller åtgärdsavsnittet med ett enda klick knappen **Redigera personlig information**. Användaren kan välja denna knapp för att öppna sidan **Personuppgifter** i **Självbetjäning för medarbetare**.

## <a name="streamlined-worker-page"></a>Strömlinjeformad arbetarsida

Arbetsrubriken på strömlinjeformade sidan **arbetare** innehåller följande information:

- Arbetares namn
- Anställningsnummer
- Befattningstitel
- Avdelningar
- Typ av arbetare
- Juridisk person för anställningen

Beroende på vilken status medarbetaren har kan informationen i rubriken komma att ändras. Om medarbetaren exempelvis har lämnat företaget innehåller rubrikkontrollen en **avslutad** bricka, slutdatum för anställningen och uppsägningsorsaken.

I tabellen nedan visas de data som visas i rubriken för olika medarbetarstatus.

| Status på medarbetare | Data som visas | Notering |
|-----------------|--------------------|------|
| Väntar | <ul><li>Namn</li><li>Anställningsnummer</li><li>Befattningstitel</li><li>Avdelning</li><li>Typ av arbetare</li><li>Juridisk person</li><li>Väntande märke</li><li>Startdatum</li><li>Rapporterar till</li><li>Befattningstyp</li></ul> | |
| Anställning nyligen | <ul><li>Namn</li><li>Anställningsnummer</li><li>Befattningstitel</li><li>Avdelning</li><li>Typ av arbetare</li><li>Juridisk person</li><li>Anställning aktivitetsikon</li><li>Antal tjänsteår</li><li>Rapporterar till</li><li>Befattningstyp</li></ul> | Standardbrickan **Anställning nyligen** visas för anställda som har anställts under de senaste sju dagarna. Om du vill ändra denna inställning, på sidan **Personalparametrar** på fliken **Allmänt** i avsnittet **Datumintervall för senaste anställningar** anger du en tidsram. Om du till exempel vill visa **Anställning nyligen** listan med medarbetare som anställdes under de senaste 14 dagarna anger du fältet **Period** till **14** och fältet **Enhet** till **Dagar**. |
| Aktiva medarbetare | <ul><li>Namn</li><li>Anställningsnummer</li><li>Befattningstitel</li><li>Avdelning</li><li>Typ av arbetare</li><li>Juridisk person</li><li>Startdatum</li><li>Rapporterar till</li><li>Befattningstyp</li></ul> | |
| Avslutar | <ul><li>Namn</li><li>Anställningsnummer</li><li>Befattningstitel</li><li>Avdelning</li><li>Typ av arbetare</li><li>Juridisk person</li><li>Avsluta bricka</li><li>Antal tjänsteår</li><li>Rapporterar till</li><li>Befattningstyp</li></ul> | Som standard visas **avsluta** bricka för medarbetare som kommer att lämna det de kommande sju dagarna. Om du vill ändra denna inställning, på sidan **Personalparametrar** på fliken **Allmänt** i avsnittet **datumintervall för arbetare som slutar** anger du en tidsram. Om du till exempel vill visa **slutar** listan med medarbetare som slutar följande 14 dagarna anger du fältet **Period** till **14** och fältet **Enhet** till **Dagar**. |
| Har slutat | <ul><li>Avsluta bricka</li><li>Anställningsnummer</li><li>Slutdatum för anställning</li><li>Orsakskod</li></ul> | Som standard visas **avslutad** bricka för medarbetare som slutat de senaste sju dagarna. Om du vill ändra denna inställning, på sidan **Personalparametrar** på fliken **Allmänt** i avsnittet **datumintervall för arbetare som slutat** anger du en tidsram. Om du till exempel vill visa **slutat** listan med medarbetare som har slutat de sista 14 dagarna anger du fältet **Period** till **14** och fältet **Enhet** till **Dagar**. |
