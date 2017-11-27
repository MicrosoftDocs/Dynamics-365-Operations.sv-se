---
title: "Synkronisera produkter direkt från Finance and Operations till produkter i Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: 6c68c4482cacf70f003669cf335e52e47425d2f7
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="62740-103">Synkronisera produkter direkt från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="62740-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="62740-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="62740-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="62740-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera produkter direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, till Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="62740-106">Dataflöden i Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="62740-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="62740-107">Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="62740-108">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="62740-109">Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="62740-110">[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="62740-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="62740-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="62740-111">Templates and tasks</span></span>

<span data-ttu-id="62740-112">För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="62740-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="62740-113">Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.</span><span class="sxs-lookup"><span data-stu-id="62740-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="62740-114">Följande mall och underliggande uppgifter används för att synkronisera produkter från Finance and Operations till Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="62740-115">**Namnet på mallen i dataintegrering:** produkter (Fin and Ops to Sales) - Direkt</span><span class="sxs-lookup"><span data-stu-id="62740-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="62740-116">**Namnen på uppgiften i dataintegreringsprojektet:** Produkter</span><span class="sxs-lookup"><span data-stu-id="62740-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="62740-117">Inga synkroniseringsuppgifter krävs innan synkroniseringen av produkt kan utföras.</span><span class="sxs-lookup"><span data-stu-id="62740-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="62740-118">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="62740-118">Entity set</span></span>

| <span data-ttu-id="62740-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="62740-119">Finance and Operations</span></span>     | <span data-ttu-id="62740-120">Försäljning</span><span class="sxs-lookup"><span data-stu-id="62740-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="62740-121">Säljbara frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="62740-121">Sellable released products</span></span> | <span data-ttu-id="62740-122">Produkter</span><span class="sxs-lookup"><span data-stu-id="62740-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="62740-123">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="62740-123">Entity flow</span></span>

<span data-ttu-id="62740-124">Produkter hanteras i Finance and Operations och synkroniseras i Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="62740-125">Dataentiteten **Säljbara frisläppta produkter** i Finance and Operations exporterar endast produkter som är *Säljbara*.</span><span class="sxs-lookup"><span data-stu-id="62740-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="62740-126">Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="62740-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="62740-127">Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="62740-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="62740-128">Produktnumret används som nyckel.</span><span class="sxs-lookup"><span data-stu-id="62740-128">The product number is used as a key.</span></span> <span data-ttu-id="62740-129">Därför när produktvarianter synkroniseras till Sales, har varje produktvarianten ett individuellt produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="62740-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="62740-130">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="62740-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="62740-131">I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="62740-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="62740-132">Det har värdet är som standrad inställt på **Ja** vid import till Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="62740-133">Följande värden finns:</span><span class="sxs-lookup"><span data-stu-id="62740-133">The following values are available:</span></span>

- <span data-ttu-id="62740-134">**Ja** – produkten kommer från Finance and Operations och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="62740-135">**Nej** – produkten angavs direkt i Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="62740-136">**(Tom)** – Produkten fanns i Sales innan lösningen Potentiell kund till kontanter aktiverades.</span><span class="sxs-lookup"><span data-stu-id="62740-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="62740-137">Fältet **Hanteras externt** hjälper till att säkerställa att endast offerter och försäljningsorder med externt hanterade produkter synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62740-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="62740-138">Externt underhållna produkter läggs automatiskt till den första giltiga prislistan med samma valuta.</span><span class="sxs-lookup"><span data-stu-id="62740-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="62740-139">Prislistor är sorterade i alfabetisk ordning efter namn.</span><span class="sxs-lookup"><span data-stu-id="62740-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="62740-140">Produktens försäljningspris från Finance and Operations används som pris i prislista.</span><span class="sxs-lookup"><span data-stu-id="62740-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="62740-141">Därför måste det finnas en prislista i Sales för varje produktförsäljningsvaluta i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62740-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="62740-142">Valutan för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.</span><span class="sxs-lookup"><span data-stu-id="62740-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> <span data-ttu-id="62740-143">Produktsynkronisering lyckas inte, såvida det inte finns en prislista som har en matchande valuta.</span><span class="sxs-lookup"><span data-stu-id="62740-143">Product synchronization won't succeed unless there is a price list that has a matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="62740-144">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="62740-144">Preconditions and mapping setup</span></span>

- <span data-ttu-id="62740-145">Innan du kör den första synkroniseringen måste du fylla i specifik produkttabell för befintliga produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62740-145">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="62740-146">Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="62740-146">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="62740-147">I Finance and Operations använder du Sök för att söka efter **Fyll i specifik produkttabell**.</span><span class="sxs-lookup"><span data-stu-id="62740-147">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="62740-148">Välj **Fyll i specifik produkttabell** för att köra jobbet.</span><span class="sxs-lookup"><span data-stu-id="62740-148">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="62740-149">Detta jobb kan endast köras en gång.</span><span class="sxs-lookup"><span data-stu-id="62740-149">This job must be run only one time.</span></span>

- <span data-ttu-id="62740-150">Kontrollera att nödvändig värdemappning för den säljande enheten (UOM) mellan Finance and Operations och Sales finns i mappningen **Säljenhetssymbol** till **Standardenhet (namn)**.</span><span class="sxs-lookup"><span data-stu-id="62740-150">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="62740-151">Uppdatera värdemappen för **Enhetsgrupp** (**defaultuomscheduleid.name**) så att de matchar **Enhetsgrupper** i Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-151">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="62740-152">Standardmallvärdet är **standardenhet**.</span><span class="sxs-lookup"><span data-stu-id="62740-152">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="62740-153">Se till att säljande UOM:er för alla produkter från Finance and Operations finns i Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-153">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="62740-154">Se till att prislistor finns i Sales för varje produktförsäljningsvaluta i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62740-154">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="62740-155">När produkter skapas i Sales kan de ha ststusen **utkast** eller **aktiv**.</span><span class="sxs-lookup"><span data-stu-id="62740-155">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="62740-156">Beteendet kontrolleras vid **inställningar** > **Administration** > **systeminställningar** > **försäljning** i Sales.</span><span class="sxs-lookup"><span data-stu-id="62740-156">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="62740-157">Produkter som har statusen **utkast** när de skapas måste aktiveras innan de kan läggas till offerter eller försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="62740-157">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="62740-158">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="62740-158">Template mapping in Data integration</span></span>

<span data-ttu-id="62740-159">I följande illustration visas ett exempel på en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="62740-159">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="62740-160">Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62740-160">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mallmappning i dataintegreraren](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="62740-162">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="62740-162">Related topics</span></span>

[<span data-ttu-id="62740-163">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="62740-163">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="62740-164">Synkronisera konton direkt från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="62740-164">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="62740-165">Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="62740-165">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="62740-166">Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="62740-166">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="62740-167">Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="62740-167">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




