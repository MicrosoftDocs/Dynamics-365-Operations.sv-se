---
title: Fördröjningstolerans (negativa dagar)
description: Det här avsnittet innehåller information om fördröjningstoleransberäkningen och hur den påverkar skapandet av planerad order i Planeringsoptimering.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306473"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="23940-103">Fördröjningstolerans (negativa dagar)</span><span class="sxs-lookup"><span data-stu-id="23940-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="23940-104">Med funktionen för fördröjningstolerans kan ett värde för planeringsoptimering ta hänsyn till värdet för **Negativa dagar** som har angetts för disponeringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="23940-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="23940-105">Den används för att utöka den fördröjningstoleransperiod som används vid huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="23940-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="23940-106">På det här sättet kan du undvika att skapa nya leveransorder om befintlig leverans kommer att täcka efterfrågan efter en kort fördröjning.</span><span class="sxs-lookup"><span data-stu-id="23940-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="23940-107">Syftet med funktionen är att avgöra om det är logiskt att skapa en ny leveransorder för en given efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="23940-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="23940-108">Aktivera funktionen i systemet</span><span class="sxs-lookup"><span data-stu-id="23940-108">Turn on the feature in your system</span></span>

<span data-ttu-id="23940-109">Om du vill göra funktionen för fördröjningstolerans tillgänglig i systemet går du till [Funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Negativa dagar för planeringsoptimering*.</span><span class="sxs-lookup"><span data-stu-id="23940-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="23940-110">Fördröjningstolerans vid planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="23940-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="23940-111">Fördröjningstoleransen representerar antalet dagar efter den lead-tid du är villiga att vänta innan du beställer nya påfyllnader när befintlig leverans redan har planerats.</span><span class="sxs-lookup"><span data-stu-id="23940-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="23940-112">Fördröjningstolerans definieras genom att använda kalenderdagar, inte arbetsdagar.</span><span class="sxs-lookup"><span data-stu-id="23940-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="23940-113">Vid huvudplaneringen, när systemet beräknar fördröjningstoleransen, tar det hänsyn till inställningen **Negativa dagar**.</span><span class="sxs-lookup"><span data-stu-id="23940-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="23940-114">Du kan ange värdet **negativa dagar** på sidan **Disponeringsgrupper** eller på sidan **Artikeldisponering**.</span><span class="sxs-lookup"><span data-stu-id="23940-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="23940-115">Systemet kopplar förseningtoleransberäkningen till det *tidigaste påfyllnadsdatumet*, som är lika med dagens datum plus ledtiden.</span><span class="sxs-lookup"><span data-stu-id="23940-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="23940-116">Fördröjningstoleransen beräknas med följande formel, där *max()* hittar det större av två värden:</span><span class="sxs-lookup"><span data-stu-id="23940-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="23940-117">*max(Tidigaste påfyllnadsdatum, Förfallodatum för efterfrågan)* – *Efterfrågans förfallodatum* + *Negativa dagar*</span><span class="sxs-lookup"><span data-stu-id="23940-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="23940-118">Formeln garanterar att huvudplaneringen inte skapar nya leveransorder när det finns tillräckligt med tillförsel under produktens produktionstid.</span><span class="sxs-lookup"><span data-stu-id="23940-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="23940-119">I beräkningen av fördröjningstoleransen i Planeringsoptimering används alltid den dynamiska beräkningen av negativa dagar från den inbyggda huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="23940-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="23940-120">Inställningen **Använd dynamiska negativa dagar** på sidan **Parametrar för huvudplanering** påverkar inte det här beteendet.</span><span class="sxs-lookup"><span data-stu-id="23940-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="23940-121">Om det befintliga tillgången innebär en efterfrågefördröjning som är mindre än eller lika med den beräknade fördröjningstoleransen, innebär Planeringsoptimering att det finns en befintlig tillgång till efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="23940-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="23940-122">I vissa fall är det bättre att försena efterfrågan än att sluta med överbehov.</span><span class="sxs-lookup"><span data-stu-id="23940-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="23940-123">Följande delgrupper ger exempel som visar hur fördröjningar tolerans påverkar skapandet av planerade order i Planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="23940-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="23940-124">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="23940-124">Example 1</span></span>

<span data-ttu-id="23940-125">En produkt har följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="23940-125">A product has the following configuration:</span></span>

- <span data-ttu-id="23940-126">**Ledtid:** *10*</span><span class="sxs-lookup"><span data-stu-id="23940-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="23940-127">**Negativa dagar:** *2*</span><span class="sxs-lookup"><span data-stu-id="23940-127">**Negative days:** *2*</span></span>

<span data-ttu-id="23940-128">Följande tillgång och efterfrågan finns för produkten:</span><span class="sxs-lookup"><span data-stu-id="23940-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="23940-129">**Efterfrågan för idag:** En försäljningsorder för kvantiteten 10</span><span class="sxs-lookup"><span data-stu-id="23940-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="23940-130">**Leverans om 12 dagar:** En inköpsorder med kvantiteten 10</span><span class="sxs-lookup"><span data-stu-id="23940-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="23940-131">Befintlig leverans kan täcka efterfrågan inom 12 dagar och den perioden är lika med fördröjningstoleransen.</span><span class="sxs-lookup"><span data-stu-id="23940-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="23940-132">När huvudplaneringen körs skapas därför inga planerade order.</span><span class="sxs-lookup"><span data-stu-id="23940-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="23940-133">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="23940-133">Example 2</span></span>

<span data-ttu-id="23940-134">En produkt har följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="23940-134">A product has the following configuration:</span></span>

- <span data-ttu-id="23940-135">**Ledtid:** *10*</span><span class="sxs-lookup"><span data-stu-id="23940-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="23940-136">**Negativa dagar:** *0*</span><span class="sxs-lookup"><span data-stu-id="23940-136">**Negative days:** *0*</span></span>

<span data-ttu-id="23940-137">Följande tillgång och efterfrågan finns för produkten:</span><span class="sxs-lookup"><span data-stu-id="23940-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="23940-138">**Efterfrågan för idag:** En försäljningsorder för kvantiteten 10</span><span class="sxs-lookup"><span data-stu-id="23940-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="23940-139">**Leverans om 12 dagar:** En inköpsorder med kvantiteten 10</span><span class="sxs-lookup"><span data-stu-id="23940-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="23940-140">Befintliga leveranser kan täcka efterfrågan endast efter 12 dagar.</span><span class="sxs-lookup"><span data-stu-id="23940-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="23940-141">Fördröjningstoleransen är dock 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="23940-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="23940-142">När huvudplaneringen körs skapas därför en planerad order med kvantiteten 10.</span><span class="sxs-lookup"><span data-stu-id="23940-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="23940-143">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="23940-143">Example 3</span></span>

<span data-ttu-id="23940-144">En produkt har följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="23940-144">A product has the following configuration:</span></span>

- <span data-ttu-id="23940-145">**Ledtid:** *10*</span><span class="sxs-lookup"><span data-stu-id="23940-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="23940-146">**Negativa dagar:** *2*</span><span class="sxs-lookup"><span data-stu-id="23940-146">**Negative days:** *2*</span></span>

<span data-ttu-id="23940-147">Följande tillgång och efterfrågan finns för produkten:</span><span class="sxs-lookup"><span data-stu-id="23940-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="23940-148">**Efterfrågan om 11 dagar:** En försäljningsorder för kvantiteten 10</span><span class="sxs-lookup"><span data-stu-id="23940-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="23940-149">**Leverans om 14 dagar:** En inköpsorder med kvantiteten 10</span><span class="sxs-lookup"><span data-stu-id="23940-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="23940-150">Befintliga leveranser kan täcka efterfrågan endast efter tre dagar.</span><span class="sxs-lookup"><span data-stu-id="23940-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="23940-151">Fördröjningstoleransen är dock två dagar.</span><span class="sxs-lookup"><span data-stu-id="23940-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="23940-152">(I det här fallet omfattar fördröjningstoleransen endast de två negativa dagarna.</span><span class="sxs-lookup"><span data-stu-id="23940-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="23940-153">Efterfrågedatumet inkluderas inte eftersom det är efter produktens ledtid.) När huvudplaneringen körs skapas därför en planerad order med kvantiteten 10.</span><span class="sxs-lookup"><span data-stu-id="23940-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
