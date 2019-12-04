---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av plats- och lagerställedata mellan Finance and Operations och Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771008"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="d8270-103">Integrerade platser och lagerställen</span><span class="sxs-lookup"><span data-stu-id="d8270-103">Integrated sites and warehouses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8270-104">I det här avsnittet beskrivs integreringen av plats- och lagerställedata mellan Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d8270-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="d8270-105">Driftplatser och driftlagerställen är vanliga koncept i en Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="d8270-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="d8270-106">De används för att modellera leveranskedjan för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="d8270-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="d8270-107">Mallar</span><span class="sxs-lookup"><span data-stu-id="d8270-107">Templates</span></span>

<span data-ttu-id="d8270-108">Med integrationen med Common Data Service finns dessa begrepp och all tillhörande information i Common Data Service med dataenheterna för platser och lagerställen i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d8270-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="d8270-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="d8270-109">Finance and Operations apps</span></span> | <span data-ttu-id="d8270-110">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="d8270-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="d8270-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d8270-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="d8270-112">Webbplatser</span><span class="sxs-lookup"><span data-stu-id="d8270-112">Sites</span></span> | <span data-ttu-id="d8270-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="d8270-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="d8270-114">Lagerställen</span><span class="sxs-lookup"><span data-stu-id="d8270-114">Warehouses</span></span> | <span data-ttu-id="d8270-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="d8270-115">msdyn_warehouses</span></span> | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

