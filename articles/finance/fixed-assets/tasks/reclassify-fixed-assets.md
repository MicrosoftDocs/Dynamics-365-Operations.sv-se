---
title: Omklassificera anläggningstillgångar
description: Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8935213c4629de408a48df5e54a2122324e1b3e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823942"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="f7739-103">Omklassificera anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="f7739-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7739-104">Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.</span><span class="sxs-lookup"><span data-stu-id="f7739-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="f7739-105">När en anläggningstillgång omklassificeras:</span><span class="sxs-lookup"><span data-stu-id="f7739-105">When a fixed asset is reclassified:</span></span>

* <span data-ttu-id="f7739-106">Alla böcker för den befintliga anläggningstillgången skapas för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="f7739-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="f7739-107">All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="f7739-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="f7739-108">Statusen för den ursprungliga anläggningstillgångens böcker är Stängd.</span><span class="sxs-lookup"><span data-stu-id="f7739-108">The status of the books for the original fixed asset is Closed.</span></span> 

* <span data-ttu-id="f7739-109">De nya böckerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet **Anskaffningsdatum**.</span><span class="sxs-lookup"><span data-stu-id="f7739-109">The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="f7739-110">Datumet i fältet **Startdatum för avskrivning** kopieras från den ursprungliga tillgångsinformationen.</span><span class="sxs-lookup"><span data-stu-id="f7739-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="f7739-111">Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet **Datum när avskrivning senast kördes**.</span><span class="sxs-lookup"><span data-stu-id="f7739-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

* <span data-ttu-id="f7739-112">De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="f7739-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="f7739-113">Följ dessa steg för att omklassificera en anläggningstillgång:</span><span class="sxs-lookup"><span data-stu-id="f7739-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="f7739-114">Gå till **Anläggningstillgångar > Periodiska uppgifter > Omklassificering**.</span><span class="sxs-lookup"><span data-stu-id="f7739-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="f7739-115">I fältet **Anläggningstillgångsgrupper** väljer du den grupp som du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="f7739-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="f7739-116">I fältet **Nummer för anläggningstillgång** väljer du den anläggningstillgång du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="f7739-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="f7739-117">I fältet **Ny anläggningstillgångsgrupp** väljer du den grupp du vill överföra anläggningstillgången till.</span><span class="sxs-lookup"><span data-stu-id="f7739-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="f7739-118">Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet **Nytt anläggningstillgångsnummer** att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie.</span><span class="sxs-lookup"><span data-stu-id="f7739-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="f7739-119">I annat fall uppdateras fältet **Nytt anläggningstillgångsnummer** med numret från den nummerserie som är inställd på sidan **Parametrar för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="f7739-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="f7739-120">Om ingen nummerserie har angetts på sidan för **Parametrar för anläggningstillgångar**, ange då ett nummer i nummerfältet för **Ny anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="f7739-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="f7739-121">Ange ett datum i fältet **Omklassificeringsdatum**.</span><span class="sxs-lookup"><span data-stu-id="f7739-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="f7739-122">Ange eller välj ett värde i fältet **Verifikationsserie**.</span><span class="sxs-lookup"><span data-stu-id="f7739-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="f7739-123">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7739-123">Click **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]