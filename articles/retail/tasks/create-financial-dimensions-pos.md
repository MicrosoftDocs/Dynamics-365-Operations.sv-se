--- 
title: " Skapa ekonomiska dimensioner för kassaregister och konfigurera dimensionsvärden för register"
description: "Den här proceduren går igenom hur du skapar ekonomiska dimensioner för kassaregister (POS) och visar hur du konfigurerar värden för ekonomiska dimension i kassor."
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
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: d2d34080409de25a3a1966d0898d0ecd98297891
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="b280d-103"> Skapa ekonomiska dimensioner för kassaregister och konfigurera dimensionsvärden för register</span><span class="sxs-lookup"><span data-stu-id="b280d-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="b280d-104">Den här proceduren går igenom hur du skapar ekonomiska dimensioner för kassaregister (POS) och visar hur du konfigurerar värden för ekonomiska dimension i kassor.</span><span class="sxs-lookup"><span data-stu-id="b280d-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="b280d-105">Detta förfarande inte omfattar andra åtgärder, såsom att skapa dimensionen ställer och strukturer.</span><span class="sxs-lookup"><span data-stu-id="b280d-105">This procedure doesn’t include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="b280d-106">Dessa uppgifter hittar du i andra avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b280d-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="b280d-107">I den här registreringen används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="b280d-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="b280d-108">Gå till huvudboken > kontoplan > mått > finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="b280d-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="b280d-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b280d-109">Click New.</span></span>
3. <span data-ttu-id="b280d-110">Välj ett alternativ i fältet Använd värden från.</span><span class="sxs-lookup"><span data-stu-id="b280d-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="b280d-111">I fältet Dimensionsnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="b280d-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="b280d-112">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="b280d-112">Click Activate.</span></span>
6. <span data-ttu-id="b280d-113">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="b280d-113">Click Close.</span></span>
7. <span data-ttu-id="b280d-114">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="b280d-114">Click Activate.</span></span>
8. <span data-ttu-id="b280d-115">Klicka på Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="b280d-115">Click Dimension values.</span></span>
9. <span data-ttu-id="b280d-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b280d-116">Close the page.</span></span>
10. <span data-ttu-id="b280d-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b280d-117">Click Save.</span></span>
11. <span data-ttu-id="b280d-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b280d-118">Close the page.</span></span>
12. <span data-ttu-id="b280d-119">Gå till butik och handel > kanalinställning > POS inställning > register.</span><span class="sxs-lookup"><span data-stu-id="b280d-119">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="b280d-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="b280d-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="b280d-121">Växla expansionen av avsnittet Ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="b280d-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="b280d-122">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="b280d-122">Click Edit.</span></span>
16. <span data-ttu-id="b280d-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Terminal.</span><span class="sxs-lookup"><span data-stu-id="b280d-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="b280d-124">I listan du söker efter och väljer dimensionsvärdet för registret som uppdateras.</span><span class="sxs-lookup"><span data-stu-id="b280d-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="b280d-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b280d-125">Click Save.</span></span>


