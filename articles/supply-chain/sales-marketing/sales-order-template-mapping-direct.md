---
title: "Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="4c8df-103">Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="4c8df-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4c8df-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="4c8df-105">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="4c8df-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="4c8df-106">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="4c8df-107">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="4c8df-108">Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="4c8df-109">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="4c8df-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="4c8df-110">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="4c8df-110">Templates and tasks</span></span>

<span data-ttu-id="4c8df-111">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="4c8df-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="4c8df-112">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="4c8df-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="4c8df-113">Följande mall och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsorder från Finance and Operations till Sales:</span><span class="sxs-lookup"><span data-stu-id="4c8df-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="4c8df-114">**Namnet på mallen i dataintegrering:** försäljningsorder (Fin and Ops till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="4c8df-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="4c8df-115">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="4c8df-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="4c8df-116">Orderrubrik</span><span class="sxs-lookup"><span data-stu-id="4c8df-116">OrderHeader</span></span>
    - <span data-ttu-id="4c8df-117">Orderrad</span><span class="sxs-lookup"><span data-stu-id="4c8df-117">OrderLine</span></span>

<span data-ttu-id="4c8df-118">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsfakturor kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="4c8df-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="4c8df-119">Produkter (Fin and Ops till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="4c8df-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="4c8df-120">Konton (Sales till Fin and Ops) - Direkt (vid behov)</span><span class="sxs-lookup"><span data-stu-id="4c8df-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="4c8df-121">Kontakter till kunder (Sales till Fin and Ops) - Direkt (vid behov)</span><span class="sxs-lookup"><span data-stu-id="4c8df-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="4c8df-122">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="4c8df-122">Entity set</span></span>

| <span data-ttu-id="4c8df-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4c8df-123">Finance and Operations</span></span>  | <span data-ttu-id="4c8df-124">Försäljning</span><span class="sxs-lookup"><span data-stu-id="4c8df-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="4c8df-125">CDS-försäljningsorderrubriker</span><span class="sxs-lookup"><span data-stu-id="4c8df-125">CDS sales order headers</span></span> | <span data-ttu-id="4c8df-126">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="4c8df-126">SalesOrders</span></span>       |
| <span data-ttu-id="4c8df-127">CDS-försäljningsorderrader</span><span class="sxs-lookup"><span data-stu-id="4c8df-127">CDS sales order lines</span></span>   | <span data-ttu-id="4c8df-128">Försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="4c8df-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="4c8df-129">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="4c8df-129">Entity flow</span></span>

<span data-ttu-id="4c8df-130">Försäljningsorder skapas i Finance and Operations och synkroniseras till Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="4c8df-131">Filter i mallen ser till att endast relevanta försäljningsorder inkluderas i synkroniseringen:</span><span class="sxs-lookup"><span data-stu-id="4c8df-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="4c8df-132">På försäljningsordern härstammar både beställande kund och fakturerande kund från Sales inkluderas i synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="4c8df-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="4c8df-133">Fälten **Beställande kund hanteras externt** och **Fakturakund hanteras externt** används för att spåra synkroniseringen i dataenheterna.</span><span class="sxs-lookup"><span data-stu-id="4c8df-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="4c8df-134">Försäljningsordern i Finance and Operations måste bekräftas.</span><span class="sxs-lookup"><span data-stu-id="4c8df-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="4c8df-135">Endast bekräftade försäljningsorder eller försäljningsorder med högre bearbetningsstatus, exempelvis **Levererad** eller **Fakturerad** synkroniseras till Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="4c8df-136">När en försäljningsorder skapas eller ändras måste batch-jobbet **Beräkna försäljningstotalen** i Finance and Operations köras.</span><span class="sxs-lookup"><span data-stu-id="4c8df-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="4c8df-137">Endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="4c8df-138">För närvarande ingår moms relaterad till avgifter i försäljningsorderrubriken inte i synkroniseringen från Finance and Operations till Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="4c8df-139">Sales stöder itne skatteinformation på rubriknivå.</span><span class="sxs-lookup"><span data-stu-id="4c8df-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="4c8df-140">Moms som är relaterad till tillägg på radnivå ingår emellertid i synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="4c8df-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="4c8df-141">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="4c8df-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="4c8df-142">Nya fält har lagst till i enheten **Order** och visas på sidan:</span><span class="sxs-lookup"><span data-stu-id="4c8df-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="4c8df-143">**Hanteras externt** - Värdet anges som **Ja** när ordern kommer från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="4c8df-144">**Bearbetningsstatus** - Detta fält visar bearbetningsstatusen för ordern i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="4c8df-145">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="4c8df-145">The following values are available:</span></span>

    - <span data-ttu-id="4c8df-146">Aktiva</span><span class="sxs-lookup"><span data-stu-id="4c8df-146">Active</span></span>
    - <span data-ttu-id="4c8df-147">Bekräftat</span><span class="sxs-lookup"><span data-stu-id="4c8df-147">Confirmed</span></span>
    - <span data-ttu-id="4c8df-148">Följesedel</span><span class="sxs-lookup"><span data-stu-id="4c8df-148">Packing Slip</span></span>
    - <span data-ttu-id="4c8df-149">Fakturerat</span><span class="sxs-lookup"><span data-stu-id="4c8df-149">Invoiced</span></span>
    - <span data-ttu-id="4c8df-150">Plockat</span><span class="sxs-lookup"><span data-stu-id="4c8df-150">Picked</span></span>
    - <span data-ttu-id="4c8df-151">Delvis plockad</span><span class="sxs-lookup"><span data-stu-id="4c8df-151">Partially Picked</span></span>
    - <span data-ttu-id="4c8df-152">Delvis förpackad</span><span class="sxs-lookup"><span data-stu-id="4c8df-152">Partially Packed</span></span>
    - <span data-ttu-id="4c8df-153">Skeppat</span><span class="sxs-lookup"><span data-stu-id="4c8df-153">Shipped</span></span>
    - <span data-ttu-id="4c8df-154">Delvis levererad</span><span class="sxs-lookup"><span data-stu-id="4c8df-154">Partially Shipped</span></span>
    - <span data-ttu-id="4c8df-155">Delvis fakturerad</span><span class="sxs-lookup"><span data-stu-id="4c8df-155">Partially Invoiced</span></span>
    - <span data-ttu-id="4c8df-156">Avbröts</span><span class="sxs-lookup"><span data-stu-id="4c8df-156">Cancelled</span></span>

<span data-ttu-id="4c8df-157">Inställningen **Har endast externt hanterade produkter** används i andra scenarier för försäljningsorder (t.ex. synkronisering från Sales till Finance and Operation) i syfte att konstant hålla reda på om en försäljningsordern helt består av externt underhållna produkter.</span><span class="sxs-lookup"><span data-stu-id="4c8df-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="4c8df-158">Om en försäljningsorder helt består av externt underhållna produkter, underhålls produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="4c8df-159">Denna inställning hjälper till att garantera att du inte försöker synkronisera försäljningsorderraderna som har produkter som är okända för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="4c8df-160">Knapparna **Skapa faktura**, **Annullera order**, **Beräkna om**, **Hämta produkter** och **Slå upp adress** på sidan **Försäljningsorder** döljs för externt hanterade order eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="4c8df-161">Ordersidan kan inte redigeras eftersom försäljningsorderinformationen synkroniseras från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="4c8df-162">Status för försäljningsorder förblir **aktiv** för att se till att ändringar från Finance and Operations når Försäljningsordern i Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="4c8df-163">För att styra detta beteende, ange standardvärdet till **Statuskod \[Status\]** till **Aktiv** i dataintegreringsprojektetet.</span><span class="sxs-lookup"><span data-stu-id="4c8df-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="4c8df-164">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4c8df-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="4c8df-165">Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar följande inställningar i systemen.</span><span class="sxs-lookup"><span data-stu-id="4c8df-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="4c8df-166">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="4c8df-166">Setup in Sales</span></span>

- <span data-ttu-id="4c8df-167">Se till att behörigheterna ställs in för teamet som användaren från din Sales-anslutning har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="4c8df-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="4c8df-168">Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst.</span><span class="sxs-lookup"><span data-stu-id="4c8df-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="4c8df-169">Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.</span><span class="sxs-lookup"><span data-stu-id="4c8df-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="4c8df-170">Gå till **Inställningar** > **Säkerhet** > **Team**, väljer du relevant team, klickar på **Hantera roller** och väljer en roll med önskade behörigheter, t.ex. **systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="4c8df-171">Gå till **inställningar** > **Administration** > **systeminställningar** > **Sales** och säkerställ att följande inställningar används:</span><span class="sxs-lookup"><span data-stu-id="4c8df-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="4c8df-172">Alternativet **Använd systemets prisberäkningssystem** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="4c8df-173">Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="4c8df-174">Inställningar i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4c8df-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="4c8df-175">Gå till **försäljning och maarknadsföring** > **periodiska uppgifter** > **Beräkna försäljningssummor** och ange att jobbet ska köras som ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="4c8df-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="4c8df-176">Ange alternativet **Beräkna summor för försäljningsorder** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="4c8df-177">Detta steg är viktigt eftersom endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="4c8df-178">Batch-jobbets frekvens ska vara densamma som frekvensen för synkroniseringen av försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="4c8df-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="4c8df-179">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="4c8df-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="4c8df-180">Aktivitet för försäljningsrubrik</span><span class="sxs-lookup"><span data-stu-id="4c8df-180">SalesHeader task</span></span>

- <span data-ttu-id="4c8df-181">Kontrollera att nödvändig mappning finns för **InvoiceCountryRegionId** till **BillingAddress\_Country** och för **DeliveryCountryRegionId** till **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="4c8df-182">Mallvärdet är en värdemappning där flera länder eller regioner som mappas.</span><span class="sxs-lookup"><span data-stu-id="4c8df-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="4c8df-183">En prislista krävs för att skapa order i Sales.</span><span class="sxs-lookup"><span data-stu-id="4c8df-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="4c8df-184">Uppdatera värdemappen för **pricelevelid.name \[Price list name\]** till den prislista som används i Sales efter valuta.</span><span class="sxs-lookup"><span data-stu-id="4c8df-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="4c8df-185">Du kan använda standardprislistan för en enda valuta.</span><span class="sxs-lookup"><span data-stu-id="4c8df-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="4c8df-186">Om du har prislistor i flera valutor kan du använda en värdekarta.</span><span class="sxs-lookup"><span data-stu-id="4c8df-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="4c8df-187">Standardmallvärdet för **pricelevelid.name \[Prislistenamn\]** är **CRM Service USA (exempel)**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="4c8df-188">Aktivitet på försäljningsrad</span><span class="sxs-lookup"><span data-stu-id="4c8df-188">SalesLine task</span></span>

- <span data-ttu-id="4c8df-189">Kontrollera att nödvändig mappning finns i **DeliveryCountryRegionId** till **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="4c8df-190">Mallvärdet är en värdemappning där flera länder eller regioner som mappas.</span><span class="sxs-lookup"><span data-stu-id="4c8df-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="4c8df-191">Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="4c8df-192">En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **Antal\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="4c8df-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4c8df-193">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="4c8df-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="4c8df-194">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="4c8df-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="4c8df-195">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="4c8df-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="4c8df-196">I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="4c8df-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="4c8df-197">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c8df-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="4c8df-198">Orderrubrik</span><span class="sxs-lookup"><span data-stu-id="4c8df-198">OrderHeader</span></span>

![Mallmappning i dataintegreraren](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="4c8df-200">Orderrad</span><span class="sxs-lookup"><span data-stu-id="4c8df-200">OrderLine</span></span>

![Mallmappning i dataintegreraren](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="4c8df-202">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4c8df-202">Related topics</span></span>

[<span data-ttu-id="4c8df-203">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="4c8df-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="4c8df-204">Synkronisera konton direkt från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4c8df-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="4c8df-205">Synkronisera produkter direkt från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="4c8df-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="4c8df-206">Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4c8df-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="4c8df-207">Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="4c8df-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




