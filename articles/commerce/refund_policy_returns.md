---
title: Skapa och uppdatera ett retur- och återbetalningspolicy för en kanal
description: I det här avsnittet beskrivs hur du ställer in en policy för returer och återbetalningar för en kanal.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 89e8fe78414e73053317ebe19e3afcc89231d440
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979733"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="0adb1-103">Skapa och uppdatera ett retur- och återbetalningspolicy för en kanal</span><span class="sxs-lookup"><span data-stu-id="0adb1-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="0adb1-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="0adb1-104">Overview</span></span>

<span data-ttu-id="0adb1-105">Med hjälp av en returpolicy för en kanal i Dynamics 365 Commerce kan återförsäljare ange vilka betalningsmedel som kan tillåtas att bearbeta en retur i en kassa.</span><span class="sxs-lookup"><span data-stu-id="0adb1-105">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="0adb1-106">I det här avsnittet beskrivs hur du ställer in en policy för returer och återbetalningar för en kanal.</span><span class="sxs-lookup"><span data-stu-id="0adb1-106">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="0adb1-107">Omfattningen av policyn är för närvarande begränsad till att ställa in betalningsmedel som kan tillåtas för en kanal.</span><span class="sxs-lookup"><span data-stu-id="0adb1-107">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="0adb1-108">Listan tillåtna är baserad på de betalsätt som används för att göra inköpet.</span><span class="sxs-lookup"><span data-stu-id="0adb1-108">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="0adb1-109">Exempel:</span><span class="sxs-lookup"><span data-stu-id="0adb1-109">For example:</span></span>

- <span data-ttu-id="0adb1-110">Om ett inköp gjorts med hjälp av ett presentkort, är butikens policy att endast bearbeta återbetalningar till ett nytt presentkort eller för att ge butikskredit.</span><span class="sxs-lookup"><span data-stu-id="0adb1-110">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="0adb1-111">Om en försäljning görs med kontanter är de alternativ som är tillåtna för återbetalning det kontanter, presentkort och kundkonto, men inte kreditkort.</span><span class="sxs-lookup"><span data-stu-id="0adb1-111">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="0adb1-112">Aktivera returpolicy</span><span class="sxs-lookup"><span data-stu-id="0adb1-112">Enable return policy</span></span>

<span data-ttu-id="0adb1-113">Aktivera funktionen för att återgå till kanalen genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="0adb1-113">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="0adb1-114">Gå till arbetsytan **Funktionshantering** i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0adb1-114">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="0adb1-115">Sök efter funktionen **aktivera kanal returprinciper** i listan med funktionsnamn.</span><span class="sxs-lookup"><span data-stu-id="0adb1-115">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="0adb1-116">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="0adb1-116">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="0adb1-117">Konfigurera returpolicy</span><span class="sxs-lookup"><span data-stu-id="0adb1-117">Configure return policy</span></span>

<span data-ttu-id="0adb1-118">Följ stegen nedan när du vill konfigurera en returpolicy för en butikskanalen eller online butikskanal.</span><span class="sxs-lookup"><span data-stu-id="0adb1-118">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="0adb1-119">Gå till **Butik och handel** \> **Kanalinstallation** \> **Returer** \> **Returpolicy för kanal**.</span><span class="sxs-lookup"><span data-stu-id="0adb1-119">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="0adb1-120">Välj **Ny** om du vill skapa en ny returpolicy för butikens öppettider.</span><span class="sxs-lookup"><span data-stu-id="0adb1-120">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="0adb1-121">Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="0adb1-121">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="0adb1-122">För nya mallar lägger du till ett namn och en beskrivning som gör det enklare att identifiera principen när den tillämpas på kanalen.</span><span class="sxs-lookup"><span data-stu-id="0adb1-122">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="0adb1-123">![Lägg till ny returpolicy](media/Return-policy-page1.png "Lägg till ny returpolicy")</span><span class="sxs-lookup"><span data-stu-id="0adb1-123">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="0adb1-124">I avsnittet **tillåtna betalsätt** för bidrag kan du definiera **tillåtna** returavgifter som är specifika för varje betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="0adb1-124">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="0adb1-125">![Lägg till betalsätt](media/Return-policy-page2.PNG "Ange tillåtna betalsätt per betalningstyp")</span><span class="sxs-lookup"><span data-stu-id="0adb1-125">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="0adb1-126">Betalsätten härleds från de betalsätt som har ställts in för organisationen.</span><span class="sxs-lookup"><span data-stu-id="0adb1-126">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="0adb1-127">Om du lägger till en betalningsmedeltyp som är tillåten för varje listad betalningsmetod kan returer göras av den tillåtna betalningsmedelstypen för retur.</span><span class="sxs-lookup"><span data-stu-id="0adb1-127">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="0adb1-128">Associera returpolicymallen för öppettider med butikerna där den ska användas.</span><span class="sxs-lookup"><span data-stu-id="0adb1-128">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="0adb1-129">Välj **Lägg till** på fliken **Butikskanaler** och koppla de tillgängliga kanalerna.</span><span class="sxs-lookup"><span data-stu-id="0adb1-129">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="0adb1-130">I dialogrutan **Välj organisationsnoder** väljer du butiker, regioner och organisationer som mallen ska associeras med.</span><span class="sxs-lookup"><span data-stu-id="0adb1-130">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="0adb1-131">Det går bara att associera en returpolicymall till varje butik.</span><span class="sxs-lookup"><span data-stu-id="0adb1-131">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="0adb1-132">Välj butiker, regioner eller organisationer med pilknapparna.</span><span class="sxs-lookup"><span data-stu-id="0adb1-132">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="0adb1-133">Giltighetsdatumet för policyn är det datum då policyn tillämpas på kanalerna och kanaljobben körs.</span><span class="sxs-lookup"><span data-stu-id="0adb1-133">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="0adb1-134">![Dialogrutan Välj organisationsnoder](media/Return-policy-page3.PNG "Dialogrutan Välj organisationsnoder")</span><span class="sxs-lookup"><span data-stu-id="0adb1-134">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="0adb1-135">På sidan **distributionsschema** kör du jobbet **1070** för att göra returpolicy för kanal tillgänglig för POS.</span><span class="sxs-lookup"><span data-stu-id="0adb1-135">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="0adb1-136">Förhandsgranska returpolicy för kanal i POS</span><span class="sxs-lookup"><span data-stu-id="0adb1-136">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="0adb1-137">Följ stegen i något av följande exempel för att visa de tillåtna betalningsmedelstyperna för retur i POS.</span><span class="sxs-lookup"><span data-stu-id="0adb1-137">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="0adb1-138">Logga in i POS som kassör eller chef.</span><span class="sxs-lookup"><span data-stu-id="0adb1-138">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="0adb1-139">Under **skift och kassalåda**, välj **visa journal**.</span><span class="sxs-lookup"><span data-stu-id="0adb1-139">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="0adb1-140">Välj den transaktion som ingår i returen.</span><span class="sxs-lookup"><span data-stu-id="0adb1-140">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="0adb1-141">Markera artiklarna som ska återbetalas och välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="0adb1-141">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="0adb1-142">Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="0adb1-142">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="0adb1-143">Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="0adb1-143">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="0adb1-144">Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="0adb1-144">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="0adb1-145">- eller -</span><span class="sxs-lookup"><span data-stu-id="0adb1-145">-or-</span></span>

1. <span data-ttu-id="0adb1-146">Logga in i POS som kassör eller chef.</span><span class="sxs-lookup"><span data-stu-id="0adb1-146">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="0adb1-147">Välj **returtransaktion** och ange kvitto-ID:t med en streckkodssökning eller per manuell inmatning.</span><span class="sxs-lookup"><span data-stu-id="0adb1-147">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="0adb1-148">Välj den transaktion som ingår i returen.</span><span class="sxs-lookup"><span data-stu-id="0adb1-148">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="0adb1-149">Markera artiklarna som ska återbetalas och välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="0adb1-149">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="0adb1-150">Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="0adb1-150">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="0adb1-151">Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="0adb1-151">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="0adb1-152">Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="0adb1-152">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="0adb1-153">![Återbetalning tillåts inte](media/Return-policy-page6.png "Återbetalningstyp tillåts inte")</span><span class="sxs-lookup"><span data-stu-id="0adb1-153">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="0adb1-154">![Lista över betalsätt](media/Return-policy-page5.PNG "Återbetalningstyp tillåts")</span><span class="sxs-lookup"><span data-stu-id="0adb1-154">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>
