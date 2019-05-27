---
title: Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera entiteterna Kontakt (kontakter) och Kontakt (kunder) från Microsoft Dynamics 365 for Sales, till Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 5363c64cd1a475f0047c079d9166718ddc765f02
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562379"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="b22f6-103">Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b22f6-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="b22f6-104">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Common Data Service för appar](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="b22f6-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="b22f6-105">I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera entiteterna Kontakt (kontakter) och Kontakt (kunder) direkt från Microsoft Dynamics 365 for Sales, till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="b22f6-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="b22f6-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="b22f6-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="b22f6-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="b22f6-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="b22f6-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="b22f6-109">Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="b22f6-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="b22f6-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="b22f6-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b22f6-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="b22f6-111">Templates and tasks</span></span>

<span data-ttu-id="b22f6-112">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="b22f6-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="b22f6-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="b22f6-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="b22f6-114">Följande mallar och underliggande uppgifter används för att synkronisera entiteterna kontakt (kontakter) i Sales och entiteterna kontakt (kunder) i Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="b22f6-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="b22f6-115">**Namn på mallar i dataintegrering:**</span><span class="sxs-lookup"><span data-stu-id="b22f6-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="b22f6-116">Kontakter (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="b22f6-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="b22f6-117">Kontakter till kund (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="b22f6-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="b22f6-118">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="b22f6-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="b22f6-119">Kontakter</span><span class="sxs-lookup"><span data-stu-id="b22f6-119">Contacts</span></span>
    - <span data-ttu-id="b22f6-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="b22f6-120">ContactToCustomer</span></span>

<span data-ttu-id="b22f6-121">Följande synkroniseringsuppgift krävs före kontaktsynkronisering: konton (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="b22f6-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="b22f6-122">Entitetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="b22f6-122">Entity sets</span></span>

| <span data-ttu-id="b22f6-123">Försäljning</span><span class="sxs-lookup"><span data-stu-id="b22f6-123">Sales</span></span>    | <span data-ttu-id="b22f6-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b22f6-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="b22f6-125">Kontakter</span><span class="sxs-lookup"><span data-stu-id="b22f6-125">Contacts</span></span> | <span data-ttu-id="b22f6-126">CDS-kontakter</span><span class="sxs-lookup"><span data-stu-id="b22f6-126">CDS Contacts</span></span>           |
| <span data-ttu-id="b22f6-127">Kontakter</span><span class="sxs-lookup"><span data-stu-id="b22f6-127">Contacts</span></span> | <span data-ttu-id="b22f6-128">Kunder V2</span><span class="sxs-lookup"><span data-stu-id="b22f6-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="b22f6-129">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="b22f6-129">Entity flow</span></span>

<span data-ttu-id="b22f6-130">Kontakter hanteras i Sales och synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="b22f6-131">En kontakt i Sales kan antingen bli en kontakt eller enkund i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="b22f6-132">För att ta reda på om en kontakt i Sales ska synkroniseras mot Finance and Operations som en kontakt eller en kund, tittar systemet på följande egenskaper för en kontakt i Sales:</span><span class="sxs-lookup"><span data-stu-id="b22f6-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="b22f6-133">**Synkronisering till en kund i Finance and Operations:** kontakter där **är aktiv kund** anges till **Ja**</span><span class="sxs-lookup"><span data-stu-id="b22f6-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="b22f6-134">**Synkronisering till en kontakt i Finance and Operations:** kontakter där **är aktiv kund** anges till **nr** och **företag** (överordnat konto/kontakt) leder till ett konto (inte en kontakt)</span><span class="sxs-lookup"><span data-stu-id="b22f6-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="b22f6-135">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="b22f6-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="b22f6-136">Ett nytt fält för **är aktiv kund** har lagts till kontakten.</span><span class="sxs-lookup"><span data-stu-id="b22f6-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="b22f6-137">Det här fältet används för att urskilja kontakter vars försäljningsaktivitet och kontakter som inte har en försäljningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="b22f6-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="b22f6-138">**Är aktiv kund** anges till **Ja** endast för kontakter som har relaterade offerter, order eller fakturor.</span><span class="sxs-lookup"><span data-stu-id="b22f6-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="b22f6-139">Endast dessa kontakter synkroniseras till Finance and Operations som kunder.</span><span class="sxs-lookup"><span data-stu-id="b22f6-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="b22f6-140">Ett nytt fält för **IsCompanyAnAccount** har lagts till kontakten.</span><span class="sxs-lookup"><span data-stu-id="b22f6-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="b22f6-141">Det här fältet indikerar om en kontakt är kopplad till ett företag (överordnat konto/kontakt) av typen **konto**.</span><span class="sxs-lookup"><span data-stu-id="b22f6-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="b22f6-142">Denna information används för att identifiera kontakter som ska synkroniseras mot Finance and Operations som kontakter.</span><span class="sxs-lookup"><span data-stu-id="b22f6-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="b22f6-143">Ett nytt fält för **kontaktnummer** har lagts till kontakten för att garantera en naturlig och unik nyckel för integration.</span><span class="sxs-lookup"><span data-stu-id="b22f6-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="b22f6-144">När en ny kontakt skapas kommer **kontaktnummer**-värde genereras automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="b22f6-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="b22f6-145">Värdet består av **CON** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="b22f6-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="b22f6-146">Här är ett exempel: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="b22f6-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="b22f6-147">När integrationslösningen för Sales används, anger ett uppgraderingsskript fältet **kontaktnummer** för befintliga kontakter med nummerserien som beskrivits tidigare.</span><span class="sxs-lookup"><span data-stu-id="b22f6-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="b22f6-148">Uppgraderingsskriptet anger också fältet **är aktiv kund** till **Ja** för alla kontakter som har försäljningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="b22f6-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="b22f6-149">I Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b22f6-149">In Finance and Operations</span></span>

<span data-ttu-id="b22f6-150">Kontakter är märkta med egenskapen **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="b22f6-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="b22f6-151">Den här egenskapen anger att en kontakt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="b22f6-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="b22f6-152">I det här fallet underhålls externt underhållna kontakter i Sales.</span><span class="sxs-lookup"><span data-stu-id="b22f6-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="b22f6-153">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b22f6-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="b22f6-154">Kontakt till kund</span><span class="sxs-lookup"><span data-stu-id="b22f6-154">Contact to customer</span></span>

- <span data-ttu-id="b22f6-155">**Kundgrupp** krävs i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="b22f6-156">För att undvika problem med synkronisering kan du ange ett standardvärde i mappningen.</span><span class="sxs-lookup"><span data-stu-id="b22f6-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="b22f6-157">Detta standardvärde används sedan om fältet lämnas tomt i Sales.</span><span class="sxs-lookup"><span data-stu-id="b22f6-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="b22f6-158">Standardmallvärdet är **10**.</span><span class="sxs-lookup"><span data-stu-id="b22f6-158">The default template value is **10**.</span></span>

- <span data-ttu-id="b22f6-159">Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="b22f6-160">Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.</span><span class="sxs-lookup"><span data-stu-id="b22f6-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="b22f6-161">**SiteId** - en standardplats kan också definieras på produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="b22f6-162">En plats måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="b22f6-163">Ett mallvärde för **SiteId** är inte definierad.</span><span class="sxs-lookup"><span data-stu-id="b22f6-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="b22f6-164">**WarehouseId** - ett standardlagerställe kan också definieras på produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="b22f6-165">Ett lagerställe måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="b22f6-166">Ett mallvärde för **WarehouseId** är inte definierad.</span><span class="sxs-lookup"><span data-stu-id="b22f6-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="b22f6-167">**LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="b22f6-168">Standardmallvärdet är **en-us**.</span><span class="sxs-lookup"><span data-stu-id="b22f6-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b22f6-169">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="b22f6-169">Template mapping in Data integration</span></span>

<span data-ttu-id="b22f6-170">I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="b22f6-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="b22f6-171">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b22f6-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="b22f6-172">Kontakt till kontakt</span><span class="sxs-lookup"><span data-stu-id="b22f6-172">Contact to contact</span></span>

![Mallmappning i dataintegreraren](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="b22f6-174">Kontakt till kund</span><span class="sxs-lookup"><span data-stu-id="b22f6-174">Contact to customer</span></span>

![Mallmappning i dataintegreraren](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="b22f6-176">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b22f6-176">Related topics</span></span>

[<span data-ttu-id="b22f6-177">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="b22f6-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="b22f6-178">Synkronisera konton direkt från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b22f6-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="b22f6-179">Synkronisera produkter direkt från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="b22f6-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="b22f6-180">Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="b22f6-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="b22f6-181">Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="b22f6-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)


