---
title: Plockad kvantitet räcker inte under genereringen av följesedeln
description: När du genererar ett paket innehåller den utgående lasten en plockad kvantitet som inte matchar den skapade arbetskvantiteten på lastraden.
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
ms.openlocfilehash: 361b61690e9e16a690234ed9319478d864c743e7559746654e4868272de13524
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716478"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a>Plockad kvantitet räcker inte under genereringen av följesedeln

Felkod: SYS54073

## <a name="symptoms"></a>Symtom

När du genererar ett paket innehåller den utgående lasten en plockad kvantitet som inte matchar den skapade arbetskvantiteten på lastraden.

När du försöker generera en följesedel visas följande felmeddelande i systemet:

> Eftersom %1 har plockats är det inte tillräckligt att uppdatera %2 när resten måste vara %3.

Du kan därför inte generera följesedel för beläggningen.

## <a name="cause"></a>Orsak

Paketet kan inte genereras kan inte bekräftas i sitt aktuella tillstånd eftersom något av följande villkor kan finnas:

- Det relaterade arbetet har ännu inte plockats och flyttats till den slutliga leveransplatsen.
- Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.
- Lastraden kvantitet, arbetskapad kvantitet och plockad kvantitet matchar inte.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.
- Justera kvantiteten för beläggningsrad.
- Återför alla plockregistreringar och gör om plockningen.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.
1. Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.

### <a name="adjust-the-load-line-quantity"></a>Justera kvantiteten för beläggningsrad

Använd följande procedur för att justera lastradkvantiteten.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.
1. På fliken  **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.
1. Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.
1. Ställ in fältet **Minska lastrad** om du vill återspegla justeringar på lastraden.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Återför alla plockregistreringar och gör om plockningen

Problemet kan inträffa eftersom någon har använt plockregistrering för att stänga en beläggningsrad utan arbete. I det här fallet måste manuell plockregistrering återföras, och plockningen måste sedan slutföras med hjälp av den mobila appen Warehouse Management.

Använd följande procedur när du återför plockregistreringen.

1. Gå till **Kundreskontra \> Order \> Alla order**.
1. Välj den försäljningsorder som du inte kan bokföra en följesedel för.
1. På fliken  **Försäljningsorderrader** väljer du den försäljningsorderrad för vilken plockningsregistreringen har gjorts.
1. Välj **Uppdatera rad \> Plockning** om du vill häva plockningen av artiklarna.
