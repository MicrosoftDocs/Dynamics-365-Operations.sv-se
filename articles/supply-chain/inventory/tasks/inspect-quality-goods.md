---
title: Kontrollera kvaliteten på varor
description: I detta ämne beskrivs hur du bearbetar kvalitetsorder.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956144"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="e4e4a-103">Kontrollera kvaliteten på varor</span><span class="sxs-lookup"><span data-stu-id="e4e4a-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4e4a-104">I detta ämne beskrivs hur du bearbetar kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="e4e4a-105">Kvalitetsinspektioner utförs vanligtvis av en kvalitetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="e4e4a-106">Om standarddemonstrationsdatan har installerats kan du använda den för att genomföra procedurerna i detta ämne.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="e4e4a-107">Om du vill använda demonstrationsdatan väljer du den juridiska personen *USMF* innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="e4e4a-108">Du måste sedan bekräfta inköpsordern *000016* och bokföra en produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="e4e4a-109">En kvalitetsorder genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="e4e4a-110">Steg 1: Välj en kvalitetsorder</span><span class="sxs-lookup"><span data-stu-id="e4e4a-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="e4e4a-111">Gör så här om du vill välja en kvalitetsorder:</span><span class="sxs-lookup"><span data-stu-id="e4e4a-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="e4e4a-112">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="e4e4a-113">Välj den kvalitetsorder som genererades innan du startade den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="e4e4a-114">Steg 2: Registrera testresultaten</span><span class="sxs-lookup"><span data-stu-id="e4e4a-114">Step 2: Record test results</span></span>

<span data-ttu-id="e4e4a-115">Gör så här om du vill registrera testresultat:</span><span class="sxs-lookup"><span data-stu-id="e4e4a-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="e4e4a-116">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-116">Select **Results**.</span></span>
1. <span data-ttu-id="e4e4a-117">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-117">Select **Edit**.</span></span>
1. <span data-ttu-id="e4e4a-118">Ange ett nummer i fältet **Resultatkvantitet**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="e4e4a-119">Välj önskad post i fältet **Resultat**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="e4e4a-120">I det här exemplet baseras resultatet på ett fördefinierat resultat.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="e4e4a-121">Vanligtvis skulle du registrera ett mer specifikt testresultat, till exempel en storlek eller en annan dimension.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="e4e4a-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-122">Select **Save**.</span></span>
1. <span data-ttu-id="e4e4a-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="e4e4a-124">Steg 3: Validera kvalitetsordern</span><span class="sxs-lookup"><span data-stu-id="e4e4a-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="e4e4a-125">Gör så här om du vill validera en kvalitetsorder:</span><span class="sxs-lookup"><span data-stu-id="e4e4a-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="e4e4a-126">Välj **validera**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-126">Select **Validate**.</span></span>
1. <span data-ttu-id="e4e4a-127">I fältet **Validerades av** väljer du den användare utför inspektionen.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="e4e4a-128">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-128">Select **Select**.</span></span>
1. <span data-ttu-id="e4e4a-129">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-129">Select **OK**.</span></span>
1. <span data-ttu-id="e4e4a-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e4e4a-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
