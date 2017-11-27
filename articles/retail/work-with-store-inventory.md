---
title: Hantera butikslager
description: "Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6245d37ace9f46ecce83a0cf80a014d5de898bbc
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="manage-store-inventory"></a><span data-ttu-id="30bb4-103">Hantera butikslager</span><span class="sxs-lookup"><span data-stu-id="30bb4-103">Manage store inventory</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="30bb4-104">Den här artikeln beskriver vilka typer av dokument som du kan använda för att hantera lager.</span><span class="sxs-lookup"><span data-stu-id="30bb4-104">This article describes the types of documents that you can use to manage inventory.</span></span>

<span data-ttu-id="30bb4-105">Du kan använda följande typer av dokument för att hantera organisationens lager.</span><span class="sxs-lookup"><span data-stu-id="30bb4-105">You can use the following types of documents to manage your organization's inventory.</span></span>

## <a name="purchase-orders"></a><span data-ttu-id="30bb4-106">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="30bb4-106">Purchase orders</span></span>
<span data-ttu-id="30bb4-107">Inköpsorder skapas på huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="30bb4-107">Purchase orders are created at the head office.</span></span> <span data-ttu-id="30bb4-108">Om ett lagerställe ingår i inköpsorderrubriken kan ordern tas emot i butiken med hjälp av Modern POS (MOPS) eller Cloud POS i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="30bb4-108">If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="30bb4-109">När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering.</span><span class="sxs-lookup"><span data-stu-id="30bb4-109">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="30bb4-110">Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="30bb4-110">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="30bb4-111">På huvudkontoret visas kvantiteterna som togs emot i butiken i Dynamics 365 for Retail i fältet **Inleverera nu** på inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="30bb4-111">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the purchase order.</span></span>

## <a name="transfer-orders"></a><span data-ttu-id="30bb4-112">Överföringsorder</span><span class="sxs-lookup"><span data-stu-id="30bb4-112">Transfer orders</span></span>
<span data-ttu-id="30bb4-113">En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från.</span><span class="sxs-lookup"><span data-stu-id="30bb4-113">A transfer order can specify that a particular store is a location that items can be shipped from.</span></span> <span data-ttu-id="30bb4-114">I det här fallet visas överföringsordern i butiken som en plockningsförfrågan i MOPS eller i Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="30bb4-114">In this case, the transfer order appears at the store as a picking request in MPOS or Cloud POS.</span></span> <span data-ttu-id="30bb4-115">När de kvantiteter som förfrågats har plockats, utfästs de och skickas till huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="30bb4-115">After the quantities that are requested are picked, they are committed and sent to the head office.</span></span> <span data-ttu-id="30bb4-116">På huvudkontoret visas kvantiteterna som plockades i butiken i Dynamics 365 for Retail i fältet **Leverera nu** på överföringsordern.</span><span class="sxs-lookup"><span data-stu-id="30bb4-116">At the head office, the quantities that were picked at the store are displayed in Dynamics 365 for Retail, in the **Ship now** field on the transfer order.</span></span> <span data-ttu-id="30bb4-117">En överföringsorder kan ange att en viss butik är en plats som artiklar kan skickas från.</span><span class="sxs-lookup"><span data-stu-id="30bb4-117">A transfer order may specify that a particular store is a location that items can be shipped to.</span></span> <span data-ttu-id="30bb4-118">I det här fallet visas överföringsordern i butiken som en inleveransförfrågan i MOPS eller i Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="30bb4-118">In this case, the transfer order appears at the store as a receiving request in MPOS or Cloud POS.</span></span> <span data-ttu-id="30bb4-119">När de kvantiteter som tas emot i butiken har angett kan de sparas lokalt för ytterligare redigering.</span><span class="sxs-lookup"><span data-stu-id="30bb4-119">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="30bb4-120">Alternativt kan kvantiteterna utfästas och skickas till huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="30bb4-120">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="30bb4-121">På huvudkontoret visas kvantiteterna som togs emot i butiken i Dynamics 365 for Retail i fältet **Inleverera nu** på inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="30bb4-121">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the transfer order.</span></span>

## <a name="stock-counts"></a><span data-ttu-id="30bb4-122">Lagerinventeringar</span><span class="sxs-lookup"><span data-stu-id="30bb4-122">Stock counts</span></span>
<span data-ttu-id="30bb4-123">Lagerinventeringar kan antingen vara tidsplanerade eller ej tidsplanerade.</span><span class="sxs-lookup"><span data-stu-id="30bb4-123">Stock counts can be either scheduled or unscheduled.</span></span> <span data-ttu-id="30bb4-124">Tidsplanerad inventering initieras på huvudkontoret och anger vilka artiklar som måste inventeras.</span><span class="sxs-lookup"><span data-stu-id="30bb4-124">Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</span></span> <span data-ttu-id="30bb4-125">Huvudkontoret skapar ett inventeringsdokument som kan inlevereras till butiken, där de faktiska lagerkvantiteterna förs in i MPOS eller Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="30bb4-125">The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</span></span> <span data-ttu-id="30bb4-126">Ej schemalagda lagerinventeringar initieras i butiken och de faktiska lagerkvantiteter uppdateras antingen i MPOS eller Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="30bb4-126">Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</span></span> <span data-ttu-id="30bb4-127">Till skillnad från schemalagda inventeringar har ej schemalagda inventeringar inte en fördefinierad lista över artiklar.</span><span class="sxs-lookup"><span data-stu-id="30bb4-127">Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</span></span> <span data-ttu-id="30bb4-128">När en lagerinventering oavsett typ utförs utfästs den och skickas till huvudkontoret.</span><span class="sxs-lookup"><span data-stu-id="30bb4-128">When a stock count of either type is completed, it is committed and sent to the head office.</span></span> <span data-ttu-id="30bb4-129">På huvudkontoret valideras och bokförs inventeringen.</span><span class="sxs-lookup"><span data-stu-id="30bb4-129">At the head office, the count is validated and posted.</span></span>

## <a name="inventory-lookup"></a><span data-ttu-id="30bb4-130">Lagersökning</span><span class="sxs-lookup"><span data-stu-id="30bb4-130">Inventory lookup</span></span>
<span data-ttu-id="30bb4-131">Den aktuella produktkvantiteten för flera butiker och lagerställen kan visas på sidan Lagersökning.</span><span class="sxs-lookup"><span data-stu-id="30bb4-131">The current product quantity on hand for multiple stores and warehouses can be viewed on the Inventory lookup page.</span></span> <span data-ttu-id="30bb4-132">Utöver det aktuella lagersaldot kan framtida ATP-kvantiteter visas för varje enskild butik.</span><span class="sxs-lookup"><span data-stu-id="30bb4-132">In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</span></span> <span data-ttu-id="30bb4-133">Välj den butik du vill visa ATP för och klicka sedan på **Visa tillgänglighet i butiken**.</span><span class="sxs-lookup"><span data-stu-id="30bb4-133">To do so, select the store that you want to view the ATP for and then click **Show store availability**.</span></span>





