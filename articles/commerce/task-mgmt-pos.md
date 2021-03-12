---
title: Uppgiftshantering i POS
description: I det här avsnittet beskrivs uppgiftshantering i Microsoft Dynamics 365 Commerce kassaprogram (POS).
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 889cc90b534de33ccd0e2bea367b2da42b5d72e0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006195"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="dc8e6-103">Uppgiftshantering i POS</span><span class="sxs-lookup"><span data-stu-id="dc8e6-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dc8e6-104">I det här avsnittet beskrivs uppgiftshantering i Microsoft Dynamics 365 Commerce kassaprogram (POS).</span><span class="sxs-lookup"><span data-stu-id="dc8e6-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="overview"></a><span data-ttu-id="dc8e6-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="dc8e6-105">Overview</span></span>

<span data-ttu-id="dc8e6-106">Dynamics 365 Commerce kassaprogrammet har funktioner för uppgiftshantering som tillåter att butikschefer och medarbetare hantera uppgifter och uppdaterar uppgiftsstatus.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-106">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="dc8e6-107">Butiksarbetare har tillgång till uppgifter antingen genom att välja panelen **Uppgifter** på startsidan för POS eller genom att välja uppgiftsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-107">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="dc8e6-108">Butiksarbetare hämtas som standard till fliken **mina uppgifter** där de kan visa de uppgifter som de har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-108">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="dc8e6-109">De kan dock enkelt växla till flikarna **Förfallna uppgifter**, **Öppna uppgifter** och **Uppgiftslistor**.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-109">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="dc8e6-110">Uppgiftsfunktioner för butikschefer</span><span class="sxs-lookup"><span data-stu-id="dc8e6-110">Task operations for store managers</span></span>

<span data-ttu-id="dc8e6-111">Butikschefer kan utföra följande uppgiftsoperationer i kassaprogrammet med hjälp av knapparna i kommandofältet:</span><span class="sxs-lookup"><span data-stu-id="dc8e6-111">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="dc8e6-112">**Tilldela** – tilldela de markerade uppgifterna till en butiksarbetare.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-112">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="dc8e6-113">**Uppgiftsstatus** – ändra status för markerade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-113">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="dc8e6-114">**Filter** – som standard visas endast aktiva uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-114">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="dc8e6-115">Med hjälp av filter kan chefer emellertid visa alla uppgifter, även uppgifter som har slutförts eller avbrutits.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-115">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="dc8e6-116">**Ny uppgift** – skapa en uppgift under en befintlig uppgiftslista eller skapa en uppgift i ett enda syfte.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-116">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="dc8e6-117">Butiksarbetare kan utföra följande uppgiftsoperationer i kassaprogrammet med hjälp av knapparna i kommandofältet:</span><span class="sxs-lookup"><span data-stu-id="dc8e6-117">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="dc8e6-118">**Uppgiftsstatus** – ändra status för markerade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-118">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="dc8e6-119">**Filter** – som standard visas endast aktiva uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-119">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="dc8e6-120">Med hjälp av filter kan medarbetare emellertid visa alla uppgifter, även uppgifter som har slutförts eller avbrutits.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-120">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="dc8e6-121">Bilden nedan visar fliken **mina uppgifter** i Commerce-kassaprogrammet.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-121">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Fliken Mina uppgifter i Commerce-kassaprogrammet](media/POS-task-management.png)

<span data-ttu-id="dc8e6-123">Illustrationen som följer visar fliken **Uppgiftslistor**.</span><span class="sxs-lookup"><span data-stu-id="dc8e6-123">The following illustration shows the **Task lists** tab.</span></span>

![Fliken Uppgiftslistor i Commerce-kassaprogrammet](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="dc8e6-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dc8e6-125">Additional resources</span></span>

[<span data-ttu-id="dc8e6-126">Översikt över uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="dc8e6-126">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="dc8e6-127">Konfigurera uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="dc8e6-127">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="dc8e6-128">Skapa uppgiftslistor och lägga till uppgifter</span><span class="sxs-lookup"><span data-stu-id="dc8e6-128">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="dc8e6-129">Tilldela uppgiftslistor till butiker eller medarbetare</span><span class="sxs-lookup"><span data-stu-id="dc8e6-129">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)
