---
title: Skapa en momsbetalning
description: Med proceduren Kvitta och bokför moms kvittas momssaldon på momskontona och kompenserar dem till momskvittningkontot för en viss period.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7aec00c2fb657f0b4074063ef7acad5f4372ebca
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646345"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="99f50-103">Skapa en momsbetalning</span><span class="sxs-lookup"><span data-stu-id="99f50-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="99f50-104">Med proceduren Kvitta och bokför moms kvittas momssaldon på momskontona och motbokar dem till momskvittningkontot för en viss period.</span><span class="sxs-lookup"><span data-stu-id="99f50-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="99f50-105">Gå till **Moms > Deklarationer > Moms > Kvitta och bokför moms**.</span><span class="sxs-lookup"><span data-stu-id="99f50-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="99f50-106">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kvittningsperiod**.</span><span class="sxs-lookup"><span data-stu-id="99f50-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="99f50-107">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="99f50-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="99f50-108">I fältet **Från datum** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="99f50-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="99f50-109">Om du inte väljer alternativet **Inkludera korrigeringar** på sidan **Redovisningsparametrar** kan kvittningen bearbetas för andra versioner.</span><span class="sxs-lookup"><span data-stu-id="99f50-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="99f50-110">Originalet är den första kvittningen för ett periodintervall och kan bara bearbetas en gång för ett periodintervall.</span><span class="sxs-lookup"><span data-stu-id="99f50-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="99f50-111">De senaste korrigeringarna kvittar momstransaktioner som har bokförts, efter den ursprungliga versionen har skapats.</span><span class="sxs-lookup"><span data-stu-id="99f50-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="99f50-112">I fältet **Transaktionsdatum**, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="99f50-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="99f50-113">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="99f50-113">Click **OK**.</span></span>

