--- 
title: Skapa en momsbetalning
description: "Med jobbet Kvitta och bokför moms kvittas momssaldon på momskontona och kompenserar dem till momskvittningkontot för en viss period."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6ee84da7fd055c8b0b50c43f134c0fc048ecfaeb
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="790aa-103">Skapa en momsbetalning</span><span class="sxs-lookup"><span data-stu-id="790aa-103">Create a sales tax payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="790aa-104">Med jobbet Kvitta och bokför moms kvittas momssaldon på momskontona och kompenserar dem till momskvittningkontot för en viss period.</span><span class="sxs-lookup"><span data-stu-id="790aa-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="790aa-105">Gå till Moms > Deklarationer > Moms > Kvitta och bokför moms.</span><span class="sxs-lookup"><span data-stu-id="790aa-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="790aa-106">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kvittningsperiod.</span><span class="sxs-lookup"><span data-stu-id="790aa-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="790aa-107">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="790aa-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="790aa-108">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="790aa-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="790aa-109">Om alternativet Inkludera korrigeringar inte har markerats på redovisningparametersidan kan kvittningen bearbetas för andra versioner.</span><span class="sxs-lookup"><span data-stu-id="790aa-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="790aa-110">Originalet är den första kvittningen för ett periodintervall och bearbetas bara en gång för ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="790aa-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="790aa-111">Senaste korrigeringar kvittar momstransaktioner som har bokförts, efter den ursprungliga versionen har skapats.</span><span class="sxs-lookup"><span data-stu-id="790aa-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="790aa-112">I fältet Transaktionsdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="790aa-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="790aa-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="790aa-113">Click OK.</span></span>


