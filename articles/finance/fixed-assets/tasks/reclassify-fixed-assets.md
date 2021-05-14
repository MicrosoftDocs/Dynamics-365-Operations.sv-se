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
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944725"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="a5e95-103">Omklassificera anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a5e95-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a5e95-104">Om du vill omklassificera en anläggningstillgång, måste du överföra den till en ny anläggningstillgångsgrupp eller tilldela ett nytt anläggningstillgångsnummer till den inom samma grupp.</span><span class="sxs-lookup"><span data-stu-id="a5e95-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="a5e95-105">När en anläggningstillgång omklassificeras:</span><span class="sxs-lookup"><span data-stu-id="a5e95-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="a5e95-106">Alla böcker för den befintliga anläggningstillgången skapas för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="a5e95-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="a5e95-107">All information som skapades för den ursprungliga anläggningstillgången kopieras till den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="a5e95-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="a5e95-108">Statusen för den ursprungliga anläggningstillgångens böcker är Stängd.</span><span class="sxs-lookup"><span data-stu-id="a5e95-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="a5e95-109">De nya böckerna för den nya anläggningstillgången innehåller datumet för omklassificeringen i fältet **Anskaffningsdatum**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="a5e95-110">Datumet i fältet **Startdatum för avskrivning** kopieras från den ursprungliga tillgångsinformationen.</span><span class="sxs-lookup"><span data-stu-id="a5e95-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="a5e95-111">Om avskrivningen redan har påbörjats visas datumet för senaste omklassificeringen i fältet **Datum när avskrivning senast kördes**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="a5e95-112">De befintliga anläggningstillgångstransaktionerna för den ursprungliga anläggningstillgången annulleras och regenereras för den nya anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="a5e95-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="a5e95-113">När en tillgång som har en överföringstransaktion har omklassificerats visas ett meddelande i **Åtgärdscentret** som anger att en överföringstransaktion inte slutförs i samband med omklassificeringen.</span><span class="sxs-lookup"><span data-stu-id="a5e95-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="a5e95-114">Det är nödvändigt att slutföra en överföringstransaktion för att flytta de befintliga omklassificeringstransaktionerna till de relevanta ekonomiska dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="a5e95-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="a5e95-115">Under omklassificeringsprocessen kör systemet följande åtgärder för att omklassificera tillgångssaldot från den ursprungliga tillgången till den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="a5e95-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="a5e95-116">Omklassificeringsprocessen kopierar data från den ursprungliga anläggningstillgångsboken till den nya anläggningstillgångsboken.</span><span class="sxs-lookup"><span data-stu-id="a5e95-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="a5e95-117">Omklassificeringstransaktionen använder information från den ursprungliga bokförda anskaffningen som inkluderar information om den ekonomiska dimension som är inkluderad i anskaffningstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="a5e95-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="a5e95-118">Samtidigt återställer omklassificeringsprocessen den ursprungliga anskaffnings- och överföringstransaktionen av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="a5e95-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="a5e95-119">Följande diagram och procedur ger ett exempel på omklassificeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a5e95-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="a5e95-120">[![Diagram som visar omklassificeringsprocessen](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="a5e95-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="a5e95-121">Följ dessa steg för att omklassificera en anläggningstillgång:</span><span class="sxs-lookup"><span data-stu-id="a5e95-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="a5e95-122">Gå till **Anläggningstillgångar > Periodiska uppgifter > Omklassificering**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="a5e95-123">I fältet **Anläggningstillgångsgrupper** väljer du den grupp som du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="a5e95-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="a5e95-124">I fältet **Nummer för anläggningstillgång** väljer du den anläggningstillgång du vill omklassificera.</span><span class="sxs-lookup"><span data-stu-id="a5e95-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="a5e95-125">I fältet **Ny anläggningstillgångsgrupp** väljer du den grupp du vill överföra anläggningstillgången till.</span><span class="sxs-lookup"><span data-stu-id="a5e95-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="a5e95-126">Om den nya anläggningstillgångsgruppen kopplas till en nummerserie, kommer fältet **Nytt anläggningstillgångsnummer** att uppdateras med numret från den nya anläggningstillgångsgruppens nummerserie.</span><span class="sxs-lookup"><span data-stu-id="a5e95-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="a5e95-127">I annat fall uppdateras fältet **Nytt anläggningstillgångsnummer** med numret från den nummerserie som är inställd på sidan **Parametrar för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="a5e95-128">Om ingen nummerserie har angetts på sidan för **Parametrar för anläggningstillgångar**, ange då ett nummer i nummerfältet för **Ny anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="a5e95-129">Ange ett datum i fältet **Omklassificeringsdatum**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="a5e95-130">Ange eller välj ett värde i fältet **Verifikationsserie**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="a5e95-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5e95-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
