---
title: Synkronisera konton direkt från Sales till kunder i Supply Chain Management
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera kontakter från Dynamics 365 Sales till Supply Chain Management.
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
ms.openlocfilehash: adde8975c709b8037a05e8edf6da8574c7b3cc55
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215827"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="ff0f0-103">Synkronisera konton direkt från Sales till kunder i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ff0f0-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="ff0f0-104">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Microsoft Dataverse för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="ff0f0-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="ff0f0-105">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera konton direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="ff0f0-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="ff0f0-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="ff0f0-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="ff0f0-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="ff0f0-109">Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="ff0f0-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="ff0f0-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ff0f0-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="ff0f0-111">Templates and tasks</span></span>

<span data-ttu-id="ff0f0-112">För att gå till tillgängliga mallar, öppna [Power Apps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="ff0f0-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="ff0f0-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="ff0f0-114">Följande mall och underliggande uppgift används för att synkronisera konton från Sales till Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="ff0f0-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="ff0f0-115">**Namnet på mallen i dataintegrering:** konton (Sales till Fin and Ops) - Direkt</span><span class="sxs-lookup"><span data-stu-id="ff0f0-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="ff0f0-116">**Namnet på aktiviteten i projektet:** Konton - Kunder</span><span class="sxs-lookup"><span data-stu-id="ff0f0-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="ff0f0-117">Inga synkroniseringsuppgifter krävs innan synkroniseringen av konto/kund kan utföras.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="ff0f0-118">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="ff0f0-118">Entity set</span></span>

| <span data-ttu-id="ff0f0-119">Försäljning</span><span class="sxs-lookup"><span data-stu-id="ff0f0-119">Sales</span></span>    | <span data-ttu-id="ff0f0-120">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="ff0f0-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="ff0f0-121">Konton</span><span class="sxs-lookup"><span data-stu-id="ff0f0-121">Accounts</span></span> | <span data-ttu-id="ff0f0-122">Kunder V2</span><span class="sxs-lookup"><span data-stu-id="ff0f0-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="ff0f0-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="ff0f0-123">Entity flow</span></span>

<span data-ttu-id="ff0f0-124">Konton hanteras i Sales och synkroniseras med Supply Chain Management som kunder.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="ff0f0-125">Egenskapen **hanteras externt** på dessa kunder anges till **Ja** för att spåra kunder som kommer från Sales.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="ff0f0-126">Den här informationen används vid fakturering för att filtrera fakturor som ska synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ff0f0-127">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="ff0f0-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ff0f0-128">Kolumnen **kontonummer** är tillgängligt på sidan **konto**.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-128">The **Account Number** column is available on the **Account** page.</span></span> <span data-ttu-id="ff0f0-129">Det har gjorts en fysisk och en unik nyckel för att stödja integreringen.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="ff0f0-130">Fysiska nyckeln i CRM-lösningen (Customer Relationship Management) kan påverka kunder som redan använder kolumnen **kontonummer** men som inte använder unika **kontonummer**-värden för varje konto.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** column, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="ff0f0-131">Integrationslösningen stöder för närvarande inte fallet.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="ff0f0-132">När ett nytt konto skapas om ett **kontonummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="ff0f0-133">Värdet består av **ACC** följt av en ökande nummerserie och sedan ett suffix på sex tecken.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="ff0f0-134">Här är ett exempel: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="ff0f0-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="ff0f0-135">När integrationslösningen för Sales används kommer ett uppgraderingsskript anges på kolumnen **kontonummer** för befintliga konton i Sales.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** column for existing accounts in Sales.</span></span> <span data-ttu-id="ff0f0-136">Om det inte finns några **kontonummer**-värden kommer nummerserien som beskrivits ovan att användas.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ff0f0-137">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="ff0f0-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="ff0f0-138">Mappningen **CustomerGroupId** måste uppdateras till ett giltigt värde i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="ff0f0-139">Du kan ange ett standardvärde eller du kan ange värdet genom att använda en värdemappning.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="ff0f0-140">Standardmallvärdet är **10**.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-140">The default template value is **10**.</span></span>

- <span data-ttu-id="ff0f0-141">Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="ff0f0-142">Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="ff0f0-143">**SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="ff0f0-144">En standardplats kan tas antingen från produkten eller från kunden från orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="ff0f0-145">Standardmallvärdet är **1**.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="ff0f0-146">**WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="ff0f0-147">Ett standardlager kan tas antingen från produkten eller från kunden från orderrubriken i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="ff0f0-148">Standardmallvärdet är **13**.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="ff0f0-149">**LanguageId** – ett språk plats måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="ff0f0-150">Som standard används språk från orderrubriken från kunden.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="ff0f0-151">Standardmallvärdet är **en-us**.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ff0f0-152">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="ff0f0-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="ff0f0-153">Kolumnerna **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** columns aren't included in the default mappings.</span></span> <span data-ttu-id="ff0f0-154">Om du vill mappa dessa kolumner måste du konfigurera en värdemappning som är specifik för data i organisationer som tabellen synkroniseras mellan.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-154">To map these columns, you must set up a value mapping that is specific to the data in the organizations that the table is synchronized between.</span></span>

<span data-ttu-id="ff0f0-155">I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff0f0-156">Mappningen visar vilken kolumninformation som kommer att synkroniseras från Sales till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ff0f0-156">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mallmappning i dataintegrering](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="ff0f0-158">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ff0f0-158">Related topics</span></span>


[<span data-ttu-id="ff0f0-159">Prospekt till kontanter</span><span class="sxs-lookup"><span data-stu-id="ff0f0-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="ff0f0-160">Synkronisera konton direkt från Sales till kunder i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ff0f0-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="ff0f0-161">Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ff0f0-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="ff0f0-162">Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ff0f0-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="ff0f0-163">Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales</span><span class="sxs-lookup"><span data-stu-id="ff0f0-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]