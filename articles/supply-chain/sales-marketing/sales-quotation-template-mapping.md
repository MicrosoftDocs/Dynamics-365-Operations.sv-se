---
title: "Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 9117b5af3beff7290816586f63091b12e357339c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="07953-103">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="07953-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="07953-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="07953-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="07953-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="07953-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="07953-106">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="07953-106">Template and tasks</span></span>

<span data-ttu-id="07953-107">Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="07953-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="07953-108">**Mallens namn:** försäljningsofferter (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="07953-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="07953-109">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="07953-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="07953-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="07953-110">QuoteHeader</span></span>
    - <span data-ttu-id="07953-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="07953-111">QuoteLine</span></span>

<span data-ttu-id="07953-112">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="07953-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="07953-113">Produkter (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="07953-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="07953-114">Konton (Sales till Fin and Ops) (vid behov)</span><span class="sxs-lookup"><span data-stu-id="07953-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="07953-115">Kontakter till kunder (Sales till Fin and Ops) (vid behov)</span><span class="sxs-lookup"><span data-stu-id="07953-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="07953-116">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="07953-116">Entity set</span></span>

| <span data-ttu-id="07953-117">Försäljning</span><span class="sxs-lookup"><span data-stu-id="07953-117">Sales</span></span>        | <span data-ttu-id="07953-118">CDS</span><span class="sxs-lookup"><span data-stu-id="07953-118">CDS</span></span>           | <span data-ttu-id="07953-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="07953-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="07953-120">Citat</span><span class="sxs-lookup"><span data-stu-id="07953-120">Quotes</span></span>       | <span data-ttu-id="07953-121">Offert</span><span class="sxs-lookup"><span data-stu-id="07953-121">Quotation</span></span>     | <span data-ttu-id="07953-122">Försäljningsoffertrubriker</span><span class="sxs-lookup"><span data-stu-id="07953-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="07953-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="07953-123">QuoteDetails</span></span> | <span data-ttu-id="07953-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="07953-124">QuotationLine</span></span> | <span data-ttu-id="07953-125">Försäljningsoffertrader för CDS</span><span class="sxs-lookup"><span data-stu-id="07953-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="07953-126">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="07953-126">Entity flow</span></span>

<span data-ttu-id="07953-127">Försäljningsofferter skapas i Sales och synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="07953-128">Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="07953-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="07953-129">Alla produkter på försäljningsoffertraderna hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="07953-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="07953-130">Försäljningsofferten är aktiv eller aktiverad.</span><span class="sxs-lookup"><span data-stu-id="07953-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="07953-131">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="07953-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="07953-132">Fältet **Har endast externt hanterade produkter** har lagts till offertentiteten för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter.</span><span class="sxs-lookup"><span data-stu-id="07953-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="07953-133">Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="07953-134">Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="07953-135">Alla produkter och rader på offerten uppdateras med informationen **Har endast externt hanterade produkter** från offerthuvudet.</span><span class="sxs-lookup"><span data-stu-id="07953-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="07953-136">Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på offertradentiteten.</span><span class="sxs-lookup"><span data-stu-id="07953-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="07953-137">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="07953-138">Den här inställningen stöder inte integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="07953-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="07953-139">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="07953-140">I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="07953-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="07953-141">**Skrivskyddade fält på försäljningsoffertens huvud:** rabatt % rabatt, Fraktbelopp</span><span class="sxs-lookup"><span data-stu-id="07953-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="07953-142">**Skrivskyddade fält på försäljningsoffertraderna:** moms</span><span class="sxs-lookup"><span data-stu-id="07953-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="07953-143">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="07953-143">Preconditions and mapping setup</span></span>

<span data-ttu-id="07953-144">Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar systemen med följande inställning:</span><span class="sxs-lookup"><span data-stu-id="07953-144">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="07953-145">Inställningar i Sales</span><span class="sxs-lookup"><span data-stu-id="07953-145">Setup in Sales</span></span>

- <span data-ttu-id="07953-146">Gå till **Inställningar** &gt; **Administration** &gt; **Systeminställningar** &gt; **Sales** och se till att fältet **Metod för rabattberäkning** har angetts som **Per enhet**.</span><span class="sxs-lookup"><span data-stu-id="07953-146">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="07953-147">Den här inställningen hjälper till att garantera att radartikelrabatt från Sales motsvarar inställningen i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-147">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="07953-148">I annat fall kommer inte rabatten att vara korrekt i Finance and Operations, eftersom Finance and Operations läser rabatten som en rabatt per enhet även om den vore en rabatt per rad i Sales.</span><span class="sxs-lookup"><span data-stu-id="07953-148">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="07953-149">Inställningar i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="07953-149">Setup in Finance and Operations</span></span>

- <span data-ttu-id="07953-150">Gå till **Kundreskontra** &gt; **Inställningar** &gt; **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="07953-150">Go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="07953-151">På fliken **nummerserie** markerar du nummerserien för försäljningsofferter och klickar sedan på **Visa detaljer**.</span><span class="sxs-lookup"><span data-stu-id="07953-151">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="07953-152">Sedan under **allmänna inställningar**, anger du fältet **manuell** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="07953-152">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="07953-153">Gå till **Kundreskontra** &gt; **Inställningar** &gt; **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="07953-153">Go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="07953-154">Klicka sedan på fliken **försändelser** och ange fältet **Leveransdatumkontroll** till **ingen**.</span><span class="sxs-lookup"><span data-stu-id="07953-154">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="07953-155">Den här inställningen förhindrar synkroniseringsfel för försäljningsofferter.</span><span class="sxs-lookup"><span data-stu-id="07953-155">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="07953-156">Inställningar i dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="07953-156">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="07953-157">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="07953-157">QuoteHeader</span></span>

- <span data-ttu-id="07953-158">Fältet **begärt leveransdatum** krävs i Finance and Operations och men synkroniseringen misslyckas om fältet lämnas tomt.</span><span class="sxs-lookup"><span data-stu-id="07953-158">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="07953-159">För att undvika det här problemet om fältet är tomt kan ett standarddatum hämtas från **källa &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="07953-159">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="07953-160">Datumet ska uppdateras till ett önskat värde.</span><span class="sxs-lookup"><span data-stu-id="07953-160">The date should be updated to a preferred value.</span></span> <span data-ttu-id="07953-161">För närvarande kan du inte ange ett värde som **idag** för att representera dagens datum.</span><span class="sxs-lookup"><span data-stu-id="07953-161">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="07953-162">Du måste ange ett specifikt datum.</span><span class="sxs-lookup"><span data-stu-id="07953-162">You must enter a specific date.</span></span> <span data-ttu-id="07953-163">Standardvärdemallen för **begärt leveransdatum** är **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="07953-163">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="07953-164">Fältet **adress landskod** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-164">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="07953-165">Du kan ange ett standardvärde som ska användas om fältet lämnas tomt i Sales om du vill förhindra synkroniseringsfel.</span><span class="sxs-lookup"><span data-stu-id="07953-165">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="07953-166">Standardvärdet är också användbart eftersom du inte behöver ange ett värde i fältet **land** för lokala adresser.</span><span class="sxs-lookup"><span data-stu-id="07953-166">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="07953-167">Det finns inget standardmallvärde för **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="07953-167">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="07953-168">Uppdatera mappning för **CDS-organisations-ID** i **källa &gt; CDD** så att den matchar **CDS-organisation** i organisationsentiteten:</span><span class="sxs-lookup"><span data-stu-id="07953-168">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="07953-169">Standardvärdet för mallen **Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="07953-169">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="07953-170">Standardvärdet för mallen **Account_Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="07953-170">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="07953-171">Standardvärdet för mallen **InvoiceAccount_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="07953-171">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="07953-172">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="07953-172">QuoteLine</span></span>

- <span data-ttu-id="07953-173">Uppdatera mappning för **CDS-organisations-ID** i **källa &gt; CDD** så att den matchar **CDS-organisation** i organisationsentiteten:</span><span class="sxs-lookup"><span data-stu-id="07953-173">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="07953-174">Standardvärdet för mallen **Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="07953-174">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="07953-175">Standardvärdet för mallen **Product_Organization_Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="07953-175">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="07953-176">Standardvärdet för mallen **Quotation_Organization_Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="07953-176">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="07953-177">Fältet **begärt leveransdatum** krävs i Finance and Operations och men synkroniseringen misslyckas om fältet lämnas tomt.</span><span class="sxs-lookup"><span data-stu-id="07953-177">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="07953-178">För att undvika det här problemet om fältet är tomt kan ett standarddatum hämtas från **källa &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="07953-178">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="07953-179">Datumet ska uppdateras till ett önskat värde.</span><span class="sxs-lookup"><span data-stu-id="07953-179">The date should be updated to a preferred value.</span></span> <span data-ttu-id="07953-180">För närvarande kan du inte ange ett värde som **idag** för att representera dagens datum.</span><span class="sxs-lookup"><span data-stu-id="07953-180">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="07953-181">Du måste ange ett specifikt datum.</span><span class="sxs-lookup"><span data-stu-id="07953-181">You must enter a specific date.</span></span> <span data-ttu-id="07953-182">Standardvärdemallen för **begärt leveransdatum** är **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="07953-182">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="07953-183">Du kan lägga till följande mappningar från **CDS &gt; Destination** för att garantera att offertraderna importeras till Finance and Operation om det inte finns någon standardinformation från varken kunden eller produkten:</span><span class="sxs-lookup"><span data-stu-id="07953-183">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="07953-184">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-184">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="07953-185">Det finns inget standrdmallvärde för **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="07953-185">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="07953-186">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-186">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="07953-187">Det finns inget standrdmallvärde för **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="07953-187">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="07953-188">Kontrollera att nödvändig värdemappningen för den säljande enheten (UOM) i  Finance and Operations finns i mappningen **CDS &gt; Destination** för **Quantity_UOM** till **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="07953-188">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="07953-189">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="07953-189">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="07953-190">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-190">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="07953-191">Den här inställningen stöder inte integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="07953-191">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="07953-192">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="07953-192">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="07953-193">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="07953-193">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="07953-194">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="07953-194">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="07953-195">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="07953-195">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="07953-196">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="07953-196">QuoteHeader</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="07953-199">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="07953-199">QuoteLine</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="07953-202">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="07953-202">Related topics</span></span>

[<span data-ttu-id="07953-203">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="07953-203">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="07953-204">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="07953-204">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="07953-205">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="07953-205">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



