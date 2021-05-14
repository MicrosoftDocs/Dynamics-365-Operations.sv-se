---
title: Godkänn en produktkonfigurationsmodell
description: När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920517"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="46631-103">Godkänn en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="46631-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46631-104">När du kör den här proceduren krävs det att det finns minst en modell för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="46631-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="46631-105">I proceduren används högtalarmodellen i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="46631-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="46631-106">Observera att den modellen redan har godkänts, men proceduren går igenom hela processen.</span><span class="sxs-lookup"><span data-stu-id="46631-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="46631-107">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="46631-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="46631-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="46631-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="46631-109">Välj högtalarmodellen till den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="46631-109">Select the High end speaker model for this procedure.</span></span>  
1. <span data-ttu-id="46631-110">Välj **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="46631-110">Select **Versions**.</span></span>
1. <span data-ttu-id="46631-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="46631-111">Select **New**.</span></span>
1. <span data-ttu-id="46631-112">I fältet **Produktnumme** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="46631-112">In the **Product number** field, enter or select a value.</span></span>
    * <span data-ttu-id="46631-113">Referensen till en produkt representerar en version av produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="46631-113">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="46631-114">Endast produktmallar som har begränsningsbaserad konfiguration visas i listan.</span><span class="sxs-lookup"><span data-stu-id="46631-114">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
1. <span data-ttu-id="46631-115">I fältet **Från datum** anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="46631-115">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="46631-116">Välj när produktmodellsversionen ska vara tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="46631-116">Select when the product model version will be available.</span></span>  
1. <span data-ttu-id="46631-117">I fältet **Till-datum**, anger du ett datum.</span><span class="sxs-lookup"><span data-stu-id="46631-117">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="46631-118">Välj ett slutdatum när produktmodellsversion ska upphöra, eller markerar Aldrig.</span><span class="sxs-lookup"><span data-stu-id="46631-118">Select an end date when this product model version will expire, or select Never.</span></span>  
1. <span data-ttu-id="46631-119">Klicka på **Godkänn** för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="46631-119">Select **Approve** to open the drop dialog.</span></span>
1. <span data-ttu-id="46631-120">I fältet **Godkändes av** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="46631-120">In the **Approved by** field, enter or select a value.</span></span>
    * <span data-ttu-id="46631-121">Välj den person som är ansvarig för att godkänna produktmodeller för användning i operationer.</span><span class="sxs-lookup"><span data-stu-id="46631-121">Select the person who is responsible for approving product models for use in operations.</span></span>  
1. <span data-ttu-id="46631-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="46631-122">Select **OK**.</span></span>
1. <span data-ttu-id="46631-123">Ange ett alternativ i fältet **Prissättningsmetod**.</span><span class="sxs-lookup"><span data-stu-id="46631-123">In the **Pricing method** field, select an option.</span></span>
    * <span data-ttu-id="46631-124">Aktivera produktmodellsversionen.</span><span class="sxs-lookup"><span data-stu-id="46631-124">Activate the product model version.</span></span> <span data-ttu-id="46631-125">Det är endast möjligt att ha en aktiv produkt för en produktmodell åt gången.</span><span class="sxs-lookup"><span data-stu-id="46631-125">It is only possible to have one product active for one product model at a time.</span></span>  
1. <span data-ttu-id="46631-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46631-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]