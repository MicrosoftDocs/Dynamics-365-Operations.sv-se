---
title: Filtrera koncerninterna order för att undvika synkronisering av order och orderrader
description: Avsnittet beskriver hur du filtrerar koncerninterna order för att undvika synkronisering av order och orderrader.
author: negudava
manager: tfehr
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701043"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Filtrera koncerninterna order för att undvika synkronisering av order och orderrader

[!include [banner](../../includes/banner.md)]

Du kan filtrera koncerninterna order för att undvika synkronisering av entiteter i **order** och **orderrader**. I vissa fall är inte den koncerninterna orderinformationen nödvändig i kundengagemangsappen.

Alla standardentiteter för Common Data Service utökas med referenser till **IntercompanyOrder** och mappningar med dubbelriktad skrivning ändras så att de refererar till de ytterligare fälten i filtren. Resultatet blir att koncerninterna order inte längre synkroniseras. Denna process undviker onödiga data i kundengagemangsappen.

1. Lägg till en referens till **IntercompanyOrder** på **CDS-försäljningsorderrubriker**. Den fylls endast i för koncerninterna order. Fältet **IntercompanyOrder** finns i **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa mellanlagring till mål, SalesOrderHeader":::
    
2. När **CDS-försäljningsorderrubriker** har utökats är fältet **IntercompanyOrder** tillgängligt i mappningen. Använd ett filter med `INTERCOMPANYORDER == ""` som frågesträng.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Försäljningsorderrubriker, redigera fråga":::

3. Lägg till en referens till **IntercompanyInventTransId** för **CDS-försäljningsorderrader**.  Den fylls endast i för koncerninterna order. Fältet **InterCompanyInventTransID** finns i **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mappa mellanlagring till mål, SalesOrderLine":::

4. När **CDS-försäljningsorderrader** har utökats är fältet **IntercompanyInventTransId** tillgängligt i mappningen. Använd ett filter med `INTERCOMPANYINVENTTRANSID == ""` som frågesträng.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Försäljningsorderrader, redigera fråga":::

5. Utvidga **Försäljningsfakturahuvuden V2** och **Försäljningsfakturarader V2** på samma sätt som du utökade Common Data Service-entiteterna i steg 1 och 2. Lägg sedan till filterfrågorna. Filtersträngen för **Försäljningsfakturahuvuden V2** är `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. Filtersträngen för **Försäljningsfakturarader V2** är `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mappa mellanlagring till mål, Försäljningsfakturahuvuden":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Försäljningsfakturahuvuden, redigera fråga":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Försäljningsfakturarader, redigera fråga":::

6. Entiteten **Offerter** har ingen koncernintern relation. Om någon skapar en offert för någon av dina koncerninterna kunder kan du placera alla dessa kunder i en kundgrupp genom att använda fältet **CustGroup**.  Huvud och rader kan utökas om du vill lägga till fältet **CustGroup** och sedan filtrera för att inte inkludera den här gruppen.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mappa mellanlagring till mål, Försäljningsofferthuvud":::

7. När du har utökat entiteten **Offerter** använder du ett filter med `CUSTGROUP !=  "<company>"` som frågesträng.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Försäljningsofferthuvud, redigera fråga":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]