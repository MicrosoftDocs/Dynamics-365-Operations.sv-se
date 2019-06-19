---
title: Förbättrad hantering av batchspårade artiklar
description: I det här avsnittet beskrivs de förbättringar som gjorts av hanteringen av batchar för batchspårade artiklar under bokföringsprocessen av butiksutdrag.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4456fc3d5bc4547fa8211642b11ca6df455fa187
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617399"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="eab13-103">Förbättrad hantering av batchspårade artiklar</span><span class="sxs-lookup"><span data-stu-id="eab13-103">Improved handling of batch-tracked items</span></span>

<span data-ttu-id="eab13-104">I Microsoft Dynamics 365 for Retail-kassan kan batchnummer inte registreras för batchspårade artiklar vid försäljningstillfället.</span><span class="sxs-lookup"><span data-stu-id="eab13-104">In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="eab13-105">För specifika konfigurationer, när försäljning bokförs vid huvudkontoret genom kundorder- eller utdragsbokföring, förväntar sig Microsoft Dynamics-systemet att det finns giltiga batchnummer för batchspårade artiklar och att de ska användas under faktureringen.</span><span class="sxs-lookup"><span data-stu-id="eab13-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="eab13-106">Om det finns giltiga batchnummer för produkter används de vid faktureringsprocessen för kundorder och försäljningsorder från utdragsbokföringen.</span><span class="sxs-lookup"><span data-stu-id="eab13-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="eab13-107">Annars kan faktureringen av kundorder inte bokföras och kassaanvändaren får ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="eab13-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="eab13-108">Utdragsbokföringen går sedan in i ett feltillstånd.</span><span class="sxs-lookup"><span data-stu-id="eab13-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="eab13-109">Det här feltillståndet inträffar även när ett negativt lager har aktiverats för produkterna.</span><span class="sxs-lookup"><span data-stu-id="eab13-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="eab13-110">När negativt lager har aktiverats för batchspårade artiklar innebär de förbättringar som gjorts i Microsoft Dynamics for Retail version 10.0.4 och senare att faktureringen av kund- och försäljningsorder som görs via utdragsbokföring inte blockeras för dessa artiklar om lagret är 0 (noll) eller om det inte finns något batchnummer.</span><span class="sxs-lookup"><span data-stu-id="eab13-110">Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="eab13-111">Den nya funktionen använder ett standardiserat batch-ID för försäljningsrader när det inte finns batchnummer.</span><span class="sxs-lookup"><span data-stu-id="eab13-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="eab13-112">Du definierar standardvärdet för det batch-ID som används för kundorder i fältet **Standard-batch-ID**, på snabbfliken **Order**, på fliken **Kundorder** på sidan **Butiksparametrar**.</span><span class="sxs-lookup"><span data-stu-id="eab13-112">To define the default batch ID that is used for customer orders, on the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="eab13-113">Du definierar standardvärdet för det batch-ID som används för försäljningsorder via utdragsbokföring i fältet **Standard-batch-ID**, på snabbfliken **Lageruppdatering**, på fliken **Bokföring** på sidan **Butiksparametrar**.</span><span class="sxs-lookup"><span data-stu-id="eab13-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Retail parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="eab13-114">Den här funktionen är bara tillgänglig när avancerad lagerstyrning har aktiverats för det specifika butikslagret och artiklarna.</span><span class="sxs-lookup"><span data-stu-id="eab13-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="eab13-115">I en senare version kommer funktionen också att fungera för tillfällen då avancerad lagerstyrning inte används.</span><span class="sxs-lookup"><span data-stu-id="eab13-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>
