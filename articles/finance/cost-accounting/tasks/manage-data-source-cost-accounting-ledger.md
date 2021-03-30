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
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48fef42f1866b0995182ac6fd022045f7dd31906
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218921"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="324c9-103">Hantera en datakälla för huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="324c9-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="324c9-104">Använd den här proceduren för att hantera datakällan för redovisning för en huvudbok för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="324c9-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="324c9-105">Innan du utför den här uppgiften måste du spela upp uppgiftsguiderna "Skapa en huvudbok för kostnadsredovisning" och "Definiera kostnadsstyrenheter".</span><span class="sxs-lookup"><span data-stu-id="324c9-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="324c9-106">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="324c9-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="324c9-107">Gå till Kostnadsredovisning > Redovisningsinställningar > Huvudböcker för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="324c9-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="324c9-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="324c9-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="324c9-109">Klicka på Faktiska versioner.</span><span class="sxs-lookup"><span data-stu-id="324c9-109">Click Actual versions.</span></span>
4. <span data-ttu-id="324c9-110">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="324c9-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="324c9-111">Klicka på Redovisning.</span><span class="sxs-lookup"><span data-stu-id="324c9-111">Click General ledger.</span></span>
6. <span data-ttu-id="324c9-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="324c9-112">Click New.</span></span>
7. <span data-ttu-id="324c9-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="324c9-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="324c9-114">Ange eller välj ett värde i fältet Dataprovider.</span><span class="sxs-lookup"><span data-stu-id="324c9-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="324c9-115">För det här exemplet väljer du Dynamics 365 Finance – redovisningsposter.</span><span class="sxs-lookup"><span data-stu-id="324c9-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="324c9-116">Ange eller välj ett värde i fältet Dimension för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="324c9-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="324c9-117">Välj Kostnadselement för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="324c9-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="324c9-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="324c9-118">Click Save.</span></span>
11. <span data-ttu-id="324c9-119">Klicka på Konfigurera dataprovider.</span><span class="sxs-lookup"><span data-stu-id="324c9-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="324c9-120">Ange eller välj ett värde i fältet Juridisk person.</span><span class="sxs-lookup"><span data-stu-id="324c9-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="324c9-121">Välj USP2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="324c9-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="324c9-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="324c9-122">Click New.</span></span>
14. <span data-ttu-id="324c9-123">Välj Aktuell i fältet Bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="324c9-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="324c9-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="324c9-124">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]