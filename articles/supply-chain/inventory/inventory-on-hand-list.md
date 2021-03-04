---
title: Lagerbehållningslista
description: I det här avsnittet beskrivs hur du använder listsidan för lagerbehållning för att granska information om lagerbehållning. Här beskrivs några av de sätt som de olika filtrerings- och sorteringsalternativen fungerar tillsammans, och hur dessa alternativ ibland kan ge oväntade resultat när de kombineras.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 33e5ccc454191e27e33835a05094b823ec54e891
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438084"
---
# <a name="inventory-on-hand-list"></a>Lagerbehållningslista

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du använder **listsidan för lagerbehållning** för att granska information om lagerbehållning. Här beskrivs några av de sätt som de olika filtrerings- och sorteringsalternativen fungerar tillsammans, och hur dessa alternativ ibland kan ge oväntade resultat när de kombineras.

## <a name="query-your-on-hand-inventory"></a>Fråga behållningslagret

Om du vill kontrollera lagerdispositionen går du till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.

Sidan **Behållningslista** uppdateras automatiskt när transaktioner görs i lagret. Dessa transaktioner kan vara prognostiserade, fysiska eller ekonomiska transaktioner.

Använd följande verktyg för att hitta de produkter du söker efter:

- I åtgärdsfönstret väljer du [**dimensioner**](#dimensions) för att öppna en dialogruta där du kan lägga till eller ta bort kolumner som visas i rutnätet **Behållning**.
- I [rutan **Filter**](#filters-pane), anger du värden för specifika fält i filterfönstret om du endast vill visa poster som matchar dessa värden. Observera att filter som du definierar här gäller för källregister som kan aggregeras senare, enligt de dimensioner som du har valt att visa. Information om hur det här beteendet kan påverka resultaten finns i [exemplen](#examples) senare i det här avsnittet.
- I fönstret **Filter** väljer du **Tillämpa** för att generera listan med matchande lagerbehållning i rutnätet **Behållning**.
- I rutnätet **Behållning** väljer du någon kolumnrubrik för att sortera eller filtrera efter värden i den kolumnen. Ett snabbfilter överst i rutnätet innehåller fler filtreringsalternativ. Dessa filter gäller för resultaten, inte källtabellerna. Information om hur det här beteendet kan påverka resultaten finns i [exemplen](#examples) senare i det här avsnittet.

För varje matchande artikel innehåller rutnätet **behållning** följande kolumner med lagerinformation.

| Kolumn | beskrivning |
|---|---|
| Fysiskt lager | Fysiskt kvantitet som är tillgänglig i lagret. |
| Reserverat fysiskt | Total kvantitet som fysiskt reserverats. |
| Fysiskt disponibelt | Den tillgängliga (inte reserverade) kvantitet som finns i fysisk inventering.<p>**Tillgängligt fysiskt** är ett beräknat fält. Värdet motsvarar värdet för **fysiskt lager** minus **fysiskt reserverat** värde.</p> |
| Tillgängliga fysiska dimensioner för extra dimensioner | Den tillgängliga fysiska kvantiteten för alla dimensioner som visas i rutnätet. |
| Totalt beställt | Den totala kvantiteten som är inkluderad på inkommande order eller som har en positiv kvantitet i olika lagerjournaler. |
| Har beställts | Den totala kvantiteten som är inkluderad på utgående order eller som har en negativ kvantitet i olika lagerjournaler. |
| Beställt reserverat | Total partikvantitet som reserverats för beställda inleveranser. Värdet i det här fältet representerar den totala kvantiteten av artiklar i avgående transaktioner som har statusen _Beställt reserverat_. Artiklar som reserveras som beställda finns inte fysiskt tillgängliga i lagret. Därför kan de inte plockas och levereras direkt. |
| Tillgänglig för reservation | Den totala kvantiteten lagerbehållning som kan reserveras.<p>**Obs!** om kryssrutan **Reservera beställda artiklar** är markerad på sidan **Parametrar för lager och lagerstyrning**, inkluderar värdet i det här fältet förväntade inleveranser. Om kryssrutan avmarkeras utesluter värdet förväntat inleveranser.</p> |
| Totalt disponibelt | Total tillgänglig kvantitet.<p>**Total tillgänglig** är ett beräknat fält. Värdet motsvarar värdet **Tillgängliga fysiska** plus det **Totalt beställt** minus värdet **Har beställts**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Använd filter för att hitta de poster du letar efter

Använd fönstret **filter** när du vill filtrera lagerbehållningslistan så att den bara innehåller poster där fältvärdena matchar filterkriterierna. Om du vill definiera ett filter, följ dessa steg.

1. I fönstret **Filter** hitta det fält som du vill filtrera på.
2. Välj en logisk operatör i fältet under namnet på målfältet (till exempel *startar med*, *lika med* eller *större än*).
3. Ange eller välj det värde du vill söka efter.

> [!IMPORTANT]
> Sidan **Behållningslista** är monterad i en detaljerad lagerbehållning som inkluderar alla tillgängliga dimensioner. Listan på den här sidan är dock en sammanfattning. Därför kan det hända att rader kombineras från källtabellen genom att värdena aggregeras enligt de dimensioner som visas.
>
> Filtren som du definierar i fönstret **filter** gäller för källtabellen, inte den aggregerade listan. Det här problemet kan ibland leda till oväntade resultat. Information om hur det här beteendet kan påverka resultaten finns i [exemplen](#examples) senare i det här avsnittet.
> 
> Men [filtren som finns i rutnätet](#grid-filters) *gäller* för den aggregerade listan. Dessa filter inkluderar både snabbfilter överst i rutnätet och filtret för varje kolumnrubrik.

Du kan ändra uppsättningen filter som är tillgängliga i fönstret **filter** genom att följa stegen nedan.

- Om du vill ta bort ett filter från fönstret väljer du knappen **Stäng** (**X**).
- Om du vill lägga till ett filter väljer du **Lägg till** högst upp i fönstret **filter**. Dialogrutan **Lägg till filterfält** som visas visar en lista över tillgängliga fält. Den visar också information om datatypen och registret för varje fält. Använd kolumnrubrikerna för att filtrera och sortera listan efter behov och markera sedan kryssrutan för varje fält som du vill lägga till i rutan **filter**. När du är klar väljer du **infoga** för att tillämpa ändringarna.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Välj vilka dimensioner som ska visas

Dimensioner anger mer om varje artikel i lagerbehållningslistan och ger dig fler sätt att sortera och filtrera listan. De dimensioner som du väljer att visa påverkar också hur rader läggs samman på sidan **lagerbehållningslistan**. Denna aggregering kan i sin tur påverka hur rader från källtabellerna kombineras i resultaten som visas. Information om hur det här beteendet kan påverka resultaten finns i [exemplen](#examples) senare i det här avsnittet.

Om du vill anpassa urvalet av lagerdimensioner som visas följer du dessa steg.

1. I åtgärdsfönstret, välj **Dimensioner**.

    Dialogrutan **Dimensionsvisning** som visas visar varje dimension.

2. Markera kryssrutan för varje dimension som du vill ta med i rutnätet.
3. Om du vill att ditt val ska användas som standard nästa gång du öppnar sidan **behållningslistan** anger du alternativet **spara inställningar** till **ja**. Om du ställer in detta alternativ till **Nej**, används ditt val bara under den aktuella sessionen. Nästa gång du öppnar sidan används därför den aktuella standardmarkeringen.
4. Välj **OK** om du vill tillämpa ändringen och stänga dialogrutan.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Filtrera efter utflödet av lagerbehållningslistan

Du kan välja någon kolumnrubrik i rutnätet **Behållning** för att sortera eller filtrera efter värden i den kolumnen. Ett snabbfilter överst i rutnätet innehåller fler filtreringsalternativ. Dessa filter gäller för resultaten, inte källtabellerna. Information om hur det här beteendet kan påverka resultaten finns i [exemplen](#examples) senare i det här avsnittet.

> [!NOTE]
> Du kan inte filtrera och sortera efter alla kolumner. De flesta av kolumnerna kvantitet inkluderar inte sorterings- och filtreringskontroller, eftersom de är beräknade fält. Kolumnen **Har beställts** är ett undantag.

## <a name="examples"></a><a name="examples"></a>Exempel

Systemet innehåller en detaljerad (ej aggregerad) lagertabell som visar följande lagerbehållning.

| Artikelnummer | Webbplats | Lagerställe | Fysiskt lager | Fysiskt disponibelt |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>Scenario 1

Sidan **Behållningslista** är inställd på att visa följande slutgiltiga dimensioner:

- Artikelnummer
- Webbplats
- Lagerställe

I rutan **Filter** ställs följande filterkriterier in:

- **Artikelnummer** \| **är exakt** \| _IA0001_
- **Tillgänglig fysiskt** \| **mindre än eller lika med** \| _1_

Här är resultatet av utdata.

| Artikelnummer | Webbplats | Lagerställe | Fysiskt lager | Fysiskt disponibelt |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>Scenario 2

Sidan **Behållningslista** är inställd på att visa följande slutgiltiga dimensioner:

- Artikelnummer
- Webbplats

I rutan **Filter** ställs följande filterkriterier in:

- **Artikelnummer** \| **är exakt** \| _IA0001_
- **Tillgänglig fysiskt** \| **mindre än eller lika med** \| _1_

Här är resultatet av utdata.

| Artikelnummer | Webbplats | Fysiskt lager | Fysiskt disponibelt |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Observera att inställningarna i fönstret **filter** gäller för den detaljerade (ej aggregerade) lager tabellen som visas i början av det här avsnittet. Det innebär att kriteriet som **tillgängligt fysiskt** \| **mindre än eller lika med** \| _1_ hittar två rader från tabellen (den första och tredje raden, som var och en visar ett **tillgängligt fysiskt** värde för _1_). I det här scenariot är dock sidan **behållningssidan** inte är inställd för att visa dimensionen **lagerställe**. Därför aggregerar den två ursprungliga raderna till en enda resulterande rad, eftersom båda raderna har identiska värden i alla dimensioner som visas. Denna rad verkar bryta mot filtreringskriteriet eftersom värdet **tillgängliga fysiska** visas som _2_. Resultatet är emellertid korrekt, eftersom inställningarna i **filter**-fönstret gäller källtabellen, inte den sammanställda tabell som visas på sidan **Behållningslista**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]