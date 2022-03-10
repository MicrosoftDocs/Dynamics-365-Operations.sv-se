---
title: Fysisk resterande kvantitet i enheten får inte vara noll
description: När du genererar en följesedel har data som levereras till den en lagerkvantitet som inte är noll, men ingen försäljningskvantitet.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d767fdce861ccb481a3fe289480a51a7534dc207
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920234"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>Fysisk resterande kvantitet i enheten får inte vara noll

Felkod: SYS19591

## <a name="symptoms"></a>Symtom

När du genererar en följesedel har data som levereras till den en lagerkvantitet som inte är noll, men ingen försäljningskvantitet.

När du försöker generera en följesedel visas följande felmeddelande i systemet:

> Fysisk rest i enheten %1 måste vara skild från noll.

Du kan därför inte generera följesedel för beläggningen.

## <a name="cause"></a>Orsak

Systemet utvärderar den fysiska återstående kvantiteten i lagerenheten och den fysiska resterande kvantiteten i leveransenheten. Om systemet hittar att den fysiska resterande kvantiteten i leveransenheten är 0 (noll), men den fysiska resterande kvantiteten i lagerenheten 0, kan du inte generera följesedeln. Det här problemet kan till exempel uppstå om försäljningsenheten och lagerenheten för artikeln skiljer sig åt och konverteringen mellan enheterna inte stämmer.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.
- Granska beläggningsraderna och gör justeringar för att kvantiteten ska kunna konverteras rensas utan avrundningsproblem.
- Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.
- Kontrollera att lagermåttet är mindre än försäljningsmåttenheten.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.
1. Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Granska beläggningsraderna och gör justeringar för att kvantiteten ska kunna konverteras rensas utan avrundningsproblem

Använd följande procedurer för att granska dina lastrader och gör justeringar för att kvantiteten ska kunna konverteras rensas utan avrundningsproblem

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.
1. På fliken **Läs in rader** markerar du inläsningsraden för den artikel som överskrider överleverans.
1. Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.
1. På fliken **Radinformation** väljer du **Order**.
1. I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att generering av följesedel kan fortsätta.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.

Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. På snabbfliken **Lastrader** väljer du lastraden för den artikel som orsakar ett problem. Lägg märke till värdet i fältet **kvantitet** och **enhet**.
1. Gå till **Organisationsadministration \> Enheter \> Enheter**.
1. Välj den enhet som följesedel inte kan genereras för.
1. Justera värdet i fältet **Decimalprecision** efter behov.

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Kontrollera att lagermåttet är mindre än försäljningsmåttenheten

Kontrollera att lagermåttet är mindre än försäljningsmåttenheten. Överväg att omkonfigurera artikelns måttenhet efter behov.
