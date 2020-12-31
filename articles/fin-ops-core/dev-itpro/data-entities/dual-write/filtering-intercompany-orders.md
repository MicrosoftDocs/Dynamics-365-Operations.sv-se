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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="9ff37-103">Filtrera koncerninterna order för att undvika synkronisering av order och orderrader</span><span class="sxs-lookup"><span data-stu-id="9ff37-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ff37-104">Du kan filtrera koncerninterna order för att undvika synkronisering av entiteter i **order** och **orderrader**.</span><span class="sxs-lookup"><span data-stu-id="9ff37-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="9ff37-105">I vissa fall är inte den koncerninterna orderinformationen nödvändig i kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="9ff37-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="9ff37-106">Alla standardentiteter för Common Data Service utökas med referenser till **IntercompanyOrder** och mappningar med dubbelriktad skrivning ändras så att de refererar till de ytterligare fälten i filtren.</span><span class="sxs-lookup"><span data-stu-id="9ff37-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="9ff37-107">Resultatet blir att koncerninterna order inte längre synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="9ff37-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="9ff37-108">Denna process undviker onödiga data i kundengagemangsappen.</span><span class="sxs-lookup"><span data-stu-id="9ff37-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="9ff37-109">Lägg till en referens till **IntercompanyOrder** på **CDS-försäljningsorderrubriker**.</span><span class="sxs-lookup"><span data-stu-id="9ff37-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="9ff37-110">Den fylls endast i för koncerninterna order.</span><span class="sxs-lookup"><span data-stu-id="9ff37-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="9ff37-111">Fältet **IntercompanyOrder** finns i **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="9ff37-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mappa mellanlagring till mål, SalesOrderHeader":::
    
2. <span data-ttu-id="9ff37-113">När **CDS-försäljningsorderrubriker** har utökats är fältet **IntercompanyOrder** tillgängligt i mappningen.</span><span class="sxs-lookup"><span data-stu-id="9ff37-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="9ff37-114">Använd ett filter med `INTERCOMPANYORDER == ""` som frågesträng.</span><span class="sxs-lookup"><span data-stu-id="9ff37-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Försäljningsorderrubriker, redigera fråga":::

3. <span data-ttu-id="9ff37-116">Lägg till en referens till **IntercompanyInventTransId** för **CDS-försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="9ff37-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="9ff37-117">Den fylls endast i för koncerninterna order.</span><span class="sxs-lookup"><span data-stu-id="9ff37-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="9ff37-118">Fältet **InterCompanyInventTransID** finns i **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="9ff37-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mappa mellanlagring till mål, SalesOrderLine":::

4. <span data-ttu-id="9ff37-120">När **CDS-försäljningsorderrader** har utökats är fältet **IntercompanyInventTransId** tillgängligt i mappningen.</span><span class="sxs-lookup"><span data-stu-id="9ff37-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="9ff37-121">Använd ett filter med `INTERCOMPANYINVENTTRANSID == ""` som frågesträng.</span><span class="sxs-lookup"><span data-stu-id="9ff37-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Försäljningsorderrader, redigera fråga":::

5. <span data-ttu-id="9ff37-123">Utvidga **Försäljningsfakturahuvuden V2** och **Försäljningsfakturarader V2** på samma sätt som du utökade Common Data Service-entiteterna i steg 1 och 2.</span><span class="sxs-lookup"><span data-stu-id="9ff37-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="9ff37-124">Lägg sedan till filterfrågorna.</span><span class="sxs-lookup"><span data-stu-id="9ff37-124">Then add the filter queries.</span></span> <span data-ttu-id="9ff37-125">Filtersträngen för **Försäljningsfakturahuvuden V2** är `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="9ff37-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="9ff37-126">Filtersträngen för **Försäljningsfakturarader V2** är `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="9ff37-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mappa mellanlagring till mål, Försäljningsfakturahuvuden":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Försäljningsfakturahuvuden, redigera fråga":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Försäljningsfakturarader, redigera fråga":::

6. <span data-ttu-id="9ff37-130">Entiteten **Offerter** har ingen koncernintern relation.</span><span class="sxs-lookup"><span data-stu-id="9ff37-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="9ff37-131">Om någon skapar en offert för någon av dina koncerninterna kunder kan du placera alla dessa kunder i en kundgrupp genom att använda fältet **CustGroup**.</span><span class="sxs-lookup"><span data-stu-id="9ff37-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="9ff37-132">Huvud och rader kan utökas om du vill lägga till fältet **CustGroup** och sedan filtrera för att inte inkludera den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="9ff37-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mappa mellanlagring till mål, Försäljningsofferthuvud":::

7. <span data-ttu-id="9ff37-134">När du har utökat entiteten **Offerter** använder du ett filter med `CUSTGROUP !=  "<company>"` som frågesträng.</span><span class="sxs-lookup"><span data-stu-id="9ff37-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Försäljningsofferthuvud, redigera fråga":::
