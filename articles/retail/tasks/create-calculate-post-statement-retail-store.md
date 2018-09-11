--- 
title: " Skapa, beräkna och bokföra ett utdrag för en butik"
description: "Den här proceduren går igenom de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik."
author: jashanno
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: d949cf46857992d5f16d349862ff67cccf417fed
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="24f81-103"> Skapa, beräkna och bokföra ett utdrag för en butik</span><span class="sxs-lookup"><span data-stu-id="24f81-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="24f81-104">Den här proceduren går igenom de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik.</span><span class="sxs-lookup"><span data-stu-id="24f81-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="24f81-105">Det finns också batchjobb som kan konfigureras för samma uppgifter.</span><span class="sxs-lookup"><span data-stu-id="24f81-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="24f81-106">Stegen för att konfigurera och att köra batchjobb finns i andra avsnitt.</span><span class="sxs-lookup"><span data-stu-id="24f81-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="24f81-107">För att slutföra den här proceduren måste du ha transaktioner som slutfördes i kassan och sedan samlats in till Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="24f81-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="24f81-108">I den här insamlingen används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="24f81-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="24f81-109">Den här proceduren kan referera till Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="24f81-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="24f81-110">Notera att Dynamics AX nu kallas Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="24f81-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="24f81-111">Alla arbetsytor > ..</span><span class="sxs-lookup"><span data-stu-id="24f81-111">Go to All workspaces > ..</span></span> <span data-ttu-id="24f81-112">> Butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="24f81-112">> Retail store financials.</span></span>
2. <span data-ttu-id="24f81-113">Klicka på Nytt utdrag.</span><span class="sxs-lookup"><span data-stu-id="24f81-113">Click New statement.</span></span>
3. <span data-ttu-id="24f81-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Butiksnummer.</span><span class="sxs-lookup"><span data-stu-id="24f81-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="24f81-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="24f81-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="24f81-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="24f81-116">Click OK.</span></span>
    * <span data-ttu-id="24f81-117">Gruppen Inställningar har inställningar för att kontrollera vilka transaktioner som ingår i utdraget och hur de grupperas till utdragsrader.</span><span class="sxs-lookup"><span data-stu-id="24f81-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="24f81-118">Du kan öppna gruppen Inställningar och ändra inställningarna, eller använda standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="24f81-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="24f81-119">Utdragmetodfältet definierar hur utdragsraderna grupperas.</span><span class="sxs-lookup"><span data-stu-id="24f81-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="24f81-120">Välj en medarbetare eller ett register om du vill beräkna ett utdrag för den specifika medarbetaren eller registret.</span><span class="sxs-lookup"><span data-stu-id="24f81-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="24f81-121">Markera ett alternativ i fältet Stängningsmetod.</span><span class="sxs-lookup"><span data-stu-id="24f81-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="24f81-122">Klicka på Beräkna utdrag.</span><span class="sxs-lookup"><span data-stu-id="24f81-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="24f81-123">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="24f81-123">Click Yes.</span></span>
    * <span data-ttu-id="24f81-124">När du har beräknat utdraget måste det finnas rader som skapas med totalbelopp för varje betalningsmetod och utdragmetod som användes.</span><span class="sxs-lookup"><span data-stu-id="24f81-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="24f81-125">Ange ett räknat belopp på varje rad om det behöver anges eller uppdateras.</span><span class="sxs-lookup"><span data-stu-id="24f81-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="24f81-126">Det beräknade fältet fylls i med belopp från kassaavstämningar som gjorts i kassan.</span><span class="sxs-lookup"><span data-stu-id="24f81-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="24f81-127">Klicka på Bokför utdrag.</span><span class="sxs-lookup"><span data-stu-id="24f81-127">Click Post statement.</span></span>
10. <span data-ttu-id="24f81-128">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="24f81-128">Click Close.</span></span>
11. <span data-ttu-id="24f81-129">Gå till Butik och handel > Kanaler > Butiksekonomi.</span><span class="sxs-lookup"><span data-stu-id="24f81-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="24f81-130">Klicka på fliken Bokförda utdrag.</span><span class="sxs-lookup"><span data-stu-id="24f81-130">Click the Posted statements tab.</span></span>


