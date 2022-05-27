---
title: Koncerninterna följesedlar
description: I det här avsnittet beskrivs hur du skapar och skriver ut följesedlar för koncerninterna transaktioner
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
ms.openlocfilehash: ca569ca7eb2a3ced36904442212bde565f499f94
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678643"
---
# <a name="intercompany-packing-slips"></a>Koncerninterna följesedlar

## <a name="generate-intercompany-packing-slips"></a>Generera koncerninterna följesedlar

[!include [banner](../../includes/banner.md)]

Om du arbetar med direktleverans genereras alltid följesedeln automatiskt på både den koncerninterna inköpsordern och på den ursprungliga säljordern när du genererar följesedeln på den koncerninterna försäljningsordern. Den koncerinterna inköpsorderfakturan baseras på följesedeln för den koncerninterna inköpsorder som genereras tidigare.

Om du gör några uppdateringar av följesedeln på den koncerninterna försäljningsordern återspeglas dessa uppdateringar både på den koncerninterna inköpsordern och den ursprungliga försäljningsordern.

Om du inte arbetar med direktleverans måste du manuellt generera följesedeln på den koncerninterna försäljningsordern, på den koncerninterna inköpsordern och på den ursprungliga försäljningsordern.

## <a name="print-intercompany-packing-slips"></a>Skriv ut koncerninterna följesedlar

[!include [banner](../../includes/banner.md)]

Om du arbetar med direktleverans kan följesedeln skrivas ut automatiskt för den koncerninterna inköpsordern och den ursprungliga försäljningsordern när du bokför följesedeln på den koncerninterna försäljningsordern.

Om du vill skriva ut följesedlar automatiskt väljer du på sidan **Koncernintern** för inköpsorder båda fälten för **Skriv ut följesedel automatiskt**.

Om du uppdaterar följesedeln på den koncerninterna försäljningsordern återspeglas ändringarna automatiskt på den koncerninterna inköpsordern och den ursprungliga försäljningsordern.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
