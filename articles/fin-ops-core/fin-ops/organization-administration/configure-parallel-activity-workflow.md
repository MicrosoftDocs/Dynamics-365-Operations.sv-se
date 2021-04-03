---
title: Konfigurera parallella aktiviteter i ett arbetsflöde
description: Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 450420d44ad4aab233afc5a116369e993aa7a15b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570624"
---
# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="60e70-103">Konfigurera parallella aktiviteter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="60e70-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60e70-104">Slutför följande procedurer i arbetsflödesredigeraren om du vill konfigurera en parallell aktivitet.</span><span class="sxs-lookup"><span data-stu-id="60e70-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="60e70-105">En parallellt aktivitet består av arbetsflödesförgreningar som körs samtidigt.</span><span class="sxs-lookup"><span data-stu-id="60e70-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="60e70-106">Namnge en parallell aktivitet</span><span class="sxs-lookup"><span data-stu-id="60e70-106">Name a parallel activity</span></span>

<span data-ttu-id="60e70-107">Följ dessa steg när du vill ange ett namn för en parallell aktivitet.</span><span class="sxs-lookup"><span data-stu-id="60e70-107">Follow these steps to enter a name for a parallel activity.</span></span>

1. <span data-ttu-id="60e70-108">Högerklicka den parallella aktiviteten och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="60e70-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="60e70-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="60e70-109">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="60e70-110">Ange ett unikt namn för den parallella aktiviteten i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="60e70-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4. <span data-ttu-id="60e70-111">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="60e70-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="60e70-112">Konfigurera förgreningarna i en parallell aktivitet</span><span class="sxs-lookup"><span data-stu-id="60e70-112">Configure the branches of a parallel activity</span></span>

<span data-ttu-id="60e70-113">Gör på följande sätt när du vill lägga till och konfigurera förgreningarna i denna parallella aktivitet.</span><span class="sxs-lookup"><span data-stu-id="60e70-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>

1. <span data-ttu-id="60e70-114">Dubbelklicka på den parallella aktiviteten för att visa förgreningarna för den parallella aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="60e70-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="60e70-115">Dra elementet **Avdelning** från området **Arbetsflödeselement** till en infogningspunkt på duken om du vill lägga till en förgrening.</span><span class="sxs-lookup"><span data-stu-id="60e70-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="60e70-116">Följande bild visar en infogningspunkt.</span><span class="sxs-lookup"><span data-stu-id="60e70-116">The following figure shows an insertion point.</span></span>

    ![Infogningspunkt](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > <span data-ttu-id="60e70-118">Ordningen för förgreningarna är oviktig eftersom alla förgreningar i en parallell aktivitet körs samtidigt.</span><span class="sxs-lookup"><span data-stu-id="60e70-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span>

3. <span data-ttu-id="60e70-119">Se [Konfigurera en parallella grenar i ett arbetsflöde](configure-parallel-branch-workflow.md) för att konfigurera respektive förgrening.</span><span class="sxs-lookup"><span data-stu-id="60e70-119">To configure each branch, see [Configure parallel branches in a workflow](configure-parallel-branch-workflow.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]