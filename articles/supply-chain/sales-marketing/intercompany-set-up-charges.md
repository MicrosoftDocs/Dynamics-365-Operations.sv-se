---
title: Ställa in avgifter på koncerninterna order
description: Det här avsnittet innehåller information om hur du ställer in avgifter på koncerninterna order
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3786df5ce185fa8433d7c69bed5bef09b4983b8b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548544"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Ställa in avgifter på koncerninterna order

[!include [banner](../../includes/banner.md)]

Du kan ställa in tillägg kan läggas till för koncerninterna order. När en kostnad läggs till för en koncernintern försäljningsorder, synkroniseras den automatiskt till den koncerninterna inköpsordern. Detta fungerar åt båda håll - från den koncerninterna försäljningsordern till inköpsordern och tvärtom.

Du kan också använda tillägg till att lägga till en vinst i en koncernintern order genom att definiera tillägget som en koncernintern procent.

När du ställer in tillägg som ska användas för koncerninterna order, aktiverar du beräkningen av intern vinst för en koncernintern försäljningsorder från nettobeloppet för den ursprungliga försäljningsordern. Du kanske vill göra detta om din koncerninterna leverantör säljer till dig till självkostnad. Följande procedur beskriver hur du gör detta för koncerninterna kunder. Du kan använda samma procedur för leverantörer.

1. Gå till **Kundreskontra \> Ställa in \> Avgifter \> Tilläggsgrupper för kunder**.
1. Skapa en avgiftsgrupp.
1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**. Välj ett kundkontolänk. I åtgärdsfönstret, välj fliken **Kund** och välj snabbfliken **Försäljningsorder**.
1. Välj **redigering** i åtgärdsfönstret om du vill aktivera redigering i fältet. I fältet **Avgiftsgrupp**, välj den koncerninterna tilläggsgrupp som du angav i steg 2.
1. Gå till **Kundreskontra \> Ställ in \> Avgifter \> Automatiska avgifter**.
1. Ställa in avgifterna genom att fylla i relevanta fält.
1. I fältet **Kundrelation**, välj den koncerninterna tilläggsgrupp som du angav i steg 2.
1. På snabbfliken **Rader** i fältet **Kategori** välj **Koncernintern procent**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
