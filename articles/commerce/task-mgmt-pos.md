---
title: Uppgiftshantering i kassan
description: I det här avsnittet beskrivs uppgiftshantering i Microsoft Dynamics 365 Commerce kassaprogram (POS).
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 38ee9db94b3b222e8c0ce5d0883f47bd5d3e7d22
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796932"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="c7464-103">Uppgiftshantering i kassan</span><span class="sxs-lookup"><span data-stu-id="c7464-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c7464-104">I det här avsnittet beskrivs uppgiftshantering i Microsoft Dynamics 365 Commerce kassaprogram (POS).</span><span class="sxs-lookup"><span data-stu-id="c7464-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="c7464-105">Dynamics 365 Commerce kassaprogrammet har funktioner för uppgiftshantering som tillåter att butikschefer och medarbetare hantera uppgifter och uppdaterar uppgiftsstatus.</span><span class="sxs-lookup"><span data-stu-id="c7464-105">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="c7464-106">Butiksarbetare har tillgång till uppgifter antingen genom att välja panelen **Uppgifter** på startsidan för POS eller genom att välja uppgiftsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c7464-106">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="c7464-107">Butiksarbetare hämtas som standard till fliken **mina uppgifter** där de kan visa de uppgifter som de har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="c7464-107">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="c7464-108">De kan dock enkelt växla till flikarna **Förfallna uppgifter**, **Öppna uppgifter** och **Uppgiftslistor**.</span><span class="sxs-lookup"><span data-stu-id="c7464-108">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="c7464-109">Uppgiftsfunktioner för butikschefer</span><span class="sxs-lookup"><span data-stu-id="c7464-109">Task operations for store managers</span></span>

<span data-ttu-id="c7464-110">Butikschefer kan utföra följande uppgiftsoperationer i kassaprogrammet med hjälp av knapparna i kommandofältet:</span><span class="sxs-lookup"><span data-stu-id="c7464-110">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="c7464-111">**Tilldela** – tilldela de markerade uppgifterna till en butiksarbetare.</span><span class="sxs-lookup"><span data-stu-id="c7464-111">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="c7464-112">**Uppgiftsstatus** – ändra status för markerade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c7464-112">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="c7464-113">**Filter** – som standard visas endast aktiva uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c7464-113">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="c7464-114">Med hjälp av filter kan chefer emellertid visa alla uppgifter, även uppgifter som har slutförts eller avbrutits.</span><span class="sxs-lookup"><span data-stu-id="c7464-114">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="c7464-115">**Ny uppgift** – skapa en uppgift under en befintlig uppgiftslista eller skapa en uppgift i ett enda syfte.</span><span class="sxs-lookup"><span data-stu-id="c7464-115">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="c7464-116">Butiksarbetare kan utföra följande uppgiftsoperationer i kassaprogrammet med hjälp av knapparna i kommandofältet:</span><span class="sxs-lookup"><span data-stu-id="c7464-116">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="c7464-117">**Uppgiftsstatus** – ändra status för markerade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c7464-117">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="c7464-118">**Filter** – som standard visas endast aktiva uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c7464-118">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="c7464-119">Med hjälp av filter kan medarbetare emellertid visa alla uppgifter, även uppgifter som har slutförts eller avbrutits.</span><span class="sxs-lookup"><span data-stu-id="c7464-119">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="c7464-120">Bilden nedan visar fliken **mina uppgifter** i Commerce-kassaprogrammet.</span><span class="sxs-lookup"><span data-stu-id="c7464-120">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Fliken Mina uppgifter i Commerce-kassaprogrammet](media/POS-task-management.png)

<span data-ttu-id="c7464-122">Illustrationen som följer visar fliken **Uppgiftslistor**.</span><span class="sxs-lookup"><span data-stu-id="c7464-122">The following illustration shows the **Task lists** tab.</span></span>

![Fliken Uppgiftslistor i Commerce-kassaprogrammet](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="c7464-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c7464-124">Additional resources</span></span>

[<span data-ttu-id="c7464-125">Översikt över uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="c7464-125">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="c7464-126">Konfigurera uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="c7464-126">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="c7464-127">Skapa uppgiftslistor och lägga till uppgifter</span><span class="sxs-lookup"><span data-stu-id="c7464-127">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="c7464-128">Tilldela uppgiftslistor till butiker eller medarbetare</span><span class="sxs-lookup"><span data-stu-id="c7464-128">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
