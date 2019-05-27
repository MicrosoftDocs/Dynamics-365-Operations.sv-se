---
title: Bokföring av försäljningar och betalningar online
description: Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.
author: jashanno
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
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550218"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="73a4a-103">Bokföring av försäljningar och betalningar online</span><span class="sxs-lookup"><span data-stu-id="73a4a-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="73a4a-104">Den här proceduren går igenom hur du kör ett återkommande batchjobb om du vill skapa försäljningsorder och betalningar för onlinebutikstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="73a4a-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="73a4a-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="73a4a-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="73a4a-106">Gå till alla arbetsytor > butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="73a4a-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="73a4a-107">Klicka på Synkronisera order.</span><span class="sxs-lookup"><span data-stu-id="73a4a-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="73a4a-108">Välj Butiker efter region i fältet Organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="73a4a-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="73a4a-109">Välj antingen en specifik onlinebutik eller välj en nod om du vill skapa batchjobbet för en grupp av butiker.</span><span class="sxs-lookup"><span data-stu-id="73a4a-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="73a4a-110">Klicka på pilen om du vill lägga till ditt val.</span><span class="sxs-lookup"><span data-stu-id="73a4a-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="73a4a-111">Klicka på fliken Kör i bakgrunden ...</span><span class="sxs-lookup"><span data-stu-id="73a4a-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="73a4a-112">Markera eller avmarkera kryssrutan Batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="73a4a-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="73a4a-113">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="73a4a-113">Click Recurrence.</span></span>
7. <span data-ttu-id="73a4a-114">Välj alternativet Slutdatum saknas.</span><span class="sxs-lookup"><span data-stu-id="73a4a-114">Select the No end date option.</span></span>
8. <span data-ttu-id="73a4a-115">Ange ett nummer i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="73a4a-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="73a4a-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73a4a-116">Click OK.</span></span>
10. <span data-ttu-id="73a4a-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="73a4a-117">Click OK.</span></span>

