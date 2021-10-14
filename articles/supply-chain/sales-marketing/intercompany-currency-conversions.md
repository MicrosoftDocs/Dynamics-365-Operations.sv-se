---
title: Konverteringar av koncernintern valuta
description: Det här ämnet innehåller information om valutakonverteringar för koncerninterna transaktioner.
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
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548548"
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
