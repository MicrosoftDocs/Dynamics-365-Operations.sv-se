---
title: " Konfigurera maskininlärningsdrivna produktrekommendationer"
description: I den här proceduren uppdateras datan i enhetsbutiken som används av maskininlärningssystemet som driver produktrekommendationerna, och sedan aktiveras produktrekommendationer på kassaklienter.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BIMeasurementDeployManagementEntityStore, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 700af913f18e23c66db53a92033def06818af1ec
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "348536"
---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="3d750-103"> Konfigurera maskininlärningsdrivna produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="3d750-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3d750-104">I den här proceduren uppdateras datan i enhetsbutiken som används av maskininlärningssystemet som driver produktrekommendationerna, och sedan aktiveras produktrekommendationer på kassaklienter.</span><span class="sxs-lookup"><span data-stu-id="3d750-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="3d750-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="3d750-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="3d750-106">Gå till System administration > Inställningar > Entity Store.</span><span class="sxs-lookup"><span data-stu-id="3d750-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="3d750-107">Välj posten "RetailSales" i listan.</span><span class="sxs-lookup"><span data-stu-id="3d750-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="3d750-108">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="3d750-108">Click Refresh.</span></span>
4. <span data-ttu-id="3d750-109">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3d750-109">Click OK.</span></span>
5. <span data-ttu-id="3d750-110">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3d750-110">Close the page.</span></span>
6. <span data-ttu-id="3d750-111">Gå till Butik och handel > Administrationsinställning > Parametrar > Butiksparametrar.</span><span class="sxs-lookup"><span data-stu-id="3d750-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="3d750-112">Klicka på fliken Machine learning.</span><span class="sxs-lookup"><span data-stu-id="3d750-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="3d750-113">Välj "Yes" i fältet "Enable product recommendations".</span><span class="sxs-lookup"><span data-stu-id="3d750-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="3d750-114">Om du får meddelandet "The recommendation models couldn't be retrieved" sker detta eftersom du nyligen uppdaterade enhetsbutiken och systemet kanske ännu inte har slutat assimilera den nya datan.</span><span class="sxs-lookup"><span data-stu-id="3d750-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="3d750-115">Vänta i 2-3 timmar och försök igen.</span><span class="sxs-lookup"><span data-stu-id="3d750-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="3d750-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="3d750-116">Click Save.</span></span>
10. <span data-ttu-id="3d750-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3d750-117">Close the page.</span></span>

