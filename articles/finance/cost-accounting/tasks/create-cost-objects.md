---
title: 'Skapa kostnadsobjekt  '
description: I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55f5f6e5048f70e744cb3dc82a2a279aae69b4af
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976125"
---
# <a name="create-cost-objects"></a><span data-ttu-id="14174-103">Skapa kostnadsobjekt  </span><span class="sxs-lookup"><span data-stu-id="14174-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="14174-104">I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling.</span><span class="sxs-lookup"><span data-stu-id="14174-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="14174-105">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="14174-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="14174-106">Skapa nya kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="14174-106">Create new cost objects</span></span>
1. <span data-ttu-id="14174-107">Gå till Kostnadsredovisning > Dimensioner > Kostnadsobjektdimensioner.</span><span class="sxs-lookup"><span data-stu-id="14174-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="14174-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="14174-108">Click New.</span></span>
3. <span data-ttu-id="14174-109">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="14174-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="14174-110">Ange eller välj ett värde i fältet Data connector for dimension members.</span><span class="sxs-lookup"><span data-stu-id="14174-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="14174-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="14174-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="14174-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="14174-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="14174-113">Konfigurera datakopplingen</span><span class="sxs-lookup"><span data-stu-id="14174-113">Configure the data connector</span></span>
1. <span data-ttu-id="14174-114">Klicka på Configure dimension member provider.</span><span class="sxs-lookup"><span data-stu-id="14174-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="14174-115">Välj CostCenter för att importera CostCenter-dimensionen till kostnadsredovisningen.</span><span class="sxs-lookup"><span data-stu-id="14174-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="14174-116">Välj Cost center i fältet Dimension name.</span><span class="sxs-lookup"><span data-stu-id="14174-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="14174-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14174-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="14174-118">Importera kostnadsställen</span><span class="sxs-lookup"><span data-stu-id="14174-118">Import cost centers</span></span>
1. <span data-ttu-id="14174-119">Klicka på Import dimension members.</span><span class="sxs-lookup"><span data-stu-id="14174-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="14174-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14174-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="14174-121">Visa de importerade kostnadsställena</span><span class="sxs-lookup"><span data-stu-id="14174-121">View the imported cost centers</span></span>
1. <span data-ttu-id="14174-122">Klicka på View dimension members.</span><span class="sxs-lookup"><span data-stu-id="14174-122">Click View dimension members.</span></span>

