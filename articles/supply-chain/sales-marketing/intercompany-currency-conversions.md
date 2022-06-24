---
title: Konverteringar av koncernintern valuta
description: Denna artikel innehåller information om valutakonverteringar för koncerninterna transaktioner
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 41bfafc0dcb3bd356931b67dc63b717c0d098116
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851490"
---
# <a name="intercompany-currency-conversions"></a>Konverteringar av koncernintern valuta

[!include [banner](../../includes/banner.md)]

När det finns en differens mellan valutakoden på den ursprungliga försäljningsordern och den koncernintern a inköpsordern konverteras valutan i följande fält:

- **Enhetspris**
- **Försäljningsavgifter** eller **Avgifter på inköp**
- **Rabatt**
- **Samköpsrabatt**

Dessa fält synkroniseras sedan till den koncerninterna försäljningsordern.

Eftersom valutan på koncerninterna inköpsorder och koncerninterna försäljningsorder alltid synkroniseras kommer följande fält att synkroniseras utan att valutan konverteras:

- **Enhetspris**
- **Försäljningsavgifter** eller **Avgifter på inköp**
- **Rabatt**
- **Rabatt i procent**
- **Samköpsrabatt**
- **Samköpsrabatt i procent**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
