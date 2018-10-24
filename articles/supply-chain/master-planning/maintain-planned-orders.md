---
title: "Underhåll planerade order"
description: "Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order."
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
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
ms.sourcegitcommit: 657c19896b20a514dc5308bf7fb086085b482fec
ms.openlocfilehash: bf578d98abc4825c5607ec031da6ab6737c3183a
ms.contentlocale: sv-se
ms.lasthandoff: 10/08/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="43229-104">Underhåll planerade order</span><span class="sxs-lookup"><span data-stu-id="43229-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43229-105">Detta avsnitt innehåller information om hur du hanterar planerade order.</span><span class="sxs-lookup"><span data-stu-id="43229-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="43229-106">Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.</span><span class="sxs-lookup"><span data-stu-id="43229-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="43229-107">Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder**och **Planerad överföring**.</span><span class="sxs-lookup"><span data-stu-id="43229-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="43229-108">Du kan använda fältet **Status** för att följa dina framsteg.</span><span class="sxs-lookup"><span data-stu-id="43229-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="43229-109">Följande värden används:</span><span class="sxs-lookup"><span data-stu-id="43229-109">The following values are used:</span></span>

-   <span data-ttu-id="43229-110">När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.</span><span class="sxs-lookup"><span data-stu-id="43229-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="43229-111">Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="43229-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="43229-112">När du väljer att inte bekräfta en planerad order kan du ge den statusen **Godkänd**.</span><span class="sxs-lookup"><span data-stu-id="43229-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="43229-113">Denna status betyder att du godkänner att den planerade ordern kan bekräftas, men att den ännu inte är bekräftad.</span><span class="sxs-lookup"><span data-stu-id="43229-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="43229-114">**Obs!** En godkänd planerad order överförs i sitt aktuella tillstånd till nästa huvudplaneringsberäkning.</span><span class="sxs-lookup"><span data-stu-id="43229-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="43229-115">Bekräfta planerade order genom att klicka på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="43229-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="43229-116">Följande planerade order kan bekräftas:</span><span class="sxs-lookup"><span data-stu-id="43229-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="43229-117">Planerade order som har valts .</span><span class="sxs-lookup"><span data-stu-id="43229-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="43229-118">Flera planerade order.</span><span class="sxs-lookup"><span data-stu-id="43229-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="43229-119">Planerade order som har genererats vid en nedbrytning från sidan **Nedbrytning**.</span><span class="sxs-lookup"><span data-stu-id="43229-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="43229-120">Klicka på **Planerade order** och välj den planerade ordern och klicka sedan på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="43229-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="43229-121">När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt.</span><span class="sxs-lookup"><span data-stu-id="43229-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> 

<a name="additional-resources"></a><span data-ttu-id="43229-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="43229-122">Additional resources</span></span>
--------

[<span data-ttu-id="43229-123">Huvudplaner</span><span class="sxs-lookup"><span data-stu-id="43229-123">Master plans</span></span>](master-plans.md)




