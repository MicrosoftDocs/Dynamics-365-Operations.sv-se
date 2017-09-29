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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fa4548d3017246cbe49e2613f8990df6ea1c368b
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="c0390-103">Godkänn en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="c0390-103">Approve a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c0390-104">När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c0390-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="c0390-105">I proceduren används högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="c0390-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="c0390-106">Observera att den modellen redan har godkänts, men proceduren går igenom hela processen.</span><span class="sxs-lookup"><span data-stu-id="c0390-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="c0390-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="c0390-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="c0390-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c0390-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="c0390-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="c0390-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c0390-110">Välj högtalarmodellen till den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="c0390-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="c0390-111">Klicka på Versioner.</span><span class="sxs-lookup"><span data-stu-id="c0390-111">Click Versions.</span></span>
5. <span data-ttu-id="c0390-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c0390-112">Click New.</span></span>
6. <span data-ttu-id="c0390-113">Ange eller välj ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="c0390-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="c0390-114">Referensen till en produkt representerar en version av produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="c0390-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="c0390-115">Endast produktmallar som har begränsningsbaserad konfiguration visas i listan.</span><span class="sxs-lookup"><span data-stu-id="c0390-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="c0390-116">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="c0390-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="c0390-117">Välj när produktmodellsversionen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="c0390-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="c0390-118">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="c0390-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="c0390-119">Välj ett slutdatum när produktmodellsversion ska upphöra, eller markerar Aldrig.</span><span class="sxs-lookup"><span data-stu-id="c0390-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="c0390-120">Klicka på Godkänn om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="c0390-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="c0390-121">Ange eller välj ett värde i fältet Godkänd.</span><span class="sxs-lookup"><span data-stu-id="c0390-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="c0390-122">Välj den person som är ansvarig för att godkänna produktmodeller för användning i operationer.</span><span class="sxs-lookup"><span data-stu-id="c0390-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="c0390-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c0390-123">Click OK.</span></span>
12. <span data-ttu-id="c0390-124">Markera ett alternativ i fältet Prissättningsmetod.</span><span class="sxs-lookup"><span data-stu-id="c0390-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="c0390-125">Aktivera produktmodellsversionen.</span><span class="sxs-lookup"><span data-stu-id="c0390-125">Activate the product model version.</span></span> <span data-ttu-id="c0390-126">Det är endast möjligt att ha en aktiv produkt för en produktmodell åt gången.</span><span class="sxs-lookup"><span data-stu-id="c0390-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="c0390-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c0390-127">Close the page.</span></span>


