--- 
title: " Konfigurera och kör ett jobb för att bokföra utdrag"
description: "Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker."
author: josaw1
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
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f3587fe70dc6a0d8330063db77e625040a53da98
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="configure-and-run-a-job-to-post-statements"></a><span data-ttu-id="1cfe7-103"> Konfigurera och kör ett jobb för att bokföra utdrag</span><span class="sxs-lookup"><span data-stu-id="1cfe7-103">Configure and run a job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="1cfe7-104">Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="1cfe7-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="1cfe7-106">Alla arbetsytor > ..</span><span class="sxs-lookup"><span data-stu-id="1cfe7-106">Go to All workspaces > ..</span></span> <span data-ttu-id="1cfe7-107">> Butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-107">> Retail store financials.</span></span>
2. <span data-ttu-id="1cfe7-108">Klicka på Bokför utdrag.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-108">Click Post statements.</span></span>
    * <span data-ttu-id="1cfe7-109">Välj en organisationshierarki och sedan i organisationsnodträdet, välj antingen en enskild butik eller en nod.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="1cfe7-110">Välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="1cfe7-111">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="1cfe7-112">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="1cfe7-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="1cfe7-113">Markera eller avmarkera kryssrutan Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="1cfe7-114">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-114">Click Recurrence.</span></span>
6. <span data-ttu-id="1cfe7-115">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="1cfe7-116">Ange en tid i fältet Starttid.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="1cfe7-117">Välj om du vill att slutföra återkommande efter ett visst antal körningar, vid ett visst datum eller aldrig.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="1cfe7-118">Välj sedan de olika alternativen för att definiera hur ofta du vill att jobbet ska köras.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="1cfe7-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-119">Click OK.</span></span>
9. <span data-ttu-id="1cfe7-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1cfe7-120">Click OK.</span></span>


