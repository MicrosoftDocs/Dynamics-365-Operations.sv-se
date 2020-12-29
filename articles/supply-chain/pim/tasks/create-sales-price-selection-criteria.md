---
title: Skapa urvalskriterier för försäljningspris
description: I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ae444008e550d808a02d55dad02cc1b52874f0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437659"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="61e7e-103">Skapa urvalskriterier för försäljningspris</span><span class="sxs-lookup"><span data-stu-id="61e7e-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61e7e-104">I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller.</span><span class="sxs-lookup"><span data-stu-id="61e7e-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="61e7e-105">Denna procedur kräver att minst en modell för försäljningspris är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="61e7e-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="61e7e-106">I det här exemplet används prismodellen för försäljningsprismodellen Speaker solution i demonstrationdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="61e7e-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="61e7e-107">Vanligtvis använder en produktchef denna procedur.</span><span class="sxs-lookup"><span data-stu-id="61e7e-107">Typically, a product manager uses this procedure.</span></span>


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="61e7e-108">Lägga till ett nytt kriterium för en befintlig försäljningsprismodell</span><span class="sxs-lookup"><span data-stu-id="61e7e-108">Add a new criterion for an existing sales price model</span></span>
1. <span data-ttu-id="61e7e-109">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="61e7e-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="61e7e-110">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="61e7e-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="61e7e-111">Markera raden för produktmodellen för Speaker solution i listan, men inte klicka på länken för modellnamn.</span><span class="sxs-lookup"><span data-stu-id="61e7e-111">In the list, select the row for the Speaker solution product model, but don't click the link for the model name.</span></span>
4. <span data-ttu-id="61e7e-112">Klicka på Modell i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="61e7e-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="61e7e-113">Klicka på Price model criteria.</span><span class="sxs-lookup"><span data-stu-id="61e7e-113">Click Price model criteria.</span></span>
6. <span data-ttu-id="61e7e-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="61e7e-114">Click New.</span></span>
7. <span data-ttu-id="61e7e-115">Ange "Customer group 10" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="61e7e-115">In the Name field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="61e7e-116">Namnet på prismodellvillkoret används för att hjälpa dig identifiera underliggande urvalskriterier.</span><span class="sxs-lookup"><span data-stu-id="61e7e-116">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
8. <span data-ttu-id="61e7e-117">Ange eller välj ett värde i fältet Price model.</span><span class="sxs-lookup"><span data-stu-id="61e7e-117">In the Price model field, enter or select a value.</span></span>
9. <span data-ttu-id="61e7e-118">Välj Sales order i fältet Order type.</span><span class="sxs-lookup"><span data-stu-id="61e7e-118">In the Order type field, select Sales order.</span></span>
    * <span data-ttu-id="61e7e-119">Ordertypen bestämmer vilka databasfält som ska vara tillgängliga för urvalsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="61e7e-119">The order type determines the database fields that will be available for the selection query.</span></span>  
10. <span data-ttu-id="61e7e-120">Ange ett datum i fältet för Valid from.</span><span class="sxs-lookup"><span data-stu-id="61e7e-120">In the Valid from field, enter a date.</span></span>
11. <span data-ttu-id="61e7e-121">Ange ett datum i fältet Expire by.</span><span class="sxs-lookup"><span data-stu-id="61e7e-121">In the Expire by field, enter a date.</span></span>
12. <span data-ttu-id="61e7e-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="61e7e-122">Click Save.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="61e7e-123">Skapa frågan för urvalskriterierna</span><span class="sxs-lookup"><span data-stu-id="61e7e-123">Create the query for the selection criteria</span></span>
1. <span data-ttu-id="61e7e-124">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="61e7e-124">Click Edit.</span></span>
2. <span data-ttu-id="61e7e-125">Markera Customers i fältet Table.</span><span class="sxs-lookup"><span data-stu-id="61e7e-125">In the Table field, select Customers.</span></span> 
3. <span data-ttu-id="61e7e-126">Välj Customer Group i fältet Field.</span><span class="sxs-lookup"><span data-stu-id="61e7e-126">In the Field field, select Customer group.</span></span>
    * <span data-ttu-id="61e7e-127">I det här exemplet används en specifik kundgrupp för urvalskriterierna.</span><span class="sxs-lookup"><span data-stu-id="61e7e-127">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="61e7e-128">Välj Customer group 10 i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="61e7e-128">In the Criteria field, select Customer group 10.</span></span> 
5. <span data-ttu-id="61e7e-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="61e7e-129">Click OK.</span></span>

