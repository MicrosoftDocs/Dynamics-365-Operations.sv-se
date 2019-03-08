---
title: Masstäng räkenskapsperiod
description: I den här proceduren visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2988b7ab0837cc9a3e4f1c4eaf3fe6e219fa721
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "311391"
---
# <a name="mass-financial-period-close"></a><span data-ttu-id="bd4cd-103">Masstäng räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="bd4cd-103">Mass financial period close</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd4cd-104">I den här proceduren visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-104">This procedure shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="bd4cd-105">Dessutom kommer uppgiften att visa hur du begränsar bokföring från användargrupper till specifika moduler.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="bd4cd-106">Gå till General ledger > Period close > Ledger calendars.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-106">Go to General ledger > Period close > Ledger calendars.</span></span>
    * <span data-ttu-id="bd4cd-107">Observera att listan med juridiska personer som visas är beroende av räkenskapskalendern som har valts på sidan.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="bd4cd-108">Endast juridiska personer som använder vald räkenskapskalender kommer att visas.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-108">Only legal entities using the selected fiscal calendar will display.</span></span>  
2. <span data-ttu-id="bd4cd-109">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-109">Click Edit.</span></span>
3. <span data-ttu-id="bd4cd-110">Välj den period som du vill ändra statusen för.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="bd4cd-111">Välj den juridiska person som du vill uppdatera statusen för.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-111">Select the legal entities for which you want to update the status.</span></span>
    * <span data-ttu-id="bd4cd-112">Du kan snabbt välja alla juridiska personer genom att välja bocken uppe på rutnätets vänstra sida.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-112">You can quickly select all legal entities  by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="bd4cd-113">Välj Update module access för att definiera bokföringsåtkomsten för en vald modul.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-113">Select Update module access to define the posting access to a selected module.</span></span>
    * <span data-ttu-id="bd4cd-114">Modulstatusen kan också uppdateras individuellt genom att redigera posterna i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="bd4cd-115">Knappen är praktisk när du snabbt vill uppdatera flera juridiska personposter.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="bd4cd-116">Markera den modul för vilken du vill uppdatera statusen i programmodulen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-116">In the Application module, select the module that you want to update the status.</span></span> <span data-ttu-id="bd4cd-117">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-117">Click Select.</span></span>
7. <span data-ttu-id="bd4cd-118">Markera All, None eller en specifik användargrupp i åtkomstnivån.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-118">In the Access level, select All, None, or a specific user group.</span></span> <span data-ttu-id="bd4cd-119">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-119">Click Select.</span></span>
    * <span data-ttu-id="bd4cd-120">Alla innebär att alla användare med redigeringsåtkomst till modulen kan bokföra om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="bd4cd-121">"None" innebär att användare inte kan bokföra i modulen om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="bd4cd-122">En specifik användargrupp anger att endast användare i gruppen får bokföra i modulen, om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="bd4cd-123">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-123">Click Update.</span></span>
9. <span data-ttu-id="bd4cd-124">Välj en annan period för att uppdatera statusen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="bd4cd-125">Välj de juridiska personer för vilka du vill uppdatera periodstatusen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="bd4cd-126">Välj Update period status och ange statusen som On hold, Open, eller Permanently closed.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-126">Select Update period status and set the status of On hold, Open, or Permanently closed.</span></span>
    * <span data-ttu-id="bd4cd-127">Öppen visar att bokföring kan göras i perioden, förutsatt att användare har åtkomst.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-127">Open indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="bd4cd-128">"On hold" innebär att inga bokföringar till perioden kan genomföras, men den kan öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-128">On hold means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="bd4cd-129">"Permanently closed" innebär att perioden är stängd och aldrig kan öppnas på nytt.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-129">Permanently closed means the period is closed and can never be opened.</span></span> <span data-ttu-id="bd4cd-130">Inga justeringar kan bokföra.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="bd4cd-131">Vi rekommenderar ingen att ställa in en period som "Permanently closed" förrän alla justeringar och revisioner har avslutats.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-131">We do not recommend setting a period to Permanently closed until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="bd4cd-132">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="bd4cd-132">Click Update.</span></span>

