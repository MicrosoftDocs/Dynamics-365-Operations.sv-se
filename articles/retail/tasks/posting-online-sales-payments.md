--- 
title: " Bokför onlineförsäljningar och -betalningar"
description: "Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner."
author: jashanno
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
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 2feaf580c7ae1fc53f9257f117576c99764c6ea0
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="post-online-sales-and-payments"></a><span data-ttu-id="bc5c5-103"> Bokför onlineförsäljningar och -betalningar</span><span class="sxs-lookup"><span data-stu-id="bc5c5-103">Post online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bc5c5-104">Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="bc5c5-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="bc5c5-106">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="bc5c5-107">Klicka på Synkronisera order.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="bc5c5-108">Välj Butiker efter region i fältet Organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="bc5c5-109">Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="bc5c5-110">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="bc5c5-111">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="bc5c5-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="bc5c5-112">Markera eller avmarkera kryssrutan Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="bc5c5-113">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-113">Click Recurrence.</span></span>
7. <span data-ttu-id="bc5c5-114">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-114">Select the No end date option.</span></span>
8. <span data-ttu-id="bc5c5-115">Ange ett nummer i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="bc5c5-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-116">Click OK.</span></span>
10. <span data-ttu-id="bc5c5-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bc5c5-117">Click OK.</span></span>


