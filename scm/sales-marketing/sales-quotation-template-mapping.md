---
title: "Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 172a3da1b6d90a25ea9ebd14265e70e4a6f9bd70
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="4295f-103">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4295f-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="4295f-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="4295f-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="4295f-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="4295f-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="4295f-106">Mall och uppgifter</span><span class="sxs-lookup"><span data-stu-id="4295f-106">Template and tasks</span></span>

<span data-ttu-id="4295f-107">Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="4295f-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="4295f-108">**Mallens namn:** försäljningsofferter (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="4295f-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="4295f-109">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="4295f-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="4295f-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="4295f-110">QuoteHeader</span></span>
    - <span data-ttu-id="4295f-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="4295f-111">QuoteLine</span></span>

<span data-ttu-id="4295f-112">Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="4295f-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="4295f-113">Produkter</span><span class="sxs-lookup"><span data-stu-id="4295f-113">Products</span></span>
- <span data-ttu-id="4295f-114">Konton (om de används)</span><span class="sxs-lookup"><span data-stu-id="4295f-114">Accounts (if used)</span></span>
- <span data-ttu-id="4295f-115">Kontakter (om de används)</span><span class="sxs-lookup"><span data-stu-id="4295f-115">Contacts (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="4295f-116">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="4295f-116">Entity set</span></span>

| <span data-ttu-id="4295f-117">Försäljning</span><span class="sxs-lookup"><span data-stu-id="4295f-117">Sales</span></span>        | <span data-ttu-id="4295f-118">CDS</span><span class="sxs-lookup"><span data-stu-id="4295f-118">CDS</span></span>           | <span data-ttu-id="4295f-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4295f-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="4295f-120">Citat</span><span class="sxs-lookup"><span data-stu-id="4295f-120">Quotes</span></span>       | <span data-ttu-id="4295f-121">Offert</span><span class="sxs-lookup"><span data-stu-id="4295f-121">Quotation</span></span>     | <span data-ttu-id="4295f-122">Försäljningsoffertrubriker</span><span class="sxs-lookup"><span data-stu-id="4295f-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="4295f-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="4295f-123">QuoteDetails</span></span> | <span data-ttu-id="4295f-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="4295f-124">QuotationLine</span></span> | <span data-ttu-id="4295f-125">Försäljningsoffertrader för CDS</span><span class="sxs-lookup"><span data-stu-id="4295f-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="4295f-126">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="4295f-126">Entity flow</span></span>

<span data-ttu-id="4295f-127">Försäljningsofferter skapas i Sales och synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="4295f-128">Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:</span><span class="sxs-lookup"><span data-stu-id="4295f-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="4295f-129">Alla produkter på försäljningsoffertraderna hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="4295f-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="4295f-130">Försäljningsofferten är aktiv eller aktiverad.</span><span class="sxs-lookup"><span data-stu-id="4295f-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="4295f-131">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="4295f-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="4295f-132">Fältet **Har endast externt hanterade produkter** har lagts till offertentiteten för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter.</span><span class="sxs-lookup"><span data-stu-id="4295f-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="4295f-133">Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="4295f-134">Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="4295f-135">Alla produkter och rader på offerten uppdateras med informationen **Har endast externt hanterade produkter** från offerthuvudet.</span><span class="sxs-lookup"><span data-stu-id="4295f-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="4295f-136">Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på offertradentiteten.</span><span class="sxs-lookup"><span data-stu-id="4295f-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="4295f-137">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="4295f-138">Den här inställningen stöder inte integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="4295f-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="4295f-139">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="4295f-140">I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="4295f-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="4295f-141">**Skrivskyddade fält på försäljningsoffertens huvud:** rabatt % rabatt, Fraktbelopp</span><span class="sxs-lookup"><span data-stu-id="4295f-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="4295f-142">**Skrivskyddade fält på försäljningsoffertraderna:** moms</span><span class="sxs-lookup"><span data-stu-id="4295f-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="4295f-143">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4295f-143">Preconditions and mapping setup</span></span>

- <span data-ttu-id="4295f-144">Innan du synkroniserar försäljningsofferter, går du i Sales tilll **Inställningar** &gt; **Administration** &gt; **Systeminställningar** &gt; **Försäljning** och kontrollerar att fältet **rabattberäkningsmetod** är inställt på **Per enhet**.</span><span class="sxs-lookup"><span data-stu-id="4295f-144">Before you synchronize sales quotations, in Sales, go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="4295f-145">Den här inställningen hjälper till att garantera att radartikelrabatt från Sales motsvarar inställningen i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-145">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="4295f-146">I annat fall kommer inte rabatten att vara korrekt i Finance and Operations, eftersom Finance and Operations läser rabatten som en rabatt per enhet även om den vore en rabatt per rad i Sales.</span><span class="sxs-lookup"><span data-stu-id="4295f-146">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>
- <span data-ttu-id="4295f-147">I Finance and Operations, gå till **kundreskontra** &gt; **inställningar** &gt; **kundreskontraparametrar**.</span><span class="sxs-lookup"><span data-stu-id="4295f-147">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="4295f-148">På fliken **nummerserie** markerar du nummerserien för försäljningsofferter och klickar sedan på **Visa detaljer**.</span><span class="sxs-lookup"><span data-stu-id="4295f-148">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="4295f-149">Sedan under **allmänna inställningar**, anger du fältet **manuell** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4295f-149">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="4295f-150">I Finance and Operations, gå till **kundreskontra** &gt; **inställningar** &gt; **kundreskontraparametrar**.</span><span class="sxs-lookup"><span data-stu-id="4295f-150">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="4295f-151">Klicka sedan på fliken **försändelser** och ange fältet **Leveransdatumkontroll** till **ingen**.</span><span class="sxs-lookup"><span data-stu-id="4295f-151">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="4295f-152">Den här inställningen förhindrar synkroniseringsfel för försäljningsofferter.</span><span class="sxs-lookup"><span data-stu-id="4295f-152">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="4295f-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="4295f-153">QuoteHeader</span></span>

- <span data-ttu-id="4295f-154">Fältet **begärt leveransdatum** krävs i Finance and Operations och men synkroniseringen misslyckas om fältet lämnas tomt.</span><span class="sxs-lookup"><span data-stu-id="4295f-154">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="4295f-155">För att undvika det här problemet om fältet är tomt kan ett standarddatum hämtas från **källa &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="4295f-155">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="4295f-156">Datumet ska uppdateras till ett önskat värde.</span><span class="sxs-lookup"><span data-stu-id="4295f-156">The date should be updated to a preferred value.</span></span> <span data-ttu-id="4295f-157">För närvarande kan du inte ange ett värde som **idag** för att representera dagens datum.</span><span class="sxs-lookup"><span data-stu-id="4295f-157">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="4295f-158">Du måste ange ett specifikt datum.</span><span class="sxs-lookup"><span data-stu-id="4295f-158">You must enter a specific date.</span></span> <span data-ttu-id="4295f-159">Standardvärdemallen för **begärt leveransdatum** är **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="4295f-159">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="4295f-160">Fältet **adress landskod** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-160">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="4295f-161">Du kan ange ett standardvärde som ska användas om fältet lämnas tomt i Sales om du vill förhindra synkroniseringsfel.</span><span class="sxs-lookup"><span data-stu-id="4295f-161">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="4295f-162">Standardvärdet är också användbart eftersom du inte behöver ange ett värde i fältet **land** för lokala adresser.</span><span class="sxs-lookup"><span data-stu-id="4295f-162">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="4295f-163">Det finns inget standardmallvärde för **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="4295f-163">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="4295f-164">Uppdatera mappning för **CDS-organisations-ID** i **källa &gt; CDD** så att den matchar **CDS-organisation** i organisationsentiteten:</span><span class="sxs-lookup"><span data-stu-id="4295f-164">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="4295f-165">Standardvärdet för mallen **Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="4295f-165">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="4295f-166">Standardvärdet för mallen **Account_Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="4295f-166">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="4295f-167">Standardvärdet för mallen **InvoiceAccount_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="4295f-167">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

### <a name="quoteline"></a><span data-ttu-id="4295f-168">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="4295f-168">QuoteLine</span></span>

- <span data-ttu-id="4295f-169">Uppdatera mappning för **CDS-organisations-ID** i **källa &gt; CDD** så att den matchar **CDS-organisation** i organisationsentiteten:</span><span class="sxs-lookup"><span data-stu-id="4295f-169">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="4295f-170">Standardvärdet för mallen **Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="4295f-170">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="4295f-171">Standardvärdet för mallen **Product_Organization_Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="4295f-171">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="4295f-172">Standardvärdet för mallen **Quotation_Organization_Organization_OrganizationId** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="4295f-172">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="4295f-173">Fältet **begärt leveransdatum** krävs i Finance and Operations och men synkroniseringen misslyckas om fältet lämnas tomt.</span><span class="sxs-lookup"><span data-stu-id="4295f-173">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="4295f-174">För att undvika det här problemet om fältet är tomt kan ett standarddatum hämtas från **källa &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="4295f-174">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="4295f-175">Datumet ska uppdateras till ett önskat värde.</span><span class="sxs-lookup"><span data-stu-id="4295f-175">The date should be updated to a preferred value.</span></span> <span data-ttu-id="4295f-176">För närvarande kan du inte ange ett värde som **idag** för att representera dagens datum.</span><span class="sxs-lookup"><span data-stu-id="4295f-176">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="4295f-177">Du måste ange ett specifikt datum.</span><span class="sxs-lookup"><span data-stu-id="4295f-177">You must enter a specific date.</span></span> <span data-ttu-id="4295f-178">Standardvärdemallen för **begärt leveransdatum** är **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="4295f-178">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="4295f-179">Du kan lägga till följande mappningar från **CDS &gt; Destination** för att garantera att offertraderna importeras till Finance and Operation om det inte finns någon standardinformation från varken kunden eller produkten:</span><span class="sxs-lookup"><span data-stu-id="4295f-179">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="4295f-180">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-180">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="4295f-181">Det finns inget standrdmallvärde för **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="4295f-181">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="4295f-182">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-182">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="4295f-183">Det finns inget standrdmallvärde för **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="4295f-183">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="4295f-184">Kontrollera att nödvändig värdemappningen för den säljande enheten (UOM) i  Finance and Operations finns i mappningen **CDS &gt; Destination** för **Quantity_UOM** till **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="4295f-184">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="4295f-185">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="4295f-185">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="4295f-186">Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-186">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="4295f-187">Den här inställningen stöder inte integreringsmappning.</span><span class="sxs-lookup"><span data-stu-id="4295f-187">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="4295f-188">I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4295f-188">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="4295f-189">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="4295f-189">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="4295f-190">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="4295f-190">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="4295f-191">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="4295f-191">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="4295f-192">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="4295f-192">QuoteHeader</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="4295f-195">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="4295f-195">QuoteLine</span></span>

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="4295f-198">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4295f-198">Related topics</span></span>

[<span data-ttu-id="4295f-199">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="4295f-199">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="4295f-200">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4295f-200">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="4295f-201">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4295f-201">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



