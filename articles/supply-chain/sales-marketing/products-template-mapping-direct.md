---
title: Synkronisera produkter direkt från Supply Chain Management till produkter i Sales
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
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
ms.openlocfilehash: f5e91d4dac8ea6d19fa32abca4e9ff73c7cd4a88
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235003"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a><span data-ttu-id="58fbe-103">Synkronisera produkter direkt från Supply Chain Management till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="58fbe-103">Synchronize products directly from Supply Chain Management to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="58fbe-104">Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Microsoft Dataverse för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="58fbe-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="58fbe-105">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter direkt från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="58fbe-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="58fbe-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="58fbe-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="58fbe-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="58fbe-109">Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="58fbe-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="58fbe-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="58fbe-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="58fbe-111">Templates and tasks</span></span>

<span data-ttu-id="58fbe-112">För att gå till tillgängliga mallar, öppna [Power Apps administratörscenter](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="58fbe-112">To access the available templates, open [Power Apps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="58fbe-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="58fbe-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="58fbe-114">Följande mall och underliggande uppgifter används för att synkronisera produkter från Supply Chain Management till Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-114">The following template and underlying tasks are used to synchronize products from Supply Chain Management to Sales.</span></span>

- <span data-ttu-id="58fbe-115">**Namnet på mallen i dataintegrering:** produkter (Supply Chain Management till Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="58fbe-115">**Name of the template in Data integration:** Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="58fbe-116">**Namnen på uppgiften i dataintegreringsprojektet:** Produkter</span><span class="sxs-lookup"><span data-stu-id="58fbe-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="58fbe-117">Inga synkroniseringsuppgifter krävs innan synkroniseringen av produkt kan utföras.</span><span class="sxs-lookup"><span data-stu-id="58fbe-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="58fbe-118">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="58fbe-118">Entity set</span></span>

| <span data-ttu-id="58fbe-119">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="58fbe-119">Supply Chain Management</span></span>    | <span data-ttu-id="58fbe-120">Försäljning</span><span class="sxs-lookup"><span data-stu-id="58fbe-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="58fbe-121">Säljbara frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="58fbe-121">Sellable released products</span></span> | <span data-ttu-id="58fbe-122">Produkter</span><span class="sxs-lookup"><span data-stu-id="58fbe-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="58fbe-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="58fbe-123">Entity flow</span></span>

<span data-ttu-id="58fbe-124">Produkter hanteras i Supply Chain Management och synkroniseras med Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-124">Products are managed in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="58fbe-125">Dataentiteten **Säljbara frisläppta produkter** i Supply Chain Management exporterar endast produkter som är *Säljbara*.</span><span class="sxs-lookup"><span data-stu-id="58fbe-125">The **Sellable released products** data entity in Supply Chain Management exports only products that are *sellable*.</span></span> <span data-ttu-id="58fbe-126">Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="58fbe-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="58fbe-127">Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="58fbe-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="58fbe-128">Produktnumret används som nyckel.</span><span class="sxs-lookup"><span data-stu-id="58fbe-128">The product number is used as a key.</span></span> <span data-ttu-id="58fbe-129">Därför när produktvarianter synkroniseras till Sales, har varje produktvarianten ett individuellt produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="58fbe-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="58fbe-130">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="58fbe-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="58fbe-131">I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="58fbe-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="58fbe-132">Det har värdet är som standrad inställt på **Ja** vid import till Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="58fbe-133">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="58fbe-133">The following values are available:</span></span>

- <span data-ttu-id="58fbe-134">**Ja** – Produkten kommer från Supply Chain Management och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-134">**Yes** – The product originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="58fbe-135">**Nej** – produkten angavs direkt i Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="58fbe-136">**(Tom)** – Produkten fanns i Sales innan lösningen Potentiell kund till kontanter aktiverades.</span><span class="sxs-lookup"><span data-stu-id="58fbe-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="58fbe-137">Fältet **Hanteras externt** hjälper till att säkerställa att endast offerter och försäljningsorder med externt hanterade produkter synkroniseras till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58fbe-137">The **Is Externally Maintained** field helps ensure that only quotations and sales orders that have externally maintained products will be synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="58fbe-138">Externt underhållna produkter läggs automatiskt till den första giltiga prislistan med samma valuta.</span><span class="sxs-lookup"><span data-stu-id="58fbe-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="58fbe-139">Prislistor är sorterade i alfabetisk ordning efter namn.</span><span class="sxs-lookup"><span data-stu-id="58fbe-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="58fbe-140">Produktens försäljningspris från Supply Chain Management används som pris i prislista.</span><span class="sxs-lookup"><span data-stu-id="58fbe-140">The product sales price from Supply Chain Management is used as the price on the price list.</span></span> <span data-ttu-id="58fbe-141">Därför måste det finnas en prislista i Sales för varje produktförsäljningsvaluta i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58fbe-141">Therefore, there must be a price list in Sales for every product sales currency in Supply Chain Management.</span></span> <span data-ttu-id="58fbe-142">Valutan för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.</span><span class="sxs-lookup"><span data-stu-id="58fbe-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="58fbe-143">Produktsynkronisering lyckas inte, såvida det inte finns en prislista som har en matchande valuta.</span><span class="sxs-lookup"><span data-stu-id="58fbe-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="58fbe-144">Du kan kontrollera den använda prislistan genom att mappa pricelevelid.name [standardprislista (namn)] i dataintegreringsprojektet.</span><span class="sxs-lookup"><span data-stu-id="58fbe-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="58fbe-145">Inmatningen måste vara i gemener.</span><span class="sxs-lookup"><span data-stu-id="58fbe-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="58fbe-146">Standardvärdet för en prislista i försäljning med namnet ”Standard” är till exempel: målfält: pricelevelid.name [standardprislista (namn)] och mapptyp: [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="58fbe-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="58fbe-147">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="58fbe-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="58fbe-148">Innan du kör den första synkroniseringen måste du fylla i specifik produkttabell för befintliga produkter i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58fbe-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Supply Chain Management.</span></span> <span data-ttu-id="58fbe-149">Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="58fbe-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="58fbe-150">I Supply Chain Management använder du Sök för att söka efter **Fyll i specifik produkttabell**.</span><span class="sxs-lookup"><span data-stu-id="58fbe-150">In Supply Chain Management, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="58fbe-151">Välj **Fyll i specifik produkttabell** för att köra jobbet.</span><span class="sxs-lookup"><span data-stu-id="58fbe-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="58fbe-152">Detta jobb kan endast köras en gång.</span><span class="sxs-lookup"><span data-stu-id="58fbe-152">This job must be run only one time.</span></span>

- <span data-ttu-id="58fbe-153">Kontrollera att nödvändig värdemappning för den säljande enheten (UOM) mellan Supply Chain Management och Sales finns i mappningen **Säljenhetssymbol** till **Standardenhet (namn)**.</span><span class="sxs-lookup"><span data-stu-id="58fbe-153">Make sure that the required value map for the selling unit of measure (UOM) between Supply Chain Management and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="58fbe-154">Uppdatera värdemappen för **Enhetsgrupp** (**defaultuomscheduleid.name**) så att de matchar **Enhetsgrupper** i Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="58fbe-155">Standardmallvärdet är **standardenhet**.</span><span class="sxs-lookup"><span data-stu-id="58fbe-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="58fbe-156">Se till att säljande UOM:er för alla produkter från Supply Chain Management finns i Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-156">Make sure that the selling UOMs for all products from Supply Chain Management exist in Sales.</span></span>
- <span data-ttu-id="58fbe-157">Se till att prislistor finns i Sales för varje produktförsäljningsvaluta i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58fbe-157">Make sure that price lists exist in Sales for every product sales currency in Supply Chain Management.</span></span>
- <span data-ttu-id="58fbe-158">När produkter skapas i Sales kan de ha ststusen **utkast** eller **aktiv**.</span><span class="sxs-lookup"><span data-stu-id="58fbe-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="58fbe-159">Beteendet kontrolleras vid **inställningar** > **Administration** > **systeminställningar** > **försäljning** i Sales.</span><span class="sxs-lookup"><span data-stu-id="58fbe-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="58fbe-160">Produkter som har statusen **utkast** när de skapas måste aktiveras innan de kan läggas till offerter eller försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="58fbe-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="58fbe-161">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="58fbe-161">Template mapping in Data integration</span></span>

<span data-ttu-id="58fbe-162">I följande illustration visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="58fbe-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="58fbe-163">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58fbe-163">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mallmappning i dataintegreraren](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="58fbe-165">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="58fbe-165">Related topics</span></span>

[<span data-ttu-id="58fbe-166">Prospekt till kontanter</span><span class="sxs-lookup"><span data-stu-id="58fbe-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="58fbe-167">Synkronisera konton direkt från Sales till kunder i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="58fbe-167">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="58fbe-168">Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="58fbe-168">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="58fbe-169">Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="58fbe-169">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="58fbe-170">Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales</span><span class="sxs-lookup"><span data-stu-id="58fbe-170">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]