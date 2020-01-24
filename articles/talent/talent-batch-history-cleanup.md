---
title: Optimera prestanda med automatiska rensningsuppgifter
description: I det här avsnittet beskrivs hur du löser vissa prestandaproblem med Microsoft Dynamics 365 Talent genom att rensa historiken för batchjobb.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: fe536ace5c25765bd9c573f9303bd92f834765f7
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897982"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="be7eb-103">Optimera prestanda med automatiska rensningsuppgifter</span><span class="sxs-lookup"><span data-stu-id="be7eb-103">Optimize performance with auto cleanup tasks</span></span>

<span data-ttu-id="be7eb-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="be7eb-104">**Issue**</span></span>

<span data-ttu-id="be7eb-105">Microsoft Dynamics 365 Talent kan uppleva prestandaproblem om historiken för batchjobb blir för stor.</span><span class="sxs-lookup"><span data-stu-id="be7eb-105">Microsoft Dynamics 365 Talent can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="be7eb-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="be7eb-106">**Cause**</span></span>

<span data-ttu-id="be7eb-107">Batchjobb som körs ofta kan leda till en hållbar tillväxt av historiken för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="be7eb-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="be7eb-108">Detta kan leda till prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="be7eb-108">This can cause performance issues.</span></span> 

<span data-ttu-id="be7eb-109">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="be7eb-109">**Resolution**</span></span>

<span data-ttu-id="be7eb-110">Schemalägg en automatisk uppgift för att rensa historiken för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="be7eb-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="be7eb-111">Vi rekommenderar att du anger att aktiviteten ska köras varje vecka, men du kan behöva göra en rensning mer eller mindre ofta, beroende på din miljö.</span><span class="sxs-lookup"><span data-stu-id="be7eb-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="be7eb-112">Följande procedur innehåller våra rekommenderade inställningar, men du kan ändra dem efter dina behov.</span><span class="sxs-lookup"><span data-stu-id="be7eb-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="be7eb-113">Välj **systemadministration** i Talent.</span><span class="sxs-lookup"><span data-stu-id="be7eb-113">In Talent, select **System administration**.</span></span>

2. <span data-ttu-id="be7eb-114">I fätet **Sök**, ange **Rensa historik för batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Sök efter rensa historik för batchjobb](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="be7eb-116">I **Historikgränser (dagar)**, ange **30**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-116">In **History limit (days)**, enter **30**.</span></span>

   ![Ange historikgräns till 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="be7eb-118">Välj **kör i bakgrunden** och välj sedan **återkommande**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Ange upprepning](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="be7eb-120">Under **definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg och välj sedan **INGET SLUTDATUM**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Definiera återkommande startdatum och tid](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="be7eb-122">Under **ÅTERKOMMANDE MÖNSTER**, välj **dagar** och ange **UPPREPA EFTER ANGIVET INTERVALL** till **7**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Ställ in rensning för att upprepa veckovis](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="be7eb-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-124">Select **OK**.</span></span>

8. <span data-ttu-id="be7eb-125">Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="be7eb-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>

