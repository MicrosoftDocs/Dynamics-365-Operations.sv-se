---
title: Bearbeta och spåra källdata
description: All databearbetning körs med jobb.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a23443c985ac681c8c31956ae5ea3e513337577
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448139"
---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="78fa6-103">Bearbeta och spåra källdata</span><span class="sxs-lookup"><span data-stu-id="78fa6-103">Process and trace source data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="78fa6-104">All databearbetning körs med jobb.</span><span class="sxs-lookup"><span data-stu-id="78fa6-104">All data processing is run by jobs.</span></span> <span data-ttu-id="78fa6-105">För varje jobb och dataprovider skapas en journal för att dokumentera processen som körs, och att transaktionerna har bearbetats i det aktuella jobbet.</span><span class="sxs-lookup"><span data-stu-id="78fa6-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="78fa6-106">Använd den här proceduren för att skapa en datakälla och sedan spåra ursprunget till en viss kostnadstransaktion.</span><span class="sxs-lookup"><span data-stu-id="78fa6-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="78fa6-107">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="78fa6-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="78fa6-108">Innan du utför den här uppgiften måste du spela upp följande uppgiftsguider: "Skapa en huvudbok för kostnadsredovisning", "Definiera kostnadsstyrenheter" och "Hantera datakälla för huvudbok för kostnadsredovisning".</span><span class="sxs-lookup"><span data-stu-id="78fa6-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="78fa6-109">Gå till Kostnadsredovisning > Redovisningsinställningar > Huvudböcker för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="78fa6-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="78fa6-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="78fa6-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="78fa6-111">Välj den huvudbok för kostnadsredovisning som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="78fa6-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="78fa6-112">Klicka på Faktiska versioner.</span><span class="sxs-lookup"><span data-stu-id="78fa6-112">Click Actual versions.</span></span>
4. <span data-ttu-id="78fa6-113">Klicka på Källdatabehandling i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78fa6-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="78fa6-114">Klicka på Överföringsjournaler för redovisningsposter.</span><span class="sxs-lookup"><span data-stu-id="78fa6-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="78fa6-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="78fa6-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="78fa6-116">Klicka på Journalposter.</span><span class="sxs-lookup"><span data-stu-id="78fa6-116">Click Journal entries.</span></span>
8. <span data-ttu-id="78fa6-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="78fa6-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="78fa6-118">Klicka på Kostnadsposter.</span><span class="sxs-lookup"><span data-stu-id="78fa6-118">Click Cost entries.</span></span>
10. <span data-ttu-id="78fa6-119">Klicka på Källpost.</span><span class="sxs-lookup"><span data-stu-id="78fa6-119">Click Source entry.</span></span>
11. <span data-ttu-id="78fa6-120">Klicka på Källdatabehandling i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="78fa6-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="78fa6-121">Klicka på Redovisning.</span><span class="sxs-lookup"><span data-stu-id="78fa6-121">Click General ledger.</span></span>
13. <span data-ttu-id="78fa6-122">Ange eller välj ett värde i fältet Räkenskapskalenderperiod.</span><span class="sxs-lookup"><span data-stu-id="78fa6-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="78fa6-123">Välj Fiscal 2017 Period 9 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="78fa6-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="78fa6-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="78fa6-124">Click OK.</span></span>

