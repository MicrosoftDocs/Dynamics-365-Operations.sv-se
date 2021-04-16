---
title: Avgöra strukturlisteversionen
description: Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4fd5f28d0ee85c267ea6a86a1452fbacc824620
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833627"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="9ec72-103">Avgöra strukturlisteversionen</span><span class="sxs-lookup"><span data-stu-id="9ec72-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ec72-104">Om en artikel har Tillverkning som förvald ordertyp söker planeringsmotorn under en efterfrågenedbrytning efter en giltig strukturlisteversion baserat på siten.</span><span class="sxs-lookup"><span data-stu-id="9ec72-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="9ec72-105">Sitedimensionen är alltid känd och anges på efterfrågetransaktionen.</span><span class="sxs-lookup"><span data-stu-id="9ec72-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="9ec72-106">Följande process fastställer vilken strukturlisteversion att använda:</span><span class="sxs-lookup"><span data-stu-id="9ec72-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="9ec72-107">Om en strukturlisteversion har definierats för artikeln på siten för efterfrågan, används denna sitespecifika strukturlista.</span><span class="sxs-lookup"><span data-stu-id="9ec72-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="9ec72-108">Om ingen strukturlisteversion har definierats för artikeln på siten för efterfrågan, används en allmän strukturlista.</span><span class="sxs-lookup"><span data-stu-id="9ec72-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="9ec72-109">En allmän strukturlista anger inte någon site och den gäller för flera siter.</span><span class="sxs-lookup"><span data-stu-id="9ec72-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="9ec72-110">Om det finns en allmän strukturlista används den.</span><span class="sxs-lookup"><span data-stu-id="9ec72-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="9ec72-111">Om det inte finns någon allmän strukturlisteversion som kan användas, stannar efterfrågenedbrytningen här.</span><span class="sxs-lookup"><span data-stu-id="9ec72-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="9ec72-112">En giltig strukturlisteversion, oavsett om den är sitespecifik eller allmän, måste uppfylla kriterierna för datum och kvantitet.</span><span class="sxs-lookup"><span data-stu-id="9ec72-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]