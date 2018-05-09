--- 
title: " Konfigurera och kör ett jobb för att beräkna utdrag"
description: "Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb om du vill skapa och beräkna utdrag för en vald butik eller grupp av butiker."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 54dacef8ae0afd1fb706d5c67fa77b315a2cb4de
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="configure-and-run-a-job-to-calculate-statements"></a><span data-ttu-id="5064b-103"> Konfigurera och kör ett jobb för att beräkna utdrag</span><span class="sxs-lookup"><span data-stu-id="5064b-103">Configure and run a job to calculate statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5064b-104">Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb om du vill skapa och beräkna utdrag för en vald butik eller grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="5064b-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="5064b-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="5064b-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5064b-106">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="5064b-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="5064b-107">Klicka på Beräkna utdrag.</span><span class="sxs-lookup"><span data-stu-id="5064b-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="5064b-108">Välj antingen en specifik butik eller en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="5064b-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="5064b-109">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="5064b-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="5064b-110">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="5064b-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="5064b-111">Välj Ja under Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="5064b-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="5064b-112">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="5064b-112">Click Recurrence.</span></span>
6. <span data-ttu-id="5064b-113">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="5064b-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="5064b-114">Ange en tid i fältet Starttid.</span><span class="sxs-lookup"><span data-stu-id="5064b-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="5064b-115">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="5064b-115">Select the No end date option.</span></span>
9. <span data-ttu-id="5064b-116">Ange Dagar i fältet PatternUnit.</span><span class="sxs-lookup"><span data-stu-id="5064b-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="5064b-117">Ange ett tal i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="5064b-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="5064b-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5064b-118">Click OK.</span></span>
12. <span data-ttu-id="5064b-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5064b-119">Click OK.</span></span>


