---
title: Felsök hierarkier för lagerställebatch och serie reservation
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med reservationshierarkier som använder batch- eller seriedimensioner.
author: perlynne
ms.date: 3/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: a1abb6f8657484d43d434076e5ee38d1c63fe2ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838188"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a><span data-ttu-id="5628b-103">Felsök hierarkier för lagerställebatch och serie reservation</span><span class="sxs-lookup"><span data-stu-id="5628b-103">Troubleshoot warehouse batch and serial reservation hierarchies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5628b-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med reservationshierarkier som använder batch- eller seriedimensioner.</span><span class="sxs-lookup"><span data-stu-id="5628b-104">This topic describes how to fix common issues that you might encounter while you work with reservation hierarchies that use batch or serial dimensions.</span></span>

<span data-ttu-id="5628b-105">För mer information [Flexibel reservationspolicy för dimension på distributionslagernivå](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="5628b-105">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>

<span data-ttu-id="5628b-106">Reservationshierarkin för en artikel anger behovet av lagringsdimensioner som måste uppfyllas för att tilldela en plats till en efterfrågeorder.</span><span class="sxs-lookup"><span data-stu-id="5628b-106">The reservation hierarchy of an item dictates the requirement of storage dimensions that must be fulfilled to assign a location to a demand order.</span></span> <span data-ttu-id="5628b-107">Dessa dimensioner kan beskrivas som *mått över plats* för alla dimensioner som måste uppfyllas innan en plats tilldelas, och *mått under plats*, för dimensioner som kan tilldelas efter att en plats har tilldelats efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="5628b-107">These dimensions can be described as *dimensions above location*, for all the dimensions that must be fulfilled before a location is assigned, and *dimensions below location*, for dimensions that can be allocated after a location has been assigned to the demand order.</span></span> <span data-ttu-id="5628b-108">Dessa bokningshierarkier är också kända som *batch ovan* och *batch under* reservationhierarkier eller *serie ovan* och *serie under* reservationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="5628b-108">These reservation hierarchies are also known as *batch-above* and *batch-below* reservation hierarchies, or *serial-above* and *serial-below* reservation hierarchies.</span></span>

<span data-ttu-id="5628b-109">Lagret kan bara allokeras om det inte finns några luckor i dimensionerna ovanför platsen.</span><span class="sxs-lookup"><span data-stu-id="5628b-109">Inventory can be successfully allocated only if there are no gaps in the dimensions above location.</span></span> <span data-ttu-id="5628b-110">Till exempel *batch-ovan* reservationshierarki, förvänta **Webbplats**, **Lagerställe** och **Batch-nummer** mått som ska specificeras på beställningen.</span><span class="sxs-lookup"><span data-stu-id="5628b-110">For example, in a *batch-above* reservation hierarchy, you expect **Site,** **Warehouse,** and **Batch number** dimensions to be specified on the demand order.</span></span> <span data-ttu-id="5628b-111">Om någon av dessa dimensioner saknas misslyckas allokeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5628b-111">If any of these dimensions are missing, the allocation process will fail.</span></span> <span data-ttu-id="5628b-112">Däremot, i en bokningshierarki *batch under* eller *serie under*, ett batch- eller serienummer kan anges i begäran, men allokeringsprocessen kräver det inte.</span><span class="sxs-lookup"><span data-stu-id="5628b-112">By contrast, in a *batch-below* or *serial-below* reservation hierarchy, a batch or serial number might be specified on the demand order, but the allocation process doesn't require it.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="5628b-113">Följande felmeddelande visas: "För att tilldelas en cykel måste lastlinjer ange dimensionerna ovanför platsen.</span><span class="sxs-lookup"><span data-stu-id="5628b-113">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="5628b-114">För att tilldela dessa dimensioner, reservera och återskapa lastraden".</span><span class="sxs-lookup"><span data-stu-id="5628b-114">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5628b-115">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="5628b-115">Issue description</span></span>

<span data-ttu-id="5628b-116">När du använder ett objekt som har en *batch ovan* bokningshierarki, kommer kommandot **Släppa till distributionslager** på sidan **Workbench för lastplanering** inte att fungera om du försäker släppa en last för en delkvantitet.</span><span class="sxs-lookup"><span data-stu-id="5628b-116">When you use an item that has a *batch-above* reservation hierarchy, the **Release to warehouse** command on the **Load planning workbench** page doesn't work if you try to release a load for a partial quantity.</span></span> <span data-ttu-id="5628b-117">Det här felmeddelandet visas och inget arbete skapas för delkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="5628b-117">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="5628b-118">Men när du använder ett objekt som har ett *batch under* bokningshierarki, kan du frisläppa en last för en delkvantitet från sidan **Workbench för lastplanering**.</span><span class="sxs-lookup"><span data-stu-id="5628b-118">However, when you use an item that has a *batch-below* reservation hierarchy, you can release a load for a partial quantity from the **Load planning workbench** page.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="5628b-119">Problemorsak</span><span class="sxs-lookup"><span data-stu-id="5628b-119">Issue cause</span></span>

<span data-ttu-id="5628b-120">När en dimension ovanför dimensionen **Plats** i reservationshierarkin måste den anges innan den kan frisläppas till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="5628b-120">When a dimension is above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="5628b-121">Delkvantiteter kan inte frisläppas om en eller flera dimensioner ovanför **plats** inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="5628b-121">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a><span data-ttu-id="5628b-122">Prompten för automatisk reservation av ett batchnummer utlöses även om det finns tillgängligt lager.</span><span class="sxs-lookup"><span data-stu-id="5628b-122">The auto-reservation prompt for a batch number is triggered even though there is available inventory.</span></span>

### <a name="issue-description"></a><span data-ttu-id="5628b-123">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="5628b-123">Issue description</span></span>

<span data-ttu-id="5628b-124">När du använder ett objekt som har ett *batch ovan* bokningshierarki i ett lager som inte har aktiverat lagerprocesser och automatisk bokning är aktiverad visas snabbokningsprompten för ett batchnummer även om bara en batch är tillgänglig för plockning.</span><span class="sxs-lookup"><span data-stu-id="5628b-124">When you use an item that has a *batch-above* reservation hierarchy in a warehouse that hasn't enabled warehouse processes, and automatic reservation is enabled, the auto-reservation prompt for a batch number is shown even if only one batch is available for picking.</span></span>

<span data-ttu-id="5628b-125">Om du använder samma artikel på ett lagerställe där lagerställeprocesser har aktiverats visas dock inte prompten för automatisk reservation.</span><span class="sxs-lookup"><span data-stu-id="5628b-125">However, when you use the same item in a warehouse where warehouse processes are enabled, the auto-reservation prompt isn't shown.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="5628b-126">Problemorsak</span><span class="sxs-lookup"><span data-stu-id="5628b-126">Issue cause</span></span>

<span data-ttu-id="5628b-127">Om en reservationshierarki definieras som *batch ovan* eller *serie ovan*, måste referensdimensionen (**batchnummer** eller **serienummer**) måste alltid anges på beställning.</span><span class="sxs-lookup"><span data-stu-id="5628b-127">If a reservation hierarchy is defined as *batch-above* or *serial-above*, the referenced dimension (**Batch number** or **Serial number**) must always be specified on demand orders.</span></span> <span data-ttu-id="5628b-128">Lagerställeprocesser kan eventuellt fylla i informationen om ett enda batch- eller serienummer finns tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="5628b-128">Warehouse processes might be able to complete the information if a single batch or serial number is available.</span></span> <span data-ttu-id="5628b-129">Eftersom lagerstället inte är aktiverat för lagerställeprocesser måste användaren alltid specificera alla dimensioner ovan **Plats**.</span><span class="sxs-lookup"><span data-stu-id="5628b-129">However, because the warehouse isn't enabled for warehouse processes, the user must always specify all the dimensions above **Location**.</span></span>

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a><span data-ttu-id="5628b-130">Artikelplaceringsmallar som har kriteriet om platsbehållning beaktas inte aktuell lagerbehållning för batchaktiverade artiklar.</span><span class="sxs-lookup"><span data-stu-id="5628b-130">Slotting templates that have the Consider on-hand slot criterion don't consider current on-hand inventory for batch-enabled items.</span></span>

<span data-ttu-id="5628b-131">Mer information finns i [Artikelplacering för distributionslager](warehouse-slotting.md).</span><span class="sxs-lookup"><span data-stu-id="5628b-131">For more information, see [Warehouse slotting](warehouse-slotting.md).</span></span>

### <a name="issue-description"></a><span data-ttu-id="5628b-132">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="5628b-132">Issue description</span></span>

<span data-ttu-id="5628b-133">Artikelplaceringsmallar som har kriteriet om *platsbehållning* beaktas inte aktuell lagerbehållning för *batch ovan* artiklar.</span><span class="sxs-lookup"><span data-stu-id="5628b-133">Slotting templates that have the *Consider on-hand* slot criterion don't consider current on-hand inventory for *batch-above* items.</span></span> <span data-ttu-id="5628b-134">De överväger det bara om batchnumret anges på försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="5628b-134">They consider it only if the batch number is specified on the sales order line.</span></span>

<span data-ttu-id="5628b-135">När du använder *batch under*, den aktuella lagerinventeringen betraktas som förväntat.</span><span class="sxs-lookup"><span data-stu-id="5628b-135">However, when you use *batch-below* items, the current on-hand inventory is considered as expected.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="5628b-136">Problemorsak</span><span class="sxs-lookup"><span data-stu-id="5628b-136">Issue cause</span></span>

<span data-ttu-id="5628b-137">Spårmallens rubrik kan definieras för *Beställt*, *Reserverat* eller *Frisläppt* efterfrågestrategi.</span><span class="sxs-lookup"><span data-stu-id="5628b-137">The slotting template header can be defined for the *Ordered,* *Reserved*, or *Released* demand strategy.</span></span> <span data-ttu-id="5628b-138">För strategin *Beställt* efterfrågestrategi, gäller samma reservationshierarki krav som gäller för reservation eller släppning till lagerprocesser.</span><span class="sxs-lookup"><span data-stu-id="5628b-138">For the *Ordered* demand strategy, the same reservation hierarchy requirements apply that apply to reservation or release to warehouse processes.</span></span> <span data-ttu-id="5628b-139">Därför för föremål som har *batch ovan* och *serie under* reservationshierarkier måste batchen eller serienumret anges på efterfrågeordern (försäljning eller överföring).</span><span class="sxs-lookup"><span data-stu-id="5628b-139">Therefore, for items that have *batch-above* and *serial-below* reservation hierarchies, the batch or serial number must be specified on the demand order (sales or transfer).</span></span> <span data-ttu-id="5628b-140">Alternativt kan strategin *Reserverad* efterfrågestrategi kan användas för att välja batch- eller serienummer innan efterfrågan på lagerlocket genereras.</span><span class="sxs-lookup"><span data-stu-id="5628b-140">Alternatively, the *Reserved* demand strategy can be used to select the batch or serial number before the warehouse slotting demand is generated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
