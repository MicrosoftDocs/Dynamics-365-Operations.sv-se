---
title: "Synkronisera konton från Sales till kunder i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.openlocfilehash: 1fdbeaaba53cd439d9872be78b1cf67cbc5a57b9
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="bbef2-103">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbef2-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="bbef2-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="bbef2-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="bbef2-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="bbef2-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="bbef2-106">Mall och uppgift</span><span class="sxs-lookup"><span data-stu-id="bbef2-106">Template and task</span></span>

<span data-ttu-id="bbef2-107">Följande mallar och underliggande uppgifter används för att synkronisera konton från Sales till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="bbef2-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="bbef2-108">**Mallens namn:** Konton (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="bbef2-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="bbef2-109">**Namnet på aktiviteten i projektet:** - Konton - Konto - Kunder</span><span class="sxs-lookup"><span data-stu-id="bbef2-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="bbef2-110">Synkronisering av uppgifter krävs innan synkronisering av konto/kund: ingen</span><span class="sxs-lookup"><span data-stu-id="bbef2-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="bbef2-111">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="bbef2-111">Entity set</span></span>

| <span data-ttu-id="bbef2-112">Försäljning</span><span class="sxs-lookup"><span data-stu-id="bbef2-112">Sales</span></span>    | <span data-ttu-id="bbef2-113">CDS</span><span class="sxs-lookup"><span data-stu-id="bbef2-113">CDS</span></span>     | <span data-ttu-id="bbef2-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbef2-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="bbef2-115">Konton</span><span class="sxs-lookup"><span data-stu-id="bbef2-115">Accounts</span></span> | <span data-ttu-id="bbef2-116">Konto</span><span class="sxs-lookup"><span data-stu-id="bbef2-116">Account</span></span> | <span data-ttu-id="bbef2-117">Kunder</span><span class="sxs-lookup"><span data-stu-id="bbef2-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="bbef2-118">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="bbef2-118">Entity flow</span></span>

<span data-ttu-id="bbef2-119">Konton hanteras i Sales och synkroniseras till Finance and Operations som kunder.</span><span class="sxs-lookup"><span data-stu-id="bbef2-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="bbef2-120">Egenskapen **hanteras externt** på dessa kunder anges till **Ja** för att spåra kunder som kommer från Sales.</span><span class="sxs-lookup"><span data-stu-id="bbef2-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="bbef2-121">Den här informationen används vid fakturering för att filtrera fakturor som ska synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="bbef2-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="bbef2-122">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="bbef2-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="bbef2-123">Fältet **kontonummer** är tillgängligt på sidan **konto**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="bbef2-124">Det har gjorts en fysisk och en unik nyckel stödja integreringen.</span><span class="sxs-lookup"><span data-stu-id="bbef2-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="bbef2-125">Fysiska nyckeln i CRM-lösningen (Customer Relationship Management) kan påverka kunder som redan använder fältet **kontonummer** men som inte använder unika **kontonummer**-värden för varje konto.</span><span class="sxs-lookup"><span data-stu-id="bbef2-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="bbef2-126">Integrationslösningen stöder för närvarande inte fallet.</span><span class="sxs-lookup"><span data-stu-id="bbef2-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="bbef2-127">När ett nytt konto skapas om ett **kontonummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="bbef2-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="bbef2-128">Värdet består av **ACC** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="bbef2-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="bbef2-129">Här är ett exempel: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="bbef2-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="bbef2-130">När integrationslösningen för Sales används kommer ett uppgraderingsskript angs på fältet **kontonummer** för befintliga konton i Sales.</span><span class="sxs-lookup"><span data-stu-id="bbef2-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="bbef2-131">Om det inte finns några **kontonummer**-värden kommer nummerserien som beskrivits ovan att användas.</span><span class="sxs-lookup"><span data-stu-id="bbef2-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="bbef2-132">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="bbef2-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="bbef2-133">**CustomerGroupId**-mappning från **CDS &gt; Destination** måste uppdateras till ett giltigt värde i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-133">**CustomerGroupId** mapping from **CDS &gt; Destination** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="bbef2-134">Du kan ange ett standardvärde eller du kan ange värdet genom att använda en värdemappning.</span><span class="sxs-lookup"><span data-stu-id="bbef2-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="bbef2-135">Standardmallvärdet är **10**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-135">The default template value is **10**.</span></span>
- <span data-ttu-id="bbef2-136">Fältet **adress landskod** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="bbef2-137">För att undvika problem med synkronisering kan du ange ett standardvärde i mappningen från **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-137">To avoid synchronization errors, you can specify a default value in the mapping from **CDS &gt; Destination**.</span></span> <span data-ttu-id="bbef2-138">Detta standardvärde används sedan om fältet lämnas tomt i Sales.</span><span class="sxs-lookup"><span data-stu-id="bbef2-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="bbef2-139">Standardvärdet för mallen **AddressCountryRegionISOCode** är **USA**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="bbef2-140">Standardvärdet för mallen **DeliveryAddressCountryRegionISOCode** är **USA**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="bbef2-141">Genom att lägga till följande mappningar från **CDS &gt; Destination**, kan du minska antalet manuella uppdateringar som krävs för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="bbef2-142">Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="bbef2-143">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="bbef2-144">En standardplats kan tas antingen från produkten eller från kunden från orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="bbef2-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="bbef2-145">Standardvärdet för mallen **SiteId** är **USA**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="bbef2-146">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="bbef2-147">Ett standardlager kan tas antingen från produkten eller från kunden från orderrubriken i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="bbef2-148">Standardvärdet för mallen **WarehouseId** är **13**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="bbef2-149">**LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbef2-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="bbef2-150">Som standard används språk från orderrubriken från kunden.</span><span class="sxs-lookup"><span data-stu-id="bbef2-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="bbef2-151">Standardvärdet för mallen **LanguageId** är **en-us**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="bbef2-152">Uppdatera CDS organisations-ID (**Organization_OrganizationId**) i **källa -&gt; CDS**-mappning.</span><span class="sxs-lookup"><span data-stu-id="bbef2-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="bbef2-153">Standardmallvärdet är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="bbef2-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="bbef2-154">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="bbef2-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="bbef2-155">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="bbef2-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="bbef2-156">Om du vill mappa dessa fält måste du ställa in en värdemappning.</span><span class="sxs-lookup"><span data-stu-id="bbef2-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="bbef2-157">Värdemappningarna är specifika för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="bbef2-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="bbef2-158">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="bbef2-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mallmappning i dataintegratör](./media/accounts-template-mapping-data-integrator-1.png)

![Mallmappning för konton i dataintegratör](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="bbef2-161">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bbef2-161">Related topics</span></span>

[<span data-ttu-id="bbef2-162">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="bbef2-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="bbef2-163">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbef2-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="bbef2-164">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbef2-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="bbef2-165">Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="bbef2-165">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="bbef2-166">Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="bbef2-166">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)




