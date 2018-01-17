---
title: "Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d7e4c435a3344f6a5d66e1889b633d80cda085eb
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="65d25-103">Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="65d25-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="65d25-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="65d25-105">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="65d25-105">Template and tasks</span></span>

<span data-ttu-id="65d25-106">Följande mallar och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsorder från Finance and Operations till Sales:</span><span class="sxs-lookup"><span data-stu-id="65d25-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="65d25-107">**Namnet på mallen i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="65d25-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="65d25-108">Försäljningsorder (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="65d25-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="65d25-109">**Namn på aktiviteter i dataintegreringsprojekt**</span><span class="sxs-lookup"><span data-stu-id="65d25-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="65d25-110">Orderrubrik</span><span class="sxs-lookup"><span data-stu-id="65d25-110">OrderHeader</span></span>
    - <span data-ttu-id="65d25-111">Orderrad</span><span class="sxs-lookup"><span data-stu-id="65d25-111">OrderLine</span></span>

<span data-ttu-id="65d25-112">Synkroniseringsuppgifter som krävs före säljfakturahuvud och radsynkronisering:</span><span class="sxs-lookup"><span data-stu-id="65d25-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="65d25-113">Produkter (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="65d25-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="65d25-114">Konton (Sales till Fin and Ops) (vid behov)</span><span class="sxs-lookup"><span data-stu-id="65d25-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="65d25-115">Kontakter till kunder (Sales till Fin and Ops) (vid behov)</span><span class="sxs-lookup"><span data-stu-id="65d25-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="65d25-116">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="65d25-116">Entity set</span></span>

| <span data-ttu-id="65d25-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65d25-117">Finance and Operations</span></span> |    <span data-ttu-id="65d25-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="65d25-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="65d25-119">Försäljning</span><span class="sxs-lookup"><span data-stu-id="65d25-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="65d25-120">CDS-försäljningsorderrubriker</span><span class="sxs-lookup"><span data-stu-id="65d25-120">CDS sales order headers</span></span>| <span data-ttu-id="65d25-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="65d25-121">SalesOrder</span></span>     | <span data-ttu-id="65d25-122">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="65d25-122">SalesOrders</span></span> |
| <span data-ttu-id="65d25-123">CDS-försäljningsorderrader</span><span class="sxs-lookup"><span data-stu-id="65d25-123">CDS sales order lines</span></span>  | <span data-ttu-id="65d25-124">Försäljningsorderrad</span><span class="sxs-lookup"><span data-stu-id="65d25-124">SalesOrderLine</span></span> | <span data-ttu-id="65d25-125">Försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="65d25-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="65d25-126">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="65d25-126">Entity flow</span></span>

<span data-ttu-id="65d25-127">Försäljningsorder skapas i Finance and Operations och synkroniseras till Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="65d25-128">Filter i mallen ser till att endast relevanta försäljningsorder inkluderas i synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="65d25-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="65d25-129">Både beställande och fakturerande kund på försäljningsordern som härstammar från försäljningen inkluderas i synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="65d25-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="65d25-130">Fälten **Beställande kund hanteras externt** och **Fakturakund hanteras externt** används för att spåra synkroniseringen i dataenheterna.</span><span class="sxs-lookup"><span data-stu-id="65d25-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="65d25-131">**Försäljningsordern** i Finance and Operations måste bekräftas.</span><span class="sxs-lookup"><span data-stu-id="65d25-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="65d25-132">Endast bekräftade försäljningsorder eller försäljningsorder med högre bearbetningsstatus, exempelvis statusen Levererad eller Fakturerad, synkroniseras till Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="65d25-133">När du skapar eller ändrar en försäljningsorder måste batch-jobbet **Beräkna försäljningstotalen** i Finance and Operations köras.</span><span class="sxs-lookup"><span data-stu-id="65d25-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="65d25-134">Endast försäljningsorder med beräknade försäljningstotaler synkroniseras med CDS och Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="65d25-135">Moms relaterat till avgifter i **Försäljningsorderrubriken** ingår i nuläget inte i synkroniseringen från Finance and Operations till Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="65d25-136">Anledningen till det är att Sales inte stöder skatteinformation på rubriknivå.</span><span class="sxs-lookup"><span data-stu-id="65d25-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="65d25-137">Skatter som berör avgifter på radnivå är inkluderade.</span><span class="sxs-lookup"><span data-stu-id="65d25-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="65d25-138">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="65d25-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="65d25-139">Nya fält läggs till i enheten **Order** och visas på sidan:</span><span class="sxs-lookup"><span data-stu-id="65d25-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="65d25-140">**Hanteras externt** - Värdet anges som **Ja** när ordern kommer från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65d25-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="65d25-141">**Bearbetningsstatus** - Används för att visa bearbetningsstatusen för ordern i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65d25-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="65d25-142">Värdena är:</span><span class="sxs-lookup"><span data-stu-id="65d25-142">Values are:</span></span>

    - <span data-ttu-id="65d25-143">Aktiva</span><span class="sxs-lookup"><span data-stu-id="65d25-143">Active</span></span>
    - <span data-ttu-id="65d25-144">Bekräftat</span><span class="sxs-lookup"><span data-stu-id="65d25-144">Confirmed</span></span>
    - <span data-ttu-id="65d25-145">Följesedel</span><span class="sxs-lookup"><span data-stu-id="65d25-145">Packing Slip</span></span>
    - <span data-ttu-id="65d25-146">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="65d25-146">Invoiced</span></span>
    - <span data-ttu-id="65d25-147">Plockat</span><span class="sxs-lookup"><span data-stu-id="65d25-147">Picked</span></span>
    - <span data-ttu-id="65d25-148">Delvis plockad</span><span class="sxs-lookup"><span data-stu-id="65d25-148">Partially Picked</span></span>
    - <span data-ttu-id="65d25-149">Delvis förpackad</span><span class="sxs-lookup"><span data-stu-id="65d25-149">Partially Packed</span></span>
    - <span data-ttu-id="65d25-150">Skeppat</span><span class="sxs-lookup"><span data-stu-id="65d25-150">Shipped</span></span>
    - <span data-ttu-id="65d25-151">Delvis levererad</span><span class="sxs-lookup"><span data-stu-id="65d25-151">Partially Shipped</span></span>
    - <span data-ttu-id="65d25-152">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="65d25-152">Partially Invoiced</span></span>
    - <span data-ttu-id="65d25-153">Avbröts</span><span class="sxs-lookup"><span data-stu-id="65d25-153">Cancelled</span></span>

<span data-ttu-id="65d25-154">Inställningen **Har endast externt hanterade produkter** används i andra scenarier för försäljningsorder (synkronisering från Sales till Finance and Operation) i syfte att konstant hålla reda på huruvida försäljningsordern enbart består av **Externt hanterade Produkter** - i detta fall hanteras produkterna i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65d25-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="65d25-155">Detta säkerställer att du inte försöker synkronisera försäljningsorderraderna med produkter som är okända för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65d25-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="65d25-156">Knapparna **Skapa faktura**, **Annullera order**, **Beräkna om**, **Hämta produkter** och **Slå upp adress** på sidan **Försäljningsorder** döljs för externt hanterade order eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="65d25-157">Ordersidan kan inte registreras eftersom försäljningsorderinformationen synkroniseras från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65d25-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="65d25-158">**Status för försäljningsorder** förblir aktiv för att se till att ändringar från Finance and Operations når **Försäljningsordern** i Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="65d25-159">Detta styrs genom att ange standard **Statuskod [Status]** som **Aktiv** i dataintegreringsprojektetet.</span><span class="sxs-lookup"><span data-stu-id="65d25-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="65d25-160">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="65d25-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="65d25-161">Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar systemen med följande inställning:</span><span class="sxs-lookup"><span data-stu-id="65d25-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="65d25-162">Inställning i Sales</span><span class="sxs-lookup"><span data-stu-id="65d25-162">Setup in Sales</span></span>

- <span data-ttu-id="65d25-163">Kontrollera behörigheterna för teamet som användaren (från **Anslutning skapad** i Sales) har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="65d25-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="65d25-164">Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte teamet.</span><span class="sxs-lookup"><span data-stu-id="65d25-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="65d25-165">Utan detta visas ett felmeddelande som det primära teamet saknar när projektet körs från dataintegreraren.</span><span class="sxs-lookup"><span data-stu-id="65d25-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="65d25-166">Under **Inställningar** > **Säkerhet** > **Team**väljer du relevant team, klickar på **Hantera roller** och väljer en roll med önskade behörigheter, t.ex. systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="65d25-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="65d25-167">Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Använd systemets prisberäkningssystem** är inställd på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="65d25-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="65d25-168">Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Metod för rabattberäkning** är inställd på **Radobjekt**.</span><span class="sxs-lookup"><span data-stu-id="65d25-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="65d25-169">Inställningar i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65d25-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="65d25-170">Ange att **Försäljning och marknadsföring** > **Periodiska uppgifter** > **Beräkna försäljningstotaler** ska köras som ett batch-jobb, med **Beräkna totaler för försäljningsorder** inställt på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="65d25-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="65d25-171">Detta är viktigt endast försäljningsorder med beräknade försäljningstotaler synkroniseras med CDS och Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="65d25-172">Batch-jobbets frekvens ska vara densamma som frekvensen för synkroniseringen av försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="65d25-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="65d25-173">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="65d25-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="65d25-174">Aktivitet för försäljningsrubrik</span><span class="sxs-lookup"><span data-stu-id="65d25-174">SalesHeader task</span></span>

- <span data-ttu-id="65d25-175">Uppdatera mappningen för **ID för CD-organisation i källa** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="65d25-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="65d25-176">Värdet för standardmall för **Konto_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65d25-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="65d25-177">Standardvärdet för **Fakturakonto_Organisation_Organisation-ID** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65d25-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="65d25-178">Värdet för standardmall för **Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65d25-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="65d25-179">Kontrollera att nödvändig mappning finns i **Källa** > **CDS för FakturaLandRegions-ID till Faktureringsadress_Land** och **LeveransLandRegions-ID till LeveransAdress_Land**.</span><span class="sxs-lookup"><span data-stu-id="65d25-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="65d25-180">Mallvärdet är **ValueMap**, med ett antal länder mappade.</span><span class="sxs-lookup"><span data-stu-id="65d25-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="65d25-181">**Prislista** krävs för att skapa order i Sales.</span><span class="sxs-lookup"><span data-stu-id="65d25-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="65d25-182">Uppdatera **ValueMap** i **CDS** > **Destination** för **pricelevelid.name [prislistans namn]** till den **Prislista** som används i Sales efter valuta.</span><span class="sxs-lookup"><span data-stu-id="65d25-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="65d25-183">Du kan antingen använda förvald **Prislista** för gemensam valuta eller använda **ValueMap** om du har **Prislistor** i flera olika valutor.</span><span class="sxs-lookup"><span data-stu-id="65d25-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="65d25-184">Standardvärdet för **pricelevelid.name [prislistans namn]** är CRM-tjänsten i USA (prov).</span><span class="sxs-lookup"><span data-stu-id="65d25-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="65d25-185">Aktivitet på försäljningsrad</span><span class="sxs-lookup"><span data-stu-id="65d25-185">SalesLine task</span></span>

- <span data-ttu-id="65d25-186">Uppdatera mappningen för **ID för CD-organisation i källa** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="65d25-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="65d25-187">Värdet för standardmall för **Försäljningsorder_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65d25-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="65d25-188">Värdet för standardmall för **Produkt_Organisation_Organisations-Id** är ORG001.</span><span class="sxs-lookup"><span data-stu-id="65d25-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="65d25-189">Kontrollera att nödvändig mappning finns i **Källa** > **CDS** för **LeveransLandRegion-ID** till **LeveransAdress_Land**.</span><span class="sxs-lookup"><span data-stu-id="65d25-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="65d25-190">Mallvärdet är **ValueMap**, med ett antal länder mappade.</span><span class="sxs-lookup"><span data-stu-id="65d25-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="65d25-191">Se till att erforderlig **ValueMap** för **Säljenhetssymbol** i Finance and Operations finns under **Källa** > **CDS-mappning**.</span><span class="sxs-lookup"><span data-stu-id="65d25-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="65d25-192">Mallvärde med **ValueMap** har definierats för **Säljenhetssymbol till kvantitet_UOM**.</span><span class="sxs-lookup"><span data-stu-id="65d25-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="65d25-193">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="65d25-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="65d25-194">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="65d25-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="65d25-195">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="65d25-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="65d25-196">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="65d25-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="65d25-197">Orderrubrik</span><span class="sxs-lookup"><span data-stu-id="65d25-197">OrderHeader</span></span>

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="65d25-200">Orderrad</span><span class="sxs-lookup"><span data-stu-id="65d25-200">OrderLine</span></span>

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="65d25-203">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65d25-203">Related topics</span></span>

[<span data-ttu-id="65d25-204">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="65d25-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="65d25-205">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65d25-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="65d25-206">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65d25-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="65d25-207">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65d25-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="65d25-208">Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="65d25-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


