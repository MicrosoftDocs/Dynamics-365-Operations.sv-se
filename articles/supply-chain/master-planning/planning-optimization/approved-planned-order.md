---
title: Visa, hantera och godkänna planerade order
description: Detta ämne innehåller information om hur du visar, hanterar och godkänner planerade order i planeringsoptimeringen.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935667"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="1eea9-103">Visa, hantera och godkänna planerade order</span><span class="sxs-lookup"><span data-stu-id="1eea9-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1eea9-104">Detta ämne innehåller information om hur du visar, hanterar och godkänner planerade order i planeringsoptimeringen.</span><span class="sxs-lookup"><span data-stu-id="1eea9-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="1eea9-105">Visa och hantera planerade order</span><span class="sxs-lookup"><span data-stu-id="1eea9-105">View and manage planned orders</span></span>

<span data-ttu-id="1eea9-106">Du kan visa och hantera planerade order på samtliga listsidor för planerade order.</span><span class="sxs-lookup"><span data-stu-id="1eea9-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="1eea9-107">Gå till någon av följande platser beroende på typen av planerade order som du vill arbeta med:</span><span class="sxs-lookup"><span data-stu-id="1eea9-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="1eea9-108">Huvudplanering \> Arbetsytor \> Huvudplanering</span><span class="sxs-lookup"><span data-stu-id="1eea9-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="1eea9-109">Huvudplanering \> Huvudplanering \> Planerade order</span><span class="sxs-lookup"><span data-stu-id="1eea9-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="1eea9-110">Produktionsstyrning \> Produktionsstyrning \> Planerade produktionsorder</span><span class="sxs-lookup"><span data-stu-id="1eea9-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="1eea9-111">Anskaffning och källa \> Inköpsorder \> Planerade inköpsorder</span><span class="sxs-lookup"><span data-stu-id="1eea9-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="1eea9-112">Lagerhantering \> Inkommande order \> Planerade överföringar</span><span class="sxs-lookup"><span data-stu-id="1eea9-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="1eea9-113">Lagerhantering \> Utgående order \> Planerade överföringar</span><span class="sxs-lookup"><span data-stu-id="1eea9-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="1eea9-114">Visa och redigera statusen för planerade order</span><span class="sxs-lookup"><span data-stu-id="1eea9-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="1eea9-115">Du kan använda fältet **Status** för respektive order i syfte att spåra dina framsteg eller ändra hur en planerad order ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="1eea9-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="1eea9-116">Följande värden för **Status** finns:</span><span class="sxs-lookup"><span data-stu-id="1eea9-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="1eea9-117">**Ej bearbetad** – När huvudplaneringen genererar planerade order erhåller de denna status.</span><span class="sxs-lookup"><span data-stu-id="1eea9-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="1eea9-118">Planerade order som innehar denna status raderas vid nästa planeringskörning.</span><span class="sxs-lookup"><span data-stu-id="1eea9-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="1eea9-119">**Slutförd** – Denna status visar att den planerade ordern har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1eea9-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="1eea9-120">Om du väljer att inte bekräfta en planerad order kan du ändra dess status till *Slutförd* manuellt.</span><span class="sxs-lookup"><span data-stu-id="1eea9-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="1eea9-121">Observera att systemet behandlar statusen *Ej bearbetad* och *Slutförd* på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="1eea9-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="1eea9-122">**Godkänd** – Den här statusen visar att den planerade ordern har godkänts för bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="1eea9-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="1eea9-123">Om du vill bekräfta en planerad order kan du ändra dess status till *Godkänd*.</span><span class="sxs-lookup"><span data-stu-id="1eea9-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="1eea9-124">Om du vill behålla redigeringarna som har gjorts för en planerad order, eller om du planerar att bekräfta en planerad order, ändrar du dess status till *Godkänd*.</span><span class="sxs-lookup"><span data-stu-id="1eea9-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="1eea9-125">Planerade order som har statusen *Godkänd* betraktas som fast och förväntad leverans i huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="1eea9-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="1eea9-126">De ändras eller tas därför inte bort under senare huvudplaneringskörningar.</span><span class="sxs-lookup"><span data-stu-id="1eea9-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="1eea9-127">För att uppnå detta kopierar planeringslogiken de planerade order som har statusen *Godkänd* från den gamla planversionen till den nya planversionen under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="1eea9-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="1eea9-128">Observera att planerade order med statusen *Godkänd* endast betraktas som leverans inom den specifika huvudplanen.</span><span class="sxs-lookup"><span data-stu-id="1eea9-128">Note that planned orders that have a status of *Approved*\* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="1eea9-129">Om du vill ändra status för en enskild planerad order [öppnar du en listsida för planerade order](#view-planned-orders), öppnar ordern och följer sedan ett av följande steg:</span><span class="sxs-lookup"><span data-stu-id="1eea9-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="1eea9-130">I snabbfliken **Allmänt** ändrar du värdet i fältet **Status**.</span><span class="sxs-lookup"><span data-stu-id="1eea9-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="1eea9-131">I åtgärdsfönstret, på fliken **Planerad order** i gruppen **Process** väljer du **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="1eea9-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="1eea9-132">För att markera ordern som godkänd väljer du **Godkänn** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1eea9-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="1eea9-133">Om du vill ändra status för flera planerade order samtidigt [öppnar du en listsida för planerade order](#view-planned-orders), väljer kryssrutan för varje order som du vill ändra, och följer sedan dessa steg:</span><span class="sxs-lookup"><span data-stu-id="1eea9-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="1eea9-134">I åtgärdsfönstret, på fliken **Planerad order** i gruppen **Process** väljer du **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="1eea9-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="1eea9-135">I åtgärdsfönstret väljer du **Godkänn** för att markera orderna som godkända.</span><span class="sxs-lookup"><span data-stu-id="1eea9-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="1eea9-136">Godkänna planerade order</span><span class="sxs-lookup"><span data-stu-id="1eea9-136">Approve planned orders</span></span>

<span data-ttu-id="1eea9-137">Godkännande av planerade order är ett valfritt steg på vägen för att skapa en bekräftad order från en planerad order.</span><span class="sxs-lookup"><span data-stu-id="1eea9-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="1eea9-138">I följande bild visas hur du kan använda värdet **Status** som tilldelas varje planerad order i syfte att implementera ett godkännandearbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="1eea9-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="1eea9-139">Om du vill implementera en godkännandeprocess justerar du värdet **Status** manuellt för varje planerad order enligt beskrivningen i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1eea9-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Planerat orderflöde](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="1eea9-141">Vi rekommenderar att du godkänner ändrade planerade order.</span><span class="sxs-lookup"><span data-stu-id="1eea9-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="1eea9-142">I annat fall ignoreras redigeringarna och skrivs över av nästa planeringskörning.</span><span class="sxs-lookup"><span data-stu-id="1eea9-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1eea9-143">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1eea9-143">Additional resources</span></span>

- [<span data-ttu-id="1eea9-144">Bekräfta planerade order</span><span class="sxs-lookup"><span data-stu-id="1eea9-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
