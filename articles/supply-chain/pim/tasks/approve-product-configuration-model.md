---
title: Godkänn en produktkonfigurationsmodell
description: När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b548e2369f30e998ecde45408ff45893b88f9a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987114"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="fa1cc-103">Godkänn en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="fa1cc-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fa1cc-104">När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="fa1cc-105">I proceduren används högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="fa1cc-106">Observera att den modellen redan har godkänts, men proceduren går igenom hela processen.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="fa1cc-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="fa1cc-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="fa1cc-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fa1cc-110">Välj högtalarmodellen till den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="fa1cc-111">Klicka på Versioner.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-111">Click Versions.</span></span>
5. <span data-ttu-id="fa1cc-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-112">Click New.</span></span>
6. <span data-ttu-id="fa1cc-113">Ange eller välj ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="fa1cc-114">Referensen till en produkt representerar en version av produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="fa1cc-115">Endast produktmallar som har begränsningsbaserad konfiguration visas i listan.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="fa1cc-116">Ange ett datum i fältet Från datum.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="fa1cc-117">Välj när produktmodellsversionen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="fa1cc-118">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="fa1cc-119">Välj ett slutdatum när produktmodellsversion ska upphöra, eller markerar Aldrig.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="fa1cc-120">Klicka på Godkänn om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="fa1cc-121">Ange eller välj ett värde i fältet Godkänd.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="fa1cc-122">Välj den person som är ansvarig för att godkänna produktmodeller för användning i operationer.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="fa1cc-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-123">Click OK.</span></span>
12. <span data-ttu-id="fa1cc-124">Markera ett alternativ i fältet Prissättningsmetod.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="fa1cc-125">Aktivera produktmodellsversionen.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-125">Activate the product model version.</span></span> <span data-ttu-id="fa1cc-126">Det är endast möjligt att ha en aktiv produkt för en produktmodell åt gången.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="fa1cc-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa1cc-127">Close the page.</span></span>

