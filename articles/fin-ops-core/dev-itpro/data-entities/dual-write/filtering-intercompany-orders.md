---
title: Filtrera koncerninterna order för att undvika synkronisering av order och orderrader
description: I det här avsnittet beskrivs hur du filtrerar koncerninterna order så att entiteterna Order och Orderrader inte synkroniseras.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 342db8c1b4337145bfd61f5698ff6de25434a400
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796616"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrera koncerninterna order för att undvika synkronisering av order och orderrader

[!include [banner](../../includes/banner.md)]

Du kan filtrera koncerninterna order så att tabellerna **order** och **orderrader** inte synkroniseras. I vissa fall är inte den koncerninterna orderinformationen nödvändig i kundengagemangsappen.

Alla standardtabeller för Dataverse utökas med referenser till kolumnen **IntercompanyOrder** och mappningar med dubbelriktad skrivning ändras så att de refererar till de ytterligare kolumnerna i filtren. Därför synkroniseras inte längre koncerninterna order. Denna process hjälper till att undvika onödiga data i kundengagemangsappen.

1. Utöka tabellen **CDS-försäljningsorderrubriker** genom att lägga till en referens till kolumnen **IntercompanyOrder**. Den här kolumnen fylls bara i på koncerninterna order. Kolumnen **IntercompanyOrder** finns i tabellen **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa mellanlagring till målsida för CDS-försäljningsorderrubriker":::

2. När **CDS-försäljningsorderrubriker** har utökats är kolumnen **IntercompanyOrder** tillgängligt i mappningen. Använd ett filter med `INTERCOMPANYORDER == ""` som frågesträng.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Redigera frågedialogruta för CDS-försäljningsorderrubriker":::

3. Utöka tabellen **CDS-försäljningsorderrader** genom att lägga till en referens till kolumnen **IntercompanyInventTransId**. Den här kolumnen fylls bara i på koncerninterna order. Kolumnen **InterCompanyInventTransId** finns i tabellen **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mappa mellanlagring till målsida för CDS-försäljningsorderrader":::

4. När **CDS-försäljningsorderrader** har utökats är kolumnen **IntercompanyInventTransId** tillgängligt i mappningen. Använd ett filter med `INTERCOMPANYINVENTTRANSID == ""` som frågesträng.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Redigera frågedialogruta för CDS-försäljningsorderrader":::

5. Upprepa steg 1 och 2 om du vill utöka tabellen **Försäljningsfakturahuvuden V2** och lägga till en filterfråga. I detta fall används `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` du som frågesträng för filtret.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mappa mellanlagring till målsida för försäljningsorderrubrik V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Redigera frågedialogruta för försäljningsorderrubrik V2":::

6. Upprepa steg 3 och 4 om du vill utöka tabellen **Försäljningsfakturarad V2** och lägga till en filterfråga. I detta fall används `INTERCOMPANYINVENTTRANSID == ""` du som frågesträng för filtret.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Redigera frågedialogruta för försäljningsorderrad V2":::

7. Tabellen **Offerter** har ingen koncernintern relation. Om någon skapar en offert för en av dina företagskunder kan du använda kolumnen **CustGroup** för att placera alla dessa kunder i en kundgrupp. Du kan utöka rubriken och raderna genom att lägga till kolumnen **CustGroup** och sedan filtrera så att gruppen inte inkluderas.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mappa mellanlagring till målsida för CDS-försäljningsofferrubrik":::

8. Efter **Offerter** utökas, tillämpa ett filter med `CUSTGROUP != "<company>"` som frågesträng.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Redigera frågedialogruta för CDS-försäljningsofferrubrik":::
