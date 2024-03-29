---
title: Ställa in avgifter på koncerninterna order
description: Denna artikel förklarar hur du konfigurerar avgifter på koncerninterna order
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7b84c0bac6c31139170a99afc65cd08d70bd018e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885853"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Ställa in avgifter på koncerninterna order

[!include [banner](../../includes/banner.md)]

Du kan konfigurera tillägg kan läggas till för koncerninterna order. När en kostnad läggs till för en koncernintern försäljningsorder, synkroniseras den automatiskt till den koncerninterna inköpsordern. Detta fungerar åt båda håll - från den koncerninterna försäljningsordern till inköpsordern och tvärtom.

Du kan också använda tillägg till att lägga till en vinst i en koncernintern order genom att definiera tillägget som en koncernintern procent.

När du konfigurerar tillägg som ska användas för koncerninterna order, aktiverar du beräkningen av intern vinst för en koncernintern försäljningsorder från nettobeloppet för den ursprungliga försäljningsordern. Du kanske vill göra detta om din koncerninterna leverantör säljer till dig till självkostnad. Följande procedur beskriver hur du gör detta för koncerninterna kunder. Du kan använda samma procedur för leverantörer.

1. Gå till **Kundreskontra \> Ställa in \> Avgifter \> Tilläggsgrupper för kunder**.
1. Skapa en avgiftsgrupp.
1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**. Välj ett kundkontolänk. I åtgärdsfönstret, välj fliken **Kund** och välj snabbfliken **Försäljningsorder**.
1. Välj **redigering** i åtgärdsfönstret om du vill aktivera redigering i fältet. I fältet **Avgiftsgrupp**, välj den koncerninterna tilläggsgrupp som du angav i steg 2.
1. Gå till **Kundreskontra \> Ställ in \> Avgifter \> Automatiska avgifter**.
1. Ställa in avgifterna genom att fylla i relevanta fält.
1. I fältet **Kundrelation**, välj den koncerninterna tilläggsgrupp som du angav i steg 2.
1. På snabbfliken **Rader** i fältet **Kategori** välj **Koncernintern procent**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
