---
title: Skapa, beräkna och bokföra utdrag för en butik
description: Det här avsnittet beskriver de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21f1b0a34205e192957405bc9d298c45c8bb4d25
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141024"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="095b8-103">Skapa, beräkna och bokföra utdrag för en butik</span><span class="sxs-lookup"><span data-stu-id="095b8-103">Create, calculate, and post statements for a retail store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="095b8-104">Det här avsnittet beskriver de manuella stegen för att skapa, beräkna och bokföra ett utdrag för en butik.</span><span class="sxs-lookup"><span data-stu-id="095b8-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="095b8-105">Det finns också batchjobb som kan konfigureras för samma uppgifter.</span><span class="sxs-lookup"><span data-stu-id="095b8-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="095b8-106">Stegen för att konfigurera och att köra batchjobb finns i andra avsnitt.</span><span class="sxs-lookup"><span data-stu-id="095b8-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="095b8-107">För att slutföra den här proceduren måste du ha transaktioner som slutfördes i kassan och sedan samlats in till Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="095b8-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="095b8-108">I den här insamlingen används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="095b8-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="095b8-109">Välj **butiksekonomi** från startsidan.</span><span class="sxs-lookup"><span data-stu-id="095b8-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="095b8-110">Välj **Nytt utdrag**.</span><span class="sxs-lookup"><span data-stu-id="095b8-110">Select **New statement**.</span></span>
3. <span data-ttu-id="095b8-111">I fältet **Butiksnummer** väljer du ett alternativ iden nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="095b8-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="095b8-112">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="095b8-112">Select **OK**.</span></span>
5. <span data-ttu-id="095b8-113">Gruppen **Inställningar** har inställningar för att kontrollera vilka transaktioner som ingår i utdraget och hur de grupperas till utdragsrader.</span><span class="sxs-lookup"><span data-stu-id="095b8-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="095b8-114">Du kan öppna gruppen **Inställningar** och ändra inställningarna, eller använda standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="095b8-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="095b8-115">Fältet **Utdragmetod** definierar hur utdragsraderna grupperas.</span><span class="sxs-lookup"><span data-stu-id="095b8-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="095b8-116">Välj en medarbetare eller ett register i fältet **Personal/register** om du vill beräkna ett utdrag för den specifika medarbetaren eller registret.</span><span class="sxs-lookup"><span data-stu-id="095b8-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="095b8-117">Markera ett alternativ i fältet **Stängningsmetod**.</span><span class="sxs-lookup"><span data-stu-id="095b8-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="095b8-118">Välj **beräkna utdrag** från åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="095b8-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="095b8-119">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="095b8-119">Select **Yes**.</span></span>
    - <span data-ttu-id="095b8-120">När du har beräknat utdraget måste det finnas rader som skapas med totalbelopp för varje betalningsmetod och utdragmetod som användes.</span><span class="sxs-lookup"><span data-stu-id="095b8-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="095b8-121">Ange ett räknat belopp på varje rad om det behöver anges eller uppdateras.</span><span class="sxs-lookup"><span data-stu-id="095b8-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="095b8-122">Det beräknade fältet fylls i med belopp från kassaavstämningar som gjorts i kassan.</span><span class="sxs-lookup"><span data-stu-id="095b8-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="095b8-123">Välj **Bokför utdrag** från åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="095b8-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="095b8-124">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="095b8-124">Select **Close**.</span></span>
11. <span data-ttu-id="095b8-125">Stäng fönstret.</span><span class="sxs-lookup"><span data-stu-id="095b8-125">Close the pane.</span></span>
12. <span data-ttu-id="095b8-126">På startsidan väljer du **butiksekonomi**.</span><span class="sxs-lookup"><span data-stu-id="095b8-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="095b8-127">Välj fliken **Bokförda utdrag**.</span><span class="sxs-lookup"><span data-stu-id="095b8-127">Select the **Posted statements** tab.</span></span>

