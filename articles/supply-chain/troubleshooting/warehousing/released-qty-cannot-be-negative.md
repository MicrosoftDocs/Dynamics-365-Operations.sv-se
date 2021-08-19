---
title: Det går inte att uppdatera en lastrad eftersom den frisläppta kvantiteten skulle bli negativ
description: Problemet uppstår när en uppdatering eller radering av en lastrad leder till en negativ frisläppt kvantitet.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728469"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>Det går inte att uppdatera en lastrad eftersom den frisläppta kvantiteten skulle bli negativ

Felkod: @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Symtom

Problemet uppstår när en uppdatering eller radering av en lastrad leder till en negativ frisläppt kvantitet. När du försöker uppdatera eller radera lastraden visas i detta fall följande felmeddelande i systemet:

> Frisläppt kvantitet kan inte vara negativ för artikel %1, parti %2.

Därför kan du inte uppdatera eller radera lastraden.

## <a name="cause"></a>Orsak

När du har uppdaterat eller raderat en lastrad uppdaterar systemet den frisläppta kvantiteten för den relaterade försäljningsraden (*whsSalesLine.ReleaseQty*). Systemet utvärderar den frisläppta kvantiteten och om den frisläppta kvantiteten för raden är negativ efter uppdateringen låter inte systemet dig uppdatera eller radera raden. Valideringen görs varje gång du försöker uppdatera antingen lastradkvantiteten eller måttenheten genom olika åtgärder, som radera en lastrad, radera en försändelse, ändra kvantitet för en lastrad, minska den plockade kvantiteten och kort plockning.

Den vanligaste rotorsaken till problemet är en ändring vid enhetskonverteringen som används för öppna lastrader. Enhetskonverteringen när en försäljningsorder frisläpptes var till exempel *50 Ea = 1 PL*. Men innan den relaterade lastsförsändelsen slutfördes ändrades enhetskonverteringen till *100 Ea = 1 PL*.

## <a name="resolution"></a>Lösning

Lösningen är att återställa enhetskonverteringens ändringar, uppdatera eller radera lastraden och sedan åter implementera konverteringen. Du måste förhindra annan last, som den artikel som orsakade problemet från att bearbetas tills problemet är löst. Annars kan de nya konverteringarna användas för andra laster som redan är öppna.

Utför följande uppgifter för att åtgärda detta problem:

1. Granska enhetskonverteringen som användes för lastraden.
2. Granska den aktuella enhetskonverteringen för artikeln och gör justeringar så det går att uppdatera eller radera lastraden.
3. Uppdatera eller radera lastraden och återställ enhetskonverteringsjusteringarna.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>Granska enhetskonverteringen som användes för lastraden

Använd följande procedur för att granska lastrader och notera enhetskonverteringen som användes för lastraden.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj lasten som innehåller lastraden som inte kan raderas eller uppdateras.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Välj relevant arbets-ID i det övre rutnätet.
1. Beräkna konverteringsförhållandet mellan värdet för **Lagerarbetskvantitet** och värdet för **Arbetskvantitet** på fliken **Allmänt** längst ner på sidan. Gör en notering av förhållandet.
1. Upprepa proceduren för alla relevanta arbets-ID för att säkerställa att samma konvertering används.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>Granska den aktuella enhetskonverteringen för artikeln och gör justeringar

Granska produktens enhetskonvertering och gör justeringar för att se till att enhetskonverteringen stämmer överens med lastraden.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna relevant produkt för att gå till sidan **Information om frisläppt produkt**.
1. I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Enhetskonverteringar**.
1. Välj konvertering mellan enheterna och gör justeringar med den konvertering du hittade i det föregående avsnittet.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>Uppdatera eller radera lastraden och återställ enhetskonverteringsjusteringarna

Gör på följande sätt för att bearbeta lastraden efter behov och återställa enhetskonverteringarna.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Öppna lasten som innehåller lastraden som inte kan raderas eller uppdateras.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Fortsätt med nödvändiga åtgärder vid behov. (T.ex. radera lastraden eller ändra dess kvantitet.)
1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna relevant produkt för att gå till sidan **Information om frisläppt produkt**.
1. I åtgärdsfönstret, på fliken **Produkt** i gruppen **Konfigurering**, markerar du **Enhetskonverteringar**.
1. Välj konverteringen mellan enheterna och återställ justeringarna som du gjorde i föregående avsnitt.
