---
title: "Synkronisera kontakter från Sales till kontakter i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera kontakt (kontakter) och kontakt (kunder) från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.openlocfilehash: 7a856a9460d092925a34a0733f37f89354c2ddf1
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="ea930-103">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ea930-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ea930-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="ea930-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="ea930-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera kontakt (kontakter) och kontakt (kunder) från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="ea930-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ea930-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="ea930-106">Templates and tasks</span></span>

<span data-ttu-id="ea930-107">Följande mallar och underliggande uppgifter används för att synkronisera kontakt (kontakter) i Sales och kontakt (kunder) i Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="ea930-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="ea930-108">**Namn på mallar:**</span><span class="sxs-lookup"><span data-stu-id="ea930-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="ea930-109">Kontakter till kontakt (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ea930-109">Contacts to Contact (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="ea930-110">Kontakter till kund (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ea930-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="ea930-111">**Namn på aktiviteter i projektet:**</span><span class="sxs-lookup"><span data-stu-id="ea930-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="ea930-112">Kontakter</span><span class="sxs-lookup"><span data-stu-id="ea930-112">Contacts</span></span>
    - <span data-ttu-id="ea930-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="ea930-113">ContactToCustomer</span></span>

<span data-ttu-id="ea930-114">Följande synkroniseringsuppgift krävs före kontaktsynkronisering: konton (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ea930-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="ea930-115">Entitetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="ea930-115">Entity sets</span></span>

| <span data-ttu-id="ea930-116">Försäljning</span><span class="sxs-lookup"><span data-stu-id="ea930-116">Sales</span></span>    | <span data-ttu-id="ea930-117">CDS</span><span class="sxs-lookup"><span data-stu-id="ea930-117">CDS</span></span>     | <span data-ttu-id="ea930-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ea930-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="ea930-119">Kontakter</span><span class="sxs-lookup"><span data-stu-id="ea930-119">Contacts</span></span> | <span data-ttu-id="ea930-120">Kontakt</span><span class="sxs-lookup"><span data-stu-id="ea930-120">Contact</span></span> | <span data-ttu-id="ea930-121">CDS-kontakter</span><span class="sxs-lookup"><span data-stu-id="ea930-121">CDS Contacts</span></span>           |
| <span data-ttu-id="ea930-122">Kontakter</span><span class="sxs-lookup"><span data-stu-id="ea930-122">Contacts</span></span> | <span data-ttu-id="ea930-123">Konto</span><span class="sxs-lookup"><span data-stu-id="ea930-123">Account</span></span> | <span data-ttu-id="ea930-124">Kunder V2</span><span class="sxs-lookup"><span data-stu-id="ea930-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="ea930-125">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="ea930-125">Entity flow</span></span>

<span data-ttu-id="ea930-126">Kontakter hanteras i Sales och synkroniseras till Common Data Service (CDS) och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="ea930-127">En kontakt i Sales kan bli en kontakt i CDS och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="ea930-128">Alternativt kan den bli ett konto i CDS och en kund i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="ea930-129">Du tar reda på om en kontakt ska öppnas i försäljning för synkronisering av CDS och Finance and Operations (till exempel kontakter i Sales &gt; kontakter i CDS &gt; kontakter i Finance and Operations), systemet tittar på följande egenskaper på en kontakt i Sales:</span><span class="sxs-lookup"><span data-stu-id="ea930-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="ea930-130">**Synkronisera till konto i CDS och kundinformation i Finance and Operations:** kontakter där **är aktiv kund** anges till **Ja**</span><span class="sxs-lookup"><span data-stu-id="ea930-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="ea930-131">**Synkronisera kontakt i CDS och kontaktinformation i Finance and Operations:** kontakter där **är aktiv kund** anges till **nr** och **företag** (överordnat konto/kontakt) leder till ett konto (inte en kontakt)</span><span class="sxs-lookup"><span data-stu-id="ea930-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ea930-132">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="ea930-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="ea930-133">Ett nytt fält för **är aktiv kund** har lagts till kontakten.</span><span class="sxs-lookup"><span data-stu-id="ea930-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="ea930-134">Det här fältet används för att urskilja kontakter vars försäljningsaktivitet och kontakter som inte har en försäljningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="ea930-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="ea930-135">**Är aktiv kund** anges till **Ja** endast för kontakter som har relaterade offerter, order eller fakturor.</span><span class="sxs-lookup"><span data-stu-id="ea930-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="ea930-136">Endast dessa kontakter synkroniseras till Finance and Operations som kunder.</span><span class="sxs-lookup"><span data-stu-id="ea930-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="ea930-137">Ett nytt fält för **IsCompanyAnAccount** har lagts till kontakten.</span><span class="sxs-lookup"><span data-stu-id="ea930-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="ea930-138">Det här fältet används för att ange om en kontakt är kopplad till ett företag (överordnat konto eller kontakt) av typen **konto**.</span><span class="sxs-lookup"><span data-stu-id="ea930-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="ea930-139">Denna information används för att identifiera kontakter som ska synkroniseras mot Finance and Operations som kontakter.</span><span class="sxs-lookup"><span data-stu-id="ea930-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="ea930-140">Ett nytt fält för **kontaktnummer** har lagts till kontakten för att garantera en naturlig och unik nyckel för integration.</span><span class="sxs-lookup"><span data-stu-id="ea930-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="ea930-141">När en ny kontakt skapas kommer **kontaktnummer**-värde genereras automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="ea930-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="ea930-142">Värdet består av **CON** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="ea930-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="ea930-143">Här är ett exempel: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="ea930-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="ea930-144">När integrationslösningen för Sales läggs till i Sales, anger ett uppgraderingsskript fältet **kontaktnummer** för befintliga kontakter med nummerserien som beskrevs tidigare.</span><span class="sxs-lookup"><span data-stu-id="ea930-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="ea930-145">Uppgraderingsskriptet anger också fältet **är aktiv kund** till **Ja** för alla kontakter som har försäljningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="ea930-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="ea930-146">I Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ea930-146">In Finance and Operations</span></span> 

<span data-ttu-id="ea930-147">Kontakter är märkta med egenskapen **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="ea930-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="ea930-148">Den här egenskapen anger att en kontakt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="ea930-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="ea930-149">I det här fallet underhålls externt underhållna kontakter i Sales.</span><span class="sxs-lookup"><span data-stu-id="ea930-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ea930-150">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="ea930-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="ea930-151">Kontakt till kontakt</span><span class="sxs-lookup"><span data-stu-id="ea930-151">Contact to Contact</span></span>

- <span data-ttu-id="ea930-152">Uppdatera **CDS organisations-ID** i **källa -&gt; CDS**-mappning.</span><span class="sxs-lookup"><span data-stu-id="ea930-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="ea930-153">Standardvärdet för mallen **Organization_OrganizationId [Organization ID]** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ea930-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="ea930-154">Standardvärdet för mallen **PrimaryAccount_Organization_OrganizationId [Organization ID]** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ea930-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="ea930-155">Fältet **adress landskod** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="ea930-156">För att undvika problem med synkronisering kan du ange ett standardvärde i **CDS &gt;Operations**-mappning.</span><span class="sxs-lookup"><span data-stu-id="ea930-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="ea930-157">Detta standardvärde används sedan om fältet lämnas tomt i Sales.</span><span class="sxs-lookup"><span data-stu-id="ea930-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="ea930-158">Standardvärdet för mallen **PrimaryAddressCountryRegionISOCode** är **USA**.</span><span class="sxs-lookup"><span data-stu-id="ea930-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="ea930-159">Kontrollera att det finns ett värde för följande fält i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="ea930-160">Om informationen inte krävs i Finance and Operations kan du ta bort mappningen från **CDS &gt;Destination**-mappning.</span><span class="sxs-lookup"><span data-stu-id="ea930-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="ea930-161">**Fältnamn i Finance and Operations:** beslut</span><span class="sxs-lookup"><span data-stu-id="ea930-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="ea930-162">**Mappning:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="ea930-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="ea930-163">Kontakt till kund</span><span class="sxs-lookup"><span data-stu-id="ea930-163">Contact to Customer</span></span>

- <span data-ttu-id="ea930-164">Uppdatera **CDS organisations-ID** i **källa -&gt; CDS**-mappning.</span><span class="sxs-lookup"><span data-stu-id="ea930-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="ea930-165">Standardvärdet för mallen **Organization_OrganizationId [Organization ID]** är **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ea930-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="ea930-166">Fältet **adress landskod** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="ea930-167">För att undvika problem med synkronisering kan du ange ett standardvärde i **CDS &gt;Destination**-mappning.</span><span class="sxs-lookup"><span data-stu-id="ea930-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="ea930-168">Detta standardvärde används sedan om fältet lämnas tomt i Sales.</span><span class="sxs-lookup"><span data-stu-id="ea930-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="ea930-169">Standardvärdet för mallen **PrimaryAddressCountryRegionISOCode** är **USA**.</span><span class="sxs-lookup"><span data-stu-id="ea930-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="ea930-170">**Kundgrupp** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="ea930-171">För att undvika problem med synkronisering kan du ange ett standardvärde i **CDS &gt;Destination**-mappning.</span><span class="sxs-lookup"><span data-stu-id="ea930-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="ea930-172">Detta standardvärde används sedan om fältet lämnas tomt i Sales.</span><span class="sxs-lookup"><span data-stu-id="ea930-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="ea930-173">Standardmallvärdet för **CustomerGroupId** är **10**.</span><span class="sxs-lookup"><span data-stu-id="ea930-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="ea930-174">Genom att lägga till följande mappningar från **CDS &gt; Destination**, kan du minska antalet manuella uppdateringar som krävs för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="ea930-175">Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.</span><span class="sxs-lookup"><span data-stu-id="ea930-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="ea930-176">**SiteId** - en standardplats kan också definieras på produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="ea930-177">En plats måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ea930-178">Ett mallvärde för **SiteId** är inte definierad.</span><span class="sxs-lookup"><span data-stu-id="ea930-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="ea930-179">**WarehouseId** - ett standardlagerställe kan också definieras på produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="ea930-180">Ett lagerställe måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ea930-181">Ett mallvärde för **WarehouseId** är inte definierad.</span><span class="sxs-lookup"><span data-stu-id="ea930-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="ea930-182">**LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ea930-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ea930-183">Standardvärdet för mallen **LanguageId** är **en-us**.</span><span class="sxs-lookup"><span data-stu-id="ea930-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="ea930-184">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="ea930-184">Template mapping in data integrator</span></span>

<span data-ttu-id="ea930-185">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="ea930-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="ea930-186">Kontakt till kontakt</span><span class="sxs-lookup"><span data-stu-id="ea930-186">Contact to Contact</span></span>

![Mallmappning i dataintegratör](./media/contacts-template-mapping-data-integrator-1.png)

![Mallmappning för kontakter i dataintegratör](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="ea930-189">Kontakt till kund</span><span class="sxs-lookup"><span data-stu-id="ea930-189">Contact to Customer</span></span>

![Mallmappning i dataintegratör](./media/contacts-template-mapping-data-integrator-3.png)

![Mallmappning för kontakter i dataintegratör](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="ea930-192">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ea930-192">Related topics</span></span>

[<span data-ttu-id="ea930-193">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="ea930-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="ea930-194">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ea930-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="ea930-195">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ea930-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

