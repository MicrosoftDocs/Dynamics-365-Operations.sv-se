---
title: Förbered ett kanban-processjobb när material är tillgängliga för arbetsgruppen
description: Den här uppgiften fokuseras på att förbereda ett kanban-processjobb när alla material är tillgängliga för arbetsgruppen.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a12773cc6d94a34197084c8fe12c90167d4dca62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977773"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="69f20-103">Förbered ett kanban-processjobb när material är tillgängliga för arbetsgruppen</span><span class="sxs-lookup"><span data-stu-id="69f20-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69f20-104">Den här uppgiften fokuseras på att förbereda ett kanban-processjobb när alla material är tillgängliga för arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="69f20-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="69f20-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="69f20-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="69f20-106">Den här uppgiften är avsedd för maskinoperatören.</span><span class="sxs-lookup"><span data-stu-id="69f20-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="69f20-107">Gå till Kanban-tavla för processjobb.</span><span class="sxs-lookup"><span data-stu-id="69f20-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="69f20-108">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="69f20-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="69f20-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="69f20-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="69f20-110">Välj arbetsgrupp 1250 och klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="69f20-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="69f20-111">Väl rad 4 i listan.</span><span class="sxs-lookup"><span data-stu-id="69f20-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="69f20-112">I det rena demonstrationsföretaget är Kanban 000329 på rad 4 det första jobbet som inte har slutförts än.</span><span class="sxs-lookup"><span data-stu-id="69f20-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="69f20-113">Växla expansionen av avsnittet Plocklista.</span><span class="sxs-lookup"><span data-stu-id="69f20-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="69f20-114">Kontrollera att tillförselstatusen är tillgänglig för alla artiklar i plocklistan.</span><span class="sxs-lookup"><span data-stu-id="69f20-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="69f20-115">Om flera jobb väljs kommer plocklistan att visa summan av alla artiklar som behövs för de valda jobben.</span><span class="sxs-lookup"><span data-stu-id="69f20-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="69f20-116">Klicka på Förbered.</span><span class="sxs-lookup"><span data-stu-id="69f20-116">Click Prepare.</span></span>
    * <span data-ttu-id="69f20-117">Förberedelseprocessen är nu slutförd.</span><span class="sxs-lookup"><span data-stu-id="69f20-117">The preparation process is now completed.</span></span> <span data-ttu-id="69f20-118">Den markerade kryssrutan för alla rader i plocklistan anger att tillförselstatusen plockas.</span><span class="sxs-lookup"><span data-stu-id="69f20-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  

