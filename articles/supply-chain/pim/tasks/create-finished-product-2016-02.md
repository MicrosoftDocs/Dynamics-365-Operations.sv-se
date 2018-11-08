--- 
title: "Skapa en färdig produkt (februari 2016)"
description: "Den här uppgiften fokuserar på att skapa en färdig produkt."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 44b3bf17c69f37e7a96c75345a3e4f27ba9eab50
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-finished-product-february-2016"></a><span data-ttu-id="8c92a-103">Skapa en färdig produkt (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="8c92a-103">Create a finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c92a-104">Den här uppgiften fokuserar på att skapa en färdig produkt.</span><span class="sxs-lookup"><span data-stu-id="8c92a-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="8c92a-105">Detta är den första uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="8c92a-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="8c92a-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="8c92a-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="8c92a-107">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="8c92a-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="8c92a-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8c92a-108">Click New.</span></span>
3. <span data-ttu-id="8c92a-109">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="8c92a-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="8c92a-110">Ange Bom_1 för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="8c92a-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="8c92a-111">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="8c92a-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-112">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="8c92a-112">Select STD.</span></span> <span data-ttu-id="8c92a-113">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="8c92a-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="8c92a-114">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="8c92a-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-115">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="8c92a-115">For example, select Audio.</span></span> <span data-ttu-id="8c92a-116">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="8c92a-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="8c92a-117">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="8c92a-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-118">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="8c92a-118">Select SiteWH.</span></span> <span data-ttu-id="8c92a-119">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="8c92a-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="8c92a-120">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="8c92a-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-121">Spårningsdimensioner kommer inte att användas i det här exemplet; välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="8c92a-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="8c92a-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8c92a-122">Click OK.</span></span>
9. <span data-ttu-id="8c92a-123">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8c92a-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="8c92a-124">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="8c92a-124">Click Default order settings.</span></span>
11. <span data-ttu-id="8c92a-125">Välj "Produktion" i fältet för förvald ordertyp.</span><span class="sxs-lookup"><span data-stu-id="8c92a-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="8c92a-126">Eftersom detta är en färdig produkt som ska tillverkas, välj Produktion.</span><span class="sxs-lookup"><span data-stu-id="8c92a-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="8c92a-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="8c92a-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-128">Välj Plats 1 för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="8c92a-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="8c92a-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="8c92a-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="8c92a-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="8c92a-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="8c92a-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="8c92a-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="8c92a-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="8c92a-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8c92a-133">Close the page.</span></span>

