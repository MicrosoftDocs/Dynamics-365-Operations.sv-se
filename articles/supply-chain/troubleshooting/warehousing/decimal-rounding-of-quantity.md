---
title: Decimalavrundning för den fysiska uppdateringskvantiteten blir fel
description: När du genererar en följesedel innehåller den utgående beläggningen en kvantitet som inte matchar det antal decimaler som definierats i enheten.
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
ms.openlocfilehash: a9e0475aab452daa9e1a6f012e17a59e611010da
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920483"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>Decimalavrundning för den fysiska uppdateringskvantiteten blir fel

Felkod: SYS19589

## <a name="symptoms"></a>Symtom

När du genererar en följesedel innehåller den utgående beläggningen en kvantitet som inte matchar det antal decimaler som definierats i enheten.

När du försöker generera en följesedel visas följande felmeddelande i systemet:

> Decimalavrundningen av den fysiskt uppdaterade kvantiteten i enheten %1 är felaktig.

Du kan därför inte generera följesedel för beläggningen.

## <a name="cause"></a>Orsak

Systemet utvärderar om decimalavrundningen för leveranskvantiteten motsvarar det decimalvärde som har definierats för leveransenheten. När systemet avrundar leveranskvantiteten till angivet antal decimaler och det visar sig att den avrundade skeppningskvantiteten inte matchar den faktiska leveranskvantiteten kan du inte generera följesedeln. Det här problemet kan till exempel inträffa om försäljningskvantiteten är 1,75 kilo (kg), men antalet decimaler är satt till *1*.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Granska dina lastrader och gör justeringar för att säkerställa att kvantiteten kan omvandlas rent utan decimaltal och andra avrundningsproblem.
- Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Granska dina lastrader och gör justeringar för att säkerställa att kvantiteten kan omvandlas rent utan decimaltal och andra avrundningsproblem

Använd följande procedurer för att granska dina lastrader och gör justeringar för att säkerställa att kvantiteten kan omvandlas rent utan decimaltal och andra avrundningsproblem.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.
1. På fliken **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.
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
