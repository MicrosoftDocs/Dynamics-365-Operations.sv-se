---
title: 'Skapa kostnadselement  '
description: Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11107993fe91e39409ccf06615a21574ad51d079
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236828"
---
# <a name="create-cost-elements"></a><span data-ttu-id="b83f6-103">Skapa kostnadselement  </span><span class="sxs-lookup"><span data-stu-id="b83f6-103">Create cost elements</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b83f6-104">Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="b83f6-104">There are several ways to create cost elements in Cost accounting.</span></span> <span data-ttu-id="b83f6-105">I den här proceduren visas hur du skapar kostnadselement genom att importera huvudkonton via en datakoppling.</span><span class="sxs-lookup"><span data-stu-id="b83f6-105">This procedure shows how to create cost elements by importing main accounts via a data connector.</span></span> <span data-ttu-id="b83f6-106">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="b83f6-106">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="b83f6-107">Denna procedur är avsedd för en kostnadsredovisningsfunktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="b83f6-107">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-elements"></a><span data-ttu-id="b83f6-108">Skapa nya kostnadselement</span><span class="sxs-lookup"><span data-stu-id="b83f6-108">Create new cost elements</span></span>
1. <span data-ttu-id="b83f6-109">Gå till Cost accounting > Dimensions > Cost element dimensions.</span><span class="sxs-lookup"><span data-stu-id="b83f6-109">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="b83f6-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b83f6-110">Click New.</span></span>
3. <span data-ttu-id="b83f6-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b83f6-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b83f6-112">Ange eller välj ett värde i fältet Data connector for dimension members.</span><span class="sxs-lookup"><span data-stu-id="b83f6-112">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="b83f6-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b83f6-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="b83f6-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b83f6-114">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="b83f6-115">Konfigurera datakopplingen</span><span class="sxs-lookup"><span data-stu-id="b83f6-115">Configure the data connector</span></span>
1. <span data-ttu-id="b83f6-116">Klicka på Configure dimension member provider.</span><span class="sxs-lookup"><span data-stu-id="b83f6-116">Click Configure dimension member provider.</span></span>
2. <span data-ttu-id="b83f6-117">Ange eller välj ett värde i fältet Chart of accounts.</span><span class="sxs-lookup"><span data-stu-id="b83f6-117">In the Chart of accounts field, enter or select a value.</span></span>
    * <span data-ttu-id="b83f6-118">Välj Shared för att använda den delade kontoplanen.</span><span class="sxs-lookup"><span data-stu-id="b83f6-118">Select Shared to use the shared chart of accounts.</span></span>  
3. <span data-ttu-id="b83f6-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b83f6-119">Click New.</span></span>
4. <span data-ttu-id="b83f6-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b83f6-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b83f6-121">Du kan använda filter på konton som uppfyller dina kriterier.</span><span class="sxs-lookup"><span data-stu-id="b83f6-121">You can apply filters to accounts to meet your criteria.</span></span>  
5. <span data-ttu-id="b83f6-122">Ange eller välj ett värde i fältet From main account.</span><span class="sxs-lookup"><span data-stu-id="b83f6-122">In the From main account field, enter or select a value.</span></span>
6. <span data-ttu-id="b83f6-123">Ange eller välj ett värde i fältet To main account.</span><span class="sxs-lookup"><span data-stu-id="b83f6-123">In the To main account field, enter or select a value.</span></span>
7. <span data-ttu-id="b83f6-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b83f6-124">Click OK.</span></span>

## <a name="import-main-accounts"></a><span data-ttu-id="b83f6-125">Importera huvudkonton</span><span class="sxs-lookup"><span data-stu-id="b83f6-125">Import main accounts</span></span>
1. <span data-ttu-id="b83f6-126">Klicka på Import dimension members.</span><span class="sxs-lookup"><span data-stu-id="b83f6-126">Click Import dimension members.</span></span>
    * <span data-ttu-id="b83f6-127">Huvudkonton importeras till kostnadsredovisningen och används som ett kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="b83f6-127">Main accounts will be imported into Cost accounting and used as cost elements.</span></span>  
2. <span data-ttu-id="b83f6-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b83f6-128">Click OK.</span></span>

## <a name="view-the-imported-accounts-as-cost-elements"></a><span data-ttu-id="b83f6-129">Visa de importerade kontona som kostnadselement</span><span class="sxs-lookup"><span data-stu-id="b83f6-129">View the imported accounts as cost elements</span></span>
1. <span data-ttu-id="b83f6-130">Klicka på View dimension members.</span><span class="sxs-lookup"><span data-stu-id="b83f6-130">Click View dimension members.</span></span>
    * <span data-ttu-id="b83f6-131">Visa de importerade redovisningskontona som kostnadselement i ditt företag som kostnader kan flöda till.</span><span class="sxs-lookup"><span data-stu-id="b83f6-131">View the imported ledger accounts as cost elements in your business that costs can flow to.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]