--- 
title: "Omklassificera anläggningstillgångar"
description: "Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp."
author: saraschi2
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fda4d71b050edde2752536985b18ebcad203d078
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="ee3b0-103">Omklassificera anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="ee3b0-103">Reclassify fixed assets</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee3b0-104">Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="ee3b0-105">När en anläggningstillgång omklassificeras:</span><span class="sxs-lookup"><span data-stu-id="ee3b0-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="ee3b0-106">• Alla värdemodeller för den befintliga anläggningstillgången skapas för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-106">• All value models for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="ee3b0-107">All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="ee3b0-108">Statusen för den ursprungliga anläggningstillgångens värdemodell är Stängd.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-108">The status of the value models for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="ee3b0-109">• De nya värdemodellerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet Anskaffningsdatum.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-109">• The new value models of the new fixed asset contain the date of the reclassification in the Acquisition date field.</span></span> <span data-ttu-id="ee3b0-110">Datumet i körfältet Avskrivning kopieras från den ursprungliga tillgångsinformationen.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-110">The date in the Depreciation run date field is copied from the original asset information.</span></span> <span data-ttu-id="ee3b0-111">Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet för senaste avskrivning.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-111">If the depreciation has already started, the Date when depreciation was last run field displays the date of the reclassification.</span></span> 

<span data-ttu-id="ee3b0-112">• De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

1. <span data-ttu-id="ee3b0-113">Gå till Anläggningstillgångar > Periodiska uppgifter > Omklassificering.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-113">Go to Fixed assets > Periodic tasks > Reclassification.</span></span>
2. <span data-ttu-id="ee3b0-114">I fältet Anläggningstillgångsgrupper väljer du den grupp som du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-114">In the Fixed asset group field, selet the group to reclassify.</span></span>
3. <span data-ttu-id="ee3b0-115">I nummerfältet för Anläggningstillgång väljer du den anläggningstillgång du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-115">In the Fixed asset number field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="ee3b0-116">I fältet Ny anläggningstillgångsgrupp väljer du den grupp du vill överföra anläggningstillgången till.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-116">In the New fixed asset group field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="ee3b0-117">Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet Nytt anläggningstillgångsnummer att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-117">If the new fixed asset group is attached to a number sequence, the New fixed asset number field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="ee3b0-118">I annat fall uppdateras fältet Nytt anläggningstillgångsnummer med numret från den nummerserie som är inställd på sidan Parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-118">Otherwise, the New fixed asset number field is updated with the number from the number sequence that is set up in the Fixed asset parameters page.</span></span> <span data-ttu-id="ee3b0-119">Om ingen nummerserie har angetts på sidan för Parametrar för anläggningstillgångar, ange då ett nummer i nummerfältet för Ny anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-119">If a number sequence is not set up in the Fixed asset parameters page, enter a number in the New fixed asset number field.</span></span>  
5. <span data-ttu-id="ee3b0-120">Ange ett datum i fältet Omklassificeringsdatum.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-120">In the Reclassification date field, enter a date.</span></span>
6. <span data-ttu-id="ee3b0-121">Ange eller välj ett värde i fältet Voucher series.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-121">In the Voucher series field, enter or select a value.</span></span>
7. <span data-ttu-id="ee3b0-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ee3b0-122">Click OK.</span></span>

