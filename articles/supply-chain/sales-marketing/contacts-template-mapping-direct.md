---
title: Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera entiteterna Kontakt (kontakter) och Kontakt (kunder) direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7bc4b48260907788eb90a19c5dc0b5c8f1d9d3b5
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908118"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="f9497-103">Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f9497-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="f9497-104">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Microsoft Dataverse för appar](/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="f9497-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="f9497-105">I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera tabellerna Kontakt (kontakter) och Kontakt (kunder) direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) tables directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="f9497-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="f9497-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="f9497-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="f9497-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="f9497-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="f9497-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="f9497-109">Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="f9497-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="f9497-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="f9497-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f9497-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="f9497-111">Templates and tasks</span></span>

<span data-ttu-id="f9497-112">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="f9497-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="f9497-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="f9497-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="f9497-114">Följande mallar och underliggande uppgifter används för att synkronisera tabellerna kontakt (kontakter) i Sales och tabellerna kontakt (kunder) i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) tables in Sales to Contact (Customers) tables in Supply Chain Management.</span></span>

- <span data-ttu-id="f9497-115">**Namn på mallar i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="f9497-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="f9497-116">Kontakter (Sales till Supply Chain Management) - direkt</span><span class="sxs-lookup"><span data-stu-id="f9497-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="f9497-117">Kontakter till kunder (Sales till Supply Chain Management) - direkt</span><span class="sxs-lookup"><span data-stu-id="f9497-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="f9497-118">**Namnen på uppgifterna i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="f9497-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="f9497-119">Kontakter</span><span class="sxs-lookup"><span data-stu-id="f9497-119">Contacts</span></span>
    - <span data-ttu-id="f9497-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="f9497-120">ContactToCustomer</span></span>

<span data-ttu-id="f9497-121">Följande synkroniseringsuppgift krävs före kontaktsynkronisering: konton (Sales till Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="f9497-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="f9497-122">Entitetsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="f9497-122">Entity sets</span></span>

| <span data-ttu-id="f9497-123">Försäljning</span><span class="sxs-lookup"><span data-stu-id="f9497-123">Sales</span></span>    | <span data-ttu-id="f9497-124">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="f9497-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="f9497-125">Kontakter</span><span class="sxs-lookup"><span data-stu-id="f9497-125">Contacts</span></span> | <span data-ttu-id="f9497-126">Dataverse-kontakter</span><span class="sxs-lookup"><span data-stu-id="f9497-126">Dataverse Contacts</span></span>           |
| <span data-ttu-id="f9497-127">Kontakter</span><span class="sxs-lookup"><span data-stu-id="f9497-127">Contacts</span></span> | <span data-ttu-id="f9497-128">Kunder V2</span><span class="sxs-lookup"><span data-stu-id="f9497-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="f9497-129">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="f9497-129">Entity flow</span></span>

<span data-ttu-id="f9497-130">Kontakter hanteras i Sales och synkroniseras med Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="f9497-131">En kontakt i Sales kan antingen bli en kontakt eller en kund i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="f9497-132">För att ta reda på om en kontakt i Sales ska synkroniseras mot Supply Chain Management som en kontakt eller en kund, tittar systemet på följande egenskaper för en kontakt i Sales:</span><span class="sxs-lookup"><span data-stu-id="f9497-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="f9497-133">**Synkronisering till en kund i Supply Chain Management:** kontakter där **är aktiv kund** anges till **Ja**</span><span class="sxs-lookup"><span data-stu-id="f9497-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="f9497-134">**Synkronisering till en kontakt i Supply Chain Management:** kontakter där **är aktiv kund** anges till **nr** och **företag** (överordnat konto/kontakt) leder till ett konto (inte en kontakt)</span><span class="sxs-lookup"><span data-stu-id="f9497-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="f9497-135">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="f9497-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="f9497-136">En ny kolumn för **är aktiv kund** har lagts till kontakten.</span><span class="sxs-lookup"><span data-stu-id="f9497-136">A new **Is Active Customer** column has been added to the contact.</span></span> <span data-ttu-id="f9497-137">Den här kolumnen används för att urskilja kontakter vars försäljningsaktivitet och kontakter som inte har en försäljningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="f9497-137">This column is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="f9497-138">**Är aktiv kund** anges till **Ja** endast för kontakter som har relaterade offerter, order eller fakturor.</span><span class="sxs-lookup"><span data-stu-id="f9497-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="f9497-139">Endast dessa kontakter synkroniseras till Supply Chain Management som kunder.</span><span class="sxs-lookup"><span data-stu-id="f9497-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="f9497-140">En ny kolumn för **IsCompanyAnAccount** har lagts till kontakten.</span><span class="sxs-lookup"><span data-stu-id="f9497-140">A new **IsCompanyAnAccount** column has been added to the contact.</span></span> <span data-ttu-id="f9497-141">Den här kolumnen indikerar om en kontakt är kopplad till ett företag (överordnat konto/kontakt) av typen **konto**.</span><span class="sxs-lookup"><span data-stu-id="f9497-141">This column indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="f9497-142">Denna information används för att identifiera kontakter som ska synkroniseras mot Supply Chain Management som kontakter.</span><span class="sxs-lookup"><span data-stu-id="f9497-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="f9497-143">En ny kolumn för **kontaktnummer** har lagts till kontakten för att garantera en naturlig och unik nyckel för integration.</span><span class="sxs-lookup"><span data-stu-id="f9497-143">A new **Contact Number** column has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="f9497-144">När en ny kontakt skapas kommer **kontaktnummer**-värde genereras automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="f9497-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="f9497-145">Värdet består av **CON** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="f9497-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="f9497-146">Här är ett exempel: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="f9497-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="f9497-147">När integrationslösningen för Sales används, anger ett uppgraderingsskript kolumnen **kontaktnummer** för befintliga kontakter med nummerserien som beskrivits tidigare.</span><span class="sxs-lookup"><span data-stu-id="f9497-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** column for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="f9497-148">Uppgraderingsskriptet anger också kolumnen **är aktiv kund** till **Ja** för alla kontakter som har försäljningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="f9497-148">The upgrade script also sets the **Is Active Customer** column to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="f9497-149">I Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f9497-149">In Supply Chain Management</span></span>

<span data-ttu-id="f9497-150">Kontakter är märkta med egenskapen **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="f9497-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="f9497-151">Den här egenskapen anger att en kontakt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="f9497-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="f9497-152">I det här fallet underhålls externt underhållna kontakter i Sales.</span><span class="sxs-lookup"><span data-stu-id="f9497-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="f9497-153">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f9497-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="f9497-154">Kontakt till kund</span><span class="sxs-lookup"><span data-stu-id="f9497-154">Contact to customer</span></span>

- <span data-ttu-id="f9497-155">**CustomerGroup** krävs i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="f9497-156">För att undvika problem med synkronisering kan du ange ett standardvärde i mappningen.</span><span class="sxs-lookup"><span data-stu-id="f9497-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="f9497-157">Detta standardvärde används sedan om kolumnen lämnas tomt i Sales.</span><span class="sxs-lookup"><span data-stu-id="f9497-157">That default value is then used if the column is left blank in Sales.</span></span>

    <span data-ttu-id="f9497-158">Standardmallvärdet är **10**.</span><span class="sxs-lookup"><span data-stu-id="f9497-158">The default template value is **10**.</span></span>

- <span data-ttu-id="f9497-159">Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="f9497-160">Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.</span><span class="sxs-lookup"><span data-stu-id="f9497-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="f9497-161">**SiteId** - en standardplats kan också definieras på produkter i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="f9497-162">En plats måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="f9497-163">Ett mallvärde för **SiteId** är inte definierad.</span><span class="sxs-lookup"><span data-stu-id="f9497-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="f9497-164">**WarehouseId** - ett standardlagerställe kan också definieras på produkter i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="f9497-165">Ett lagerställe måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="f9497-166">Ett mallvärde för **WarehouseId** är inte definierad.</span><span class="sxs-lookup"><span data-stu-id="f9497-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="f9497-167">**LanguageId** – ett språk plats måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="f9497-168">Standardmallvärdet är **en-us**.</span><span class="sxs-lookup"><span data-stu-id="f9497-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f9497-169">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="f9497-169">Template mapping in Data integration</span></span>

<span data-ttu-id="f9497-170">I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="f9497-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="f9497-171">Mappningen visar vilken kolumninformation som kommer att synkroniseras från Sales till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f9497-171">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="f9497-172">Kontakt till kontakt</span><span class="sxs-lookup"><span data-stu-id="f9497-172">Contact to contact</span></span>

![Mallmappning i dataintegreraren](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="f9497-174">Kontakt till kund</span><span class="sxs-lookup"><span data-stu-id="f9497-174">Contact to customer</span></span>

![Mallmappning i dataintegreraren](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="f9497-176">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f9497-176">Related topics</span></span>

[<span data-ttu-id="f9497-177">Prospekt till kontanter</span><span class="sxs-lookup"><span data-stu-id="f9497-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="f9497-178">Synkronisera konton direkt från Sales till kunder i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f9497-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="f9497-179">Synkronisera produkter direkt från Supply Chain Management till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="f9497-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="f9497-180">Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f9497-180">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="f9497-181">Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales</span><span class="sxs-lookup"><span data-stu-id="f9497-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]