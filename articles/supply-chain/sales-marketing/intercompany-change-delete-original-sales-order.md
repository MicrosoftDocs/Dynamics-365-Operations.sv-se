---
title: Ändra eller ta bort en ursprunglig koncernintern försäljningsorder
description: I det här avsnittet beskrivs hur du ändrar och tar bort en ursprunglig försäljningsorderfunktion.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7bd6bdbf65499e9f18bf6bb5e160a5634bc37fba
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548536"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Ändra eller ta bort en ursprunglig koncernintern försäljningsorder

[!include [banner](../../includes/banner.md)]

När du ändrar en försäljningsorder synkroniseras ändringarna automatiskt med både den relevanta koncerninterna inköpsordern och den koncerninterna försäljningsordern.

> [!NOTE]
> Försäljningsorder för externa leverantörer påverkas inte av de ändringar du gör. Det gör inte heller de ursprungliga försäljningsraderna som är kopplade till inköpsorderrader för externa leverantörer.

I tabellen nedan sammanfattas de ändringar du kan göra och de förväntade resultaten.

| Operation | Resultat |
|---|---|
| Radera&nbsp;en&nbsp;ursprunglig&nbsp;försäljningsorder&nbsp;. | Den relaterade koncerninterna inköpsordern och den koncerninterna försäljningsordern raderas också. Om orderns status är **Plocklista** eller senare i processen går det inte att radera försäljningsordern. |
| Radera en ursprunglig försäljningsorderrad. | Den relaterade koncerninterna inköpsorderraden och den koncerninterna försäljningsorderraden raderas också. Om orderns status är **Plocklista** eller senare i processen går det inte att radera försäljningsorderraden. |
| Lägga till en ny försäljningsrad på en ursprunglig försäljningsorder. | Den nya försäljningsraden skapas på både den koncerninterna inköpsordern och den koncerninterna försäljningsordern. |
| Ändra kvantiteten på en ursprunglig försäljningsorderrad. | Kvantiteten synkroniseras med båda den koncerninterna inköpsorderraden och den koncerninterna försäljningsorderraden. Nettobeloppet räknas om på alla order. |
| Inaktivera direktleverans på en ursprunglig försäljningsorder. | Du kan inte ändra fältet **Direktleverans** på den ursprungliga försäljningsordern om den koncerninterna försäljningsorderraden har nått minimistatusen **Plocklista**, **Utleveransorder** eller **Plocklistejournal**. Leveransadressen på den koncerninterna inköpsordern ändras till standardleveransadressen (standardleveransadress för inköpsorder). De koncerninterna inköpsorderraderna ändras också till standardleveransadress för raderna. Båda synkroniseras sedan till den koncerninterna försäljningsordern och raderna. Leveranstypen på alla rader på den ursprungliga försäljningsordern ändras till **Ingen** och fältet synkroniseras till de koncerninterna inköpsorderraderna. Försäljningsorder för externa leverantörer påverkas inte. Det gör inte heller de ursprungliga försäljningsraderna som är kopplade till inköpsorderrader för externa leverantörer. Leveransdatumet på den koncerninterna inköpsordern och raderna och de begärda datumen för inleverans/skeppning på den koncerninterna försäljningsordern och raderna uppdateras. |
| Aktivera direktleverans på en ursprunglig försäljningsorder. | Om den koncerninterna försäljningsorderraden har nått minimistatusen **Plocklista**, **Utleveransorder** eller **Plocklistejournal**, kan du inte ändra fältet **Direktleverans** på den ursprungliga försäljningsordern. Leveransadressen på den koncerninterna inköpsordern ändras till leveransadressen från den ursprungliga försäljningsordern och synkroniseras med den koncerninterna försäljningsordern. Leveranstypen på alla rader på den ursprungliga försäljningsordern ändras till **Direktleverans** och fältet synkroniseras till de koncerninterna inköpsorderraderna. Leveransadressen på varje ursprunglig försäljningsorderrad synkroniseras med både de koncerninterna inköpsorderraderna och de koncerninterna försäljningsorderraderna. Leveransdatumet på den koncerninterna inköpsordern och raderna och de begärda datumen för inleverans/skeppning på den koncerninterna försäljningsordern och raderna uppdateras. |
| Lägga till en notering till både rubriken och raderna i en ursprunglig försäljningsorder. | Noteringen kopieras till den koncerninterna inköpsordern och den koncerninterna försäljningsordern. |
| Ändra eller radera en notering. | Om du ändrar eller raderar en notering, ändras eller raderas motsvarande notering på den koncerninterna inköpsordern och den koncerninterna försäljningsordern på samma sätt. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
