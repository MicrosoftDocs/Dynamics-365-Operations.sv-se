---
title: "Synkronisera huvuden och rader i försäljningsofferter direkt från Sales till Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 97536c27dea113cc3c019473f22d1925e7617f8f
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="87e20-103">Synkronisera huvuden och rader i försäljningsofferter direkt från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87e20-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="87e20-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="87e20-105">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="87e20-105">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="87e20-106">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="87e20-106">Template and tasks</span></span>

<span data-ttu-id="87e20-107">Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader direkt i försäljningsofferter från Sales till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="87e20-107">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="87e20-108">**Namnet på mallen i dataintegrering:** försäljningsofferter (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="87e20-108">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="87e20-109">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="87e20-109">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="87e20-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="87e20-110">QuoteHeader</span></span>
    - <span data-ttu-id="87e20-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="87e20-111">QuoteLine</span></span>

<span data-ttu-id="87e20-112">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="87e20-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="87e20-113">Produkter (Fin and Ops till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="87e20-113">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="87e20-114">Konton (Sales till Fin and Ops) - Direkt (vid behov)</span><span class="sxs-lookup"><span data-stu-id="87e20-114">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="87e20-115">Kontakter till kunder (Sales till Fin and Ops) - Direkt (vid behov)</span><span class="sxs-lookup"><span data-stu-id="87e20-115">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="87e20-116">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="87e20-116">Entity set</span></span>

| <span data-ttu-id="87e20-117">Försäljning</span><span class="sxs-lookup"><span data-stu-id="87e20-117">Sales</span></span>        | <span data-ttu-id="87e20-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="87e20-118">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="87e20-119">Citat</span><span class="sxs-lookup"><span data-stu-id="87e20-119">Quotes</span></span>       | <span data-ttu-id="87e20-120">CDS-försäljningsofferrubrik</span><span class="sxs-lookup"><span data-stu-id="87e20-120">CDS sales quotation header</span></span> |
| <span data-ttu-id="87e20-121">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="87e20-121">QuoteDetails</span></span> | <span data-ttu-id="87e20-122">Försäljningsoffertrader för CDS</span><span class="sxs-lookup"><span data-stu-id="87e20-122">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="87e20-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="87e20-123">Entity flow</span></span>

<span data-ttu-id="87e20-124">Försäljningsofferter skapas i Sales och synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-124">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="87e20-125">Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="87e20-125">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="87e20-126">Alla offertprodukter på försäljningsofferna hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="87e20-126">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="87e20-127">När du har klickat på **aktivera offert**, är försäljningsofferten aktiv.</span><span class="sxs-lookup"><span data-stu-id="87e20-127">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="87e20-128">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="87e20-128">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="87e20-129">Fältet **Har endast externt hanterade produkter** har lagts till entiteten **Offert** för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter.</span><span class="sxs-lookup"><span data-stu-id="87e20-129">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="87e20-130">Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-130">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="87e20-131">Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-131">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="87e20-132">Alla offertprodukter på försäljningsofferten uppdateras med informationen **Har endast externt hanterade produkter** från försäljningsofferthuvudet.</span><span class="sxs-lookup"><span data-stu-id="87e20-132">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="87e20-133">Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på entiteten **Offertdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="87e20-133">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="87e20-134">En rabatt kan läggas till i offertprodukten och synkroniseras med Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-134">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="87e20-135">Fälten **rabatt**, **tillägg**, och **moms** på rubriken styrs av en inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-135">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="87e20-136">För närvarande stöder inte den här inställningen integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="87e20-136">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="87e20-137">I den aktuella designen underhålls fälten **pris**, **rabatt**, **tillägg**, och **moms** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-137">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="87e20-138">I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="87e20-138">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="87e20-139">Skrivskyddade fält på försäljningsoffertens huvud: **Rabatt %**, **Rabatt** och **Fraktbelopp**</span><span class="sxs-lookup"><span data-stu-id="87e20-139">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="87e20-140">Skrivskyddade fält på offertprodukter: **moms**</span><span class="sxs-lookup"><span data-stu-id="87e20-140">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="87e20-141">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="87e20-141">Preconditions and mapping setup</span></span>

<span data-ttu-id="87e20-142">Innan försäljningsofferter synkroniseras är det viktigt att du uppdaterar följande inställningar.</span><span class="sxs-lookup"><span data-stu-id="87e20-142">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="87e20-143">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="87e20-143">Setup in Sales</span></span>

- <span data-ttu-id="87e20-144">Se till att behörigheterna ställs in för teamet som användaren från din anslutning som anges i Sales har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="87e20-144">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="87e20-145">Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst.</span><span class="sxs-lookup"><span data-stu-id="87e20-145">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="87e20-146">Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.</span><span class="sxs-lookup"><span data-stu-id="87e20-146">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="87e20-147">Om du vill ställa in behörigheter för gruppen gå till **inställningar**&gt;**säkerhet**&gt;**team**, och välj relevant team.</span><span class="sxs-lookup"><span data-stu-id="87e20-147">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="87e20-148">Välj **hantera roller**, och välj sedan en roll med behörigheter, t.ex. **systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="87e20-148">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="87e20-149">Gå till **inställningar** &gt; **Administration** &gt; **systeminställningar** &gt; **Sales** och säkerställ att följande inställningar används:</span><span class="sxs-lookup"><span data-stu-id="87e20-149">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="87e20-150">Alternativet **Använd systemets prisberäkningssystem** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="87e20-150">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="87e20-151">Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.</span><span class="sxs-lookup"><span data-stu-id="87e20-151">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="87e20-152">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="87e20-152">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="87e20-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="87e20-153">QuoteHeader</span></span>

- <span data-ttu-id="87e20-154">Kontrollera att nödvändig mappning finns i **Shipto\_land** till **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="87e20-154">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="87e20-155">Du kan definiera ett standardvärde som används om värdet är tomt i värdemappningen.</span><span class="sxs-lookup"><span data-stu-id="87e20-155">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="87e20-156">Lämna bara värdet på vänster sida tomt och ange höger sida till önskat land eller region.</span><span class="sxs-lookup"><span data-stu-id="87e20-156">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="87e20-157">På så sätt kan du inte ange land eller region för nationella order.</span><span class="sxs-lookup"><span data-stu-id="87e20-157">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="87e20-158">Mallvärdet är en värdemappning där flera länder eller regioner som mappas och där ett tomt värde är lika med **US**.</span><span class="sxs-lookup"><span data-stu-id="87e20-158">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="87e20-159">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="87e20-159">QuoteLine</span></span>

- <span data-ttu-id="87e20-160">Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-160">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="87e20-161">Kontrollera att nödvändiga enheter definieras i Sales.</span><span class="sxs-lookup"><span data-stu-id="87e20-161">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="87e20-162">En värdemall som har en värdemappning definieras för **oumid.name** till **Säljenhetssymbol**.</span><span class="sxs-lookup"><span data-stu-id="87e20-162">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="87e20-163">Valfritt: Du kan lägga till följande mappningar för att garantera att försäljningsoffertraderna importeras till Finance and Operations om det inte finns någon standardinformation från varken kunden eller produkten:</span><span class="sxs-lookup"><span data-stu-id="87e20-163">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="87e20-164">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-164">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="87e20-165">Det finns inget standrdmallvärde för **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="87e20-165">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="87e20-166">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-166">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="87e20-167">Det finns inget standrdmallvärde för **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="87e20-167">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="87e20-168">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="87e20-168">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="87e20-169">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-169">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="87e20-170">För närvarande stöder inte den här inställningen integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="87e20-170">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="87e20-171">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="87e20-171">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="87e20-172">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="87e20-172">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="87e20-173">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="87e20-173">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="87e20-174">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="87e20-174">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="87e20-175">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="87e20-175">QuoteHeader</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="87e20-177">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="87e20-177">QuoteLine</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="87e20-179">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="87e20-179">Related topics</span></span>

[<span data-ttu-id="87e20-180">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="87e20-180">Prospect to cash</span></span>](prospect-to-cash.md)


