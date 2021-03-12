---
title: Synkronisera försäljningsoffertrubriker och rader direkt från Sales till Supply Chain Management
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsoffertrubriker och rader direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 19c7de1436b2fe4a859ac20d3db1fefa445a115f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991875"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a><span data-ttu-id="7d53d-103">Synkronisera försäljningsoffertrubriker och rader direkt från Sales till Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="7d53d-103">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="7d53d-104">I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsoffertrubriker och rader direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

> [!NOTE]
> <span data-ttu-id="7d53d-105">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Microsoft Dataverse för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="7d53d-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="7d53d-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="7d53d-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="7d53d-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="7d53d-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="7d53d-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="7d53d-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="7d53d-109">Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="7d53d-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="7d53d-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="7d53d-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="7d53d-111">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="7d53d-111">Template and tasks</span></span>

<span data-ttu-id="7d53d-112">Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader direkt i försäljningsofferter från Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="7d53d-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="7d53d-113">**Namnet på mallen i dataintegrering:** försäljningsofferter (Sales till Supply Chain Management) - Direkt</span><span class="sxs-lookup"><span data-stu-id="7d53d-113">**Name of the template in Data integration:** Sales Quotes (Sales to Supply Chain Management) - Direct</span></span>
- <span data-ttu-id="7d53d-114">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="7d53d-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="7d53d-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="7d53d-115">QuoteHeader</span></span>
    - <span data-ttu-id="7d53d-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="7d53d-116">QuoteLine</span></span>

<span data-ttu-id="7d53d-117">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="7d53d-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="7d53d-118">Produkter (Supply Chain Management till Sales) - direkt</span><span class="sxs-lookup"><span data-stu-id="7d53d-118">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="7d53d-119">Konton (Sales till Supply Chain Management)-direkt (om den används)</span><span class="sxs-lookup"><span data-stu-id="7d53d-119">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="7d53d-120">Kontakter till kunder (Sales till Supply Chain Management) - direkt (om den används)</span><span class="sxs-lookup"><span data-stu-id="7d53d-120">Contacts to Customers (Sales to Supply Chain Management) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="7d53d-121">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="7d53d-121">Entity set</span></span>

| <span data-ttu-id="7d53d-122">Försäljning</span><span class="sxs-lookup"><span data-stu-id="7d53d-122">Sales</span></span>        | <span data-ttu-id="7d53d-123">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="7d53d-123">Supply Chain Management</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="7d53d-124">Citat</span><span class="sxs-lookup"><span data-stu-id="7d53d-124">Quotes</span></span>       | <span data-ttu-id="7d53d-125">Dataverse-försäljningsofferrubrik</span><span class="sxs-lookup"><span data-stu-id="7d53d-125">Dataverse sales quotation header</span></span> |
| <span data-ttu-id="7d53d-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="7d53d-126">QuoteDetails</span></span> | <span data-ttu-id="7d53d-127">Dataverse-försäljningsoffertrader</span><span class="sxs-lookup"><span data-stu-id="7d53d-127">Dataverse sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="7d53d-128">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="7d53d-128">Entity flow</span></span>

<span data-ttu-id="7d53d-129">Försäljningsofferter skapas i Sales och synkroniseras med Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-129">Sales quotations are created in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="7d53d-130">Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="7d53d-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="7d53d-131">Alla offertprodukter på försäljningsofferna hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="7d53d-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="7d53d-132">När du har klickat på **aktivera offert**, är försäljningsofferten aktiv.</span><span class="sxs-lookup"><span data-stu-id="7d53d-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="7d53d-133">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="7d53d-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="7d53d-134">Fältet **Har endast externt hanterade produkter** har lagts till entiteten **Offert** för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter.</span><span class="sxs-lookup"><span data-stu-id="7d53d-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="7d53d-135">Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-135">If a sales quotation has only externally maintained products, the products are maintained in Supply Chain Management.</span></span> <span data-ttu-id="7d53d-136">Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Supply Chain Management.</span></span>

<span data-ttu-id="7d53d-137">Alla offertprodukter på försäljningsofferten uppdateras med informationen **Har endast externt hanterade produkter** från försäljningsofferthuvudet.</span><span class="sxs-lookup"><span data-stu-id="7d53d-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="7d53d-138">Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på entiteten **Offertdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="7d53d-139">En rabatt kan läggas till i offertprodukten och synkroniseras med Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-139">A discount can be added to the quote product and will be synchronized to Supply Chain Management.</span></span> <span data-ttu-id="7d53d-140">Fälten **rabatt**, **tillägg**, och **moms** på rubriken styrs av en inställning i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Supply Chain Management.</span></span> <span data-ttu-id="7d53d-141">För närvarande stöder inte den här inställningen integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="7d53d-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="7d53d-142">I den aktuella designen underhålls fälten **pris**, **rabatt**, **tillägg**, och **moms** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in FSupply Chain Management.</span></span>

<span data-ttu-id="7d53d-143">I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Supply Chain Management:</span></span>

- <span data-ttu-id="7d53d-144">Skrivskyddade fält på försäljningsoffertens huvud: **Rabatt %**, **Rabatt** och **Fraktbelopp**</span><span class="sxs-lookup"><span data-stu-id="7d53d-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="7d53d-145">Skrivskyddade fält på offertprodukter: **moms**</span><span class="sxs-lookup"><span data-stu-id="7d53d-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="7d53d-146">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="7d53d-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="7d53d-147">Innan försäljningsofferter synkroniseras är det viktigt att du uppdaterar följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="7d53d-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="7d53d-148">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="7d53d-148">Setup in Sales</span></span>

- <span data-ttu-id="7d53d-149">Se till att behörigheterna ställs in för teamet som användaren från din anslutning som anges i Sales har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="7d53d-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="7d53d-150">Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst.</span><span class="sxs-lookup"><span data-stu-id="7d53d-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="7d53d-151">Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.</span><span class="sxs-lookup"><span data-stu-id="7d53d-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="7d53d-152">Om du vill ställa in behörigheter för gruppen gå till **inställningar**&gt;**säkerhet**&gt;**team**, och välj relevant team.</span><span class="sxs-lookup"><span data-stu-id="7d53d-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="7d53d-153">Välj **hantera roller**, och välj sedan en roll med behörigheter, t.ex. **systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="7d53d-154">Gå till **inställningar** &gt; **Administration** &gt; **systeminställningar** &gt; **Sales** och säkerställ att följande inställningar används:</span><span class="sxs-lookup"><span data-stu-id="7d53d-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="7d53d-155">Alternativet **Använd systemets prisberäkningssystem** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="7d53d-156">Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="7d53d-157">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="7d53d-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="7d53d-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="7d53d-158">QuoteHeader</span></span>

- <span data-ttu-id="7d53d-159">Kontrollera att nödvändig mappning finns i **Shipto\_land** till **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="7d53d-160">Du kan definiera ett standardvärde som används om värdet är tomt i värdemappningen.</span><span class="sxs-lookup"><span data-stu-id="7d53d-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="7d53d-161">Lämna bara värdet på vänster sida tomt och ange höger sida till önskat land eller region.</span><span class="sxs-lookup"><span data-stu-id="7d53d-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="7d53d-162">På så sätt kan du inte ange land eller region för nationella order.</span><span class="sxs-lookup"><span data-stu-id="7d53d-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="7d53d-163">Mallvärdet är en värdemappning där flera länder eller regioner som mappas och där ett tomt värde är lika med **US**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="7d53d-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="7d53d-164">QuoteLine</span></span>

- <span data-ttu-id="7d53d-165">Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-165">Make sure that the required value map exists for **SalesUnitSymbol** in Supply Chain Management.</span></span>
- <span data-ttu-id="7d53d-166">Kontrollera att nödvändiga enheter definieras i Sales.</span><span class="sxs-lookup"><span data-stu-id="7d53d-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="7d53d-167">En värdemall som har en värdemappning definieras för **oumid.name** till **Säljenhetssymbol**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="7d53d-168">Valfritt: Du kan lägga till följande mappningar för att garantera att försäljningsoffertraderna importeras till Supply Chain Management om det inte finns någon standardinformation från varken kunden eller produkten:</span><span class="sxs-lookup"><span data-stu-id="7d53d-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Supply Chain Management if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="7d53d-169">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="7d53d-170">Det finns inget standrdmallvärde för **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="7d53d-171">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="7d53d-172">Det finns inget standrdmallvärde för **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="7d53d-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="7d53d-173">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="7d53d-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="7d53d-174">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Supply Chain Management.</span></span> <span data-ttu-id="7d53d-175">För närvarande stöder inte den här inställningen integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="7d53d-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="7d53d-176">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7d53d-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Supply Chain Management.</span></span>
> - <span data-ttu-id="7d53d-177">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="7d53d-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="7d53d-178">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="7d53d-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="7d53d-179">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="7d53d-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="7d53d-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="7d53d-180">QuoteHeader</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="7d53d-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="7d53d-182">QuoteLine</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="7d53d-184">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7d53d-184">Related topics</span></span>

[<span data-ttu-id="7d53d-185">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="7d53d-185">Prospect to cash</span></span>](prospect-to-cash.md)

