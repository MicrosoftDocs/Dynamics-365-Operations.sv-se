---
title: "Konfigurera en parallell aktivitet i ett arbetsflöde"
description: "Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ec1c1d8abc49deb8ef16322370c59d40b01d344c
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="configure-a-parallel-activity-in-a-workflow"></a><span data-ttu-id="d5372-103">Konfigurera en parallell aktivitet i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d5372-103">Configure a parallel activity in a workflow</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="d5372-104">Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.</span><span class="sxs-lookup"><span data-stu-id="d5372-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="d5372-105">En parallellt aktivitet består av arbetsflödesförgreningar som körs samtidigt.</span><span class="sxs-lookup"><span data-stu-id="d5372-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="d5372-106">Namnge en parallell aktivitet</span><span class="sxs-lookup"><span data-stu-id="d5372-106">Name a parallel activity</span></span>
<span data-ttu-id="d5372-107">Följ dessa steg när du vill ange ett namn för en parallell aktivitet.</span><span class="sxs-lookup"><span data-stu-id="d5372-107">Follow these steps to enter a name for a parallel activity.</span></span>
1.  <span data-ttu-id="d5372-108">Högerklicka den parallella aktiviteten och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="d5372-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2.  <span data-ttu-id="d5372-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="d5372-109">In the left pane, click **Basic Settings**.</span></span>
3.  <span data-ttu-id="d5372-110">Ange ett unikt namn för den parallella aktiviteten i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="d5372-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4.  <span data-ttu-id="d5372-111">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d5372-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="d5372-112">Konfigurera förgreningarna i en parallell aktivitet</span><span class="sxs-lookup"><span data-stu-id="d5372-112">Configure the branches of a parallel activity</span></span>
<span data-ttu-id="d5372-113">Gör på följande sätt när du vill lägga till och konfigurera förgreningarna i denna parallella aktivitet.</span><span class="sxs-lookup"><span data-stu-id="d5372-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>
1. <span data-ttu-id="d5372-114">Dubbelklicka på den parallella aktiviteten för att visa förgreningarna för den parallella aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="d5372-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="d5372-115">Dra elementet **Avdelning** från området **Arbetsflödeselement** till en infogningspunkt på duken om du vill lägga till en förgrening.</span><span class="sxs-lookup"><span data-stu-id="d5372-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="d5372-116">Följande bild visar en infogningspunkt.![Infogningspunkt](./media/workflow_insertionpoint.gif)</span><span class="sxs-lookup"><span data-stu-id="d5372-116">The following figure shows an insertion point.![Insertion point](./media/workflow_insertionpoint.gif)</span></span>

   |                                              <span data-ttu-id="d5372-117"><strong>Obs!</strong></span><span class="sxs-lookup"><span data-stu-id="d5372-117"><strong>Note</strong></span></span>                                               |
   |------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="d5372-118">Ordningen för förgreningarna är oviktig eftersom alla förgreningar i en parallell aktivitet körs samtidigt.</span><span class="sxs-lookup"><span data-stu-id="d5372-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span> |


3. <span data-ttu-id="d5372-119">Se [Konfigurera en parallell gren](configure-parallel-branch-workflow.md) för att konfigurera respektive förgrening.</span><span class="sxs-lookup"><span data-stu-id="d5372-119">To configure each branch, see [Configure a parallel branch](configure-parallel-branch-workflow.md).</span></span>






