---
title: Skapa ekonomiska dimensioner för butikskanaler och konfigurera dimensionsvärden för butiker
description: Den här proceduren beskriver hur du skapar en ekonomisk dimension för handelskanal med dimensionsvärden och stegen för att konfigurera värden för ekonomisk dimension på butiker.
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
ms.openlocfilehash: ea36732023092f714b3a783d98b512c0fea7dade
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415883"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="66d7e-103">Skapa ekonomiska dimensioner för butikskanaler och konfigurera dimensionsvärden för butiker</span><span class="sxs-lookup"><span data-stu-id="66d7e-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66d7e-104">Den här proceduren beskriver hur du skapar en ekonomisk dimension för handelskanal med dimensionsvärden och stegen för att konfigurera värden för ekonomisk dimension på butiker.</span><span class="sxs-lookup"><span data-stu-id="66d7e-104">This procedure walks through creating a commerce channel financial dimension with dimension values and steps to configure financial dimension values on stores.</span></span> <span data-ttu-id="66d7e-105">Ämnet inkluderar inte andra relaterade steg, till exempel skapa dimensionsuppsättningar och kontostrukturer.</span><span class="sxs-lookup"><span data-stu-id="66d7e-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="66d7e-106">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="66d7e-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="66d7e-107">Gå till huvudboken > kontoplan > mått > finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="66d7e-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="66d7e-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="66d7e-108">Click New.</span></span>
3. <span data-ttu-id="66d7e-109">I fältet Använd värden från, välj Handelskanaler.</span><span class="sxs-lookup"><span data-stu-id="66d7e-109">In the Use values from field, select 'Commerce channels'.</span></span>
4. <span data-ttu-id="66d7e-110">I fältet Dimensionsnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="66d7e-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="66d7e-111">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="66d7e-111">Click Activate.</span></span>
6. <span data-ttu-id="66d7e-112">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="66d7e-112">Click Close.</span></span>
7. <span data-ttu-id="66d7e-113">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="66d7e-113">Click Activate.</span></span>
8. <span data-ttu-id="66d7e-114">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="66d7e-114">Click Dimension values.</span></span>
9. <span data-ttu-id="66d7e-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-115">Close the page.</span></span>
10. <span data-ttu-id="66d7e-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="66d7e-116">Click Save.</span></span>
11. <span data-ttu-id="66d7e-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-117">Close the page.</span></span>
12. <span data-ttu-id="66d7e-118">Gå till Butik och handel > Kanaler > Butiker >Alla butiker.</span><span class="sxs-lookup"><span data-stu-id="66d7e-118">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
13. <span data-ttu-id="66d7e-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="66d7e-120">Växla expansionen av avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="66d7e-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="66d7e-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="66d7e-121">Click Edit.</span></span>
16. <span data-ttu-id="66d7e-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Handelskanal.</span><span class="sxs-lookup"><span data-stu-id="66d7e-122">In the Commerce channel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="66d7e-123">I listan du söker efter och väljer dimensionsvärdet för butiken som uppdateras.</span><span class="sxs-lookup"><span data-stu-id="66d7e-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="66d7e-124">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="66d7e-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="66d7e-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="66d7e-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="66d7e-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="66d7e-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="66d7e-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="66d7e-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="66d7e-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="66d7e-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="66d7e-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="66d7e-131">Click Save.</span></span>

