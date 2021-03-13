---
title: Ställ in global källskatt
description: Detta ämne ämnet innehåller en lista med steg för att ställa in global källskatt för försäljning och inköp.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7ee577651694f0553447d6e9d0851402a586f363
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060795"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="b4fa5-103">Ställ in global källskatt</span><span class="sxs-lookup"><span data-stu-id="b4fa5-103">Set up global withholding tax</span></span>

<span data-ttu-id="b4fa5-104">Detta ämne ämnet innehåller en lista med steg för att ställa in global källskatt för försäljning och inköp.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="b4fa5-105">Ställ in källskattemyndigheter på sidan **Källskattemyndigheter**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="b4fa5-106">Ställ in kvittningsperioder för källskatt på sidan **Kvittningsperioder för källskatt**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="b4fa5-107">Ställ in bokföringsgrupp för källskatt på sidan för **Källskatt > Bokföringsgrupp för redovisning**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="b4fa5-108">Kontot för **Källskatt** kommer att tilldelas ett huvudkonto med bokföringstypen **Källskatt**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="b4fa5-109">Kontot för **Källskattsförskjutning** kommer också att tilldelas ett huvudkonto med **Bokföringstypen** "Källskattsförskjutning".</span><span class="sxs-lookup"><span data-stu-id="b4fa5-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="b4fa5-110">Gå till **Redovisning > Kontoplan > Konton > Huvudkonton**, konfigurera **Bokföringstyp** i det underordnade formuläret **Bokföringsvalidering** för huvudkontona.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="b4fa5-111">Konfigurera källskattekoder på sidan **Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="b4fa5-112">Konfigurera källskattekoder på sidan **Källskattegrupper**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="b4fa5-113">Konfigurera intäktstyper för källskatt på sidan **Intäktstyper för** för **källskatt**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="b4fa5-114">Konfigurera källskattegrupper på sidan **Källskattegrupper för artiklar** för en artikel eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="b4fa5-115">Ställ in **Minsta fakturabelopp** på sidan **Redovisningsparametrar > Källskatt**.</span><span class="sxs-lookup"><span data-stu-id="b4fa5-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>
