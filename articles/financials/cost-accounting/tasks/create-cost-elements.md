--- 
title: 'Skapa kostnadselement  '
description: "Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 266cb53b3734c8252810ba8e82759d9dec785196
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-cost-elements"></a><span data-ttu-id="039c1-103">Skapa kostnadselement  </span><span class="sxs-lookup"><span data-stu-id="039c1-103">Create cost elements</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="039c1-104">Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="039c1-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="039c1-105">I den här proceduren visas hur du skapar kostnadselement genom att importera huvudkonton via en datakoppling.</span><span class="sxs-lookup"><span data-stu-id="039c1-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="039c1-106">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="039c1-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="039c1-107">Denna procedur är avsedd för en kostnadsredovisningsfunktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="039c1-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="039c1-108">Skapa nya kostnadselement</span><span class="sxs-lookup"><span data-stu-id="039c1-108">Create new cost elements</span></span>
1. <span data-ttu-id="039c1-109">Gå till Cost accounting > Dimensions > Cost element dimensions.</span><span class="sxs-lookup"><span data-stu-id="039c1-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="039c1-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="039c1-110">Click New.</span></span>
3. <span data-ttu-id="039c1-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="039c1-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="039c1-112">Ange eller välj ett värde i fältet Data connector for dimension members.</span><span class="sxs-lookup"><span data-stu-id="039c1-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="039c1-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="039c1-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="039c1-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="039c1-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="039c1-115">Konfigurera datakopplingen</span><span class="sxs-lookup"><span data-stu-id="039c1-115">Configure the data connector</span></span>
1. <span data-ttu-id="039c1-116">Klicka på Configure dimension member provider.</span><span class="sxs-lookup"><span data-stu-id="039c1-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="039c1-117">Ange eller välj ett värde i fältet Chart of accounts.</span><span class="sxs-lookup"><span data-stu-id="039c1-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="039c1-118">Välj Shared för att använda den delade kontoplanen.</span><span class="sxs-lookup"><span data-stu-id="039c1-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="039c1-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="039c1-119">Click New.</span></span>
4. <span data-ttu-id="039c1-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="039c1-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="039c1-121">Du kan använda filter på konton som uppfyller dina kriterier.</span><span class="sxs-lookup"><span data-stu-id="039c1-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="039c1-122">Ange eller välj ett värde i fältet From main account.</span><span class="sxs-lookup"><span data-stu-id="039c1-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="039c1-123">Ange eller välj ett värde i fältet To main account.</span><span class="sxs-lookup"><span data-stu-id="039c1-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="039c1-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="039c1-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="039c1-125">Importera huvudkonton</span><span class="sxs-lookup"><span data-stu-id="039c1-125">Import main accounts</span></span>
1. <span data-ttu-id="039c1-126">Klicka på Import dimension members.</span><span class="sxs-lookup"><span data-stu-id="039c1-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="039c1-127">Huvudkonton importeras till kostnadsredovisningen och används som ett kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="039c1-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="039c1-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="039c1-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="039c1-129">Visa de importerade kontona som kostnadselement</span><span class="sxs-lookup"><span data-stu-id="039c1-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="039c1-130">Klicka på View dimension members.</span><span class="sxs-lookup"><span data-stu-id="039c1-130">Click View dimension members.</span></span>
    * <span data-ttu-id="039c1-131">Visa de importerade redovisningskontona som kostnadselement i ditt företag som kostnader kan flöda till.</span><span class="sxs-lookup"><span data-stu-id="039c1-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  


