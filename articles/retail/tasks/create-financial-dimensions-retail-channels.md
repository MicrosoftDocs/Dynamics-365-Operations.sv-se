---
title: Skapa ekonomiska dimensioner för detaljhandelskanaler och konfigurera dimensionsvärden för butiker
description: Den här proceduren beskriver hur du skapar en ekonomisk dimension för butikskanal med dimensionsvärden och stegen för att konfigurera värden för ekonomisk dimension på butiker.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf32d17a36fd699141ce697d23e20b2eb5cbfa54
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "354539"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="872cd-103">Skapa ekonomiska dimensioner för detaljhandelskanaler och konfigurera dimensionsvärden för butiker</span><span class="sxs-lookup"><span data-stu-id="872cd-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="872cd-104">Den här proceduren beskriver hur du skapar en ekonomisk dimension för butikskanal med dimensionsvärden och stegen för att konfigurera värden för ekonomisk dimension på butiker.</span><span class="sxs-lookup"><span data-stu-id="872cd-104">This procedure walks through creating a retail channel financial dimension with dimension values and steps to configure financial dimension values on retail stores.</span></span> <span data-ttu-id="872cd-105">Ämnet inkluderar inte andra relaterade steg, till exempel skapa dimensionsuppsättningar och kontostrukturer.</span><span class="sxs-lookup"><span data-stu-id="872cd-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="872cd-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="872cd-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="872cd-107">Gå till huvudboken > kontoplan > mått > finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="872cd-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="872cd-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="872cd-108">Click New.</span></span>
3. <span data-ttu-id="872cd-109">I fältet Använd värden från, välj Butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="872cd-109">In the Use values from field, select 'Retail channels'.</span></span>
4. <span data-ttu-id="872cd-110">I fältet Dimensionsnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="872cd-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="872cd-111">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="872cd-111">Click Activate.</span></span>
6. <span data-ttu-id="872cd-112">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="872cd-112">Click Close.</span></span>
7. <span data-ttu-id="872cd-113">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="872cd-113">Click Activate.</span></span>
8. <span data-ttu-id="872cd-114">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="872cd-114">Click Dimension values.</span></span>
9. <span data-ttu-id="872cd-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="872cd-115">Close the page.</span></span>
10. <span data-ttu-id="872cd-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="872cd-116">Click Save.</span></span>
11. <span data-ttu-id="872cd-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="872cd-117">Close the page.</span></span>
12. <span data-ttu-id="872cd-118">Gå till butik och handel > Kanaler > butiker > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="872cd-118">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
13. <span data-ttu-id="872cd-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="872cd-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="872cd-120">Växla expansionen av avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="872cd-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="872cd-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="872cd-121">Click Edit.</span></span>
16. <span data-ttu-id="872cd-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Butikskanal.</span><span class="sxs-lookup"><span data-stu-id="872cd-122">In the Retailchannel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="872cd-123">I listan du söker efter och väljer dimensionsvärdet för butiken som uppdateras.</span><span class="sxs-lookup"><span data-stu-id="872cd-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="872cd-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="872cd-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="872cd-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="872cd-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="872cd-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="872cd-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="872cd-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="872cd-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="872cd-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="872cd-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="872cd-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="872cd-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="872cd-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="872cd-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="872cd-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="872cd-131">Click Save.</span></span>

