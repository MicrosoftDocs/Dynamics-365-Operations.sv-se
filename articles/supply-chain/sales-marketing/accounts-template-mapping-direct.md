---
title: "Synkronisera konton direkt från Sales till kunder i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 0e917634572efcb7fcfa277d5b3fb479bffd1366
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="b5be4-103">Synkronisera konton direkt från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5be4-103">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="b5be4-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="b5be4-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="b5be4-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="b5be4-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="b5be4-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="b5be4-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="b5be4-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span>  <span data-ttu-id="b5be4-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="b5be4-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="b5be4-109">Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="b5be4-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="b5be4-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="b5be4-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b5be4-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="b5be4-111">Templates and tasks</span></span>

<span data-ttu-id="b5be4-112">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="b5be4-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="b5be4-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="b5be4-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="b5be4-114">Följande mallar och underliggande uppgifter används för att synkronisera konton från Sales till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="b5be4-114">The following template and underlying task are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="b5be4-115">**Namnet på mallen i dataintegrering:** konton (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="b5be4-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="b5be4-116">**Namnet på aktiviteten i projektet:** Konton - Kunder</span><span class="sxs-lookup"><span data-stu-id="b5be4-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="b5be4-117">Inga synkroniseringsuppgifter krävs innan synkroniseringen av konto/kund kan utföras.</span><span class="sxs-lookup"><span data-stu-id="b5be4-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="b5be4-118">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="b5be4-118">Entity set</span></span>

| <span data-ttu-id="b5be4-119">Försäljning</span><span class="sxs-lookup"><span data-stu-id="b5be4-119">Sales</span></span>    | <span data-ttu-id="b5be4-120">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5be4-120">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="b5be4-121">Konton</span><span class="sxs-lookup"><span data-stu-id="b5be4-121">Accounts</span></span> | <span data-ttu-id="b5be4-122">Kunder V2</span><span class="sxs-lookup"><span data-stu-id="b5be4-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="b5be4-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="b5be4-123">Entity flow</span></span>

<span data-ttu-id="b5be4-124">Konton hanteras i Sales och synkroniseras till Finance and Operations som kunder.</span><span class="sxs-lookup"><span data-stu-id="b5be4-124">Accounts are managed in Sales and synchronized to Finance and Operations as customers.</span></span> <span data-ttu-id="b5be4-125">Egenskapen **hanteras externt** på dessa kunder anges till **Ja** för att spåra kunder som kommer från Sales.</span><span class="sxs-lookup"><span data-stu-id="b5be4-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="b5be4-126">Den här informationen används vid fakturering för att filtrera fakturor som ska synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="b5be4-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="b5be4-127">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="b5be4-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="b5be4-128">Fältet **kontonummer** är tillgängligt på sidan **konto**.</span><span class="sxs-lookup"><span data-stu-id="b5be4-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="b5be4-129">Det har gjorts en fysisk och en unik nyckel för att stödja integreringen.</span><span class="sxs-lookup"><span data-stu-id="b5be4-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="b5be4-130">Fysiska nyckeln i CRM-lösningen (Customer Relationship Management) kan påverka kunder som redan använder fältet **kontonummer** men som inte använder unika **kontonummer**-värden för varje konto.</span><span class="sxs-lookup"><span data-stu-id="b5be4-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="b5be4-131">Integrationslösningen stöder för närvarande inte fallet.</span><span class="sxs-lookup"><span data-stu-id="b5be4-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="b5be4-132">När ett nytt konto skapas om ett **kontonummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="b5be4-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="b5be4-133">Värdet består av **ACC** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="b5be4-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="b5be4-134">Här är ett exempel: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="b5be4-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="b5be4-135">När integrationslösningen för Sales används kommer ett uppgraderingsskript angs på fältet **kontonummer** för befintliga konton i Sales.</span><span class="sxs-lookup"><span data-stu-id="b5be4-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="b5be4-136">Om det inte finns några **kontonummer**-värden kommer nummerserien som beskrivits ovan att användas.</span><span class="sxs-lookup"><span data-stu-id="b5be4-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="b5be4-137">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b5be4-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="b5be4-138">Mappningen **CustomerGroupId** måste uppdateras till ett giltigt värde i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-138">The **CustomerGroupId** mapping must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="b5be4-139">Du kan ange ett standardvärde eller du kan ange värdet genom att använda en värdemappning.</span><span class="sxs-lookup"><span data-stu-id="b5be4-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="b5be4-140">Standardmallvärdet är **10**.</span><span class="sxs-lookup"><span data-stu-id="b5be4-140">The default template value is **10**.</span></span>

- <span data-ttu-id="b5be4-141">Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="b5be4-142">Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.</span><span class="sxs-lookup"><span data-stu-id="b5be4-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="b5be4-143">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="b5be4-144">En standardplats kan tas antingen från produkten eller från kunden från orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="b5be4-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="b5be4-145">Standardmallvärdet är **1**.</span><span class="sxs-lookup"><span data-stu-id="b5be4-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="b5be4-146">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="b5be4-147">Ett standardlager kan tas antingen från produkten eller från kunden från orderrubriken i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span>

        <span data-ttu-id="b5be4-148">Standardmallvärdet är **13**.</span><span class="sxs-lookup"><span data-stu-id="b5be4-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="b5be4-149">**LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="b5be4-150">Som standard används språk från orderrubriken från kunden.</span><span class="sxs-lookup"><span data-stu-id="b5be4-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="b5be4-151">Standardmallvärdet är **en-us**.</span><span class="sxs-lookup"><span data-stu-id="b5be4-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b5be4-152">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="b5be4-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="b5be4-153">Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="b5be4-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="b5be4-154">Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="b5be4-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="b5be4-155">I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="b5be4-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5be4-156">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5be4-156">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mallmappning i dataintegrering](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="b5be4-158">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b5be4-158">Related topics</span></span>


[<span data-ttu-id="b5be4-159">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="b5be4-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="b5be4-160">Synkronisera konton direkt från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5be4-160">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="b5be4-161">Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5be4-161">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="b5be4-162">Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="b5be4-162">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="b5be4-163">Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="b5be4-163">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)


