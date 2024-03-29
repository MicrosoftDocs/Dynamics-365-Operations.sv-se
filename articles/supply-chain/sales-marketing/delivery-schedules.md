---
title: Leveransplaner
description: Leveransplaner ger möjlighet att följa orderradkvantiteter när du använder flera leveranser för en enskild försäljningsorder, försäljningsoffert eller inköpsorder.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b50558c5da71351082d36276a3185e1f91543f2b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573475"
---
# <a name="delivery-schedules"></a>Leveransplaner

[!include [banner](../includes/banner.md)]

Leveransplaner ger möjlighet att följa orderradkvantiteter när du använder flera leveranser för en enskild försäljningsorder, försäljningsoffert eller inköpsorder.

Använd en leveransplan när den totala kvantiteten på en order- eller offertrad måste levereras i flera försändelser. Enskilda försändelser representeras av leveransrader. Två eller fler leveransrader utgör en leveransplan. Leveransraderna kan ha andra leveransdatum, kvantiteter, leveranssätt och lagringsdimensioner, till exempel plats och lagerställe.  

**Exempel på en leveransplan**

| Artikel                              | Värde                                    |
|-----------------------------------|------------------------------------------|
| Total order (den ursprungliga orderraden) | 600 stolar                               |
| Begärd leveransplan       | 100 stolar per månad                     |
| Önskat tidsram för leverans | 6 månader den första dagen i varje månad |

I det här scenariot begär kunden leverans av 600 stolar i batchar med 100 stolar över en period i halvåret. Om du vill spåra leveranskraven skapar du en leveransplan. På sidan leveransplan skapar du sex separata leveransrader. Varje leveransrad innehåller 100 stolar och visar leveransdatum för dessa 100 stolar. I det här fallet motbokas varje rad på den första i månaden för sex månader i följd.  

När du skapar en leveransplan, ändras typen för den ursprungliga orderraden automatiskt till **Orderrad med flera leveranser**. En rad med den här typen kallas för en kommersiella rad och är markerade med en ikon. Leveransraden är markerad med en annan ikon. Om du ändrar en kvantitet på en leveransrad uppdateras den kommersiella raden till den totala kvantiteten för leveransplanen. Om ett handelsavtal har definierat en total rabatt för ordern, garanterar leveransplanen att din order är berättigad till en total orderrabatt, även om ordern är uppdelad i separata leveranser.  

Order som har en leveransplan bearbetas mot leveransraderna. Bearbetningen inkluderar bokföring av följesedlar, produktinleveranser och fakturering.  

Dokumentera utskrifter av order och offerter som har en leveransplan Visa bara leveransraderna. De visar inte de ursprungliga raderna (kommersiella rader). **Obs!** Dessutom visas bara leveransraderna när du genomför dessa åtgärder:

-   Bokför
-   Kopiera sidor
-   Bläddra i listasidor och rapporter

När du bekräftar försäljningsofferter, visar de resulterande försäljningsorder hela leveransplanen, även orderraderna som har flera leveranser. Dessutom visas hela leveransplanen på alla sidor, till exempel försäljningsorder, försäljningsofferter och inköpsorder.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]