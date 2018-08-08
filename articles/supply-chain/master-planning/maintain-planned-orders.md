---
title: "Underhåll planerade order"
description: "Den här artikeln innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1c764bb541b371cb2778040e7498c347ac9d7dfe
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="f63d2-104">Underhåll planerade order</span><span class="sxs-lookup"><span data-stu-id="f63d2-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f63d2-105">Den här artikeln innehåller information om hur du hanterar planerade order.</span><span class="sxs-lookup"><span data-stu-id="f63d2-105">This article provides information about how to manage planned orders.</span></span> <span data-ttu-id="f63d2-106">Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.</span><span class="sxs-lookup"><span data-stu-id="f63d2-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="f63d2-107">Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder**och **Planerad överföring**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="f63d2-108">Du kan använda fältet **Status** för att följa dina framsteg.</span><span class="sxs-lookup"><span data-stu-id="f63d2-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="f63d2-109">Följande värden används:</span><span class="sxs-lookup"><span data-stu-id="f63d2-109">The following values are used:</span></span>

-   <span data-ttu-id="f63d2-110">När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="f63d2-111">Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="f63d2-112">När du väljer att inte bekräfta en planerad order kan du ge den statusen **Godkänd**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="f63d2-113">Denna status betyder att du godkänner att den planerade ordern kan bekräftas, men att den ännu inte är bekräftad.</span><span class="sxs-lookup"><span data-stu-id="f63d2-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="f63d2-114">**Obs!** En godkänd planerad order överförs i sitt aktuella tillstånd till nästa huvudplaneringsberäkning.</span><span class="sxs-lookup"><span data-stu-id="f63d2-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="f63d2-115">Bekräfta planerade order genom att klicka på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="f63d2-116">Följande planerade order kan bekräftas:</span><span class="sxs-lookup"><span data-stu-id="f63d2-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="f63d2-117">Planerade order som har valts .</span><span class="sxs-lookup"><span data-stu-id="f63d2-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="f63d2-118">Flera planerade order.</span><span class="sxs-lookup"><span data-stu-id="f63d2-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="f63d2-119">Planerade order som har genererats vid en nedbrytning från sidan **Nedbrytning**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="f63d2-120">Klicka på **Planerade order** och välj den planerade ordern och klicka sedan på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="f63d2-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="f63d2-121">När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt.</span><span class="sxs-lookup"><span data-stu-id="f63d2-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> <span data-ttu-id="f63d2-122">**Obs!** Du kan högerklicka på en planerad order med en viss status och filtrera efter andra planerade order som har samma status.</span><span class="sxs-lookup"><span data-stu-id="f63d2-122">**Note:** You can right-click a planned order that has a particular status and filter for other planned orders that have the same status.</span></span> <span data-ttu-id="f63d2-123">Den här funktionen är praktisk om du till exempel vill filtrera efter alla planerade order som har statusen **Godkänd** så att du sedan kan bekräfta dem.</span><span class="sxs-lookup"><span data-stu-id="f63d2-123">This functionality is useful if, for example, you want to filter for all planned orders that have a status of **Approved**, so that you can then firm them.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f63d2-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f63d2-124">Additional resources</span></span>
--------

[<span data-ttu-id="f63d2-125">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="f63d2-125">Master plans</span></span>](master-plans.md)




