---
title: Filtrera koncerninterna order för att undvika synkronisering av order och orderrader
description: I det här avsnittet beskrivs hur du filtrerar koncerninterna order så att entiteterna Order och Orderrader inte synkroniseras.
author: negudava
ms.date: 11/09/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: negudava
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8575f38ca23ef245947a41c35846983604662ef2
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782563"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrera koncerninterna order för att undvika synkronisering av order och orderrader

[!include [banner](../../includes/banner.md)]

Du kan filtrera koncerninterna order så att tabellerna **order** och **orderrader** inte synkroniseras. I vissa fall är inte den koncerninterna orderinformationen nödvändig i kundengagemangsappen.

Alla standardtabeller för Dataverse utökas med referenser till kolumnen **IntercompanyOrder** och mappningar med dubbelriktad skrivning ändras så att de refererar till de ytterligare kolumnerna i filtren. Därför synkroniseras inte längre koncerninterna order. Denna process hjälper till att undvika onödiga data i kundengagemangsappen.

1. Utöka tabellen **CDS-försäljningsorderrubriker** genom att lägga till en referens till kolumnen **IntercompanyOrder**. Den här kolumnen fylls bara i på koncerninterna order. Kolumnen **IntercompanyOrder** finns i tabellen **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa mellanlagring till mål för CDS-försäljningsorderrubriker.":::

2. När **CDS-försäljningsorderrubriker** har utökats är kolumnen **IntercompanyOrder** tillgängligt i mappningen. Använd ett filter med `INTERCOMPANYORDER == ""` som frågesträng.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Redigera frågedialogruta för CDS-försäljningsorderrubriker.":::

3. Utöka tabellen **CDS-försäljningsorderrader** genom att lägga till en referens till kolumnen **IntercompanyInventTransId**. Den här kolumnen fylls bara i på koncerninterna order. Kolumnen **InterCompanyInventTransId** finns i tabellen **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Sida för mappning av mellanlagring till mål för CDS-försäljningsorderrader.":::

4. När **CDS-försäljningsorderrader** har utökats är kolumnen **IntercompanyInventTransId** tillgängligt i mappningen. Använd ett filter med `INTERCOMPANYINVENTTRANSID == ""` som frågesträng.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Redigera frågedialogruta för CDS-försäljningsorderrader.":::

5. Upprepa steg 1 och 2 om du vill utöka tabellen **Försäljningsfakturahuvuden V2** och lägga till en filterfråga. I detta fall används `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` du som frågesträng för filtret.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Sidan Mappa mellanlagring till mål för försäljningsorderrubrik V2.":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Redigera frågedialogruta för försäljningsorderrubrik V2.":::

6. Upprepa steg 3 och 4 om du vill utöka tabellen **Försäljningsfakturarad V2** och lägga till en filterfråga. I detta fall används `INTERCOMPANYINVENTTRANSID == ""` du som frågesträng för filtret.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Redigera frågedialogruta för försäljningsorderrad V2.":::

7. Tabellen **Offerter** har ingen koncernintern relation. Om någon skapar en offert för en av dina företagskunder kan du använda kolumnen **CustGroup** för att placera alla dessa kunder i en kundgrupp. Du kan utöka rubriken och raderna genom att lägga till kolumnen **CustGroup** och sedan filtrera så att gruppen inte inkluderas.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Sidan Mappa mellanlagring till mål för CDS-försäljningsoffertrubrik.":::

8. Efter **Offerter** utökas, tillämpa ett filter med `CUSTGROUP != "<company>"` som frågesträng.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Redigera frågedialogruta för CDS-försäljningsoffertrubrik.":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]