---
title: "Synkronisera produkter från Finance and Operations till produkter i Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: 405a6cf9f3e6cc52925ff7d9f10836196343c36b
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="a3282-103">Synkronisera produkter från Finance and Operations till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="a3282-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="a3282-104">Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="a3282-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="a3282-105">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="a3282-106">Mall och uppgift</span><span class="sxs-lookup"><span data-stu-id="a3282-106">Template and task</span></span>

<span data-ttu-id="a3282-107">Följande mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) till Microsoft Dynamics 365 for Sales (Sales).</span><span class="sxs-lookup"><span data-stu-id="a3282-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="a3282-108">Mallens namn: produkter (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="a3282-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="a3282-109">Namn på uppgiften projekt: produkter</span><span class="sxs-lookup"><span data-stu-id="a3282-109">Name of task in project: Products</span></span>

<span data-ttu-id="a3282-110">Synkronisering av uppgifter krävs innan synkronisering av produkt: ingen</span><span class="sxs-lookup"><span data-stu-id="a3282-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="a3282-111">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="a3282-111">Entity set</span></span>

| <span data-ttu-id="a3282-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="a3282-112">**Finance and Operations**</span></span> | <span data-ttu-id="a3282-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="a3282-113">**CDS**</span></span> | <span data-ttu-id="a3282-114">**Försäljning**</span><span class="sxs-lookup"><span data-stu-id="a3282-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="a3282-115">Säljbara frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="a3282-115">Sellable released products</span></span> | <span data-ttu-id="a3282-116">Produkt</span><span class="sxs-lookup"><span data-stu-id="a3282-116">Product</span></span> | <span data-ttu-id="a3282-117">Produkter</span><span class="sxs-lookup"><span data-stu-id="a3282-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="a3282-118">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="a3282-118">Entity flow</span></span>

<span data-ttu-id="a3282-119">Produkter hanteras i Finance and Operations och synkroniseras i Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="a3282-120">Dataentiteten **Säljbara frisläppta produkter** i Finance and Operations exporterar endast produkter som är säljbara, vilket innebär att produkterna har nödvändig information för att användas på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a3282-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="a3282-121">Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="a3282-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="a3282-122">**Produktnummer** används som nyckel, vilket innebär att produktvarianter synkroniseras till CDS och Sales med enskilda **produkt-ID-nummer** per **produktvariant**.</span><span class="sxs-lookup"><span data-stu-id="a3282-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="a3282-123">Lösningen potentiell kund till kontanter för Sales</span><span class="sxs-lookup"><span data-stu-id="a3282-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="a3282-124">I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt.</span><span class="sxs-lookup"><span data-stu-id="a3282-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="a3282-125">Det har värdet **Ja** som standard vid import till Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="a3282-126">**Hanteras externt = Ja**: produkten härrör från Finance and Operations och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="a3282-127">**Hanteras externt = Nej**: produkten anges direkt i Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="a3282-128">**Hanteras externt = tom**: produkten finns i Sales innan du aktiverar den potentiella kunden till kontantlösning.</span><span class="sxs-lookup"><span data-stu-id="a3282-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="a3282-129">Informationen **hanteras externt** används för att säkerställa att endast **offerter** och **försäljningsorder** med **externt hanterade produkter** synkroniseras till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3282-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="a3282-130">**Externt underhållna produkter** läggs automatiskt till den första giltiga **prislistan** med samma valuta.</span><span class="sxs-lookup"><span data-stu-id="a3282-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="a3282-131">Observera att listan är i alfabetisk ordning efter **namn**.</span><span class="sxs-lookup"><span data-stu-id="a3282-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="a3282-132">Produktens försäljningspris från Finance and Operations används som pris i **prislista**.</span><span class="sxs-lookup"><span data-stu-id="a3282-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="a3282-133">Detta innebär att den måste ha en **prislista** i Sales för varje **produktförsäljningsvaluta** i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3282-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="a3282-134">Valuta för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.</span><span class="sxs-lookup"><span data-stu-id="a3282-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="a3282-135">Produktsynkronisering kommer inte att fungera utan en **prislista** med matchande valuta.</span><span class="sxs-lookup"><span data-stu-id="a3282-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="a3282-136">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="a3282-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="a3282-137">Innan du kör den första synkroniseringen måste du fylla i **specifik produkttabell** för befintliga produkter i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3282-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="a3282-138">Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="a3282-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="a3282-139">I Finance and Operations använder du Sök för att söka efter **Fyll i specifik produkttabell**.</span><span class="sxs-lookup"><span data-stu-id="a3282-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="a3282-140">Klicka på **Fyll i specifik produkttabell** för att köra jobbet.</span><span class="sxs-lookup"><span data-stu-id="a3282-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="a3282-141">Det här jobbet behöver bara köras en gång.</span><span class="sxs-lookup"><span data-stu-id="a3282-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="a3282-142">Försäkra sig om att den nödvändiga **ValueMap** för försäljningens **måttenhet** (UOM) i Finance and Operations finns i **källa -\> CDS-mappning SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="a3282-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="a3282-143">Uppdatera **CDS organisations-ID Organization_OrganizationId** i **källa -\> CDS**.</span><span class="sxs-lookup"><span data-stu-id="a3282-143">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="a3282-144">Mallvärdet är som standard ORG001.</span><span class="sxs-lookup"><span data-stu-id="a3282-144">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="a3282-145">Uppdatera **ValueMap** för **enhetsgrupp** (**defaultuomscheduleid.name**) i **CDS -\> Destination** så att de matchar **enhetsgrupper** i Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-145">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="a3282-146">Mallvärdet är som standard **standardenhet**.</span><span class="sxs-lookup"><span data-stu-id="a3282-146">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="a3282-147">Se till att alla produkter som säljer UOM:er från Finance and Operations finns i Sales med värdet **CDS-plocklistor**.</span><span class="sxs-lookup"><span data-stu-id="a3282-147">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="a3282-148">Se till att **prislistor** finns i Sales för varje produktförsäljningsvaluta i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a3282-148">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="a3282-149">Produkter kan skapas i Sales med status **utkast** eller **aktiv**.</span><span class="sxs-lookup"><span data-stu-id="a3282-149">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="a3282-150">Detta styrs i **systeminställningar** under **försäljning** i Sales.</span><span class="sxs-lookup"><span data-stu-id="a3282-150">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="a3282-151">Produkter som skapats med utkaststatus måste aktiveras innan de kan läggas till i **offert** eller **försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="a3282-151">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="a3282-152">Mallmappning i dataintegratör</span><span class="sxs-lookup"><span data-stu-id="a3282-152">Template mapping in data integrator</span></span>

<span data-ttu-id="a3282-153">I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.</span><span class="sxs-lookup"><span data-stu-id="a3282-153">The following illustrations show an example of a template mapping in data integrator.</span></span>

![mallmappning i dataintegratör](./media/products-template-mapping-data-integrator-1.png)

![mallmappning för produkter i dataintegratör](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="a3282-156">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a3282-156">Related topics</span></span>

[<span data-ttu-id="a3282-157">Synkronisera konton från Sales till kunder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3282-157">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="a3282-158">Synkronisera kontakter från Sales till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3282-158">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="a3282-159">Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3282-159">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="a3282-160">Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="a3282-160">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="a3282-161">Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="a3282-161">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


