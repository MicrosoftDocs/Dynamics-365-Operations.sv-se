--- 
title: "Konfigurera och köra jobb för att bokföra utdrag"
description: "Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker."
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 676216d90c50c0d3fa1a839cab7a734e624708ba
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="ee283-103">Konfigurera och köra jobb för att bokföra utdrag</span><span class="sxs-lookup"><span data-stu-id="ee283-103">Configure and run job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ee283-104">Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb för att bokföra utdrag för en vald butik eller grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="ee283-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="ee283-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="ee283-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ee283-106">Alla arbetsytor > ..</span><span class="sxs-lookup"><span data-stu-id="ee283-106">Go to All workspaces > ..</span></span> <span data-ttu-id="ee283-107">> Butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="ee283-107">> Retail store financials.</span></span>
2. <span data-ttu-id="ee283-108">Klicka på Bokför utdrag.</span><span class="sxs-lookup"><span data-stu-id="ee283-108">Click Post statements.</span></span>
    * <span data-ttu-id="ee283-109">Välj en organisationshierarki och sedan i organisationsnodträdet, välj antingen en enskild butik eller en nod.</span><span class="sxs-lookup"><span data-stu-id="ee283-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="ee283-110">Välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="ee283-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="ee283-111">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="ee283-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="ee283-112">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="ee283-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="ee283-113">Markera eller avmarkera kryssrutan Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="ee283-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="ee283-114">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="ee283-114">Click Recurrence.</span></span>
6. <span data-ttu-id="ee283-115">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="ee283-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="ee283-116">Ange en tid i fältet Starttid.</span><span class="sxs-lookup"><span data-stu-id="ee283-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="ee283-117">Välj om du vill att slutföra återkommande efter ett visst antal körningar, vid ett visst datum eller aldrig.</span><span class="sxs-lookup"><span data-stu-id="ee283-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="ee283-118">Välj sedan de olika alternativen för att definiera hur ofta du vill att jobbet ska köras.</span><span class="sxs-lookup"><span data-stu-id="ee283-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="ee283-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ee283-119">Click OK.</span></span>
9. <span data-ttu-id="ee283-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ee283-120">Click OK.</span></span>


