---
title: "Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales"
description: "Avsnittet diskuterar de mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsfakturor mellan Microsoft Dynamics 365 for Finance and Operations, Enterprise edition och Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="65b36-103">Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="65b36-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="65b36-104">Avsnittet diskuterar de mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsfakturor mellan Microsoft Dynamics 365 for Finance and Operations, Enterprise edition och Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="65b36-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="65b36-105">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="65b36-105">Templates and tasks</span></span>

<span data-ttu-id="65b36-106">Följande mallar och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsfakturor mellan Finance and Operations och Sales:</span><span class="sxs-lookup"><span data-stu-id="65b36-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="65b36-107">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="65b36-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="65b36-108">Försäljningsfakturor (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="65b36-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="65b36-109">**Namnen på uppgifterna i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="65b36-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="65b36-110">Rubrik på försäljningsfakturan</span><span class="sxs-lookup"><span data-stu-id="65b36-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="65b36-111">Rad i försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="65b36-111">SalesInvoiceLine</span></span>

<span data-ttu-id="65b36-112">Synkronisera uppgifter som krävs före synkronisering av rubrik och rader i försäljningsfaktura:</span><span class="sxs-lookup"><span data-stu-id="65b36-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="65b36-113">Produkter (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="65b36-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="65b36-114">Konton (Sales till Fin and Ops) (vid behov)</span><span class="sxs-lookup"><span data-stu-id="65b36-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="65b36-115">Kontakter (Sales till Fin and Ops) (vid behov)</span><span class="sxs-lookup"><span data-stu-id="65b36-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="65b36-116">Rubrik och rader i försäljningsfaktura (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="65b36-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="65b36-117">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="65b36-117">Entity set</span></span>

| <span data-ttu-id="65b36-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65b36-118">Finance and Operations</span></span>                               | <span data-ttu-id="65b36-119">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="65b36-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="65b36-120">Försäljning</span><span class="sxs-lookup"><span data-stu-id="65b36-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="65b36-121">Huvuden för kundförsäljningsfakturor som underhålls externt</span><span class="sxs-lookup"><span data-stu-id="65b36-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="65b36-122">Försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="65b36-122">SalesInvoice</span></span>     | <span data-ttu-id="65b36-123">Fakturor</span><span class="sxs-lookup"><span data-stu-id="65b36-123">Invoices</span></span>       |
| <span data-ttu-id="65b36-124">Rader för kundförsäljningsfakturor som underhålls externt</span><span class="sxs-lookup"><span data-stu-id="65b36-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="65b36-125">Rad i försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="65b36-125">SalesInvoiceLine</span></span> | <span data-ttu-id="65b36-126">Fakturainformation</span><span class="sxs-lookup"><span data-stu-id="65b36-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="65b36-127">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="65b36-127">Entity flow</span></span>

<span data-ttu-id="65b36-128">Försäljningsfakturor skapas i Finance and Operations och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="65b36-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="65b36-129">Skatter relaterade till **försäljningsfakturans rubrik** ingår i nuläget inte i synkroniseringen mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="65b36-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="65b36-130">Anledningen till det är att Sales inte stöder skatteinformation på rubriknivå.</span><span class="sxs-lookup"><span data-stu-id="65b36-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="65b36-131">Skatter som berör avgifter på radnivå är inkluderade.</span><span class="sxs-lookup"><span data-stu-id="65b36-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="65b36-132">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="65b36-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="65b36-133">Ett **fält för fakturanummer** läggs till i entiteten **Faktura** och visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="65b36-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="65b36-134">Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="65b36-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="65b36-135">Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65b36-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="65b36-136">**Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Finance and Operations har synkroniserats med Sales.</span><span class="sxs-lookup"><span data-stu-id="65b36-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="65b36-137">Ägaren till den försäljningsorder som fakturan skapades ur görs dessutom till fakturaägare.</span><span class="sxs-lookup"><span data-stu-id="65b36-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="65b36-138">Detta ger försäljningsfakturans ägare möjlighet att granska fakturan.</span><span class="sxs-lookup"><span data-stu-id="65b36-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="65b36-139">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="65b36-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="65b36-140">Innan du synkroniserar försäljningsfakturor är det viktigt att du uppdaterar systemen med följande inställning:</span><span class="sxs-lookup"><span data-stu-id="65b36-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="65b36-141">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="65b36-141">Setup in Sales</span></span>

- <span data-ttu-id="65b36-142">Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Använd systemets prisberäkningssystem** är inställd på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="65b36-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="65b36-143">Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Metod för rabattberäkning** är inställd på **Radobjekt**.</span><span class="sxs-lookup"><span data-stu-id="65b36-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="65b36-144">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="65b36-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="65b36-145">Rubrikuppgift på försäljningsfakturan</span><span class="sxs-lookup"><span data-stu-id="65b36-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="65b36-146">Uppdatera mappningen för **ID för CDS-organisation** under **Källa** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="65b36-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="65b36-147">Värdet för standardmall för **Försäljningsorder_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65b36-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="65b36-148">Värdet för standardmall för **Konto_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65b36-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="65b36-149">Värdet för standardmall för **Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65b36-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="65b36-150">Se till att erforderlig mappning finns under **Källa** > **CDS för FakturaLandRegions-Id** till **Faktureringsadress_Land**.</span><span class="sxs-lookup"><span data-stu-id="65b36-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="65b36-151">Mallvärdet är **ValueMap**, med ett antal länder mappade.</span><span class="sxs-lookup"><span data-stu-id="65b36-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="65b36-152">**Prislista** krävs för att skapa fakturor i Sales.</span><span class="sxs-lookup"><span data-stu-id="65b36-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="65b36-153">Uppdatera **ValueMap** i **CDS** > **Destination för pricelevelid.name [namn på prislista]** till den **prislista** som används i Sales efter valuta.</span><span class="sxs-lookup"><span data-stu-id="65b36-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="65b36-154">Du kan välja mellan att använda den förvalda **Prislistan** för en enstaka valuta eller att använda **ValueMap** om du har **prislistor** i flera olika valutor.</span><span class="sxs-lookup"><span data-stu-id="65b36-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="65b36-155">Mallvärdet för **pricelevelid.name [prislistans namn]** är **ValueMap** baserad på **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="65b36-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="65b36-156">usd: CRM Service USA (exempel).</span><span class="sxs-lookup"><span data-stu-id="65b36-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="65b36-157">Raduppgift i försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="65b36-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="65b36-158">Se till att erforderlig mappning finns under **Källa** > **CDS för måttenhet**.</span><span class="sxs-lookup"><span data-stu-id="65b36-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="65b36-159">Se till att erforderlig **ValueMap** för **Säljenhetssymbol** i Finance and Operations finns under **Källa** > **CDS-mappning**.</span><span class="sxs-lookup"><span data-stu-id="65b36-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="65b36-160">Mallvärde med **ValueMap** har definierats för **Säljenhetssymbol till kvantitet_UOM**.</span><span class="sxs-lookup"><span data-stu-id="65b36-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="65b36-161">Uppdatera mappningen för **ID för CD-organisation i källa** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="65b36-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="65b36-162">Värdet för standardmall för **Försäljningsfaktura_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65b36-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="65b36-163">Värdet för standardmall för **Produkt_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65b36-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="65b36-164">Mallmappning i dataintegreraren</span><span class="sxs-lookup"><span data-stu-id="65b36-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="65b36-165">**Betalningsvillkor**, **Fraktvillkor**, **Leveransvillkor**, **Leveransmetod** och **Leveranssätt** ingår inte i standardmappningen.</span><span class="sxs-lookup"><span data-stu-id="65b36-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="65b36-166">Mappning av dessa fält kräver att värdemappning konfigureras som är specifik för datan i de organisationer mellan vilka entiteten synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="65b36-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="65b36-167">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="65b36-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="65b36-172">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65b36-172">Related topics</span></span>

[<span data-ttu-id="65b36-173">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="65b36-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="65b36-174">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65b36-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="65b36-175">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65b36-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="65b36-176">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65b36-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="65b36-177">Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="65b36-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


