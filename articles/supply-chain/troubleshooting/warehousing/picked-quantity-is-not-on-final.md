---
title: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
description: Du kan inte bekräfta en leverans eftersom inga artiklar har plockats
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b57d3151852c9a2880185b7d9414e4246b7efb6429fcfce04c7cdae4ee00e37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760934"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Du kan inte bekräfta en leverans eftersom inga artiklar har plockats

Felkod: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en leverans visas följande felmeddelande i systemet:

> Vissa av de artiklar som behövs för lasten %1 har ännu inte plockats och förflyttats till den slutliga leveransplatsen.

Du kan därför inte bekräfta leveransen för beläggningen.

## <a name="cause"></a>Orsak

Beläggningen eller leveransen kan inte bekräftas i sitt aktuella tillstånd eftersom något av följande villkor kan finnas:

- Det relaterade arbetet har ännu inte plockats och flyttats till den slutliga leveransplatsen.
- Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.
- Platsdirektivet har konfigurerats med förpackningsplats som den slutliga leveransplatsen vid användning av påfyllnadsmall för skapande av behållare.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där leveransbekräftelsen misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.
- Avbryt de arbets-ID som har skapats med förpackningsplatsen som slutlig leveransplats, omkonfigurera plats direktivet och återutsläpp belastningen.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar

Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som leveransen inte kan bekräftas för.
1. På snabbfliken **Beläggningsrader** väljer du beläggningsraden.
1. Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.
1. I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.
1. Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.
1. Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Avbryt de arbets-ID som har skapats med förpackningsplatsen som slutlig leveransplats, omkonfigurera plats direktivet och återutsläpp belastningen

Använd följande procedur för att avbryta arbets-ID som har förpackningsplatsen som den slutliga placeringsplatsen med automatiserad skapande av behållare på plats.

1. Gå till **Warehouse management \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. Dialogrutan **Avbryt arbete**. I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta. Det valda arbets-ID:t måste ha ett värdet **Arbetsstatus** av *Öppen*, *Pågår*, *Annullerat*, *Kombinerad* eller *Stängd*.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.
1. Upprepa denna procedur för övriga arbets-ID:n efter behov.

Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).

Använd följande procedur om du vill omkonfigurera platsdirektivet så att förpackningsplatsen inte används som den slutliga leveransplatsen när automatisk skapande av behållare ställs in för påfyllnadsmall.

1. Gå till **Warehouse management \> Inställningar \> Platsdirektiv**.
1. Välj **Inköpsorder** i fältet *Försäljningsarbetsorder*.
1. Välj det platsdirektivet du använder för automatiserad skapande av behållare.
1. På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.
1. I dialogrutan frågeredigera, på **Intervall** hitta raden där **Fält** anges *Platsprofil* och kontrollera att fältet **Villkor** för den raden är inte inställt på en platsprofil som har en **Platstyp** av *Förpackning*. Justera fältet **Kriterier** för att korrigera den slutliga placeringsplatsen.

Använd följande procedur för att frigöra lasten igen och skapa arbets-ID med rätt slutlig leveransplats.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. I avsnittet **Laster** hittar du den last som behöver frisläppas.
1. I avsnittet **Laster** välj **Släpp \> Släpp till lagerställe** om du vill frisläppa den valda beläggningen till lagerstället.
1. Upprepa denna procedur för övriga laster efter behov.
