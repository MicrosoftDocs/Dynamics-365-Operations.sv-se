---
title: Hantera en datakälla för huvudbok för kostnadsredovisning
description: Använd den här proceduren för att hantera datakällan för redovisning för en huvudbok för kostnadsredovisning.
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
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cf53e905cf32557f4671477b173b1c5072d186e
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3137831"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="e1b2d-103">Hantera en datakälla för huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="e1b2d-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1b2d-104">Använd den här proceduren för att hantera datakällan för redovisning för en huvudbok för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="e1b2d-105">Innan du utför den här uppgiften måste du spela upp uppgiftsguiderna "Skapa en huvudbok för kostnadsredovisning" och "Definiera kostnadsstyrenheter".</span><span class="sxs-lookup"><span data-stu-id="e1b2d-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="e1b2d-106">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="e1b2d-107">Gå till Kostnadsredovisning > Redovisningsinställningar > Huvudböcker för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="e1b2d-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e1b2d-109">Klicka på Faktiska versioner.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-109">Click Actual versions.</span></span>
4. <span data-ttu-id="e1b2d-110">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="e1b2d-111">Klicka på Redovisning.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-111">Click General ledger.</span></span>
6. <span data-ttu-id="e1b2d-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-112">Click New.</span></span>
7. <span data-ttu-id="e1b2d-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="e1b2d-114">Ange eller välj ett värde i fältet Dataprovider.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="e1b2d-115">För det här exemplet väljer du Dynamics 365 Finance - redovisningsposter.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="e1b2d-116">Ange eller välj ett värde i fältet Dimension för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="e1b2d-117">Välj Kostnadselement för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="e1b2d-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-118">Click Save.</span></span>
11. <span data-ttu-id="e1b2d-119">Klicka på Konfigurera dataprovider.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="e1b2d-120">Ange eller välj ett värde i fältet Juridisk person.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="e1b2d-121">Välj USP2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="e1b2d-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-122">Click New.</span></span>
14. <span data-ttu-id="e1b2d-123">Välj Aktuell i fältet Bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="e1b2d-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e1b2d-124">Click OK.</span></span>

