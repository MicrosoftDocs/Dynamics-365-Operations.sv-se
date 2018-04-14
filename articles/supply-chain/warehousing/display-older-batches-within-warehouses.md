---
title: "Konfigurera visning av äldre batcher inom lagerstället på en mobil enhet"
description: "Det här avsnittet beskriver hur du ställer in en mobil enhet för att visa en lista över platser med batchar som är äldre än den aktuella platsen för en arbetsrad."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4f2dc9221b72600c928db9fd306038725c7af305
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a><span data-ttu-id="54487-103">Konfigurera visning av äldre batcher inom lagerstället på en mobil enhet</span><span class="sxs-lookup"><span data-stu-id="54487-103">Configure Display older batches within warehouse on a mobile device</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="54487-104">Konfigurationen **visning av äldre batcher inom lagerstället på en mobil enhet** låter dig visa en lista över platser med batchar som är äldre än den aktuella platsen för arbetsraden.</span><span class="sxs-lookup"><span data-stu-id="54487-104">The **Display older batches within warehouse** configuration lets you display a list of locations with batches older than the current location of the work line.</span></span> <span data-ttu-id="54487-105">Listan över platser som visas innehåller information om äldre batchar på platsen med utgångsdatum och inventering av varje batch.</span><span class="sxs-lookup"><span data-stu-id="54487-105">The list of locations that are displayed includes information about the older batches in the location with the expiration date and the physical inventory of each batch.</span></span> <span data-ttu-id="54487-106">Du kan välja från en ny plats eller att fortsätta plocka från den aktuella platsen.</span><span class="sxs-lookup"><span data-stu-id="54487-106">You can choose to pick from a new location or to continue picking from the current location.</span></span> 
- <span data-ttu-id="54487-107">Plocka från en ny plats - om du väljer en ny plats att plocka från, kommer den aktuella arbetsraden att uppdateras för att använda den nya platsen och arbete fortsätter som vanligt med den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="54487-107">Pick from a new location - If you select a new location to pick from, the  current work line will be updated to use the new location and work will continue as usual with the new location.</span></span> <span data-ttu-id="54487-108">Det måste ha tillräckligt med tillgänglig kvantitet för hela arbetsraden för att den nya platsen ska gälla.</span><span class="sxs-lookup"><span data-stu-id="54487-108">For the new location to be valid, it must have enough available quantity for the whole work line.</span></span> <span data-ttu-id="54487-109">Om den begärda kvantiteten inte är tillgänglig kommer arbetsraden inte att uppdateras och listan visas.</span><span class="sxs-lookup"><span data-stu-id="54487-109">If the required quantity is not available, the work line will not be updated, and the list will display.</span></span> 
- <span data-ttu-id="54487-110">Fortsätt plocka från den aktuella platsen – om du fortsätter med den aktuella arbetsradplatsen, fortsätter kvantiteterna för arbetsraden att plockas från ursprungsplatsen.</span><span class="sxs-lookup"><span data-stu-id="54487-110">Continue picking from the current location - If you continue with the current work line location, the quantities for the work line will continue to be picked from the original location.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="54487-111">Tillämpning</span><span class="sxs-lookup"><span data-stu-id="54487-111">Where it applies</span></span>
<span data-ttu-id="54487-112">Visning av äldre batcher inom lagerstället konfigureras på en mobil enhets menyalternativ och påverkar plockningen av batchen under artiklar.</span><span class="sxs-lookup"><span data-stu-id="54487-112">Display older batches within warehouse is configured on mobile device menu items and affects the pick for batch below items.</span></span>

## <a name="set-up-display-older-batches-within-warehouse"></a><span data-ttu-id="54487-113">Ställ in visning av äldre batchar i lager</span><span class="sxs-lookup"><span data-stu-id="54487-113">Set up Display older batches within warehouse</span></span>
<span data-ttu-id="54487-114">Konfigurationen **visning av äldre batcher inom lagerstället på en mobil enhet** finns på mobilenhetens menyalternativ när alternativet **plocka äldsta batch** är inställt på **Varna**.</span><span class="sxs-lookup"><span data-stu-id="54487-114">The **Display older batches within warehouse** configuration is available on mobile device menu items when the **Pick oldest batch** option is set to **Warn**.</span></span>

- <span data-ttu-id="54487-115">Under **lagerstyrning** > **inställningar** > **mobiltelefon** > **Menyalternativ på mobil enhet**, ange **använd befintligt arbete** till **Ja** för menyobjekt och välj **Varna** i fältet **plocka äldsta batch**.</span><span class="sxs-lookup"><span data-stu-id="54487-115">Under **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**, set **Use existing work** to **Yes** for the menu item, and select **Warn** in the **Pick oldest batch** field.</span></span> 


