---
title: "Kontrollera kvaliteten på varor"
description: "I den här proceduren visas hur du bearbetar en kvalitetsorder."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 3a4ace658b8a3a20d613b7a251eb85c32c7f1c09
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="bdd04-103">Kontrollera kvaliteten på varor</span><span class="sxs-lookup"><span data-stu-id="bdd04-103">Inspect the quality of goods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bdd04-104">I den här proceduren visas hur du bearbetar en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="bdd04-104">This procedure shows you how to process a quality order.</span></span> <span data-ttu-id="bdd04-105">Du kan köra den här handboken i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bdd04-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="bdd04-106">Innan du startar den här exempelproceduren måste du bekräfta inköpsorder ”000016” och bokföra en produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="bdd04-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="bdd04-107">Då skapas en kvalitetsorder automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bdd04-107">This will automatically create a quality order.</span></span> <span data-ttu-id="bdd04-108">Kvalitets-inspektioner utförs vanligtvis av en kvalitetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="bdd04-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="bdd04-109">Välj en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="bdd04-109">Select a quality order</span></span>
1. <span data-ttu-id="bdd04-110">Gå till Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="bdd04-110">Go to Inventory management > Periodic tasks > Quality management > Quality orders.</span></span>
2. <span data-ttu-id="bdd04-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="bdd04-112">Välj den kvalitetsorder som skapades innan du startade den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="bdd04-112">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="bdd04-113">Registrera testresultat</span><span class="sxs-lookup"><span data-stu-id="bdd04-113">Record test results</span></span>
1. <span data-ttu-id="bdd04-114">Klicka på Resultat.</span><span class="sxs-lookup"><span data-stu-id="bdd04-114">Click Results.</span></span>
2. <span data-ttu-id="bdd04-115">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="bdd04-115">Click Edit.</span></span>
3. <span data-ttu-id="bdd04-116">Ange ett nummer i fältet Resultatkvantitet.</span><span class="sxs-lookup"><span data-stu-id="bdd04-116">In the Result quantity field, enter a number.</span></span>
4. <span data-ttu-id="bdd04-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-117">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="bdd04-118">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Resultat.</span><span class="sxs-lookup"><span data-stu-id="bdd04-118">In the Outcome field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="bdd04-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bdd04-120">I det här exemplet baseras resultatet på ett fördefinierat resultat.</span><span class="sxs-lookup"><span data-stu-id="bdd04-120">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="bdd04-121">Normalt sett skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.</span><span class="sxs-lookup"><span data-stu-id="bdd04-121">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
7. <span data-ttu-id="bdd04-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="bdd04-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bdd04-123">Click Save.</span></span>
9. <span data-ttu-id="bdd04-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-124">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="bdd04-125">Validera kvalitetsordern</span><span class="sxs-lookup"><span data-stu-id="bdd04-125">Validate the quality order</span></span>
1. <span data-ttu-id="bdd04-126">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="bdd04-126">Click Validate.</span></span>
2. <span data-ttu-id="bdd04-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Validerad av.</span><span class="sxs-lookup"><span data-stu-id="bdd04-127">In the Validated by field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bdd04-128">Välj den användare som utför inspektionen.</span><span class="sxs-lookup"><span data-stu-id="bdd04-128">Select the user performing the inspection.</span></span>  
3. <span data-ttu-id="bdd04-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-129">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bdd04-130">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="bdd04-130">Click Select.</span></span>
5. <span data-ttu-id="bdd04-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bdd04-131">Click OK.</span></span>
6. <span data-ttu-id="bdd04-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bdd04-132">Close the page.</span></span>

