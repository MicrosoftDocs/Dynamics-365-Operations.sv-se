---
title: Synkronisera koncerninterna priser och rabatter
description: Det här ämnet förklarar synkronisering av priser och rabatter för koncerninterna försäljningsorder och inköpsorder
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
ms.openlocfilehash: a9467e8d06a44cfaab9e3c8ea3944675c3eb8fb5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548529"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Synkronisera koncerninterna priser och rabatter

[!include [banner](../../includes/banner.md)]

Rabatter och priser synkroniseras alltid mellan den koncerninterna försäljningsordern och den koncerninterna inköpsordern. Du kan också synkronisera priset och rabatterna till/från den ursprungliga försäljningsordern så att alla order har samma priser och rabatter. Det gör du från sidan **Koncernintern** som kan nås från fliken **Allmänt** på listsidan **Alla kunder** antingen från **Försäljning och marknadsföring** eller **Anskaffning och källa**.

Fältet **Pris och rabatt** synkroniseras till raden i den koncerninterna försäljningsordern. Det innebär att du, genom att välja fälten **Tillåt prisredigering** och **Tillåt rabattredigering** har tillåtit en förändring mellan den koncerninterna försäljningsordern och den koncerninterna inköpsordern. En förändring av priset per enhet, prisenheten eller försäljningsavgiften på den koncerninterna försäljningsordern avgör priset på raden i den koncerninterna inköpsordern.

Om fälten **Tillåt prisredigering** och **Tillåt rabattredigering** är aktiverade på den koncerninterna försäljningsordern eller den koncerninterna inköpsordern kan du ändra priset eller rabatten manuellt på någon av orderna. Annars kan du inte.

Om fälten **Tillåt prisredigering** och **Tillåt rabattredigering** är aktiverade på den koncerninterna försäljningsordern du kan inte göra en manuell ändring av priset (eller avgifterna) eller rabatten på en koncernintern försäljningsorder.

Om fälten **Tillåt prisredigering** och **Tillåt rabattredigering** är aktiverade på den koncerninterna inköpsordern du kan inte göra en manuell ändring av priset (eller avgifterna) eller rabatten på en koncernintern inköpsorder.

Om fälten **Tillåt prisredigering** och **Tillåt rabattredigering** är aktiverade på både koncerninterna inköpsordern och koncerninterna försäljningsordern, du kan göra manuella ändringar på båda order. Detta kan dock leda till en situation där uppdateringar som görs av en person åsidosätts av uppdateringar som görs av en annan person i ett annat företag i samma order.

> [!NOTE]
> Om du har aktiverat fältet **Pris och rabatt** på både den koncerninterna inköpsordern och den koncerninterna försäljningsordern kan du inte styra över priserna.

För att undvika sådana här konflikter är det säkrast att endast tillåta att priser och rabatter ändras på den koncerninterna försäljningsordern eller den koncerninterna inköpsordern. Det gör du genom att aktivera fälten **Tillåt prisredigering** och **Tillåt rabattredigering** på någon av dessa order.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
