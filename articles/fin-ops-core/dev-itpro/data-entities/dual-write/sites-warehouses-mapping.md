---
title: Integrerade platser och lagerställen
description: I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Dataverse.
author: t-benebo
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 533635ece005636dcee4e24d1d132111e1e2b370
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750676"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="6952c-103">Integrerade platser och lagerställen</span><span class="sxs-lookup"><span data-stu-id="6952c-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="6952c-104">I det här avsnittet beskrivs integreringen av webbplats- och lagerställedata mellan Finance and Operations och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6952c-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="6952c-105">Driftplatser och driftlagerställen är vanliga koncept i en Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="6952c-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="6952c-106">De används för att modellera leveranskedjan för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="6952c-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="6952c-107">Mallar</span><span class="sxs-lookup"><span data-stu-id="6952c-107">Templates</span></span>

<span data-ttu-id="6952c-108">Med integrationen med Dataverse finns dessa begrepp och all tillhörande information i Dataverse med datatabellerna för platser och lagerställen i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6952c-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="6952c-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="6952c-109">Finance and Operations apps</span></span> | <span data-ttu-id="6952c-110">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="6952c-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="6952c-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="6952c-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="6952c-112">Webbplatser</span><span class="sxs-lookup"><span data-stu-id="6952c-112">Sites</span></span> | <span data-ttu-id="6952c-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="6952c-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="6952c-114">Lagerställen</span><span class="sxs-lookup"><span data-stu-id="6952c-114">Warehouses</span></span> | <span data-ttu-id="6952c-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="6952c-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]