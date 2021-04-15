---
title: Skapa och uppdatera ett retur- och återbetalningspolicy för en kanal
description: I det här avsnittet beskrivs hur du ställer in en policy för returer och återbetalningar för en kanal.
author: ShalabhjainMSFT
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: e23291130d55fdfb5c2e2077b78c221866d72c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792085"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="4592a-103">Skapa och uppdatera en retur- och återbetalningspolicy för en kanal</span><span class="sxs-lookup"><span data-stu-id="4592a-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4592a-104">Med hjälp av en returpolicy för en kanal i Dynamics 365 Commerce kan återförsäljare ange vilka betalningsmedel som kan tillåtas att bearbeta en retur i en kassa.</span><span class="sxs-lookup"><span data-stu-id="4592a-104">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="4592a-105">I det här avsnittet beskrivs hur du ställer in en policy för returer och återbetalningar för en kanal.</span><span class="sxs-lookup"><span data-stu-id="4592a-105">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="4592a-106">Omfattningen av policyn är för närvarande begränsad till att ställa in betalningsmedel som kan tillåtas för en kanal.</span><span class="sxs-lookup"><span data-stu-id="4592a-106">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="4592a-107">Listan tillåtna är baserad på de betalsätt som används för att göra inköpet.</span><span class="sxs-lookup"><span data-stu-id="4592a-107">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="4592a-108">Exempel:</span><span class="sxs-lookup"><span data-stu-id="4592a-108">For example:</span></span>

- <span data-ttu-id="4592a-109">Om ett inköp gjorts med hjälp av ett presentkort, är butikens policy att endast bearbeta återbetalningar till ett nytt presentkort eller för att ge butikskredit.</span><span class="sxs-lookup"><span data-stu-id="4592a-109">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="4592a-110">Om en försäljning görs med kontanter är de alternativ som är tillåtna för återbetalning det kontanter, presentkort och kundkonto, men inte kreditkort.</span><span class="sxs-lookup"><span data-stu-id="4592a-110">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="4592a-111">Aktivera returpolicy</span><span class="sxs-lookup"><span data-stu-id="4592a-111">Enable return policy</span></span>

<span data-ttu-id="4592a-112">Aktivera funktionen för att återgå till kanalen genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="4592a-112">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="4592a-113">Gå till arbetsytan **Funktionshantering** i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4592a-113">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="4592a-114">Sök efter funktionen **aktivera kanal returprinciper** i listan med funktionsnamn.</span><span class="sxs-lookup"><span data-stu-id="4592a-114">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="4592a-115">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="4592a-115">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="4592a-116">Konfigurera returpolicy</span><span class="sxs-lookup"><span data-stu-id="4592a-116">Configure return policy</span></span>

<span data-ttu-id="4592a-117">Följ stegen nedan när du vill konfigurera en returpolicy för en butikskanalen eller online butikskanal.</span><span class="sxs-lookup"><span data-stu-id="4592a-117">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="4592a-118">Gå till **Butik och handel** \> **Kanalinstallation** \> **Returer** \> **Returpolicy för kanal**.</span><span class="sxs-lookup"><span data-stu-id="4592a-118">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="4592a-119">Välj **Ny** om du vill skapa en ny returpolicy för butikens öppettider.</span><span class="sxs-lookup"><span data-stu-id="4592a-119">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="4592a-120">Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="4592a-120">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="4592a-121">För nya mallar lägger du till ett namn och en beskrivning som gör det enklare att identifiera principen när den tillämpas på kanalen.</span><span class="sxs-lookup"><span data-stu-id="4592a-121">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="4592a-122">![Lägg till ny returpolicy](media/Return-policy-page1.png "Lägg till ny returpolicy")</span><span class="sxs-lookup"><span data-stu-id="4592a-122">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="4592a-123">I avsnittet **tillåtna betalsätt** för bidrag kan du definiera **tillåtna** returavgifter som är specifika för varje betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="4592a-123">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="4592a-124">![Lägg till betalsätt](media/Return-policy-page2.PNG "Ange tillåtna betalsätt per betalningstyp")</span><span class="sxs-lookup"><span data-stu-id="4592a-124">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="4592a-125">Betalsätten härleds från de betalsätt som har ställts in för organisationen.</span><span class="sxs-lookup"><span data-stu-id="4592a-125">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="4592a-126">Om du lägger till en betalningsmedeltyp som är tillåten för varje listad betalningsmetod kan returer göras av den tillåtna betalningsmedelstypen för retur.</span><span class="sxs-lookup"><span data-stu-id="4592a-126">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="4592a-127">Associera returpolicymallen för öppettider med butikerna där den ska användas.</span><span class="sxs-lookup"><span data-stu-id="4592a-127">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="4592a-128">Välj **Lägg till** på fliken **Butikskanaler** och koppla de tillgängliga kanalerna.</span><span class="sxs-lookup"><span data-stu-id="4592a-128">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="4592a-129">I dialogrutan **Välj organisationsnoder** väljer du butiker, regioner och organisationer som mallen ska associeras med.</span><span class="sxs-lookup"><span data-stu-id="4592a-129">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="4592a-130">Det går bara att associera en returpolicymall till varje butik.</span><span class="sxs-lookup"><span data-stu-id="4592a-130">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="4592a-131">Välj butiker, regioner eller organisationer med pilknapparna.</span><span class="sxs-lookup"><span data-stu-id="4592a-131">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="4592a-132">Giltighetsdatumet för policyn är det datum då policyn tillämpas på kanalerna och kanaljobben körs.</span><span class="sxs-lookup"><span data-stu-id="4592a-132">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="4592a-133">![Dialogrutan Välj organisationsnoder](media/Return-policy-page3.PNG "Dialogrutan Välj organisationsnoder")</span><span class="sxs-lookup"><span data-stu-id="4592a-133">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="4592a-134">På sidan **distributionsschema** kör du jobbet **1070** för att göra returpolicy för kanal tillgänglig för POS.</span><span class="sxs-lookup"><span data-stu-id="4592a-134">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="4592a-135">Förhandsgranska returpolicy för kanal i POS</span><span class="sxs-lookup"><span data-stu-id="4592a-135">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="4592a-136">Följ stegen i något av följande exempel för att visa de tillåtna betalningsmedelstyperna för retur i POS.</span><span class="sxs-lookup"><span data-stu-id="4592a-136">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="4592a-137">Logga in i POS som kassör eller chef.</span><span class="sxs-lookup"><span data-stu-id="4592a-137">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="4592a-138">Under **skift och kassalåda**, välj **visa journal**.</span><span class="sxs-lookup"><span data-stu-id="4592a-138">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="4592a-139">Välj den transaktion som ingår i returen.</span><span class="sxs-lookup"><span data-stu-id="4592a-139">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="4592a-140">Markera artiklarna som ska återbetalas och välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="4592a-140">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="4592a-141">Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="4592a-141">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="4592a-142">Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="4592a-142">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="4592a-143">Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="4592a-143">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="4592a-144">- eller -</span><span class="sxs-lookup"><span data-stu-id="4592a-144">-or-</span></span>

1. <span data-ttu-id="4592a-145">Logga in i POS som kassör eller chef.</span><span class="sxs-lookup"><span data-stu-id="4592a-145">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="4592a-146">Välj **returtransaktion** och ange kvitto-ID:t med en streckkodssökning eller per manuell inmatning.</span><span class="sxs-lookup"><span data-stu-id="4592a-146">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="4592a-147">Välj den transaktion som ingår i returen.</span><span class="sxs-lookup"><span data-stu-id="4592a-147">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="4592a-148">Markera artiklarna som ska återbetalas och välj betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="4592a-148">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="4592a-149">Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="4592a-149">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="4592a-150">Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="4592a-150">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="4592a-151">Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.</span><span class="sxs-lookup"><span data-stu-id="4592a-151">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="4592a-152">![Återbetalning tillåts inte](media/Return-policy-page6.png "Återbetalningstyp tillåts inte")</span><span class="sxs-lookup"><span data-stu-id="4592a-152">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="4592a-153">![Lista över betalsätt](media/Return-policy-page5.PNG "Återbetalningstyp tillåts")</span><span class="sxs-lookup"><span data-stu-id="4592a-153">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
