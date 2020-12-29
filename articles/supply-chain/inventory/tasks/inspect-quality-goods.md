---
title: Kontrollera kvaliteten på varor
description: I det här avsnittet beskrivs hur du bearbetar en kvalitetsorder.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee5f83b2dad60567341f33a73ce63d01e9da8289
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437929"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="1d338-103">Kontrollera kvaliteten på varor</span><span class="sxs-lookup"><span data-stu-id="1d338-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1d338-104">I det här avsnittet beskrivs hur du bearbetar en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d338-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="1d338-105">Du kan köra den här handboken i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="1d338-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="1d338-106">Innan du startar den här exempelproceduren måste du bekräfta inköpsorder ”000016” och bokföra en produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="1d338-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="1d338-107">Då skapas en kvalitetsorder automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1d338-107">This will automatically create a quality order.</span></span> <span data-ttu-id="1d338-108">Kvalitets-inspektioner utförs vanligtvis av en kvalitetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="1d338-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="1d338-109">Välj en kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="1d338-109">Select a quality order</span></span>
1. <span data-ttu-id="1d338-110">I navigeringsfönstret gå till **Moduler > Lagerhantering > Periodiska uppgifter > Kvalitetshantering > Kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="1d338-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="1d338-111">Välj den kvalitetsorder som skapades innan du startade den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="1d338-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="1d338-112">Registrera testresultat</span><span class="sxs-lookup"><span data-stu-id="1d338-112">Record test results</span></span>
1. <span data-ttu-id="1d338-113">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="1d338-113">Select **Results**.</span></span>
2. <span data-ttu-id="1d338-114">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1d338-114">Select **Edit**.</span></span>
3. <span data-ttu-id="1d338-115">Ange ett nummer i fältet **Resultatkvantitet**.</span><span class="sxs-lookup"><span data-stu-id="1d338-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="1d338-116">I fältet **Resultat**  väljer du önskad post i listrutan.</span><span class="sxs-lookup"><span data-stu-id="1d338-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="1d338-117">I det här exemplet baseras resultatet på ett fördefinierat resultat.</span><span class="sxs-lookup"><span data-stu-id="1d338-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="1d338-118">Normalt sett skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.</span><span class="sxs-lookup"><span data-stu-id="1d338-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="1d338-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1d338-119">Select **Save**.</span></span>
6. <span data-ttu-id="1d338-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1d338-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="1d338-121">Validera kvalitetsordern</span><span class="sxs-lookup"><span data-stu-id="1d338-121">Validate the quality order</span></span>
1. <span data-ttu-id="1d338-122">Välj **validera**.</span><span class="sxs-lookup"><span data-stu-id="1d338-122">Select **Validate**.</span></span>
2. <span data-ttu-id="1d338-123">I fältet **validerad av** väljer du den användare som utför inspektionen i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="1d338-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="1d338-124">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="1d338-124">Click **Select**.</span></span>
4. <span data-ttu-id="1d338-125">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d338-125">Select **OK**.</span></span>
5. <span data-ttu-id="1d338-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1d338-126">Close the page.</span></span>

