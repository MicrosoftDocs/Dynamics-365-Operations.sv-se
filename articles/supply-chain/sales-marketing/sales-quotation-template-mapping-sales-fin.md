---
title: Synkronisera huvuden och rader i försäljningsofferter direkt från Sales till Finance and Operations
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsoffertrubriker och rader direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: 0894f4728d3f1df21db130cd9e87d9881726e7fa
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743381"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="e6695-103">Synkronisera huvuden och rader i försäljningsofferter direkt från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e6695-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6695-104">I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsoffertrubriker och rader direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="e6695-105">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Common Data Service för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="e6695-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="e6695-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="e6695-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="e6695-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e6695-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="e6695-108">Potentiell kund till pengar-mallarna med funktion för dataintegrering möjliggör ett dataflöde för konton, produkter, kontakter, produkter, försäljningskvoter, försäljningsorder samt försäljningsfakturor Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e6695-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="e6695-109">Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e6695-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="e6695-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="e6695-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="e6695-111">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="e6695-111">Template and tasks</span></span>

<span data-ttu-id="e6695-112">Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader direkt i försäljningsofferter från Sales till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e6695-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="e6695-113">**Namnet på mallen i dataintegrering:** försäljningsofferter (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="e6695-113">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="e6695-114">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="e6695-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="e6695-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e6695-115">QuoteHeader</span></span>
    - <span data-ttu-id="e6695-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e6695-116">QuoteLine</span></span>

<span data-ttu-id="e6695-117">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="e6695-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="e6695-118">Produkter (Fin and Ops till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="e6695-118">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="e6695-119">Konton (Sales till Fin and Ops) - Direkt (vid behov)</span><span class="sxs-lookup"><span data-stu-id="e6695-119">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="e6695-120">Kontakter till kunder (Sales till Fin and Ops) - Direkt (vid behov)</span><span class="sxs-lookup"><span data-stu-id="e6695-120">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="e6695-121">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="e6695-121">Entity set</span></span>

| <span data-ttu-id="e6695-122">Försäljning</span><span class="sxs-lookup"><span data-stu-id="e6695-122">Sales</span></span>        | <span data-ttu-id="e6695-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e6695-123">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="e6695-124">Citat</span><span class="sxs-lookup"><span data-stu-id="e6695-124">Quotes</span></span>       | <span data-ttu-id="e6695-125">CDS-försäljningsofferrubrik</span><span class="sxs-lookup"><span data-stu-id="e6695-125">CDS sales quotation header</span></span> |
| <span data-ttu-id="e6695-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="e6695-126">QuoteDetails</span></span> | <span data-ttu-id="e6695-127">Försäljningsoffertrader för CDS</span><span class="sxs-lookup"><span data-stu-id="e6695-127">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="e6695-128">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="e6695-128">Entity flow</span></span>

<span data-ttu-id="e6695-129">Försäljningsofferter skapas i Sales och synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-129">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="e6695-130">Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="e6695-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="e6695-131">Alla offertprodukter på försäljningsofferna hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="e6695-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="e6695-132">När du har klickat på **aktivera offert**, är försäljningsofferten aktiv.</span><span class="sxs-lookup"><span data-stu-id="e6695-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e6695-133">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="e6695-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="e6695-134">Fältet **Har endast externt hanterade produkter** har lagts till entiteten **Offert** för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter.</span><span class="sxs-lookup"><span data-stu-id="e6695-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="e6695-135">Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-135">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="e6695-136">Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="e6695-137">Alla offertprodukter på försäljningsofferten uppdateras med informationen **Har endast externt hanterade produkter** från försäljningsofferthuvudet.</span><span class="sxs-lookup"><span data-stu-id="e6695-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="e6695-138">Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på entiteten **Offertdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="e6695-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="e6695-139">En rabatt kan läggas till i offertprodukten och synkroniseras med Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-139">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="e6695-140">Fälten **rabatt**, **tillägg**, och **moms** på rubriken styrs av en inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="e6695-141">För närvarande stöder inte den här inställningen integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="e6695-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="e6695-142">I den aktuella designen underhålls fälten **pris**, **rabatt**, **tillägg**, och **moms** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="e6695-143">I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e6695-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="e6695-144">Skrivskyddade fält på försäljningsoffertens huvud: **Rabatt %**, **Rabatt** och **Fraktbelopp**</span><span class="sxs-lookup"><span data-stu-id="e6695-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="e6695-145">Skrivskyddade fält på offertprodukter: **moms**</span><span class="sxs-lookup"><span data-stu-id="e6695-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="e6695-146">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e6695-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="e6695-147">Innan försäljningsofferter synkroniseras är det viktigt att du uppdaterar följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="e6695-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="e6695-148">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="e6695-148">Setup in Sales</span></span>

- <span data-ttu-id="e6695-149">Se till att behörigheterna ställs in för teamet som användaren från din anslutning som anges i Sales har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="e6695-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="e6695-150">Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst.</span><span class="sxs-lookup"><span data-stu-id="e6695-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="e6695-151">Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.</span><span class="sxs-lookup"><span data-stu-id="e6695-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="e6695-152">Om du vill ställa in behörigheter för gruppen gå till **inställningar**&gt;**säkerhet**&gt;**team**, och välj relevant team.</span><span class="sxs-lookup"><span data-stu-id="e6695-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="e6695-153">Välj **hantera roller**, och välj sedan en roll med behörigheter, t.ex. **systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="e6695-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="e6695-154">Gå till **inställningar** &gt; **Administration** &gt; **systeminställningar** &gt; **Sales** och säkerställ att följande inställningar används:</span><span class="sxs-lookup"><span data-stu-id="e6695-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="e6695-155">Alternativet **Använd systemets prisberäkningssystem** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e6695-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="e6695-156">Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.</span><span class="sxs-lookup"><span data-stu-id="e6695-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="e6695-157">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="e6695-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="e6695-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e6695-158">QuoteHeader</span></span>

- <span data-ttu-id="e6695-159">Kontrollera att nödvändig mappning finns i **Shipto\_land** till **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="e6695-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="e6695-160">Du kan definiera ett standardvärde som används om värdet är tomt i värdemappningen.</span><span class="sxs-lookup"><span data-stu-id="e6695-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="e6695-161">Lämna bara värdet på vänster sida tomt och ange höger sida till önskat land eller region.</span><span class="sxs-lookup"><span data-stu-id="e6695-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="e6695-162">På så sätt kan du inte ange land eller region för nationella order.</span><span class="sxs-lookup"><span data-stu-id="e6695-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="e6695-163">Mallvärdet är en värdemappning där flera länder eller regioner som mappas och där ett tomt värde är lika med **US**.</span><span class="sxs-lookup"><span data-stu-id="e6695-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="e6695-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e6695-164">QuoteLine</span></span>

- <span data-ttu-id="e6695-165">Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-165">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="e6695-166">Kontrollera att nödvändiga enheter definieras i Sales.</span><span class="sxs-lookup"><span data-stu-id="e6695-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="e6695-167">En värdemall som har en värdemappning definieras för **oumid.name** till **Säljenhetssymbol**.</span><span class="sxs-lookup"><span data-stu-id="e6695-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="e6695-168">Valfritt: Du kan lägga till följande mappningar för att garantera att försäljningsoffertraderna importeras till Finance and Operations om det inte finns någon standardinformation från varken kunden eller produkten:</span><span class="sxs-lookup"><span data-stu-id="e6695-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="e6695-169">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="e6695-170">Det finns inget standrdmallvärde för **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="e6695-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="e6695-171">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="e6695-172">Det finns inget standrdmallvärde för **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="e6695-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="e6695-173">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="e6695-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="e6695-174">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="e6695-175">För närvarande stöder inte den här inställningen integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="e6695-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="e6695-176">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6695-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="e6695-177">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="e6695-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="e6695-178">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="e6695-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="e6695-179">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="e6695-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="e6695-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e6695-180">QuoteHeader</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="e6695-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e6695-182">QuoteLine</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="e6695-184">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e6695-184">Related topics</span></span>

[<span data-ttu-id="e6695-185">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="e6695-185">Prospect to cash</span></span>](prospect-to-cash.md)

