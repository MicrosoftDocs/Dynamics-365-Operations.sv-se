--- 
title: "Godkänn en produktkonfigurationsmodell"
description: "När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6d19c904ca7d974a8f80eebe7d237bede080c8f6
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="903c1-103">Godkänn en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="903c1-103">Approve a product configuration model</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="903c1-104">När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="903c1-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="903c1-105">I proceduren används högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="903c1-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="903c1-106">Observera att den modellen redan har godkänts, men proceduren går igenom hela processen.</span><span class="sxs-lookup"><span data-stu-id="903c1-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="903c1-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="903c1-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="903c1-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="903c1-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="903c1-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="903c1-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="903c1-110">Välj högtalarmodellen till den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="903c1-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="903c1-111">Klicka på Versioner.</span><span class="sxs-lookup"><span data-stu-id="903c1-111">Click Versions.</span></span>
5. <span data-ttu-id="903c1-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="903c1-112">Click New.</span></span>
6. <span data-ttu-id="903c1-113">Ange eller välj ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="903c1-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="903c1-114">Referensen till en produkt representerar en version av produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="903c1-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="903c1-115">Endast produktmallar som har begränsningsbaserad konfiguration visas i listan.</span><span class="sxs-lookup"><span data-stu-id="903c1-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="903c1-116">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="903c1-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="903c1-117">Välj när produktmodellsversionen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="903c1-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="903c1-118">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="903c1-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="903c1-119">Välj ett slutdatum när produktmodellsversion ska upphöra, eller markerar Aldrig.</span><span class="sxs-lookup"><span data-stu-id="903c1-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="903c1-120">Klicka på Godkänn om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="903c1-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="903c1-121">Ange eller välj ett värde i fältet Godkänd.</span><span class="sxs-lookup"><span data-stu-id="903c1-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="903c1-122">Välj den person som är ansvarig för att godkänna produktmodeller för användning i operationer.</span><span class="sxs-lookup"><span data-stu-id="903c1-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="903c1-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="903c1-123">Click OK.</span></span>
12. <span data-ttu-id="903c1-124">Markera ett alternativ i fältet Prissättningsmetod.</span><span class="sxs-lookup"><span data-stu-id="903c1-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="903c1-125">Aktivera produktmodellsversionen.</span><span class="sxs-lookup"><span data-stu-id="903c1-125">Activate the product model version.</span></span> <span data-ttu-id="903c1-126">Det är endast möjligt att ha en aktiv produkt för en produktmodell åt gången.</span><span class="sxs-lookup"><span data-stu-id="903c1-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="903c1-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="903c1-127">Close the page.</span></span>


