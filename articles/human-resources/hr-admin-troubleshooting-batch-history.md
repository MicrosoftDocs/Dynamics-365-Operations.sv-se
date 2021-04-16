---
title: Optimera prestanda med automatiska rensningsuppgifter
description: I det här avsnittet beskrivs hur du löser vissa prestandaproblem med Microsoft Dynamics 365 Human Resources genom att rensa historiken för batchjobb.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 0372833c11e0919fa03d57ea258e81a89ab9ff31
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803955"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="976b9-103">Optimera prestanda med automatiska rensningsuppgifter</span><span class="sxs-lookup"><span data-stu-id="976b9-103">Optimize performance with auto cleanup tasks</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="976b9-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="976b9-104">**Issue**</span></span>

<span data-ttu-id="976b9-105">Microsoft Dynamics 365 Human Resources kan uppleva prestandaproblem om historiken för batchjobb blir för stor.</span><span class="sxs-lookup"><span data-stu-id="976b9-105">Microsoft Dynamics 365 Human Resources can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="976b9-106">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="976b9-106">**Cause**</span></span>

<span data-ttu-id="976b9-107">Batchjobb som körs ofta kan leda till en hållbar tillväxt av historiken för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="976b9-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="976b9-108">Detta kan leda till prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="976b9-108">This can cause performance issues.</span></span> 

<span data-ttu-id="976b9-109">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="976b9-109">**Resolution**</span></span>

<span data-ttu-id="976b9-110">Schemalägg en automatisk uppgift för att rensa historiken för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="976b9-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="976b9-111">Vi rekommenderar att du anger att aktiviteten ska köras varje vecka, men du kan behöva göra en rensning mer eller mindre ofta, beroende på din miljö.</span><span class="sxs-lookup"><span data-stu-id="976b9-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="976b9-112">Följande procedur innehåller våra rekommenderade inställningar, men du kan ändra dem efter dina behov.</span><span class="sxs-lookup"><span data-stu-id="976b9-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="976b9-113">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="976b9-113">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="976b9-114">I fätet **Sök**, ange **Rensa historik för batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="976b9-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Sök efter rensa historik för batchjobb](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="976b9-116">I **Historikgränser (dagar)**, ange **30**.</span><span class="sxs-lookup"><span data-stu-id="976b9-116">In **History limit (days)**, enter **30**.</span></span>

   ![Ange historikgräns till 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="976b9-118">Välj **kör i bakgrunden** och välj sedan **återkommande**.</span><span class="sxs-lookup"><span data-stu-id="976b9-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Ange upprepning](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="976b9-120">Under **definiera återkommande**, ange **Startdatum** och **Starttid** vid ledighet eller helg och välj sedan **INGET SLUTDATUM**.</span><span class="sxs-lookup"><span data-stu-id="976b9-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Definiera återkommande startdatum och tid](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="976b9-122">Under **ÅTERKOMMANDE MÖNSTER**, välj **dagar** och ange **UPPREPA EFTER ANGIVET INTERVALL** till **7**.</span><span class="sxs-lookup"><span data-stu-id="976b9-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Ställ in rensning för att upprepa veckovis](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="976b9-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="976b9-124">Select **OK**.</span></span>

8. <span data-ttu-id="976b9-125">Ändra övriga parametrar under **kör i bakgrunden** om det behövs och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="976b9-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]