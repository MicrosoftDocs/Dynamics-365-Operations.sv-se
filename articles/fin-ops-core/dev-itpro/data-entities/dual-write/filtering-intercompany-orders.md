---
title: Filtrera koncerninterna order för att undvika synkronisering av order och orderrader
description: I det här avsnittet beskrivs hur du filtrerar koncerninterna order så att entiteterna Order och Orderrader inte synkroniseras.
author: negudava
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 123427db61782490d348489c23e0eaf5f8b513c9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748651"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="dfc12-103">Filtrera koncerninterna order för att undvika synkronisering av order och orderrader</span><span class="sxs-lookup"><span data-stu-id="dfc12-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dfc12-104">Du kan filtrera koncerninterna order så att tabellerna **order** och **orderrader** inte synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="dfc12-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="dfc12-105">I vissa fall är inte den koncerninterna orderinformationen nödvändig i kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="dfc12-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="dfc12-106">Alla standardtabeller för Dataverse utökas med referenser till kolumnen **IntercompanyOrder** och mappningar med dubbelriktad skrivning ändras så att de refererar till de ytterligare kolumnerna i filtren.</span><span class="sxs-lookup"><span data-stu-id="dfc12-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="dfc12-107">Därför synkroniseras inte längre koncerninterna order.</span><span class="sxs-lookup"><span data-stu-id="dfc12-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="dfc12-108">Denna process hjälper till att undvika onödiga data i kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="dfc12-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="dfc12-109">Utöka tabellen **CDS-försäljningsorderrubriker** genom att lägga till en referens till kolumnen **IntercompanyOrder**.</span><span class="sxs-lookup"><span data-stu-id="dfc12-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="dfc12-110">Den här kolumnen fylls bara i på koncerninterna order.</span><span class="sxs-lookup"><span data-stu-id="dfc12-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="dfc12-111">Kolumnen **IntercompanyOrder** finns i tabellen **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="dfc12-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa mellanlagring till målsida för CDS-försäljningsorderrubriker":::

2. <span data-ttu-id="dfc12-113">När **CDS-försäljningsorderrubriker** har utökats är kolumnen **IntercompanyOrder** tillgängligt i mappningen.</span><span class="sxs-lookup"><span data-stu-id="dfc12-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="dfc12-114">Använd ett filter med `INTERCOMPANYORDER == ""` som frågesträng.</span><span class="sxs-lookup"><span data-stu-id="dfc12-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Redigera frågedialogruta för CDS-försäljningsorderrubriker":::

3. <span data-ttu-id="dfc12-116">Utöka tabellen **CDS-försäljningsorderrader** genom att lägga till en referens till kolumnen **IntercompanyInventTransId**.</span><span class="sxs-lookup"><span data-stu-id="dfc12-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="dfc12-117">Den här kolumnen fylls bara i på koncerninterna order.</span><span class="sxs-lookup"><span data-stu-id="dfc12-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="dfc12-118">Kolumnen **InterCompanyInventTransId** finns i tabellen **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="dfc12-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mappa mellanlagring till målsida för CDS-försäljningsorderrader":::

4. <span data-ttu-id="dfc12-120">När **CDS-försäljningsorderrader** har utökats är kolumnen **IntercompanyInventTransId** tillgängligt i mappningen.</span><span class="sxs-lookup"><span data-stu-id="dfc12-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="dfc12-121">Använd ett filter med `INTERCOMPANYINVENTTRANSID == ""` som frågesträng.</span><span class="sxs-lookup"><span data-stu-id="dfc12-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Redigera frågedialogruta för CDS-försäljningsorderrader":::

5. <span data-ttu-id="dfc12-123">Upprepa steg 1 och 2 om du vill utöka tabellen **Försäljningsfakturahuvuden V2** och lägga till en filterfråga.</span><span class="sxs-lookup"><span data-stu-id="dfc12-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="dfc12-124">I detta fall används `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` du som frågesträng för filtret.</span><span class="sxs-lookup"><span data-stu-id="dfc12-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mappa mellanlagring till målsida för försäljningsorderrubrik V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Redigera frågedialogruta för försäljningsorderrubrik V2":::

6. <span data-ttu-id="dfc12-127">Upprepa steg 3 och 4 om du vill utöka tabellen **Försäljningsfakturarad V2** och lägga till en filterfråga.</span><span class="sxs-lookup"><span data-stu-id="dfc12-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="dfc12-128">I detta fall används `INTERCOMPANYINVENTTRANSID == ""` du som frågesträng för filtret.</span><span class="sxs-lookup"><span data-stu-id="dfc12-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Redigera frågedialogruta för försäljningsorderrad V2":::

7. <span data-ttu-id="dfc12-130">Tabellen **Offerter** har ingen koncernintern relation.</span><span class="sxs-lookup"><span data-stu-id="dfc12-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="dfc12-131">Om någon skapar en offert för en av dina företagskunder kan du använda kolumnen **CustGroup** för att placera alla dessa kunder i en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="dfc12-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="dfc12-132">Du kan utöka rubriken och raderna genom att lägga till kolumnen **CustGroup** och sedan filtrera så att gruppen inte inkluderas.</span><span class="sxs-lookup"><span data-stu-id="dfc12-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mappa mellanlagring till målsida för CDS-försäljningsofferrubrik":::

8. <span data-ttu-id="dfc12-134">Efter **Offerter** utökas, tillämpa ett filter med `CUSTGROUP != "<company>"` som frågesträng.</span><span class="sxs-lookup"><span data-stu-id="dfc12-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Redigera frågedialogruta för CDS-försäljningsofferrubrik":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]