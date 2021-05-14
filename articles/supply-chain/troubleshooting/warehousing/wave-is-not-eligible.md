---
title: Cyklen är ej berättigad till rensning
description: Cyklen är ej berättigad till rensning
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924337"
---
# <a name="wave-isnt-eligible-for-cleanup"></a><span data-ttu-id="c6592-103">Cyklen är ej berättigad till rensning</span><span class="sxs-lookup"><span data-stu-id="c6592-103">Wave isn't eligible for cleanup</span></span>

<span data-ttu-id="c6592-104">Felkod: WaveNotEligibleForCleanup</span><span class="sxs-lookup"><span data-stu-id="c6592-104">Error code: WaveNotEligibleForCleanup</span></span>

## <a name="symptoms"></a><span data-ttu-id="c6592-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="c6592-105">Symptoms</span></span>

<span data-ttu-id="c6592-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c6592-106">The system shows the following error message:</span></span>

> <span data-ttu-id="c6592-107">Påfyllnaden %1 är inte berättigad till rensning.</span><span class="sxs-lookup"><span data-stu-id="c6592-107">Wave %1 is not eligible for cleanup.</span></span>

<span data-ttu-id="c6592-108">Cykeldatan kan inte rensas.</span><span class="sxs-lookup"><span data-stu-id="c6592-108">The wave data can't be cleaned up.</span></span>  

## <a name="cause"></a><span data-ttu-id="c6592-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="c6592-109">Cause</span></span>

<span data-ttu-id="c6592-110">Cyklen bearbetas just nu enligt något av följande villkor:</span><span class="sxs-lookup"><span data-stu-id="c6592-110">The wave is currently being processed, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="c6592-111">Fältet **Cykelstatus** är inställt på *Körs*.</span><span class="sxs-lookup"><span data-stu-id="c6592-111">The **Wave status** field is set to *Executing*.</span></span>
- <span data-ttu-id="c6592-112">När du väljer **Batchjobb** i gruppen **Cykel** på fliken **Cykel** i åtgärdsfönstret, är fältet **Status** inte inställt på *Avslutat*, *Fel* eller *Avslutad*.</span><span class="sxs-lookup"><span data-stu-id="c6592-112">When you select **Batch job** in the **Wave** group on the **Wave** tab of the Action Pane, the **Status** field isn't set to *Ended*, *Error*, or *Canceled*.</span></span> <span data-ttu-id="c6592-113">Därför körs för tillfället ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="c6592-113">Therefore, a batch job is currently running.</span></span>

## <a name="resolution"></a><span data-ttu-id="c6592-114">Upplösning</span><span class="sxs-lookup"><span data-stu-id="c6592-114">Resolution</span></span>

<span data-ttu-id="c6592-115">I åtgärdsfönstret, på fliken **Cykel** i gruppen **Cykel**, väljer du **Batchjobb** och följer sedan ett av följande steg:</span><span class="sxs-lookup"><span data-stu-id="c6592-115">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Batch job**, and then follow one of these steps:</span></span>

- <span data-ttu-id="c6592-116">Om fältet **Status** är inställt på *Körs*: I åtgärdsfönstret, på fliken **Batchjobb** i gruppen **Batchjobb** väljer du **Visa uppgifter**.</span><span class="sxs-lookup"><span data-stu-id="c6592-116">If the **Status** field is set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Batch job** group, select **View tasks**.</span></span> <span data-ttu-id="c6592-117">Genom att uppdatera sidan **Batchuppgifter** kan du följa processen.</span><span class="sxs-lookup"><span data-stu-id="c6592-117">You can follow the progress by refreshing the **Batch tasks** page.</span></span>
- <span data-ttu-id="c6592-118">Om fältet **Status** inte är inställt på *Körs*: I åtgärdsfönstret, på fliken **Batchjobb** i gruppen **Funktioner**, väljer du **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="c6592-118">If the **Status** field isn't set to *Executing*: On the Action Pane, on the **Batch job** tab, in the **Functions** group, select **Change status**.</span></span> <span data-ttu-id="c6592-119">I fältet **Välj ny status** väljer du *Väntar*.</span><span class="sxs-lookup"><span data-stu-id="c6592-119">In the **Select new status** field, select *Waiting*.</span></span> <span data-ttu-id="c6592-120">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6592-120">Then select **OK**.</span></span>
