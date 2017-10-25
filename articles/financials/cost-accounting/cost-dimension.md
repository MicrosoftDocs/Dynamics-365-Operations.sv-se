---
title: Skapa dimensioner och importera dimensionsmedlemmar
description: "Kostnadsredovisningen är en oberoende modul som kräver huvuddata från andra moduler."
author: YuyuScheller
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0fb276e7d62e2f7c02934e74741c8cf74778fc12
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="0c4b9-103">Skapa dimensioner och importera dimensionsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="0c4b9-103">Create dimensions and import dimension members</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0c4b9-104">Kostnadsredovisningen är en oberoende modul som kräver data från andra moduler.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="0c4b9-105">Denna data kategoriseras till följande:</span><span class="sxs-lookup"><span data-stu-id="0c4b9-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="0c4b9-106">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="0c4b9-106">Cost elements</span></span>
-  <span data-ttu-id="0c4b9-107">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="0c4b9-107">Cost objects</span></span>
-  <span data-ttu-id="0c4b9-108">Statistikdimensioner</span><span class="sxs-lookup"><span data-stu-id="0c4b9-108">Statistical dimensions</span></span>

<span data-ttu-id="0c4b9-109">Ett **Kostnadselement** motsvarar en kostnadsrelevant artikel i kontolistan.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="0c4b9-110">Ett **kostnadsobjekt** motsvarar valfri ekonomisk dimensionstyp, till exempel produkter, kostnadsställen samt projekt som du vill beräkna, allokera kostnader till eller mäta direkt.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="0c4b9-111">En **statistisk dimension** och dess medlemmar används för att registrera icke-monetära poster.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="0c4b9-112">Statistiska dimensionsmedlemmar kan användas som allokeringsbas inom kostnadsdistribution och -allokering</span><span class="sxs-lookup"><span data-stu-id="0c4b9-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="0c4b9-113">Följande diagram illustrerar de dimensioner som används inom kostnadsredovisningen.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="0c4b9-114">[![Dimensioner i kostnadsredovisning](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="0c4b9-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="0c4b9-115">När datan väl har importerats till kostnadsredovisningen kan du använda den för att skapa olika perspektiv som ger insikter till chefer på alla organisationsnivåer.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="0c4b9-116">Mer information om hur du skapar dimensioner och importerar dimensionsmedlemmar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="0c4b9-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="0c4b9-117">Dimensioner för kostnadselement</span><span class="sxs-lookup"><span data-stu-id="0c4b9-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="0c4b9-118">Skapa kostnadselement (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="0c4b9-118">Create cost elements (Task guide)</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="0c4b9-119">Kostnadsobjektdimensioner</span><span class="sxs-lookup"><span data-stu-id="0c4b9-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="0c4b9-120">Skapa kostnadselement (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="0c4b9-120">Create cost elements (Task guide)</span></span>](./tasks/create-cost-objects.md)
-  [<span data-ttu-id="0c4b9-121">Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="0c4b9-121">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="0c4b9-122">Mappa dimension för kostnadselement (uppgiftsguide)</span><span class="sxs-lookup"><span data-stu-id="0c4b9-122">Map a cost element dimension (Task guide)</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="0c4b9-123">Providermallar för statistiska dimensionsmedlemmar och statistiska mätningar</span><span class="sxs-lookup"><span data-stu-id="0c4b9-123">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)






