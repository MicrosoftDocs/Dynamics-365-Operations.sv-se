---
title: Konfigurera och köra jobb för att beräkna utdrag
description: Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb om du vill skapa och beräkna utdrag för en vald butik eller grupp av butiker.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f52603672e95d0ae4973844851c4ed260484e5f0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550172"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="acde0-103">Konfigurera och köra jobb för att beräkna utdrag</span><span class="sxs-lookup"><span data-stu-id="acde0-103">Configure and run job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="acde0-104">Den här proceduren går igenom konfigurationen och körning av regelbundet återkommande batchjobb om du vill skapa och beräkna utdrag för en vald butik eller grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="acde0-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="acde0-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="acde0-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="acde0-106">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="acde0-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="acde0-107">Klicka på Beräkna utdrag.</span><span class="sxs-lookup"><span data-stu-id="acde0-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="acde0-108">Välj antingen en specifik butik eller en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="acde0-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="acde0-109">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="acde0-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="acde0-110">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="acde0-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="acde0-111">Välj Ja under Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="acde0-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="acde0-112">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="acde0-112">Click Recurrence.</span></span>
6. <span data-ttu-id="acde0-113">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="acde0-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="acde0-114">Ange en tid i fältet Starttid.</span><span class="sxs-lookup"><span data-stu-id="acde0-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="acde0-115">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="acde0-115">Select the No end date option.</span></span>
9. <span data-ttu-id="acde0-116">Ange Dagar i fältet PatternUnit.</span><span class="sxs-lookup"><span data-stu-id="acde0-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="acde0-117">Ange ett tal i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="acde0-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="acde0-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="acde0-118">Click OK.</span></span>
12. <span data-ttu-id="acde0-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="acde0-119">Click OK.</span></span>

