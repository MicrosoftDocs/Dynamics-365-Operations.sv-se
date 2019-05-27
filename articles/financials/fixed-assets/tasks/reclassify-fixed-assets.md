---
title: Omklassificera anläggningstillgångar
description: Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df4a2fa3c1a38519da83391bcf1c4aa38b6504ff
ms.sourcegitcommit: 6890b5a372a18e11354003098a512685e339ddb0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2019
ms.locfileid: "1541207"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="327ed-103">Omklassificera anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="327ed-103">Reclassify fixed assets</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="327ed-104">Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.</span><span class="sxs-lookup"><span data-stu-id="327ed-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="327ed-105">När en anläggningstillgång omklassificeras:</span><span class="sxs-lookup"><span data-stu-id="327ed-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="327ed-106">• Alla böcker för den befintliga anläggningstillgången skapas för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="327ed-106">• All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="327ed-107">All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="327ed-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="327ed-108">Statusen för den ursprungliga anläggningstillgångens böcker är Stängd.</span><span class="sxs-lookup"><span data-stu-id="327ed-108">The status of the books for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="327ed-109">• De nya böckerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet **Anskaffningsdatum**.</span><span class="sxs-lookup"><span data-stu-id="327ed-109">• The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="327ed-110">Datumet i fältet **Startdatum för avskrivning** kopieras från den ursprungliga tillgångsinformationen.</span><span class="sxs-lookup"><span data-stu-id="327ed-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="327ed-111">Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet **Datum när avskrivning senast kördes**.</span><span class="sxs-lookup"><span data-stu-id="327ed-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

<span data-ttu-id="327ed-112">• De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="327ed-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="327ed-113">Följ dessa steg för att omklassificera en anläggningstillgång:</span><span class="sxs-lookup"><span data-stu-id="327ed-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="327ed-114">Gå till **Anläggningstillgångar > Periodiska uppgifter > Omklassificering**.</span><span class="sxs-lookup"><span data-stu-id="327ed-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="327ed-115">I fältet **Anläggningstillgångsgrupper** väljer du den grupp som du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="327ed-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="327ed-116">I fältet **Nummer för anläggningstillgång** väljer du den anläggningstillgång du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="327ed-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="327ed-117">I fältet **Ny anläggningstillgångsgrupp** väljer du den grupp du vill överföra anläggningstillgången till.</span><span class="sxs-lookup"><span data-stu-id="327ed-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="327ed-118">Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet **Nytt anläggningstillgångsnummer** att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie.</span><span class="sxs-lookup"><span data-stu-id="327ed-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="327ed-119">I annat fall uppdateras fältet **Nytt anläggningstillgångsnummer** med numret från den nummerserie som är inställd på sidan **Parametrar för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="327ed-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="327ed-120">Om ingen nummerserie har angetts på sidan för **Parametrar för anläggningstillgångar**, ange då ett nummer i nummerfältet för **Ny anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="327ed-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="327ed-121">Ange ett datum i fältet **Omklassificeringsdatum**.</span><span class="sxs-lookup"><span data-stu-id="327ed-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="327ed-122">Ange eller välj ett värde i fältet **Verifikationsserie**.</span><span class="sxs-lookup"><span data-stu-id="327ed-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="327ed-123">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="327ed-123">Click **OK**.</span></span>
