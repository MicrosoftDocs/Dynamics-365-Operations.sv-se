---
title: Kontrollera kvaliteten på varor
description: I det här avsnittet beskrivs hur du bearbetar en kvalitetsorder.
author: perlynne
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10acb9aadfeb11ede1d66dd525ace7b70db3bd1c
ms.sourcegitcommit: fbaccf72df82e6b6927f0c9f0d35af0ca3ecbc2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1855696"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="e4870-103">Kontrollera kvaliteten på varor</span><span class="sxs-lookup"><span data-stu-id="e4870-103">Inspect the quality of goods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4870-104">I det här avsnittet beskrivs hur du bearbetar en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="e4870-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="e4870-105">Du kan köra den här handboken i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e4870-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="e4870-106">Innan du startar den här exempelproceduren måste du bekräfta inköpsorder ”000016” och bokföra en produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="e4870-106">Before you start this example procedure, you need to confirm purchase order “000016” and post a product receipt.</span></span> <span data-ttu-id="e4870-107">Då skapas en kvalitetsorder automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e4870-107">This will automatically create a quality order.</span></span> <span data-ttu-id="e4870-108">Kvalitets-inspektioner utförs vanligtvis av en kvalitetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="e4870-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="e4870-109">Välj en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="e4870-109">Select a quality order</span></span>
1. <span data-ttu-id="e4870-110">I navigeringsfönstret gå till **Moduler > Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="e4870-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="e4870-111">Välj den kvalitetsorder som skapades innan du startade den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="e4870-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="e4870-112">Registrera testresultat</span><span class="sxs-lookup"><span data-stu-id="e4870-112">Record test results</span></span>
1. <span data-ttu-id="e4870-113">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="e4870-113">Select **Results**.</span></span>
2. <span data-ttu-id="e4870-114">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e4870-114">Select **Edit**.</span></span>
3. <span data-ttu-id="e4870-115">Ange ett nummer i fältet **Resultatkvantitet**.</span><span class="sxs-lookup"><span data-stu-id="e4870-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="e4870-116">I fältet **Resultat**  väljer du önskad post i listrutan.</span><span class="sxs-lookup"><span data-stu-id="e4870-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="e4870-117">I det här exemplet baseras resultatet på ett fördefinierat resultat.</span><span class="sxs-lookup"><span data-stu-id="e4870-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="e4870-118">Normalt sett skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.</span><span class="sxs-lookup"><span data-stu-id="e4870-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="e4870-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e4870-119">Select **Save**.</span></span>
6. <span data-ttu-id="e4870-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4870-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="e4870-121">Validera kvalitetsordern</span><span class="sxs-lookup"><span data-stu-id="e4870-121">Validate the quality order</span></span>
1. <span data-ttu-id="e4870-122">Välj **validera**.</span><span class="sxs-lookup"><span data-stu-id="e4870-122">Select **Validate**.</span></span>
2. <span data-ttu-id="e4870-123">I fältet **validerad av** väljer du den användare som utför inspektionen i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="e4870-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="e4870-124">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="e4870-124">Click **Select**.</span></span>
4. <span data-ttu-id="e4870-125">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4870-125">Select **OK**.</span></span>
5. <span data-ttu-id="e4870-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4870-126">Close the page.</span></span>

