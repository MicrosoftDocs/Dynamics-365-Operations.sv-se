---
title: Synkronisera produkter direkt från Finance and Operations till produkter i Sales
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Sales.
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
ms.openlocfilehash: feb9fbc066162e2caa9fc5dbaeec2c063ae23060
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "348260"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="1c964-103">Synkronisera produkter direkt från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="1c964-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="1c964-104">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Common Data Service för appar](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="1c964-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="1c964-105">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter direkt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="1c964-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="1c964-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="1c964-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="1c964-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="1c964-109">Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="1c964-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="1c964-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="1c964-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="1c964-111">Templates and tasks</span></span>

<span data-ttu-id="1c964-112">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="1c964-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="1c964-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="1c964-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="1c964-114">Följande mall och underliggande uppgifter används för att synkronisera produkter från Finance and Operations till Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="1c964-115">**Namnet på mallen i dataintegrering:** produkter (Fin and Ops to Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="1c964-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="1c964-116">**Namnen på uppgiften i dataintegreringsprojektet:** Produkter</span><span class="sxs-lookup"><span data-stu-id="1c964-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="1c964-117">Inga synkroniseringsuppgifter krävs innan synkroniseringen av produkt kan utföras.</span><span class="sxs-lookup"><span data-stu-id="1c964-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="1c964-118">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="1c964-118">Entity set</span></span>

| <span data-ttu-id="1c964-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1c964-119">Finance and Operations</span></span>     | <span data-ttu-id="1c964-120">Försäljning</span><span class="sxs-lookup"><span data-stu-id="1c964-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="1c964-121">Säljbara frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="1c964-121">Sellable released products</span></span> | <span data-ttu-id="1c964-122">Produkter</span><span class="sxs-lookup"><span data-stu-id="1c964-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="1c964-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="1c964-123">Entity flow</span></span>

<span data-ttu-id="1c964-124">Produkter hanteras i Finance and Operations och synkroniseras i Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="1c964-125">Dataentiteten **Säljbara frisläppta produkter** i Finance and Operations exporterar endast produkter som är *Säljbara*.</span><span class="sxs-lookup"><span data-stu-id="1c964-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="1c964-126">Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1c964-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="1c964-127">Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="1c964-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="1c964-128">Produktnumret används som nyckel.</span><span class="sxs-lookup"><span data-stu-id="1c964-128">The product number is used as a key.</span></span> <span data-ttu-id="1c964-129">Därför när produktvarianter synkroniseras till Sales, har varje produktvarianten ett individuellt produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="1c964-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="1c964-130">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="1c964-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="1c964-131">I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="1c964-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="1c964-132">Det har värdet är som standrad inställt på **Ja** vid import till Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="1c964-133">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="1c964-133">The following values are available:</span></span>

- <span data-ttu-id="1c964-134">**Ja** – produkten kommer från Finance and Operations och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="1c964-135">**Nej** – produkten angavs direkt i Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="1c964-136">**(Tom)** – Produkten fanns i Sales innan lösningen Potentiell kund till kontanter aktiverades.</span><span class="sxs-lookup"><span data-stu-id="1c964-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="1c964-137">Fältet **Hanteras externt** hjälper till att säkerställa att endast offerter och försäljningsorder med externt hanterade produkter synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1c964-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="1c964-138">Externt underhållna produkter läggs automatiskt till den första giltiga prislistan med samma valuta.</span><span class="sxs-lookup"><span data-stu-id="1c964-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="1c964-139">Prislistor är sorterade i alfabetisk ordning efter namn.</span><span class="sxs-lookup"><span data-stu-id="1c964-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="1c964-140">Produktens försäljningspris från Finance and Operations används som pris i prislista.</span><span class="sxs-lookup"><span data-stu-id="1c964-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="1c964-141">Därför måste det finnas en prislista i Sales för varje produktförsäljningsvaluta i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1c964-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="1c964-142">Valutan för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.</span><span class="sxs-lookup"><span data-stu-id="1c964-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="1c964-143">Produktsynkronisering lyckas inte, såvida det inte finns en prislista som har en matchande valuta.</span><span class="sxs-lookup"><span data-stu-id="1c964-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="1c964-144">Du kan kontrollera den använda prislistan genom att mappa pricelevelid.name [standardprislista (namn)] i dataintegreringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="1c964-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="1c964-145">Inmatningen måste vara i gemener.</span><span class="sxs-lookup"><span data-stu-id="1c964-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="1c964-146">Standardvärdet för en prislista i försäljning med namnet ”Standard” är till exempel: målfält: pricelevelid.name [standardprislista (namn)] och mapptyp: [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="1c964-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="1c964-147">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="1c964-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="1c964-148">Innan du kör den första synkroniseringen måste du fylla i specifik produkttabell för befintliga produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1c964-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="1c964-149">Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="1c964-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="1c964-150">I Finance and Operations använder du Sök för att söka efter **Fyll i specifik produkttabell**.</span><span class="sxs-lookup"><span data-stu-id="1c964-150">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="1c964-151">Välj **Fyll i specifik produkttabell** för att köra jobbet.</span><span class="sxs-lookup"><span data-stu-id="1c964-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="1c964-152">Detta jobb kan endast köras en gång.</span><span class="sxs-lookup"><span data-stu-id="1c964-152">This job must be run only one time.</span></span>

- <span data-ttu-id="1c964-153">Kontrollera att nödvändig värdemappning för den säljande enheten (UOM) mellan Finance and Operations och Sales finns i mappningen **Säljenhetssymbol** till **Standardenhet (namn)**.</span><span class="sxs-lookup"><span data-stu-id="1c964-153">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="1c964-154">Uppdatera värdemappen för **Enhetsgrupp** (**defaultuomscheduleid.name**) så att de matchar **Enhetsgrupper** i Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="1c964-155">Standardmallvärdet är **standardenhet**.</span><span class="sxs-lookup"><span data-stu-id="1c964-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="1c964-156">Se till att säljande UOM:er för alla produkter från Finance and Operations finns i Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-156">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="1c964-157">Se till att prislistor finns i Sales för varje produktförsäljningsvaluta i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1c964-157">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="1c964-158">När produkter skapas i Sales kan de ha ststusen **utkast** eller **aktiv**.</span><span class="sxs-lookup"><span data-stu-id="1c964-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="1c964-159">Beteendet kontrolleras vid **inställningar** > **Administration** > **systeminställningar** > **försäljning** i Sales.</span><span class="sxs-lookup"><span data-stu-id="1c964-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="1c964-160">Produkter som har statusen **utkast** när de skapas måste aktiveras innan de kan läggas till offerter eller försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1c964-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="1c964-161">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="1c964-161">Template mapping in Data integration</span></span>

<span data-ttu-id="1c964-162">I följande illustration visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="1c964-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="1c964-163">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1c964-163">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mallmappning i dataintegreraren](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="1c964-165">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1c964-165">Related topics</span></span>

[<span data-ttu-id="1c964-166">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="1c964-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="1c964-167">Synkronisera konton direkt från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1c964-167">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="1c964-168">Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1c964-168">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="1c964-169">Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="1c964-169">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="1c964-170">Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="1c964-170">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



