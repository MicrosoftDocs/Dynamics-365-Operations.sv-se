---
title: Batchattribut
description: Den här ämnet innehåller information om batchattribut. Batchattribut är egenskaper för råmaterial och färdiga produkter som utgör lagerbatchar. Ämnet innehåller även information om hur du tilldelar batchattribut och hur du kan söka i dem när du reserverar batchar.
author: ShylaThompson
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup, WHSBatchAttribReserve
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 744c8d65d8f1b28dc8197f3f8dd1803f916958b5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246487"
---
# <a name="batch-attributes"></a>Batchattribut

[!include [banner](../includes/banner.md)]

Den här ämnet innehåller information om batchattribut. Batchattribut är egenskaper för råmaterial och färdiga produkter som utgör lagerbatchar. Ämnet innehåller även information om hur du tilldelar batchattribut och hur du kan söka i dem när du reserverar batchar.

Batchattribut är egenskaper för råmaterial och färdiga produkter som utgör lagerbatchar. Batchattribut kan variera, beroende på faktorer som miljöfaktorer, kvaliteten på råmaterial som används för att producera batchen, eller resultatet av den färdiga produkten. Numret och typerna av batchattribut som används, kan variera mycket från en bransch till en annan. Här följer två exempel som visar hur du använder batchattribut:

-   I ostbranschen kan mjölk, som är ett av råmaterialen som används för att tillverka osten, ha attribut som till exempel fetthalt och procentsatsvikt. Osten som tillverkas av mjölken kan i sin tur ha attribut som fukthalt och ålder.
-   I stålbranschen kan järnet som tillverkas ha attribut som procentsatser av magnesiuminnehåll, silverinnehåll och zinkinnehåll.

Fär att bättre kunna hantera numret och typerna av attribut, kan du använda batchattributgrupper. På detta sätt måste du inte lägga till varje enskilt attribut.

## <a name="assign-batch-attributes"></a>Tilldela batchattribut
Du kan tilldela batchattribut till enskilda produkter som hålls i lagerbatchar, eller så kan du tilldela dem till produkter som är associerade med specifika kunder. Innan du kan tilldela ett batchattribut på kundnivån, måste du tilldela den till produktnivån. Produkten måste ha batchdimensionen inställd på **Aktiv** i spårningsdimensiongruppen. För att tilldela ett batchattribut till en enskild produkt använder du den produktspecifika sidan. Om attributet är specifikt för en produkt för en kund, ska du använda den kundspecifika sidan. När du lägger till ett attribut till en produkt, definierar du också andra parametrar. Nedan följer några exempel:

-   Det lägsta och högsta intervallen för ett attribut av typerna **Heltal** eller **Del**.
-   Toleransåtgärder för ett attribut av typen **Heltal** eller **Del**. Om värdet för attributet ligger utanför intervallet för minsta och största värde, kan åtgärden vara antingen en varning eller ett felmeddelande.
-   Målvärdet för attributet. Det här värdet är det optimala värdet för attributet och det gäller för alla attributtyper.

Du kan öppna sidorna för produkter som du väljer på sidan **Frisläppta produkter** i Produktinformationshantering. När du har tilldelat batchattribut till en produkt, kan du lägga till specifika värden till attributen på sidan **Batchattribut i lager**.

## <a name="reserve-batches"></a>Reservera batchar 
Du kan söka i batchattribut när du gör batchreservationer för en försäljningsorder för att fullfölja en kunds order, eller när du plockar och reserverar batchar för en tillverkningsorder. Sökninghjälpen hittar en lagerbatch som innehåller produkten som har det batchattribut som du vill ha. När du har hittat batchen eller batcharna kan du reservera produkten till den ursprungliga lagertransaktionsraden.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]