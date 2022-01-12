---
title: Kvantiteten som du försöker uppdatera överstiger den mottagna/levererade kvantiteten.
description: När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider arbetskvantiteten som plockades och reserverades för försäljningsordern.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ec5e0ac8dd097e5ebf016683fc5c17df7ecb2305
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920408"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a>Kvantiteten som du försöker uppdatera överstiger den mottagna/levererade kvantiteten

Felkod: SYS7676

## <a name="symptoms"></a>Symtom

När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider arbetskvantiteten som plockades och reserverades för försäljningsordern.

När du försöker generera en följesedel visas följande felmeddelande i systemet:

> Kvantiteten som du försöker uppdatera överskrider den kvantitet som inlevererats/levererats.

Du kan därför inte generera följesedel för beläggningen.

## <a name="cause"></a>Orsak

Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden. Det här problemet kan till exempel inträffa om beläggningsradkvantiteten, arbetskvantiteten eller den plockade kvantiteten inte stämmer.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.
- Justera kvantiteten för beläggningsrad.
- Återför alla plockregistreringar och gör om plockningen.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan genereras för.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.
1. Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.

### <a name="adjust-the-load-line-quantity"></a>Justera kvantiteten för beläggningsrad

Använd följande procedur för att justera lastradkvantiteten.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.
1. På fliken **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.
1. Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.
1. Ställ in fältet **Minska lastrad** om du vill återspegla justeringar på lastraden.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Återför alla plockregistreringar och gör om plockningen

Om någon har använt plockregistrering för att stänga en lastrad utan arbete kan det uppstå en avvikelse mellan kvantiteten på lastraden och den plockade kvantiteten. I det här fallet måste manuell plockregistrering återföras, och plockningen måste sedan slutföras med hjälp av den mobila appen Warehouse Management.

Använd följande procedur när du återför plockregistreringen.

1. Gå till **Kundreskontra \> Order \> Alla order**.
1. Välj den försäljningsorder som du inte kan bokföra en följesedel för.
1. På fliken **Försäljningsorderrader** väljer du den försäljningsorderrad för vilken plockningsregistreringen har gjorts.
1. Välj **Uppdatera rad \> Plockning** om du vill häva plockningen av artiklarna.
