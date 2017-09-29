---
title: "Uppdatering av standardkostnader i en icke-tillverkningsmiljö"
description: "Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en icke-tillverkningsmiljö."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b428af5a694668ac161a7187d5a949f44e8ec2a2
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="59af8-103">Uppdatering av standardkostnader i en icke-tillverkningsmiljö</span><span class="sxs-lookup"><span data-stu-id="59af8-103">Update standard costs in a non-manufacturing environment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="59af8-104">Det här avsnittet ger vägledning om hur du uppdaterar standardkostnader i en icke-tillverkningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="59af8-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="59af8-105">I följande riktlinjer förutsätts det att du bara använder tvåversionssättet när du vill uppdatera standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="59af8-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="59af8-106">I den här metoden, en kostnadsredovisningsversion innehåller standardkostnader som ursprungligen angetts för den frysta perioden, och den andra kostnadsredovisningsversion innehåller de inkrementella uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="59af8-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="59af8-107">Varje uppdatering anges som en kostnadspost som bifogas i den andra kostnadsredovisningsversionen och slutligen har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="59af8-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="59af8-108">Ett alternativ, enversionssättet, använder standardkostnadsuppsättningen som ursprungligen angetts.</span><span class="sxs-lookup"><span data-stu-id="59af8-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="59af8-109">Tvåversionssättet innebär att du definierar en andra kostnadsredovisningsversion.</span><span class="sxs-lookup"><span data-stu-id="59af8-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="59af8-110">Här följer riktlinjerna om hur du definierar denna kostnadsredovisningsversion:</span><span class="sxs-lookup"><span data-stu-id="59af8-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="59af8-111">Tilldela en kostnadskalkyleringstyp för **Standardkostnader**.</span><span class="sxs-lookup"><span data-stu-id="59af8-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="59af8-112">Tilldela ett meningsfullt ID som anger innehållet för kostnadsredovisningsversionen, till exempel **2016-UPPDATERINGAR**.</span><span class="sxs-lookup"><span data-stu-id="59af8-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="59af8-113">Kontrollera att innehållet inkluderar kostnadsposter.</span><span class="sxs-lookup"><span data-stu-id="59af8-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="59af8-114">Tillåt att kostnadsposter anges för alla platser.</span><span class="sxs-lookup"><span data-stu-id="59af8-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="59af8-115">Om du anger en plats, kan kostnadsposter anges endast för den platsen.</span><span class="sxs-lookup"><span data-stu-id="59af8-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="59af8-116">Ange reservprincipen **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="59af8-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="59af8-117">Reservprincipen gäller endast för kostnadsberäkningar av tillverkade artiklar.</span><span class="sxs-lookup"><span data-stu-id="59af8-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="59af8-118">Utför följande steg om du vill korrigera, justera eller uppdatera standardkostnader för nya artiklar:</span><span class="sxs-lookup"><span data-stu-id="59af8-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="59af8-119">Använd **Kostnadsredovisningsversion** **inställningar**-sidan för att möjliggöra att kostnadsdata kan anges i den andra kostnadsredovisningsversionen.</span><span class="sxs-lookup"><span data-stu-id="59af8-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="59af8-120">Du kan även välja att förhindra att pågående kostnader aktiveras, så att aktiveringen tillåts när de pågående kostnaderna har definierats fullständigt och korrekt.</span><span class="sxs-lookup"><span data-stu-id="59af8-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="59af8-121">Du kan också kan ange ett datum i **Från datum**-fältet.</span><span class="sxs-lookup"><span data-stu-id="59af8-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="59af8-122">Som en allmän riktlinje bör du använda det datum då du tänker aktivera de stegvisa uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="59af8-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="59af8-123">Du kan även lämna fältet **Från datum** tomt för kostnadsredovisningsversionen och sedan ange ett datum i fältet **Från datum** för varje kostnadspost.</span><span class="sxs-lookup"><span data-stu-id="59af8-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="59af8-124">Använd **Artikelpris**-sidan för att ange uppdateringar som artikelkostnadsposter som bifogas i den andra kostnadsredovisningsversionen.</span><span class="sxs-lookup"><span data-stu-id="59af8-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="59af8-125">Använd **Artikelpriser**-rapporten för att kontrollera att de artikelkostnadsposter som bifogas i den andra kostnadsredovisningsversionen är slutförda och korrekta.</span><span class="sxs-lookup"><span data-stu-id="59af8-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="59af8-126">Använd **Underhåll av kostnadsredovisningsversion**-sidan för att ändra spärrflaggan för att tillåta aktivering av de väntande kostnadsposter som bifogas i den andra kostnadsredovisningsversionen.</span><span class="sxs-lookup"><span data-stu-id="59af8-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="59af8-127">Använd **Aktivera priser**-sidan (som du öppnar från sidan **Underhåll av kostnadsredovisningsversion**) för att aktivera alla väntande artikelkostnadsposter som bifogas i den andra kostnadsredovisningsversionen.</span><span class="sxs-lookup"><span data-stu-id="59af8-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="59af8-128">Du kan även aktivera de väntande kostnadsposterna för enskilda artiklar genom att klicka på knappen **Aktivera väntande pris** på sidan **Artikelpris**.</span><span class="sxs-lookup"><span data-stu-id="59af8-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="59af8-129">För att förhindra ytterligare dataunderhåll, använd **Inställningar för kostnadsredovisningsversion**-sidan för att ändra spärrflaggorna som bifogas i den andra kostnadsredovisningsversionen.</span><span class="sxs-lookup"><span data-stu-id="59af8-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="59af8-130">Spärrprinciperna förhindrar registrering av nya pågående kostnader samt aktivering av pågående kostnader.</span><span class="sxs-lookup"><span data-stu-id="59af8-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>





