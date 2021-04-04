---
title: Lastmallar
description: I det här avsnittet beskrivs hur du ställer in lastmallar och hur du kopplar en lastmall till en ny last.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 80004b5d22e1cf81c1ffa9f74c2c479e1561df72
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247224"
---
# <a name="load-templates"></a><span data-ttu-id="8bb25-103">Lastmallar</span><span class="sxs-lookup"><span data-stu-id="8bb25-103">Load templates</span></span>

<span data-ttu-id="8bb25-104">När du skapar en ny last kan du tilldela en lastmall.</span><span class="sxs-lookup"><span data-stu-id="8bb25-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="8bb25-105">Lastmallen innehåller information om utrustning och om mått som höjd, bredd, djup och volym för lasten.</span><span class="sxs-lookup"><span data-stu-id="8bb25-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="8bb25-106">I det här avsnittet beskrivs hur du ställer in lastmallar och hur du kopplar en lastmall till en ny last.</span><span class="sxs-lookup"><span data-stu-id="8bb25-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="8bb25-107">Ställa in en lastmall</span><span class="sxs-lookup"><span data-stu-id="8bb25-107">Set up a load template</span></span>

1. <span data-ttu-id="8bb25-108">Gå till **Transporthantering \> Installation \> Lastuppbyggnad \> Lastmall**.</span><span class="sxs-lookup"><span data-stu-id="8bb25-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="8bb25-109">I åtgärdsfönstret, välj **Ny** om du vill lägga till en ny mall eller **Redigera** för att redigera en befintlig mall.</span><span class="sxs-lookup"><span data-stu-id="8bb25-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="8bb25-110">Ange följande fält i raden för den nya eller befintliga mallen:</span><span class="sxs-lookup"><span data-stu-id="8bb25-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="8bb25-111">**Lastmall-ID** – Ange en unik identifierare (ID) för lastmallen.</span><span class="sxs-lookup"><span data-stu-id="8bb25-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="8bb25-112">**Utrustning** – Välj den utrustning som ska användas för att leverera lasten.</span><span class="sxs-lookup"><span data-stu-id="8bb25-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="8bb25-113">**Lastens höjd**, **Lastens bredd** och **Lastens djup** – Ange måtten för lasten.</span><span class="sxs-lookup"><span data-stu-id="8bb25-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="8bb25-114">**Max. tillåten lastvolym** och **Max. tillåten lastvikt** – Ange högsta tillåtna volym och vikt för lasten.</span><span class="sxs-lookup"><span data-stu-id="8bb25-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="8bb25-115">**Högsta tillåtna bruttovikt** – Ange lastens maximala tillåtna bruttovikt.</span><span class="sxs-lookup"><span data-stu-id="8bb25-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="8bb25-116">Lastens bruttovikt inkluderar både dess taravikt och dess lastvikt.</span><span class="sxs-lookup"><span data-stu-id="8bb25-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="8bb25-117">**Maximalt tillåtet antal fraktenheter** – Ange det maximala antalet gods som lasten kan innehålla.</span><span class="sxs-lookup"><span data-stu-id="8bb25-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="8bb25-118">**Stapla last på golv** – Markera den här kryssrutan om du vill använda golvpåfyllning.</span><span class="sxs-lookup"><span data-stu-id="8bb25-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="8bb25-119">I ett scenario för golvpåfyllning staplas lådor från golv till taket och vägg till vägg inuti behållaren för att maximera kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="8bb25-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="8bb25-120">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8bb25-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="8bb25-121">Associera en lastmall med en ny last</span><span class="sxs-lookup"><span data-stu-id="8bb25-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="8bb25-122">Gå till **Transporthantering \> Planering \> Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="8bb25-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="8bb25-123">Välj en av följande flikar i den övre delen av sidan, beroende på vilken typ av källdokument som du har skapat en beläggning för: **leveranser**, **försäljningsrader**, **överföringsrader** eller **inköpsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="8bb25-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="8bb25-124">Välj det specifika dokument som du vill planera lasten för.</span><span class="sxs-lookup"><span data-stu-id="8bb25-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="8bb25-125">I Åtgärdsfönster, på fliken **Tillgång och efterfrågan** i gruppen **Lägg till** välj **Till ny last**.</span><span class="sxs-lookup"><span data-stu-id="8bb25-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="8bb25-126">I dialogrutan **Lastmall** ange fältet **Lastmall-ID** välj mall att tillämpa.</span><span class="sxs-lookup"><span data-stu-id="8bb25-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="8bb25-127">Välj **OK** för att använda mallen.</span><span class="sxs-lookup"><span data-stu-id="8bb25-127">Select **OK** to apply the template.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]