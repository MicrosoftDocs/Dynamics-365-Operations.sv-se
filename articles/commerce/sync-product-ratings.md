---
title: Synkronisera produktklassificeringar i Dynamics 365 Commerce
description: I det här avsnittet beskrivs hur du synkroniserar produktvärderingar i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: '---'
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6757a5a13d16c490dced7118c1da8aa0ea6d8994
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029496"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a><span data-ttu-id="67d1a-103">Synkronisera produktklassificeringar i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="67d1a-103">Sync product ratings in Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="67d1a-104">I det här avsnittet beskrivs hur du synkroniserar produktvärderingar i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="67d1a-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="67d1a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="67d1a-105">Overview</span></span>

<span data-ttu-id="67d1a-106">Om du vill använda produktvärderingar i flera kanaler, t.ex vid kassan (POS) och i kundtjänst, måste produktvärderingar från tjänsten omdömen och recensioner importeras till databas för handelskanal.</span><span class="sxs-lookup"><span data-stu-id="67d1a-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Commerce channel database.</span></span> <span data-ttu-id="67d1a-107">När produktvärderingar görs tillgängliga i flera kanaler kan de hjälpa kunderna indirekt under sina interaktioner med säljare.</span><span class="sxs-lookup"><span data-stu-id="67d1a-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="67d1a-108">Detta avsnitt beskriver följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="67d1a-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="67d1a-109">Konfigurera **synkroniseringsjobb för produktklassificering** som ett batchjobb för att synkronisera produktklassificeringar från **tjänsten omdömen och recensioner**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-109">Configure **Product ratings sync job** as a batch job to synchronize product ratings from the **Ratings and Reviews service**.</span></span>
1. <span data-ttu-id="67d1a-110">Kontrollera att batchjobbet för synkronisering av produktvärderingar har slutförts.</span><span class="sxs-lookup"><span data-stu-id="67d1a-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="67d1a-111">Göra produkt produktvärderingar tillgängliga i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a><span data-ttu-id="67d1a-112">Konfigurera ett batchjobb för att synkronisera produktvärderingar</span><span class="sxs-lookup"><span data-stu-id="67d1a-112">Configure a batch job to synchronize product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67d1a-113">Innan du börjar ska du kontrollera att version 10.0.6 eller senare av Dynamics 365 Commerce är installerad.</span><span class="sxs-lookup"><span data-stu-id="67d1a-113">Before you start, make sure that version 10.0.6 or later of Dynamics 365 Commerce is installed.</span></span>

### <a name="initialize-the-commerce-scheduler"></a><span data-ttu-id="67d1a-114">Initiera schemaläggare för handel</span><span class="sxs-lookup"><span data-stu-id="67d1a-114">Initialize the commerce scheduler</span></span>

<span data-ttu-id="67d1a-115">För att initiera schemaläggare för handel, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="67d1a-115">To initialize the commerce scheduler, follow these steps.</span></span>

1. <span data-ttu-id="67d1a-116">Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Initiiera schemaläggare för handel**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-116">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Initialize commerce scheduler**.</span></span> <span data-ttu-id="67d1a-117">Du kan också söka efter "initiera schemaläggare för handel".</span><span class="sxs-lookup"><span data-stu-id="67d1a-117">Alternatively, search for "Initialize commerce scheduler."</span></span>
1. <span data-ttu-id="67d1a-118">I dialogrutan **Initiera schemaläggare för handel** se till att alternativet **ta bort befintligt konfiguration** anges till **nej** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-118">In the **Initialize commerce scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="67d1a-119">Kontrollera deljobbet RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="67d1a-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="67d1a-120">Så här kontrollerar du att deljobb **RetailProductRating** finns:</span><span class="sxs-lookup"><span data-stu-id="67d1a-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="67d1a-121">Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Deljobb i schemaläggare**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-121">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="67d1a-122">Du kan också söka efter "Deljobb i schemaläggare".</span><span class="sxs-lookup"><span data-stu-id="67d1a-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="67d1a-123">I deljobbslistan, sök efter deljobbet **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="67d1a-124">Följande illustration visar ett exempel på deljobbdetaljer i handel.</span><span class="sxs-lookup"><span data-stu-id="67d1a-124">The following illustration shows an example of the subjob details in Commerce.</span></span>

![Detaljer för deljobbet RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="67d1a-126">Om du inte hittar deljobbet **RetailProductRating** kanske du redan har kört jobbet **synkronisera produktklassificering** och **1040 CDX**-jobb innan du initierade schemaläggare för handel.</span><span class="sxs-lookup"><span data-stu-id="67d1a-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the Commerce scheduler.</span></span> <span data-ttu-id="67d1a-127">I det här fallet följer du stegen nedan för att köra jobbet **fullständig datasynkronisering**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-127">In this case, follow these steps to run the **Full data sync** job.</span></span>

> 1. <span data-ttu-id="67d1a-128">Gå till **Butik och handel \> Administrationsinställning \> Schemaläggare för handel \> Kanaldatabas**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-128">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span> <span data-ttu-id="67d1a-129">Du kan också söka efter "Kanaldatabas".</span><span class="sxs-lookup"><span data-stu-id="67d1a-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="67d1a-130">Välj den kanaldatabas som ska synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="67d1a-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="67d1a-131">I åtgärdsfönstret, välj **Fullständig datasynkronisering**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-131">On the action pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="67d1a-132">I dialogrutan **Välj ett distributionsschema**, välj **1040 - produkter** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="67d1a-133">Upprepa stegen i föregående procedur för att kontrollera att **RetailProductRating**-deljobbet har skapats.</span><span class="sxs-lookup"><span data-stu-id="67d1a-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="67d1a-134">Importera produktvärdering</span><span class="sxs-lookup"><span data-stu-id="67d1a-134">Import product ratings</span></span>

<span data-ttu-id="67d1a-135">Om du vill importera produktvärderingar till handel från klassificering och recensioner följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-135">To import product ratings into Commerce from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="67d1a-136">Gå till **Butik och handel \> Inställningar av administrationen \> Schemaläggare för handel \> Synkronisera produktklassificeringsjobb**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-136">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="67d1a-137">Du kan också söka efter "synkronisera produktklassificeringsjobb".</span><span class="sxs-lookup"><span data-stu-id="67d1a-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="67d1a-138">I dialogrutan **Dra produktvärderingar** på snabbfliken **Kör i bakgrunden** välj **Återkommande**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="67d1a-139">I dialogrutan **Definiera upprepning** ange ett mönster för återkommande.</span><span class="sxs-lookup"><span data-stu-id="67d1a-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="67d1a-140">(Det föreslagna värdet är två timmar.) Schemalägg inte en återkommande tid som är mindre än en timme.</span><span class="sxs-lookup"><span data-stu-id="67d1a-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="67d1a-141">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-141">Select **OK**.</span></span>
1. <span data-ttu-id="67d1a-142">Ange alternativet **Batchbearbetning** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="67d1a-143">Den här inställningen säkerställer att du kan granska loggarna och verifiera status för batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="67d1a-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="67d1a-144">Klicka på **OK** för att schemalägga batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="67d1a-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="67d1a-145">Följande illustration visar ett exempel på konfiguration av batchjobb i handel.</span><span class="sxs-lookup"><span data-stu-id="67d1a-145">The following illustration shows an example of batch job configuration in Commerce.</span></span>

![Konfiguration av batchjobbet Synkronisera produktklassificeringar](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="67d1a-147">Kontrollera att batchjobbet för synkronisering av produktvärderingar har slutförts.</span><span class="sxs-lookup"><span data-stu-id="67d1a-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="67d1a-148">För att kontrollera att batchjobbet **Synkronisera produktklassificeringar** lyckas, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="67d1a-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="67d1a-149">Gå till **Butik och handel \> Systemadministratör \> Frågor \> Batchjobb** eller om du använder en lagerhållningsenhet (SKU) för endast handel **Butik och handel \> Frågor och rapporter \> Batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-149">Go to **Retail and Commerce \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Commerce-only stock keeping unit (SKU), **Retail and Commerce \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="67d1a-150">Du kan alternativt söka efter batchjobb.</span><span class="sxs-lookup"><span data-stu-id="67d1a-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="67d1a-151">Om du vill visa information om batchjobbet går du till kolumnen **jobbeskrivning** och söker efter en beskrivning som innehåller "Visa produktklassificeringar" i batchjobbets lista.</span><span class="sxs-lookup"><span data-stu-id="67d1a-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="67d1a-152">Välj jobb-ID om du vill visa detaljer för batchjobbet, t.ex. tidsplanerat startdatum/-tid och upprepningstext.</span><span class="sxs-lookup"><span data-stu-id="67d1a-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="67d1a-153">I följande illustration visas ett exempel på detaljerna i batchjobbet i Handel när batchjobbet är tidsplanerat för körning med två timmars intervall.</span><span class="sxs-lookup"><span data-stu-id="67d1a-153">The following illustration shows an example of the batch job details in Commerce when the batch job is scheduled to run at two-hour intervals.</span></span>

![Detaljer för batchjobbet Synkronisera produktklassificeringar](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="67d1a-155">Göra produkt produktvärderingar tillgängliga i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="67d1a-156">Lösningen för klassificeringar och recensioner i Dynamics 365 Commerce är en flerkanalslösning.</span><span class="sxs-lookup"><span data-stu-id="67d1a-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="67d1a-157">Produktklassificeringar visas dock inte som standard i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="67d1a-158">För att hjälpa kunder i butikerna se värderingar och recensioner när de får hjälp av säljarna måste du aktivera produktvärderingar i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="67d1a-159">Så här aktiverar du produktrecensioner i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="67d1a-160">Gå till **Butik och handel \> Inställning av Handel \> Parametrar \> Handelparametrar**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-160">Go to **Retail and Commerce \> Commerce setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="67d1a-161">Du kan också söka efter "Handelparametrar".</span><span class="sxs-lookup"><span data-stu-id="67d1a-161">Alternatively, search for "Commerce parameters."</span></span>
1. <span data-ttu-id="67d1a-162">På fliken **konfigurationsparametrar** välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="67d1a-163">Ange ett namn som till exempel **RatingsAndReviews.EnableProductRatingsForRetailStores** och ange värdet till **sant**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="67d1a-164">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-164">Select **Save**.</span></span>
1. <span data-ttu-id="67d1a-165">Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-165">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span> <span data-ttu-id="67d1a-166">Du kan också söka efter "fördelningsplan".</span><span class="sxs-lookup"><span data-stu-id="67d1a-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="67d1a-167">I jobblistan, välj **1110** (**Global konfiguration**) och välj sedan **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="67d1a-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="67d1a-168">När jobbet har körts kontrollerar du att produktklassificeringen nu visas i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="67d1a-169">Följande illustration visar ett exempel på konfigurationen av parametrarna för Handel som ska aktiveras för produktvärderingar i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-169">The following illustration shows an example of the configuration of the Commerce parameters to turn on product ratings at the POS.</span></span>

![Konfiguration av handelsparametrarna för produktvärderingar i kassan](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="67d1a-171">Följande illustration visar ett exempel på produktvärderingar i kassan.</span><span class="sxs-lookup"><span data-stu-id="67d1a-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Produktvärderingar i kassan](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="67d1a-173">Följande illustration visar ett exempel på produktvärderingar kundtjänstkanaler.</span><span class="sxs-lookup"><span data-stu-id="67d1a-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Produktvärderingar i en kundtjänstkanal](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="67d1a-175">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="67d1a-175">Additional resources</span></span>

[<span data-ttu-id="67d1a-176">Översikt över omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="67d1a-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="67d1a-177">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="67d1a-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="67d1a-178">Hantera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="67d1a-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="67d1a-179">Konfigurera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="67d1a-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
