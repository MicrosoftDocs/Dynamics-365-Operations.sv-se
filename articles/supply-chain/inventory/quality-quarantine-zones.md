---
title: Karantänzoner för avvikelser
description: I detta ämne beskrivs hur du skapar och använder karantänzoner för avvikelser.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ca74ec4586fffa3b9156aadab887629283b98a
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956838"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="5a50f-103">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="5a50f-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a50f-104">I detta ämne beskrivs hur du skapar och använder karantänzoner för avvikelser.</span><span class="sxs-lookup"><span data-stu-id="5a50f-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="5a50f-105">Du använder sidan **Karantänzoner** för att definiera zoner som kan tilldelas avvikelser.</span><span class="sxs-lookup"><span data-stu-id="5a50f-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="5a50f-106">När du skapar en avvikelse kan du ange fälten **Karantänzon** och **Karantänzon** på fliken **Allmänt** på sidan **Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="5a50f-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="5a50f-107">Fältet **Karantänzon** anger vanligtvis området eller platsen där artikeln finns.</span><span class="sxs-lookup"><span data-stu-id="5a50f-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="5a50f-108">I fältet **Karantäntyp** definieras artikeln som antingen *Begränsad användning* eller *Oanvändbar*.</span><span class="sxs-lookup"><span data-stu-id="5a50f-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="5a50f-109">När du skriver ut en avvikelse- eller korrigeringsrapport för en avvikelse kan du visa karantänzonen där artikeln finns.</span><span class="sxs-lookup"><span data-stu-id="5a50f-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="5a50f-110">Du kan även skriva ut en avvikelsetagg för en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="5a50f-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="5a50f-111">Denna rapport anger tilldelad karantänzon samt information om användning i syfte att ge vägledning om hur defekta material bör hanteras.</span><span class="sxs-lookup"><span data-stu-id="5a50f-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="5a50f-112">Karantänzonerna kan överensstämma med lagerplatser eller funktionsresurser.</span><span class="sxs-lookup"><span data-stu-id="5a50f-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="5a50f-113">Exempel på karantänzoner</span><span class="sxs-lookup"><span data-stu-id="5a50f-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="5a50f-114">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="5a50f-114">Example 1</span></span>

<span data-ttu-id="5a50f-115">Du arbetar på ett tillverkningsföretag för elektronik som producerar och distribuerar TV-apparater, högtalare och mediaspelare.</span><span class="sxs-lookup"><span data-stu-id="5a50f-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="5a50f-116">I detta fall kan du konfigurera en karantänzon som representerar varje typ av produkt.</span><span class="sxs-lookup"><span data-stu-id="5a50f-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="5a50f-117">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="5a50f-117">Example 2</span></span>

<span data-ttu-id="5a50f-118">Tre behållare och två ställ används för att lagra artiklar som är avvikelser.</span><span class="sxs-lookup"><span data-stu-id="5a50f-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="5a50f-119">I det här fallet kan du konfigurera fem karantänzoner, en för respektive behållare och ställ.</span><span class="sxs-lookup"><span data-stu-id="5a50f-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="5a50f-120">Skapa en karantänzon</span><span class="sxs-lookup"><span data-stu-id="5a50f-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="5a50f-121">Gå till **Lagerhantering \> Inställningar \> Kvalitetshantering \> Karantänzoner**.</span><span class="sxs-lookup"><span data-stu-id="5a50f-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="5a50f-122">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5a50f-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="5a50f-123">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="5a50f-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="5a50f-124">**Karantänzon** – Ange ett unikt ID eller namn för karantänzonen.</span><span class="sxs-lookup"><span data-stu-id="5a50f-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="5a50f-125">**Beskrivning** – Ange en detaljerad beskrivning av karantänzonen.</span><span class="sxs-lookup"><span data-stu-id="5a50f-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="5a50f-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5a50f-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a50f-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5a50f-127">Additional resources</span></span>

- [<span data-ttu-id="5a50f-128">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="5a50f-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="5a50f-129">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="5a50f-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="5a50f-130">Medarbetare som ansvarar för godkännande av avvikelser</span><span class="sxs-lookup"><span data-stu-id="5a50f-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="5a50f-131">Problemtyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="5a50f-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="5a50f-132">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="5a50f-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="5a50f-133">Kvalitetsavgifter för avvikelser</span><span class="sxs-lookup"><span data-stu-id="5a50f-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="5a50f-134">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="5a50f-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="5a50f-135">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="5a50f-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
