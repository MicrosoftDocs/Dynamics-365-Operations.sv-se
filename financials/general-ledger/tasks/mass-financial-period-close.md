--- 
title: "Masstäng räkenskapsperiod"
description: "I den här proceduren visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8d7151cbcd02f9312ca6b0de5e27231a0b0dc9d6
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="mass-financial-period-close"></a><span data-ttu-id="e0687-103">Masstäng räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="e0687-103">Mass financial period close</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0687-104">I den här proceduren visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången.</span><span class="sxs-lookup"><span data-stu-id="e0687-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="e0687-105">Dessutom kommer uppgiften att visa hur du begränsar bokföring från användargrupper till specifika moduler.</span><span class="sxs-lookup"><span data-stu-id="e0687-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="e0687-106">Gå till General ledger > Period close > Ledger calendars.</span><span class="sxs-lookup"><span data-stu-id="e0687-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="e0687-107">Observera att listan med juridiska personer som visas är beroende av räkenskapskalendern som har valts på sidan.</span><span class="sxs-lookup"><span data-stu-id="e0687-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="e0687-108">Endast juridiska personer som använder vald räkenskapskalender kommer att visas.</span><span class="sxs-lookup"><span data-stu-id="e0687-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="e0687-109">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="e0687-109">Click Edit.</span></span>
3. <span data-ttu-id="e0687-110">Välj den period som du vill ändra statusen för.</span><span class="sxs-lookup"><span data-stu-id="e0687-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="e0687-111">Välj den juridiska person som du vill uppdatera statusen för.</span><span class="sxs-lookup"><span data-stu-id="e0687-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="e0687-112">Du kan snabbt välja alla juridiska personer genom att välja bocken uppe på rutnätets vänstra sida.</span><span class="sxs-lookup"><span data-stu-id="e0687-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="e0687-113">Välj Update module access för att definiera bokföringsåtkomsten för en vald modul.</span><span class="sxs-lookup"><span data-stu-id="e0687-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="e0687-114">Modulstatusen kan också uppdateras individuellt genom att redigera posterna i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="e0687-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="e0687-115">Knappen är praktisk när du snabbt vill uppdatera flera juridiska personposter.</span><span class="sxs-lookup"><span data-stu-id="e0687-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="e0687-116">Markera den modul för vilken du vill uppdatera statusen i programmodulen.</span><span class="sxs-lookup"><span data-stu-id="e0687-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="e0687-117">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="e0687-117">Click Select.</span></span>
7. <span data-ttu-id="e0687-118">Markera All, None eller en specifik användargrupp i åtkomstnivån.</span><span class="sxs-lookup"><span data-stu-id="e0687-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="e0687-119">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="e0687-119">Click Select.</span></span>
    * <span data-ttu-id="e0687-120">Alla innebär att alla användare med redigeringsåtkomst till modulen kan bokföra om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="e0687-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="e0687-121">"None" innebär att användare inte kan bokföra i modulen om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="e0687-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="e0687-122">En specifik användargrupp anger att endast användare i gruppen får bokföra i modulen, om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="e0687-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="e0687-123">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e0687-123">Click Update.</span></span>
9. <span data-ttu-id="e0687-124">Välj en annan period för att uppdatera statusen.</span><span class="sxs-lookup"><span data-stu-id="e0687-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="e0687-125">Välj de juridiska personer för vilka du vill uppdatera periodstatusen.</span><span class="sxs-lookup"><span data-stu-id="e0687-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="e0687-126">Välj Update period status och ange statusen som On hold, Open, eller Permanently closed.</span><span class="sxs-lookup"><span data-stu-id="e0687-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="e0687-127">Öppen visar att bokföring kan göras i perioden, förutsatt att användare har åtkomst.</span><span class="sxs-lookup"><span data-stu-id="e0687-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="e0687-128">"On hold" innebär att inga bokföringar till perioden kan genomföras, men den kan öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="e0687-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="e0687-129">"Permanently closed" innebär att perioden är stängd och aldrig kan öppnas på nytt.</span><span class="sxs-lookup"><span data-stu-id="e0687-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="e0687-130">Inga justeringar kan bokföra.</span><span class="sxs-lookup"><span data-stu-id="e0687-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="e0687-131">Vi rekommenderar ingen att ställa in en period som "Permanently closed" förrän alla justeringar och revisioner har avslutats.</span><span class="sxs-lookup"><span data-stu-id="e0687-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="e0687-132">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="e0687-132">Click Update.</span></span>


