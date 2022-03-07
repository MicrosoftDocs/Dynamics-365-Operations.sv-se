---
title: Du kan inte bekräfta en leverans eftersom lastrader har noll kvantitet
description: Du kan inte bekräfta en leverans eftersom lastrader har noll kvantitet.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5dc5f8962ba37d21d7ef505fea940dc8767a9d9295588cb0e12e9eebe379a35c
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012215"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>Du kan inte bekräfta en leverans eftersom lastrader har noll kvantitet

Felkod: WAX:LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Alla rader i beläggningen %1 har kvantiteten noll.  
> Leveransen för last %1 kunde inte bekräftas

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Systemet utvärderar om lastraden kan skickas bekräftad, baserat på de arbets-ID:n som har skapats, kvantitet för lastraden och procentsatsen för underleverans. Om det inte finns några arbets-ID:n och om procentsatsen för underleverans är inställd på 100 procent, kan du inte bekräfta leveransen.

Detta problem kan till exempel uppstå om arbetet har avbrutits och procentsatsen för underleverans på lastraden är 100 procent.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där leveransbekräftelsen misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Granska dina lastrader för att se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna stämmer.
- Granska lastraderna för att se till att procentsatsen och kvantiteterna för underleverans stämmer överens med det plockade arbetet.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Granska dina lastrader för att se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna stämmer

Använd följande procedur för att granska dina lastrader för att se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna stämmer.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Öppna den last som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.
1. Om du hittar ett matchningsfel avbryter du det relevanta arbetet, omkonfigurerar platsdirektivet och frisläpper lasten på nytt. Instruktioner finns i [Du kan inte bekräfta en leverans eftersom artiklarna inte har plockats](picked-quantity-is-not-on-final.md).
1. Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Granska lastraderna för att se till att procentsatsen och kvantiteterna för underleverans stämmer överens med det plockade arbetet

Använd följande procedur för att granska lastraderna och se till att procentsatsen och kvantiteterna för underleverans stämmer överens med det plockade arbetet.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Öppna den last som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** markerar du beläggningsraden för den artikel som överskrider underleveransprocenten.
1. Justera värdet i fältet **Underleverans** **Kvantitet** efter behov.

> [!TIP]
> Om problemet består måste du kanske slutföra mer plockningsarbete för relaterade försäljningsorder eller överföringsorder tills den tillgängliga kvantiteten stämmer överens med beläggningen eller försändelsen.
