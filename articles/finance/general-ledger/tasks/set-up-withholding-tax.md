---
title: Ställ in källskatt
description: Det här avsnittet innehåller information om hur du ställer in källskatt.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 135cca434a1689bf22ee468894dcf8746071e7ca
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144707"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="b64dc-103">Ställ in källskatt</span><span class="sxs-lookup"><span data-stu-id="b64dc-103">Set up withholding tax</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b64dc-104">Det här avsnittet innehåller information om hur du ställer in källskatt.</span><span class="sxs-lookup"><span data-stu-id="b64dc-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="b64dc-105">*Källskatt* är en skatt på leverantörer som inte skapar momstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="b64dc-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="b64dc-106">Källskatt som beräknats på leverantörsbetalningar är en skuld.</span><span class="sxs-lookup"><span data-stu-id="b64dc-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="b64dc-107">Därför är endast balansräkningskonton eller skuldkonton giltiga konton för bokföring av källskatt.</span><span class="sxs-lookup"><span data-stu-id="b64dc-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="b64dc-108">Den här uppgifthandboken visar hur du ställer in källskatt.</span><span class="sxs-lookup"><span data-stu-id="b64dc-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="b64dc-109">Gå till **Navigeringsfönster > Moduler > Skatt > Indirekt moms > Källskatt > Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="b64dc-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-110">Select **New**.</span></span>
3. <span data-ttu-id="b64dc-111">I fältet **Källskattekod** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="b64dc-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="b64dc-112">Ange namnet på källskattekoden i fältet **Källskattenamn**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="b64dc-113">Välj **huvudkontot** för bokföring av källskatteskulder i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="b64dc-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="b64dc-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-114">Select **Save**.</span></span>
7. <span data-ttu-id="b64dc-115">Välj **Värden** och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="b64dc-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="b64dc-116">Ange en procentsats som används för beräkning av källskatten i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="b64dc-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-117">Select **Save**.</span></span>
10. <span data-ttu-id="b64dc-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b64dc-118">Close the page.</span></span>
11. <span data-ttu-id="b64dc-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-119">Select **Save**.</span></span>
12. <span data-ttu-id="b64dc-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b64dc-120">Close the page.</span></span>
13. <span data-ttu-id="b64dc-121">Gå till **Navigeringsfönster > Moduler > Skatt > Indirekt moms > Källskatt > Källskattegrupper**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="b64dc-122">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-122">Select **New**.</span></span>
15. <span data-ttu-id="b64dc-123">Ange ID på källskattegruppen i fältet **Källskattegrupp**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="b64dc-124">Ange namn på källskattegruppen i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="b64dc-125">Välj källskattekoden i fältet **Källskattekod**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="b64dc-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b64dc-126">Select **Save**.</span></span>
19. <span data-ttu-id="b64dc-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b64dc-127">Close the page.</span></span>

