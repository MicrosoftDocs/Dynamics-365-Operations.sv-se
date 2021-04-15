---
title: 'Skapa kostnadsobjekt  '
description: I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1219cb15ecec7c156579c5cf7c3a3511a141e00b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810064"
---
# <a name="create-cost-objects"></a><span data-ttu-id="8cf11-103">Skapa kostnadsobjekt  </span><span class="sxs-lookup"><span data-stu-id="8cf11-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8cf11-104">I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling.</span><span class="sxs-lookup"><span data-stu-id="8cf11-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="8cf11-105">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="8cf11-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="8cf11-106">Skapa nya kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="8cf11-106">Create new cost objects</span></span>
1. <span data-ttu-id="8cf11-107">Gå till Kostnadsredovisning > Dimensioner > Kostnadsobjektdimensioner.</span><span class="sxs-lookup"><span data-stu-id="8cf11-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="8cf11-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8cf11-108">Click New.</span></span>
3. <span data-ttu-id="8cf11-109">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8cf11-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8cf11-110">Ange eller välj ett värde i fältet Data connector for dimension members.</span><span class="sxs-lookup"><span data-stu-id="8cf11-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="8cf11-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8cf11-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="8cf11-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8cf11-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="8cf11-113">Konfigurera datakopplingen</span><span class="sxs-lookup"><span data-stu-id="8cf11-113">Configure the data connector</span></span>
1. <span data-ttu-id="8cf11-114">Klicka på Configure dimension member provider.</span><span class="sxs-lookup"><span data-stu-id="8cf11-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="8cf11-115">Välj CostCenter för att importera CostCenter-dimensionen till kostnadsredovisningen.</span><span class="sxs-lookup"><span data-stu-id="8cf11-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="8cf11-116">Välj Cost center i fältet Dimension name.</span><span class="sxs-lookup"><span data-stu-id="8cf11-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="8cf11-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8cf11-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="8cf11-118">Importera kostnadsställen</span><span class="sxs-lookup"><span data-stu-id="8cf11-118">Import cost centers</span></span>
1. <span data-ttu-id="8cf11-119">Klicka på Import dimension members.</span><span class="sxs-lookup"><span data-stu-id="8cf11-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="8cf11-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8cf11-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="8cf11-121">Visa de importerade kostnadsställena</span><span class="sxs-lookup"><span data-stu-id="8cf11-121">View the imported cost centers</span></span>
1. <span data-ttu-id="8cf11-122">Klicka på View dimension members.</span><span class="sxs-lookup"><span data-stu-id="8cf11-122">Click View dimension members.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]