---
title: Ställ in en anskaffningskategorihierarki
description: I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess.
author: RichardLuan
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44fd02d37ec4e6431ca25dc980ed1d1785e45fac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239360"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="ef307-103">Ställ in en anskaffningskategorihierarki</span><span class="sxs-lookup"><span data-stu-id="ef307-103">Set up a procurement category hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef307-104">I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess.</span><span class="sxs-lookup"><span data-stu-id="ef307-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="ef307-105">Dessa uppgifter utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="ef307-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="ef307-106">Innan du kan starta den här proceduren måste det finnas en kategorihierarki av typen anskaffning.</span><span class="sxs-lookup"><span data-stu-id="ef307-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="ef307-107">Om du använder ett demonstrationsdataföretag kan du köra denna procedur i USMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="ef307-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="ef307-108">Lägg till en ny anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="ef307-108">Add a new procurement category</span></span>
1. <span data-ttu-id="ef307-109">Gå till **Navigeringsfönstret > Moduler > Anskaffning och källa > Försändelse > Anskaffningskategorier**.</span><span class="sxs-lookup"><span data-stu-id="ef307-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="ef307-110">I åtgärdsfönstret klickar du på **Redigera kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="ef307-110">On the Action Pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="ef307-111">Den aktuella anskaffningskategorihierarkin visas till vänster på sidan.</span><span class="sxs-lookup"><span data-stu-id="ef307-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="ef307-112">Du är på väg att ändra hierarkin.</span><span class="sxs-lookup"><span data-stu-id="ef307-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="ef307-113">I åtgärdsfönstret klickar du på **Ny kategorinod**.</span><span class="sxs-lookup"><span data-stu-id="ef307-113">On the Action Pane, select **New category node**.</span></span> <span data-ttu-id="ef307-114">Systemet väljer toppnoden som standard.</span><span class="sxs-lookup"><span data-stu-id="ef307-114">The system selects the top node by default.</span></span> <span data-ttu-id="ef307-115">Om du kör den här proceduren som en uppgiftsguide kan du klicka på fliken Lås upp och välja en annan överordnad nod att infoga den nya noden i.</span><span class="sxs-lookup"><span data-stu-id="ef307-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="ef307-116">Lås uppgifthandboken igen och klicka på noden Ny kategori när det är klart.</span><span class="sxs-lookup"><span data-stu-id="ef307-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="ef307-117">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ef307-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ef307-118">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ef307-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="ef307-119">Skriv ett värde i fältet **Eget namn**.</span><span class="sxs-lookup"><span data-stu-id="ef307-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="ef307-120">Det egna namnet är valfritt.</span><span class="sxs-lookup"><span data-stu-id="ef307-120">The friendly name is optional.</span></span> <span data-ttu-id="ef307-121">Detta visas i kategorisökningar tillsammans med kategorinamnet.</span><span class="sxs-lookup"><span data-stu-id="ef307-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="ef307-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ef307-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="ef307-123">Lägg till produkter i den nya anskaffningskategorin</span><span class="sxs-lookup"><span data-stu-id="ef307-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="ef307-124">Gå till **Anskaffning och källa > Försändelse > Anskaffningskategorier**.</span><span class="sxs-lookup"><span data-stu-id="ef307-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="ef307-125">Välj den nod som du precis lade till.</span><span class="sxs-lookup"><span data-stu-id="ef307-125">Select the node you just added.</span></span> <span data-ttu-id="ef307-126">Om du kör den här proceduren som en uppgiftsguide kanske du behöver låsa upp uppgiftsguiden för att välja noden.</span><span class="sxs-lookup"><span data-stu-id="ef307-126">If you're running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="ef307-127">Växla expansionen av avsnittet **Produkter**.</span><span class="sxs-lookup"><span data-stu-id="ef307-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="ef307-128">Klicka på **Lägg till** i associerade produkter med anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="ef307-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="ef307-129">Välj de produkter som du vill lägga till i anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="ef307-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="ef307-130">Välj pilen för att lägga till produkter till tabellen **Valda**.</span><span class="sxs-lookup"><span data-stu-id="ef307-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="ef307-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef307-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]