---
title: Funktionsplatser och tillgångar
description: Det här avsnittet beskriver funktionsplats och tillgångar i tillgångshantering. Tillgångshantering är en avancerad modul för hantering av tillgångar och underhållsjobb i Microsoft Dynamics 365 for Finance and Operations.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783614"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="1b81a-104">Funktionsplatser och tillgångar</span><span class="sxs-lookup"><span data-stu-id="1b81a-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="1b81a-105">Det här avsnittet beskriver funktionsplats och tillgångar i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="1b81a-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="1b81a-106">Tillgångshantering är en avancerad modul för hantering av tillgångar och underhållsjobb i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1b81a-106">Asset Management is an advanced module for managing assets and maintenance jobs in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="overview"></a><span data-ttu-id="1b81a-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="1b81a-107">Overview</span></span>

<span data-ttu-id="1b81a-108">Tillgångshantering integreras sömlöst med flera moduler i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1b81a-108">Asset Management is integrated seamlessly with several modules in Finance and Operations.</span></span> <span data-ttu-id="1b81a-109">Följande illustration visar gränssnitten med andra moduler.</span><span class="sxs-lookup"><span data-stu-id="1b81a-109">The following illustration shows the interfaces with other modules.</span></span>

![Figur 1](media/01-overview-image.png)

<span data-ttu-id="1b81a-111">Med tillgångshantering kan du effektivt hantera och utföra alla uppgifter som är relaterade till hantering och underhåll av många typer av utrustning i företaget.</span><span class="sxs-lookup"><span data-stu-id="1b81a-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="1b81a-112">Denna utrustning omfattar maskiner, produktionsutrustning och fordon.</span><span class="sxs-lookup"><span data-stu-id="1b81a-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="1b81a-113">Tillgångshantering stödjer även lösningar inom många branscher.</span><span class="sxs-lookup"><span data-stu-id="1b81a-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="1b81a-114">Följande illustration visar en översikt över de viktigaste funktionerna som täcks av tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="1b81a-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Figur 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="1b81a-116">Funktionsplatser och tillgångar</span><span class="sxs-lookup"><span data-stu-id="1b81a-116">Functional locations and assets</span></span>

<span data-ttu-id="1b81a-117">Funktionsplatser används för att hantera tillgångar på platser.</span><span class="sxs-lookup"><span data-stu-id="1b81a-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="1b81a-118">I den här hanteringen ingår spårning av tillgångskostnader på funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="1b81a-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="1b81a-119">Funktionsplatser struktureras hierarkiskt och platser kan ha underordnade platser.</span><span class="sxs-lookup"><span data-stu-id="1b81a-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="1b81a-120">Strukturen på funktionsplatser är statisk.</span><span class="sxs-lookup"><span data-stu-id="1b81a-120">The structure of functional locations is static.</span></span> <span data-ttu-id="1b81a-121">Med andra ord kan platser inte ändra plats.</span><span class="sxs-lookup"><span data-stu-id="1b81a-121">In other words, locations can't change place.</span></span> <span data-ttu-id="1b81a-122">Tillgångar kan installeras på funktionsplatser och kan, efter behov, installeras på andra funktionsplatser senare.</span><span class="sxs-lookup"><span data-stu-id="1b81a-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="1b81a-123">Tillgångskostnader följer alltid placeringen av tillgången.</span><span class="sxs-lookup"><span data-stu-id="1b81a-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="1b81a-124">Med andra ord, om du installerar en tillgång på en ny funktionsplats, använder tillgången automatiskt de ekonomiska dimensionerna som är relaterade till den nya funktionsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1b81a-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="1b81a-125">Därför är tillgångskostnader alltid relaterade till den funktionsplats som tillgången är installerad på.</span><span class="sxs-lookup"><span data-stu-id="1b81a-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="1b81a-126">Denna automatiska hantering av ekonomiska dimensioner hjälper till att garantera fullständig spårning av kostnader när ditt företag utför projektstyrning och rapportering på funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="1b81a-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="1b81a-127">Hur du bygger din hierarki av funktionsplatser beror på ditt företags krav på underhåll av intern utrustning eller service av kundutrustning.</span><span class="sxs-lookup"><span data-stu-id="1b81a-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="1b81a-128">Följande bild visar ett exempel på funktionsplatser som är baserade på geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="1b81a-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Figur 3](media/03-overview-image.png)

<span data-ttu-id="1b81a-130">Följande bild visar ett exempel på funktionsplatser som är baserade på kunder.</span><span class="sxs-lookup"><span data-stu-id="1b81a-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Figur 4](media/04-overview-image.png)
