---
title: "Importera leverantörskataloger"
description: "Det här ämnet beskriver hur du importerar leverantörskatalogdata."
author: mkirknel
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.search.region: Global
ms.search.industry: 
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ac7754bd6361ad74f7ab4d564ae3114dd4b9f165
ms.openlocfilehash: caf801ea27ade63c24bb0907313e7f8294c50702
ms.contentlocale: sv-se
ms.lasthandoff: 04/26/2018

---

# <a name="import-vendor-catalogs"></a><span data-ttu-id="5d800-103">Importera leverantörskataloger</span><span class="sxs-lookup"><span data-stu-id="5d800-103">Import vendor catalogs</span></span>
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="5d800-104">Importera leverantörskataloger</span><span class="sxs-lookup"><span data-stu-id="5d800-104">Vendor catalogs import</span></span>

<span data-ttu-id="5d800-105">I Microsoft Dynamics 365 for Finance and Operations kan inköpare skapa och underhålla kataloger som anställda i företaget kan använda när de beställer artiklar och tjänster för intern användning.</span><span class="sxs-lookup"><span data-stu-id="5d800-105">In Microsoft Dynamics 365 for Finance and Operations, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="5d800-106">Om du vill skapa en anskaffningskatalog kan du lägga till artiklar och tjänster som du vill göra tillgänglig för anställda, antingen genom att importera produktkatalogdata eller genom att manuellt lägga till produktkatalogdata till produktmallen.</span><span class="sxs-lookup"><span data-stu-id="5d800-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="5d800-107">Du kan överföra katalogdata som skickas av en leverantör från Microsoft Dynamics 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="5d800-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="5d800-108">Den produktdata som en leverantör skickar till dig i form av en CMR-fil (Catalog Maintenance Request) måste vara i XML-format.</span><span class="sxs-lookup"><span data-stu-id="5d800-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="5d800-109">CMR-filen ska innehålla information om de produkter som leverantören tillhandahåller till ditt företag.</span><span class="sxs-lookup"><span data-stu-id="5d800-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>

## <a name="import-vendor-catalog-data"></a><span data-ttu-id="5d800-110">Importera leverantörskatalogdata</span><span class="sxs-lookup"><span data-stu-id="5d800-110">Import vendor catalog data</span></span>

<span data-ttu-id="5d800-111">Om du vill importera leverantörskatalogdata måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="5d800-111">To import vendor catalog data, you must complete the following tasks:</span></span>

1.  <span data-ttu-id="5d800-112">Ställ in ett projekt i arbetsytan Datahantering när du har definierat dina datamappningsregler.</span><span class="sxs-lookup"><span data-stu-id="5d800-112">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="5d800-113">Välj **Datahantering** och markera **Konfigurera roller för dataprojekt**.</span><span class="sxs-lookup"><span data-stu-id="5d800-113">Select **Data management** and then select **Set up roles for data projects**.</span></span> 

2.  <span data-ttu-id="5d800-114">Ställ in en anskaffningskategorihierarki och tilldela dina leverantörer till anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="5d800-114">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="5d800-115">Om du använder artikelkoder, lägg till artikelkoder till anskaffningskategorierna.</span><span class="sxs-lookup"><span data-stu-id="5d800-115">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="5d800-116">För information om hur du ställer in en anskaffningskategorihierarki, se [Ställ in en anskaffningskategorihierarki](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="5d800-116">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>

3.  <span data-ttu-id="5d800-117">Konfigurera leverantören för katalogimport</span><span class="sxs-lookup"><span data-stu-id="5d800-117">Configure the vendor for catalog import.</span></span> <span data-ttu-id="5d800-118">Markera en leverantör och välj sedan **Anskaffning** > **Ställ in** > **Konfigurera leverantör för katalogimport**.</span><span class="sxs-lookup"><span data-stu-id="5d800-118">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>

4.  <span data-ttu-id="5d800-119">Konfigurera arbetsflöde för katalogimport.</span><span class="sxs-lookup"><span data-stu-id="5d800-119">Configure workflow for catalog import.</span></span> <span data-ttu-id="5d800-120">Skapa en mall för CMR-fil och dela den med leverantören.</span><span class="sxs-lookup"><span data-stu-id="5d800-120">Create a CMR file template and share this with your vendor.</span></span>

5.  <span data-ttu-id="5d800-121">Välj **Anskaffning och källa**\>**Gemensam**\>**Kataloger**\>**Leverantörskataloger** om du vill skapa en leverantörskatalog.</span><span class="sxs-lookup"><span data-stu-id="5d800-121">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="5d800-122">CMR-filen (Catalog Maintenance Request) som du får från leverantören grupperas i katalogen.</span><span class="sxs-lookup"><span data-stu-id="5d800-122">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6.  <span data-ttu-id="5d800-123">Överför CMR-filen.</span><span class="sxs-lookup"><span data-stu-id="5d800-123">Upload the CMR file.</span></span>

7.  <span data-ttu-id="5d800-124">Granska, godkänn eller avvisa produkterna i leverantörskatalogen.</span><span class="sxs-lookup"><span data-stu-id="5d800-124">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="5d800-125">Produkter mappas automatiskt till anskaffningskategorier i Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5d800-125">The products are automatically mapped to the procurement categories in Dynamics 365 for Finance and Operations.</span></span> 
    
<span data-ttu-id="5d800-126">Godkända produkter läggs till i produktmallen och frisläpps för de valda juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="5d800-126">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="5d800-127">Endast godkända produkter kan läggas till anskaffningskatalogen.</span><span class="sxs-lookup"><span data-stu-id="5d800-127">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="5d800-128">Skapa mall för katalogfil för import</span><span class="sxs-lookup"><span data-stu-id="5d800-128">Generate a catalog import file template</span></span>

<span data-ttu-id="5d800-129">En filmall för katalogimport är en XSD-fil som du använder för att skapa en CMR-fil för en leverantörs produkter.</span><span class="sxs-lookup"><span data-stu-id="5d800-129">The catalog import file template is an XSD file that you use to create a CMR file for a vendor’s products.</span></span> <span data-ttu-id="5d800-130">Du kan använda CMR-filen om du vill skapa en ny katalog, ersätta en existerande katalog eller ändra en existerande katalog.</span><span class="sxs-lookup"><span data-stu-id="5d800-130">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1.  <span data-ttu-id="5d800-131">Välj **Anskaffning och källa**\>**Kataloger**\>**Leverantörskataloger** och dubbelklicka på den katalog som du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="5d800-131">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor catalogs** and double-click the catalog that you want to work with.</span></span>

2.  <span data-ttu-id="5d800-132">Hämta en aktuella katalogimportmallen (XSD-fil).</span><span class="sxs-lookup"><span data-stu-id="5d800-132">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="5d800-133">På sidan **Uppdatera katalog** i **Åtgärdsfönstret**klickar du på fliken **Kataloger** i gruppen **Relaterad information** genom att klicka på **Skapa katalog** och välj **Anskaffningskategori**.</span><span class="sxs-lookup"><span data-stu-id="5d800-133">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    -   <span data-ttu-id="5d800-134">Med alternativet **Anskaffningskategori** kan du generera en katalogmall som innehåller anskaffningskategorierna där leverantören har behörighet att leverera produkter.</span><span class="sxs-lookup"><span data-stu-id="5d800-134">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="5d800-135">Välj plats där du vill lagra katalogfilmallen och spara filen i dialogrutan **Spara som**.</span><span class="sxs-lookup"><span data-stu-id="5d800-135">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="5d800-136">Mer information och exempel finns i det här blogginlägget: [leverantörskataloger i Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span><span class="sxs-lookup"><span data-stu-id="5d800-136">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>
