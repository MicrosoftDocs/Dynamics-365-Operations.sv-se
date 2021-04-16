---
title: Masstäng räkenskapsperiod
description: I det här avsnittet visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången.
author: aprilolson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54a5b16f731e850b468ea2e05e47b47774e45838
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826508"
---
# <a name="mass-financial-period-close"></a><span data-ttu-id="25287-103">Masstäng räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="25287-103">Mass financial period close</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25287-104">I det här avsnittet visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången.</span><span class="sxs-lookup"><span data-stu-id="25287-104">This topic shows how to place a period on hold or permanently close a period or more than one legal entity at a time.</span></span> <span data-ttu-id="25287-105">Dessutom kommer uppgiften att visa hur du begränsar bokföring från användargrupper till specifika moduler.</span><span class="sxs-lookup"><span data-stu-id="25287-105">In addition, the task will show how to restrict user group posting to specific modules.</span></span>

1. <span data-ttu-id="25287-106">i navigeringsfönstret, gå till **Moduler > Redovisning > Periodstängning > Redovisningskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="25287-106">In the navigation pane, go to **Modules > General ledger > Period close > Ledger calendars**.</span></span> <span data-ttu-id="25287-107">Observera att listan med juridiska personer som visas är beroende av räkenskapskalendern som har valts på sidan.</span><span class="sxs-lookup"><span data-stu-id="25287-107">Note that the list of legal entities displayed is dependent on the fiscal calendar selected on the page.</span></span> <span data-ttu-id="25287-108">Endast juridiska personer som använder vald räkenskapskalender kommer att visas.</span><span class="sxs-lookup"><span data-stu-id="25287-108">Only legal entities using the selected fiscal calendar will display.</span></span>
2. <span data-ttu-id="25287-109">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="25287-109">Select **Edit**.</span></span>
3. <span data-ttu-id="25287-110">Välj den period som du vill ändra statusen för.</span><span class="sxs-lookup"><span data-stu-id="25287-110">Select the period for which you want to modify the status.</span></span>
4. <span data-ttu-id="25287-111">Välj den juridiska person som du vill uppdatera statusen för.</span><span class="sxs-lookup"><span data-stu-id="25287-111">Select the legal entities for which you want to update the status.</span></span> <span data-ttu-id="25287-112">Du kan snabbt välja alla juridiska personer genom att välja bocken uppe på rutnätets vänstra sida.</span><span class="sxs-lookup"><span data-stu-id="25287-112">You can quickly select all legal entities by selecting the check mark on the upper left side of the grid.</span></span>  
5. <span data-ttu-id="25287-113">Välj **Uppdatera modulåtkomst** för att definiera bokföringsåtkomsten för en vald modul.</span><span class="sxs-lookup"><span data-stu-id="25287-113">Select **Update module access** to define the posting access to a selected module.</span></span> <span data-ttu-id="25287-114">Modulstatusen kan också uppdateras individuellt genom att redigera posterna i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="25287-114">The module status can also be updated one-by-one by editing the records in the grid.</span></span> <span data-ttu-id="25287-115">Knappen är praktisk när du snabbt vill uppdatera flera juridiska personposter.</span><span class="sxs-lookup"><span data-stu-id="25287-115">The button is useful when you want to quickly update multiple legal entity records.</span></span>  
6. <span data-ttu-id="25287-116">Välj den modul för vilken du vill uppdatera statusen i modulen **Program** .</span><span class="sxs-lookup"><span data-stu-id="25287-116">In the **Application** module, select the module that you want to update the status.</span></span> <span data-ttu-id="25287-117">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="25287-117">Click **Select**.</span></span>
7. <span data-ttu-id="25287-118">På nivån **Åtkomst**, välj **Alla**, **Ingen** eller en specifik användargrupp.</span><span class="sxs-lookup"><span data-stu-id="25287-118">In the **Access** level, select **All**, **None**, or a specific user group.</span></span> <span data-ttu-id="25287-119">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="25287-119">Click **Select**.</span></span> <span data-ttu-id="25287-120">Alla innebär att alla användare med redigeringsåtkomst till modulen kan bokföra om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="25287-120">All indicates all users with edit access to the module can post if the period is open.</span></span> <span data-ttu-id="25287-121">"None" innebär att användare inte kan bokföra i modulen om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="25287-121">None indicates that users cannot post to the module if the period is open.</span></span> <span data-ttu-id="25287-122">En specifik användargrupp anger att endast användare i gruppen får bokföra i modulen, om perioden är öppen.</span><span class="sxs-lookup"><span data-stu-id="25287-122">A specific user group indicates only users in the group are able to post to the module if the period is open.</span></span>  
8. <span data-ttu-id="25287-123">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="25287-123">Select **Update**.</span></span>
9. <span data-ttu-id="25287-124">Välj en annan period för att uppdatera statusen.</span><span class="sxs-lookup"><span data-stu-id="25287-124">Select another period to update the status.</span></span>
10. <span data-ttu-id="25287-125">Välj de juridiska personer för vilka du vill uppdatera periodstatusen.</span><span class="sxs-lookup"><span data-stu-id="25287-125">Select the legal entites for which you want to update the period status.</span></span>
11. <span data-ttu-id="25287-126">Välj **Uppdatera periodstatus** och ställ in statusen **Spärrad**, **Öppen** eller **Permanent stängd**.</span><span class="sxs-lookup"><span data-stu-id="25287-126">Select **Update period status** and set the status of **On hold**, **Open**, or **Permanently closed**.</span></span> <span data-ttu-id="25287-127">**Öppen** visar att bokföring kan göras i perioden, förutsatt att användare har åtkomst.</span><span class="sxs-lookup"><span data-stu-id="25287-127">**Open** indicates the period can be posted to, provided the user has access.</span></span> <span data-ttu-id="25287-128">**Spärrad** innebär att inga bokföringar till perioden kan genomföras, men den kan öppnas igen.</span><span class="sxs-lookup"><span data-stu-id="25287-128">**On hold** means the period cannot be posted to, but the period can be reopened.</span></span> <span data-ttu-id="25287-129">**Permanent stängd** innebär att perioden är stängd och aldrig kan öppnas på nytt.</span><span class="sxs-lookup"><span data-stu-id="25287-129">**Permanently closed** means the period is closed and can never be opened.</span></span> <span data-ttu-id="25287-130">Inga justeringar kan bokföra.</span><span class="sxs-lookup"><span data-stu-id="25287-130">Adjustments cannot be posted.</span></span> <span data-ttu-id="25287-131">Vi rekommenderar ingen att ställa in en period som **Permanent stängd** förrän alla justeringar och revisioner har avslutats.</span><span class="sxs-lookup"><span data-stu-id="25287-131">We do not recommend setting a period to **Permanently closed** until all adjustments and audits are complete.</span></span>  
12. <span data-ttu-id="25287-132">Välj **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="25287-132">Select **Update**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]