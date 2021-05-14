---
title: Skapa urvalskriterier för försäljningspris
description: I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920541"
---
# <a name="create-sales-price-selection-criteria"></a><span data-ttu-id="9fa3e-103">Skapa urvalskriterier för försäljningspris</span><span class="sxs-lookup"><span data-stu-id="9fa3e-103">Create sales price selection criteria</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9fa3e-104">I den här proceduren visas hur du skapar ett kriterier för urval för försäljningspris för attributbaserade försäljningsprismodeller.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-104">This procedure shows how to create a sales price selection criterion for attribute-based sales price models.</span></span> <span data-ttu-id="9fa3e-105">Denna procedur kräver att minst en modell för försäljningspris är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-105">This procedure requires that at least one sales price model be available.</span></span> <span data-ttu-id="9fa3e-106">I det här exemplet används prismodellen för försäljningsprismodellen Speaker solution i demonstrationdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-106">This example uses the price model for the Speaker solution sales price model in the USMF demo data company.</span></span> <span data-ttu-id="9fa3e-107">Vanligtvis använder en produktchef denna procedur.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-107">Typically, a product manager uses this procedure.</span></span>

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a><span data-ttu-id="9fa3e-108">Lägga till ett nytt kriterium för en befintlig försäljningsprismodell</span><span class="sxs-lookup"><span data-stu-id="9fa3e-108">Add a new criterion for an existing sales price model</span></span>

1. <span data-ttu-id="9fa3e-109">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="9fa3e-110">Markera raden för produktmodellen för högtalarlösning i listan, men markera inte länken för modellnamn.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-110">In the list, select the row for the Speaker solution product model, but don't select the link for the model name.</span></span>
1. <span data-ttu-id="9fa3e-111">Klicka på **Modell** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="9fa3e-112">Välj **Prismodellkriterier**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-112">Select **Price model criteria**.</span></span>
1. <span data-ttu-id="9fa3e-113">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-113">Select **New**.</span></span>
1. <span data-ttu-id="9fa3e-114">I fältet **Namn** anger du "Kundgrupp 10".</span><span class="sxs-lookup"><span data-stu-id="9fa3e-114">In the **Name** field, type 'Customer group 10'.</span></span>
    * <span data-ttu-id="9fa3e-115">Namnet på prismodellvillkoret används för att hjälpa dig identifiera underliggande urvalskriterier.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-115">The name of the price model criterion is used to help identify the underlying selection criteria.</span></span>  
1. <span data-ttu-id="9fa3e-116">Ange eller välj ett värde i fältet **Prismodell**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-116">In the **Price model** field, enter or select a value.</span></span>
1. <span data-ttu-id="9fa3e-117">I fältet **Ordertyp** väljer du *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-117">In the **Order type** field, select *Sales order*.</span></span>
    * <span data-ttu-id="9fa3e-118">Ordertypen bestämmer vilka databasfält som ska vara tillgängliga för urvalsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-118">The order type determines the database fields that will be available for the selection query.</span></span>  
1. <span data-ttu-id="9fa3e-119">Ange ett datum i fältet **Giltigt från**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-119">In the **Valid from** field, enter a date.</span></span>
1. <span data-ttu-id="9fa3e-120">Ange ett datum i fältet **Löp ut den**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-120">In the **Expire by** field, enter a date.</span></span>
1. <span data-ttu-id="9fa3e-121">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-121">Select **Save**.</span></span>

## <a name="create-the-query-for-the-selection-criteria"></a><span data-ttu-id="9fa3e-122">Skapa frågan för urvalskriterierna</span><span class="sxs-lookup"><span data-stu-id="9fa3e-122">Create the query for the selection criteria</span></span>

1. <span data-ttu-id="9fa3e-123">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-123">Select **Edit**.</span></span>
2. <span data-ttu-id="9fa3e-124">I fältet **Register** väljer du *Kunder*.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-124">In the **Table** field, select *Customers*.</span></span>
3. <span data-ttu-id="9fa3e-125">I fältet **Fält** väljer du *Kundgrupp*.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-125">In the **Field** field, select *Customer group*.</span></span>
    * <span data-ttu-id="9fa3e-126">I det här exemplet används en specifik kundgrupp för urvalskriterierna.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-126">In this example, we will use a specific customer group for the selection criteria.</span></span>  
4. <span data-ttu-id="9fa3e-127">I fältet **Kriterier** väljer du *Kundgrupp 10*.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-127">In the **Criteria** field, select *Customer group 10*.</span></span>
5. <span data-ttu-id="9fa3e-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fa3e-128">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]