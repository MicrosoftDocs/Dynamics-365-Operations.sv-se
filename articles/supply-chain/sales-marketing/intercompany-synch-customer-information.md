---
title: Synkronisera koncernintern kundinformation
description: I det här avsnittet beskrivs synkronisering av kundinformation för koncerninterna order
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
ms.openlocfilehash: c82216c8391f6c447bec74f25cd16b9db18d468d
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548543"
---
# <a name="synchronize-intercompany-customer-information"></a>Synkronisera koncernintern kundinformation

[!include [banner](../../includes/banner.md)]

Kundinformation synkroniseras om fältet **Kundinformation** är aktiverat när försäljningsordern skapas eller när kunden, leverantörsreferensen eller kundrekvisitionsnumret ändras.

Du kan alltid ändra värdet i dessa synkroniseringsfält. Du kan dock bara avgöra om det här värdet kopieras till andra koncerninterna order genom att välja den här parametern. Om du har aktiverat fältet **Kundinformation** på den koncerninterna försäljningsordern synkroniseras en ändring av den koncerninterna försäljningsordern till den koncerninterna inköpsordern. Om du också har aktiverat fältet **Kundinformation** på den koncerninterna inköpsordern synkroniseras den också tillbaka till den ursprungliga försäljningsordern.

> [!NOTE]
> Om du har aktiverat fältet **Kundinformation** på både den koncerninterna inköpsordern och den koncerninterna försäljningsordern åsidosätts uppdateringar som görs av en person i företaget av uppdateringar i samma order som görs av en annan person i företaget.

Det är det bästa sättet att aktivera fältet **Kundinformation** på den koncerninterna inköpsordern. Detta aktiverar synkronisering mellan den ursprungliga försäljningsordern och den koncerninterna inköpsordern och från den koncerninterna inköpsordern till den koncerninterna försäljningsordern.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
