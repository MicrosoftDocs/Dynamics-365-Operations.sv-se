--- 
title: 'Skapa kostnadsobjekt  '
description: "I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för Dynamics 365 for Finance and Operations, Enterprise Edition-kostnadsställen till kostnadsredovisning via en datakoppling."
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-objects"></a><span data-ttu-id="91c74-103">Skapa kostnadsobjekt  </span><span class="sxs-lookup"><span data-stu-id="91c74-103">Create cost objects</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91c74-104">I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för Dynamics 365 for Finance and Operations, Enterprise Edition-kostnadsställen till kostnadsredovisning via en datakoppling.</span><span class="sxs-lookup"><span data-stu-id="91c74-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="91c74-105">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="91c74-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="91c74-106">Denna procedur är avsedd för en kostnadsredovisningsfunktion som lades till i Dynamics 365 for Operations, version 1611.</span><span class="sxs-lookup"><span data-stu-id="91c74-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="91c74-107">Skapa nya kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="91c74-107">Create new cost objects</span></span>
1. <span data-ttu-id="91c74-108">Gå till Kostnadsredovisning > Dimensioner > Kostnadsobjektdimensioner.</span><span class="sxs-lookup"><span data-stu-id="91c74-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="91c74-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91c74-109">Click New.</span></span>
3. <span data-ttu-id="91c74-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="91c74-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="91c74-111">Ange eller välj ett värde i fältet Data connector for dimension members.</span><span class="sxs-lookup"><span data-stu-id="91c74-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="91c74-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="91c74-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="91c74-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="91c74-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="91c74-114">Konfigurera datakopplingen</span><span class="sxs-lookup"><span data-stu-id="91c74-114">Configure the data connector</span></span>
1. <span data-ttu-id="91c74-115">Klicka på Configure dimension member provider.</span><span class="sxs-lookup"><span data-stu-id="91c74-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="91c74-116">Välj CostCenter för att importera CostCenter-dimensionen till kostnadsredovisningen.</span><span class="sxs-lookup"><span data-stu-id="91c74-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="91c74-117">Välj Cost center i fältet Dimension name.</span><span class="sxs-lookup"><span data-stu-id="91c74-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="91c74-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="91c74-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="91c74-119">Importera kostnadsställen</span><span class="sxs-lookup"><span data-stu-id="91c74-119">Import cost centers</span></span>
1. <span data-ttu-id="91c74-120">Klicka på Import dimension members.</span><span class="sxs-lookup"><span data-stu-id="91c74-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="91c74-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="91c74-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="91c74-122">Visa de importerade kostnadsställena</span><span class="sxs-lookup"><span data-stu-id="91c74-122">View the imported cost centers</span></span>
1. <span data-ttu-id="91c74-123">Klicka på View dimension members.</span><span class="sxs-lookup"><span data-stu-id="91c74-123">Click View dimension members.</span></span>


