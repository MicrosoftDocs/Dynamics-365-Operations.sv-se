---
title: Kontrollera kvaliteten på varor
description: I den här proceduren visas hur du bearbetar en kvalitetsorder.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "315439"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="56e32-103">Kontrollera kvaliteten på varor</span><span class="sxs-lookup"><span data-stu-id="56e32-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="56e32-104">I den här proceduren visas hur du bearbetar en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="56e32-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="56e32-105">Du kan köra den här handboken i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="56e32-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="56e32-106">Innan du startar den här exempelproceduren måste du bekräfta inköpsorder ”000016” och bokföra en produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="56e32-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="56e32-107">Då skapas en kvalitetsorder automatiskt.</span><span class="sxs-lookup"><span data-stu-id="56e32-107">This will automatically create a quality order.</span></span> <span data-ttu-id="56e32-108">Kvalitets-inspektioner utförs vanligtvis av en kvalitetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="56e32-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="56e32-109">Välj en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="56e32-109">Select a quality order</span></span>
1. <span data-ttu-id="56e32-110">Gå till Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="56e32-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="56e32-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="56e32-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="56e32-112">Välj den kvalitetsorder som skapades innan du startade den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="56e32-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="56e32-113">Registrera testresultat</span><span class="sxs-lookup"><span data-stu-id="56e32-113">Record test results</span></span>
1. <span data-ttu-id="56e32-114">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="56e32-114">Click Results.</span></span>
2. <span data-ttu-id="56e32-115">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="56e32-115">Click Edit.</span></span>
3. <span data-ttu-id="56e32-116">Ange ett nummer i fältet Resultatkvantitet.</span><span class="sxs-lookup"><span data-stu-id="56e32-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="56e32-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="56e32-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="56e32-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Resultat.</span><span class="sxs-lookup"><span data-stu-id="56e32-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="56e32-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="56e32-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="56e32-120">I det här exemplet baseras resultatet på ett fördefinierat resultat.</span><span class="sxs-lookup"><span data-stu-id="56e32-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="56e32-121">Normalt sett skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.</span><span class="sxs-lookup"><span data-stu-id="56e32-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="56e32-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="56e32-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="56e32-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="56e32-123">Click Save.</span></span>
9. <span data-ttu-id="56e32-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="56e32-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="56e32-125">Validera kvalitetsordern</span><span class="sxs-lookup"><span data-stu-id="56e32-125">Validate the quality order</span></span>
1. <span data-ttu-id="56e32-126">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="56e32-126">Click Validate.</span></span>
2. <span data-ttu-id="56e32-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Validerad av.</span><span class="sxs-lookup"><span data-stu-id="56e32-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="56e32-128">Välj den användare som utför inspektionen.</span><span class="sxs-lookup"><span data-stu-id="56e32-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="56e32-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="56e32-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="56e32-130">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="56e32-130">Click Select.</span></span>
5. <span data-ttu-id="56e32-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e32-131">Click OK.</span></span>
6. <span data-ttu-id="56e32-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="56e32-132">Close the page.</span></span>

