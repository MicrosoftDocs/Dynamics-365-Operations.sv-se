---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: d5c2030160f6025c9de63b2c29215364f5f87e6f
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997635"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="4ff43-103">Integrerade platser och lagerställen</span><span class="sxs-lookup"><span data-stu-id="4ff43-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="4ff43-104">I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4ff43-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="4ff43-105">Driftplatser och driftlagerställen är vanliga koncept i en Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="4ff43-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="4ff43-106">De används för att modellera leveranskedjan för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="4ff43-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="4ff43-107">Mallar</span><span class="sxs-lookup"><span data-stu-id="4ff43-107">Templates</span></span>

<span data-ttu-id="4ff43-108">Med integrationen med Common Data Service finns dessa begrepp och all tillhörande information i Common Data Service med dataenheterna för platser och lagerställen i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="4ff43-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="4ff43-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="4ff43-109">Finance and Operations apps</span></span> | <span data-ttu-id="4ff43-110">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="4ff43-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="4ff43-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4ff43-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="4ff43-112">Webbplatser</span><span class="sxs-lookup"><span data-stu-id="4ff43-112">Sites</span></span> | <span data-ttu-id="4ff43-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="4ff43-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="4ff43-114">Lagerställen</span><span class="sxs-lookup"><span data-stu-id="4ff43-114">Warehouses</span></span> | <span data-ttu-id="4ff43-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="4ff43-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

