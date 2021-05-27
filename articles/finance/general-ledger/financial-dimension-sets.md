---
title: Ekonomiska dimensionsuppsättningar
description: Detta ämne beskriver ekonomiska dimensionsuppsättningar och innehåller lite tips för hur du optimerar deras användning.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021838"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="7368d-103">Ekonomiska dimensionsuppsättningar</span><span class="sxs-lookup"><span data-stu-id="7368d-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7368d-104">Detta ämne beskriver ekonomiska dimensionsuppsättningar och innehåller lite tips för hur du optimerar deras användning.</span><span class="sxs-lookup"><span data-stu-id="7368d-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="7368d-105">En dimensionsuppsättning är en ordnad lista över ekonomiska dimensioner som kan användas för att sammanfatta redovisningsdata på ett användardefinierat sätt.</span><span class="sxs-lookup"><span data-stu-id="7368d-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="7368d-106">En primär användning av dimensionsuppsättningar är att definiera en råbalans.</span><span class="sxs-lookup"><span data-stu-id="7368d-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="7368d-107">Den enda standarddimensionsuppsättningen är den dimensionsuppsättning som bara innehåller huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="7368d-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="7368d-108">På sidan **Uppsättningar för ekonomisk dimension** kan du skapa och hantera ekonomiska dimensionsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="7368d-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="7368d-109">Saldon för dimensionsuppsättning</span><span class="sxs-lookup"><span data-stu-id="7368d-109">Dimension set balances</span></span>

<span data-ttu-id="7368d-110">En dimensionsuppsättning kan ha saldon som baseras på dess ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="7368d-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="7368d-111">Saldon finns i redovisningen och baseras på dimensionsuppsättningsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7368d-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="7368d-112">Saldona summeras från redovisningsdatan i syfte att förbättra prestandan när de hämtas (till exempel när en råbalans genereras).</span><span class="sxs-lookup"><span data-stu-id="7368d-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="7368d-113">Skapa saldon</span><span class="sxs-lookup"><span data-stu-id="7368d-113">Create balances</span></span>

<span data-ttu-id="7368d-114">Använd knappen **Skapa saldon** för att initiera saldona för en dimensionsuppsättning som för närvarande inte har några saldon.</span><span class="sxs-lookup"><span data-stu-id="7368d-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="7368d-115">Vi rekommenderar att du begränsar antalet dimensionsuppsättningar som har saldon, detta eftersom saldouppdateringar påverkar alla redovisningsbokföringsaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="7368d-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="7368d-116">Uppdatera saldon</span><span class="sxs-lookup"><span data-stu-id="7368d-116">Update balances</span></span>

<span data-ttu-id="7368d-117">Använd knappen **Uppdatera saldon** för att inkludera den senaste bokföringsaktiviteten för redovisning i saldona.</span><span class="sxs-lookup"><span data-stu-id="7368d-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="7368d-118">Saldouppdateringar är lätta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="7368d-118">Balance updates are light operations.</span></span> <span data-ttu-id="7368d-119">De får bara bearbeta den bokföringsaktivitet i redovisningen som har skett sedan den senaste uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="7368d-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="7368d-120">Visning av råbalansen framtvingar en uppdatering i syfte att säkerställa att de saldon som visas är aktuella.</span><span class="sxs-lookup"><span data-stu-id="7368d-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="7368d-121">Överväg att använda ett återkommande batchjobb så att det går snabbt att uppdatera de dimensionsuppsättningar som används mest.</span><span class="sxs-lookup"><span data-stu-id="7368d-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="7368d-122">På detta sätt minimerar du den tid som råbalansanvändare måste vänta.</span><span class="sxs-lookup"><span data-stu-id="7368d-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="7368d-123">Återskapa saldon</span><span class="sxs-lookup"><span data-stu-id="7368d-123">Rebuild balances</span></span>

<span data-ttu-id="7368d-124">Använd knappen **Återskapa saldon** om du vill skapa saldona från grunden.</span><span class="sxs-lookup"><span data-stu-id="7368d-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="7368d-125">På det här sättet hjälper du till att säkerställa att de matchar data i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="7368d-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="7368d-126">Att skapa saldon på nytt kräver mycket bearbetning och ska normalt inte krävas.</span><span class="sxs-lookup"><span data-stu-id="7368d-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="7368d-127">Om det finns ett scenario där saldon regelbundet måste byggas om rekommenderar vi att du kontaktar kundtjänsten.</span><span class="sxs-lookup"><span data-stu-id="7368d-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="7368d-128">Kundtjänst kan hjälpa dig att ta reda på varför saldon inte matchar datan i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="7368d-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="7368d-129">Rensa saldon</span><span class="sxs-lookup"><span data-stu-id="7368d-129">Clear balances</span></span>

<span data-ttu-id="7368d-130">Använd knappen **Rensa saldon** om du vill ta bort saldon och stoppa ytterligare uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="7368d-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="7368d-131">Dimensionsuppsättningen kommer inte längre att påverka aktiviteter i redovisningsbokföringen.</span><span class="sxs-lookup"><span data-stu-id="7368d-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="7368d-132">Mer information finns i [Ekonomiska dimensioner](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="7368d-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
