---
title: Anslut ett experiment och redigera varianter
description: I det här avsnittet beskrivs hur du ansluter ett experiment till en tredjepartstjänst till Dynamics 365 Commerce och hur du redigerar varianter för experimentet.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4c9c9463162f21cdaf40f1c4ed6d5ae51e97cb88
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799095"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="af6dc-103">Anslut ett experiment och redigera varianter</span><span class="sxs-lookup"><span data-stu-id="af6dc-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="af6dc-104">I det här avsnittet beskrivs hur du ansluter ditt experiment i Commerce och ändrar varianterna så att de överensstämmer med din hypotes.</span><span class="sxs-lookup"><span data-stu-id="af6dc-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so that they align with your hypothesis.</span></span> 

<span data-ttu-id="af6dc-105">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="af6dc-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="af6dc-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="af6dc-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="af6dc-107">[ ![Experimentets användarresa – anslut och redigera](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="af6dc-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="af6dc-108">När du har [ställt in experimentet](experimentation-setup.md) i en tjänst från tredje part, ska du ansluta experimentet i Dynamics 365 Commerce och redigera experimentets varianter.</span><span class="sxs-lookup"><span data-stu-id="af6dc-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="af6dc-109">Att tänka på vid planering</span><span class="sxs-lookup"><span data-stu-id="af6dc-109">Planning considerations</span></span>

<span data-ttu-id="af6dc-110">Innan du kopplar ditt experiment i Commerce måste du fatta vissa beslut som påverkar hur ditt innehåll hanteras i Commerce.</span><span class="sxs-lookup"><span data-stu-id="af6dc-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="af6dc-111">Bestäm räckvidden för ditt experiment</span><span class="sxs-lookup"><span data-stu-id="af6dc-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="af6dc-112">När du ansluter ett experiment uppmanas du att definiera testets omfång.</span><span class="sxs-lookup"><span data-stu-id="af6dc-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="af6dc-113">Experiment definieras som **del** omfattning eller **hel** omfattning.</span><span class="sxs-lookup"><span data-stu-id="af6dc-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="af6dc-114">Välj **del** om du vill göra ett experiment på en viss del av sidan.</span><span class="sxs-lookup"><span data-stu-id="af6dc-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="af6dc-115">Om du väljer det här alternativet måste du identifiera vilka moduler som ingår i experimentet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="af6dc-116">Ändringar som görs av delar av standardsidan eller fragment som inte är relaterade till experimentet synkroniseras automatiskt över varianter.</span><span class="sxs-lookup"><span data-stu-id="af6dc-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="af6dc-117">Välj **hel** om du vill göra ett experiment med en hel sida eller ett fragment.</span><span class="sxs-lookup"><span data-stu-id="af6dc-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="af6dc-118">Separata kopior av standardsidan eller fragmentet skapas.</span><span class="sxs-lookup"><span data-stu-id="af6dc-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="af6dc-119">Du behöver inte välja vilka moduler som ska ingå i experimentet, eftersom hela redigeringsytan kan ändras.</span><span class="sxs-lookup"><span data-stu-id="af6dc-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="af6dc-120">Du kan lägga till, ta bort och ändra ordning på modulerna efter behov.</span><span class="sxs-lookup"><span data-stu-id="af6dc-120">You can add, delete, or re-order modules as needed.</span></span> <span data-ttu-id="af6dc-121">Men om ändringar görs på den standard sida eller det fragment som experimentet associeras med, måste dessa ändringar synkroniseras manuellt över alla varianter.</span><span class="sxs-lookup"><span data-stu-id="af6dc-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="af6dc-122">Om du associerar experimentet med en sida som använder en layout, kan du bara omfatta experimentet med **hel**.</span><span class="sxs-lookup"><span data-stu-id="af6dc-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="af6dc-123">Bestäm om du vill schemalägga när experimentet publiceras</span><span class="sxs-lookup"><span data-stu-id="af6dc-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="af6dc-124">Om du vill schemalägga när experimentet publiceras på din aktiva webbplats, kontrollerar du att det innehåll du vill associera med experimentet finns tillgängligt i en publiceringsgrupp *innan* du ansluter experimentet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="af6dc-125">Mer information om publiceringsgrupper finns i [arbeta med publiceringsgrupper](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="af6dc-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="af6dc-126">Anslut ditt experiment</span><span class="sxs-lookup"><span data-stu-id="af6dc-126">Connect your experiment</span></span>
<span data-ttu-id="af6dc-127">Om du vill ansluta ditt experiment startar du guiden **Ansluta experiment**.</span><span class="sxs-lookup"><span data-stu-id="af6dc-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="af6dc-128">Guiden vägleder dig genom de steg som krävs för att ansluta experimentet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="af6dc-129">När du slutför guiden är experimentet anslutet och varianter skapas och kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="af6dc-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

<span data-ttu-id="af6dc-130">För att komma igång med att ansluta ditt experiment i Commerce webbplatsskaparen, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="af6dc-130">To get started connecting your experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="af6dc-131">Starta guiden **Anslutningsförsök** genom att välja **Experiment** i det vänstra navigeringsfönstret och sedan välja **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="af6dc-131">To launch the **Connect experiment** wizard, select **Experiments** in the left navigation pane, and then select **Connect**.</span></span> <span data-ttu-id="af6dc-132">Du kan också öppna guiden från en sida eller ett fragmentredigerare genom att redigera den och välja **Anslut experiment** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-132">Alternatively, you can access the wizard from a page or fragment editor by editing it and selecting **Connect experiment** on the command bar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="af6dc-133">En sida kan bara kopplas till ett experiment åt gången.</span><span class="sxs-lookup"><span data-stu-id="af6dc-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="af6dc-134">Om du vill ansluta en sida till ett annat experiment tar du först bort experimentet som sidan är ansluten till för tillfället.</span><span class="sxs-lookup"><span data-stu-id="af6dc-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="af6dc-135">Välj sidan eller fragmentet som du vill köra ditt experiment på.</span><span class="sxs-lookup"><span data-stu-id="af6dc-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="af6dc-136">Ange att experimentets omfattning till **del** eller **hel**, baserat på det val du gjorde i avsnittet [avgör omfattningen av experiment](#determine-the-scope-of-your-experiment) ovan.</span><span class="sxs-lookup"><span data-stu-id="af6dc-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="af6dc-137">Funktionen **Experiment på sidor eller fragment** måste vara aktiverat om du vill experimentera på hela sidan eller avsnittet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="af6dc-138">Se ämnet [Experimentera i Dynamics 365 Commerce](experimentation-overview.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="af6dc-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="af6dc-139">I det sista steget, välj **Skapa varianter och avsluta guiden**.</span><span class="sxs-lookup"><span data-stu-id="af6dc-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="af6dc-140">varianter skapas för experimentet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="af6dc-141">Redigera dina varianter</span><span class="sxs-lookup"><span data-stu-id="af6dc-141">Edit your variations</span></span>
<span data-ttu-id="af6dc-142">När du avslutar guiden skapas varianter åt dig.</span><span class="sxs-lookup"><span data-stu-id="af6dc-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="af6dc-143">Därefter ska du redigera varianterna så att de återspeglar de val du behöver kontrollera i experimentet.</span><span class="sxs-lookup"><span data-stu-id="af6dc-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="af6dc-144">Välj en av följande procedurer som motsvarar den omfattning du väljer för experimentet i avsnittet [avgöra omfattningen av experimentet](#determine-the-scope-of-your-experiment) ovan.</span><span class="sxs-lookup"><span data-stu-id="af6dc-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="af6dc-145">Redigera varianter för experiment med delomfattning</span><span class="sxs-lookup"><span data-stu-id="af6dc-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="af6dc-146">Följ dessa steg om du har definierat omfattningen av experimentet som ett **del** i avsnittet **Anslut experiment**.</span><span class="sxs-lookup"><span data-stu-id="af6dc-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="af6dc-147">Använd den nedrullningsbara menyn för varianter under kommandofältet för att redigera varje variant baserat på den ursprungliga hypotesen.</span><span class="sxs-lookup"><span data-stu-id="af6dc-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="af6dc-148">Du kanske också vill fastställa en kontroll eller en basvariant genom att lämna någon av varianterna oförändrad.</span><span class="sxs-lookup"><span data-stu-id="af6dc-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="af6dc-149">Välj vilken modul som ska experimenteras, välj tre punkter (...) och välj sedan **Lägg till i experimentet**.</span><span class="sxs-lookup"><span data-stu-id="af6dc-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="af6dc-150">Redigera varianter för experiment med hel omfattning</span><span class="sxs-lookup"><span data-stu-id="af6dc-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="af6dc-151">Om du har definierat omfattningen av experimentet som **hel** i guiden **Anslut experiment**, i redigeringsvy, använder du den nedrullningsbara menyn för varianter under kommandofältet för att redigera varje variant utifrån den ursprungliga hypotesen.</span><span class="sxs-lookup"><span data-stu-id="af6dc-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="af6dc-152">Du kanske också vill fastställa en kontroll eller en basvariant genom att lämna någon av varianterna oförändrad.</span><span class="sxs-lookup"><span data-stu-id="af6dc-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="af6dc-153">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="af6dc-153">Previous step</span></span>
[<span data-ttu-id="af6dc-154">Konfigurera ett experiment</span><span class="sxs-lookup"><span data-stu-id="af6dc-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="af6dc-155">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="af6dc-155">Next step</span></span>
[<span data-ttu-id="af6dc-156">Förhandsgranska och publicera ett experiment</span><span class="sxs-lookup"><span data-stu-id="af6dc-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]