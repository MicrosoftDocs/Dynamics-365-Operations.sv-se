---
title: Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsfakturahuvud och rader direkt från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: fa2772db63332319c399999bd5f747b2ac729d9e
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653285"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="d49c1-103">Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="d49c1-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d49c1-104">I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsfakturahuvud och rader direkt från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="d49c1-105">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="d49c1-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="d49c1-106">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="d49c1-107">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="d49c1-108">Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-108">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="d49c1-109">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="d49c1-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d49c1-110">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="d49c1-110">Templates and tasks</span></span>

<span data-ttu-id="d49c1-111">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="d49c1-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="d49c1-112">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="d49c1-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="d49c1-113">Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader i försäljningsfakturor direkt i försäljningsofferter från Supply Chain Management till Sales:</span><span class="sxs-lookup"><span data-stu-id="d49c1-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Supply Chain Management to Sales:</span></span>

- <span data-ttu-id="d49c1-114">**Namnet på mallen i dataintegrering:** försäljningsfaktura (Fin and Ops till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="d49c1-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="d49c1-115">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="d49c1-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="d49c1-116">Rubrik på försäljningsfakturan</span><span class="sxs-lookup"><span data-stu-id="d49c1-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="d49c1-117">Rad i försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="d49c1-117">SalesInvoiceLine</span></span>

<span data-ttu-id="d49c1-118">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsfakturor kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="d49c1-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="d49c1-119">Produkter (Supply Chain Management till Sales) - direkt</span><span class="sxs-lookup"><span data-stu-id="d49c1-119">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="d49c1-120">Konton (Sales till Supply Chain Management)-direkt (om den används)</span><span class="sxs-lookup"><span data-stu-id="d49c1-120">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="d49c1-121">Kontakter (Sales till Supply Chain Management)-direkt (om den används)</span><span class="sxs-lookup"><span data-stu-id="d49c1-121">Contacts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="d49c1-122">Rubrik och rader i försäljningsfaktura (Supply Chain Management till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="d49c1-122">Sales order header and lines (Supply Chain Management to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="d49c1-123">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="d49c1-123">Entity set</span></span>

| <span data-ttu-id="d49c1-124">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="d49c1-124">Supply Chain Management</span></span>                              | <span data-ttu-id="d49c1-125">Försäljning</span><span class="sxs-lookup"><span data-stu-id="d49c1-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="d49c1-126">Huvuden för kundförsäljningsfakturor som underhålls externt</span><span class="sxs-lookup"><span data-stu-id="d49c1-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="d49c1-127">Fakturor</span><span class="sxs-lookup"><span data-stu-id="d49c1-127">Invoices</span></span>       |
| <span data-ttu-id="d49c1-128">Rader för kundförsäljningsfakturor som underhålls externt</span><span class="sxs-lookup"><span data-stu-id="d49c1-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="d49c1-129">Fakturainformation</span><span class="sxs-lookup"><span data-stu-id="d49c1-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="d49c1-130">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="d49c1-130">Entity flow</span></span>

<span data-ttu-id="d49c1-131">Försäljningsfakturor skapas i Supply Chain Management och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-131">Sales invoices are created in Supply Chain Management and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="d49c1-132">För närvarande ingår moms relaterad till avgifter i försäljningsfakturarubriken inte i synkroniseringen från Supply Chain Management till Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Supply Chain Managements to Sales.</span></span> <span data-ttu-id="d49c1-133">Sales stöder itne skatteinformation på rubriknivå.</span><span class="sxs-lookup"><span data-stu-id="d49c1-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="d49c1-134">Moms som är relaterad till tillägg på radnivå ingår emellertid i synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="d49c1-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d49c1-135">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="d49c1-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="d49c1-136">Ett fält för **fakturanummer** har lagts till i entiteten **Faktura** och visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="d49c1-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="d49c1-137">Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Supply Chain Management och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="d49c1-138">Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d49c1-138">The **Invoice** page can't be edited, because invoices will be synchronized from Supply Chain Management.</span></span>
- <span data-ttu-id="d49c1-139">Värdet **Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Supply Chain Management har synkroniserats med Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Supply Chain Management has been synchronized to Sales.</span></span> <span data-ttu-id="d49c1-140">Dessutom kan ägaren till den försäljningsorder som fakturan skapades från tilldelas till fakturaägaren.</span><span class="sxs-lookup"><span data-stu-id="d49c1-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="d49c1-141">Därför kan ägaren till försäljningsordern kan visa fakturan.</span><span class="sxs-lookup"><span data-stu-id="d49c1-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d49c1-142">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d49c1-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="d49c1-143">Innan du synkroniserar försäljningsfakturor är det viktigt att du uppdaterar följande inställningar i systemen.</span><span class="sxs-lookup"><span data-stu-id="d49c1-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="d49c1-144">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="d49c1-144">Setup in Sales</span></span>

<span data-ttu-id="d49c1-145">Gå till **inställningar** > **Administration** > **systeminställningar** > **Sales** och säkerställ att följande inställningar används:</span><span class="sxs-lookup"><span data-stu-id="d49c1-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="d49c1-146">Alternativet **Använd systemets prisberäkningssystem** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d49c1-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="d49c1-147">Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.</span><span class="sxs-lookup"><span data-stu-id="d49c1-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="d49c1-148">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="d49c1-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="d49c1-149">Rubrikuppgift på försäljningsfakturan</span><span class="sxs-lookup"><span data-stu-id="d49c1-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="d49c1-150">Kontrollera att nödvändig mappning finns i **InvoiceCountryRegionId** till **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="d49c1-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="d49c1-151">Mallvärdet är en värdemappning där flera länder eller regioner som mappas.</span><span class="sxs-lookup"><span data-stu-id="d49c1-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="d49c1-152">En prislista krävs för att skapa fakturor i Sales.</span><span class="sxs-lookup"><span data-stu-id="d49c1-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="d49c1-153">Uppdatera värdemappen för **pricelevelid.name \[Price list name\]** till den prislista som används i Sales efter valuta.</span><span class="sxs-lookup"><span data-stu-id="d49c1-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="d49c1-154">Du kan använda standardprislistan för en enda valuta.</span><span class="sxs-lookup"><span data-stu-id="d49c1-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="d49c1-155">Om du har prislistor i flera valutor kan du använda en värdekarta.</span><span class="sxs-lookup"><span data-stu-id="d49c1-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="d49c1-156">Mallvärdet för **pricelevelid.name \[prislistans namn\]** är en värdemappning som baseras på valuta med USD = CRM Service USA (exempel).</span><span class="sxs-lookup"><span data-stu-id="d49c1-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="d49c1-157">Raduppgift i försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="d49c1-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="d49c1-158">Kontrollera att nödvändig mappning finns i **Måttenhet**.</span><span class="sxs-lookup"><span data-stu-id="d49c1-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="d49c1-159">Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d49c1-159">Make sure that the required value map for **SalesUnitSymbol** in Supply Chain Management exists.</span></span>

    <span data-ttu-id="d49c1-160">En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **Antal\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="d49c1-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d49c1-161">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="d49c1-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="d49c1-162">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="d49c1-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="d49c1-163">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="d49c1-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="d49c1-164">I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="d49c1-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="d49c1-165">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d49c1-165">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="d49c1-166">Rubrik på försäljningsfakturan</span><span class="sxs-lookup"><span data-stu-id="d49c1-166">SalesInvoiceHeader</span></span>

![Mallmappning i dataintegrering](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="d49c1-168">Rad i försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="d49c1-168">SalesInvoiceLine</span></span>

![Mallmappning i dataintegrering](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="d49c1-170">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d49c1-170">Related topics</span></span>

[<span data-ttu-id="d49c1-171">Prospekt till kontanter</span><span class="sxs-lookup"><span data-stu-id="d49c1-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="d49c1-172">Synkronisera konton direkt från Sales till kunder i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d49c1-172">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="d49c1-173">Synkronisera produkter direkt från Supply Chain Management till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="d49c1-173">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="d49c1-174">Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d49c1-174">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="d49c1-175">Synkronisera försäljningsorderrubrik och rader i försäljningsfakturor direkt från Supply Chain Management till Sales</span><span class="sxs-lookup"><span data-stu-id="d49c1-175">Synchronize sales order headers and lines directly from Supply Chain Management to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)
