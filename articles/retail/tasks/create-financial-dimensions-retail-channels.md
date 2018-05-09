--- 
title: " Skapa ekonomiska dimensioner för detaljhandelskanaler och konfigurera dimensionsvärden för butiker"
description: "Den här proceduren beskriver hur du skapar en ekonomisk dimension för butikskanal med dimensionsvärden och stegen för att konfigurera värden för ekonomisk dimension på butiker."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3782d5d2a43b6b22a6f5b25c806e9d4bba5999a5
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="99c50-103"> Skapa ekonomiska dimensioner för detaljhandelskanaler och konfigurera dimensionsvärden för butiker</span><span class="sxs-lookup"><span data-stu-id="99c50-103">Create financial dimensions for Retail channels and configure dimension values on stores</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="99c50-104">Den här proceduren beskriver hur du skapar en ekonomisk dimension för butikskanal med dimensionsvärden och stegen för att konfigurera värden för ekonomisk dimension på butiker.</span><span class="sxs-lookup"><span data-stu-id="99c50-104">This procedure walks through creating a retail channel financial dimension with dimension values and steps to configure financial dimension values on retail stores.</span></span> <span data-ttu-id="99c50-105">Ämnet inkluderar inte andra relaterade steg, till exempel skapa dimensionsuppsättningar och kontostrukturer.</span><span class="sxs-lookup"><span data-stu-id="99c50-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="99c50-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="99c50-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="99c50-107">Gå till huvudboken > kontoplan > mått > finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="99c50-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="99c50-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99c50-108">Click New.</span></span>
3. <span data-ttu-id="99c50-109">I fältet Använd värden från, välj Butikskanaler.</span><span class="sxs-lookup"><span data-stu-id="99c50-109">In the Use values from field, select 'Retail channels'.</span></span>
4. <span data-ttu-id="99c50-110">I fältet Dimensionsnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="99c50-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="99c50-111">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="99c50-111">Click Activate.</span></span>
6. <span data-ttu-id="99c50-112">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="99c50-112">Click Close.</span></span>
7. <span data-ttu-id="99c50-113">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="99c50-113">Click Activate.</span></span>
8. <span data-ttu-id="99c50-114">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="99c50-114">Click Dimension values.</span></span>
9. <span data-ttu-id="99c50-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="99c50-115">Close the page.</span></span>
10. <span data-ttu-id="99c50-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99c50-116">Click Save.</span></span>
11. <span data-ttu-id="99c50-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="99c50-117">Close the page.</span></span>
12. <span data-ttu-id="99c50-118">Gå till butik och handel > Kanaler > butiker > Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="99c50-118">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
13. <span data-ttu-id="99c50-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99c50-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="99c50-120">Växla expansionen av avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="99c50-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="99c50-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="99c50-121">Click Edit.</span></span>
16. <span data-ttu-id="99c50-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Butikskanal.</span><span class="sxs-lookup"><span data-stu-id="99c50-122">In the Retailchannel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="99c50-123">I listan du söker efter och väljer dimensionsvärdet för butiken som uppdateras.</span><span class="sxs-lookup"><span data-stu-id="99c50-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="99c50-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99c50-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="99c50-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="99c50-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="99c50-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="99c50-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="99c50-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99c50-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="99c50-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="99c50-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="99c50-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="99c50-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="99c50-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99c50-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="99c50-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99c50-131">Click Save.</span></span>


