---
title: Konfigurera Dataverse-integrering
description: Du kan aktivera eller inaktivera integration mellan Microsoft Dataverse och Dynamics 365 Human Resources. Du kan också visa synkroniseringsinformation, ta bort spårningsdata och synkronisera om ett register för att hjälpa till att felsöka dataproblem från de två miljöerna.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 080f66e4e13df44a77f0499c6d69686f0e3d7021
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801201"
---
# <a name="configure-dataverse-integration"></a><span data-ttu-id="27c86-104">Konfigurera Dataverse-integrering</span><span class="sxs-lookup"><span data-stu-id="27c86-104">Configure Dataverse integration</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="27c86-105">Du kan aktivera eller inaktivera integration mellan Microsoft Dataverse och Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="27c86-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="27c86-106">Du kan också visa synkroniseringsinformationen, rensa spårningsdata och synkronisera om ett register för att hjälpa till att felsöka dataproblem från de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="27c86-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="27c86-107">Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="27c86-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="27c86-108">När du stänger av integrationen kan användarna göra ändringar i personal eller Dataverse, men dessa ändringar synkroniseras inte mellan de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="27c86-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="27c86-109">Som standard inaktiveras dataintegrering mellan personal och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="27c86-110">Du kanske vill inaktivera integration i följande situationer:</span><span class="sxs-lookup"><span data-stu-id="27c86-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="27c86-111">Du fyller i data via datahanteringsramverket och måste importera data flera gånger för att de ska få rätt status.</span><span class="sxs-lookup"><span data-stu-id="27c86-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="27c86-112">Det finns problem med data i personal eller Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="27c86-113">Om du inaktiverar integration kan du ta bort en post i en miljö utan att ta bort den i den andra.</span><span class="sxs-lookup"><span data-stu-id="27c86-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="27c86-114">När du aktiverar integreringen igen kommer posten i miljön där den inte togs bort att synkroniseras till den miljö där den togs bort.</span><span class="sxs-lookup"><span data-stu-id="27c86-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="27c86-115">Synkroniseringen påbörjas nästa gång batchjobbet **Dataverse-integrering missade begärd synkronisering** körs.</span><span class="sxs-lookup"><span data-stu-id="27c86-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="27c86-116">När du stänger av dataintegreringen måste du se till att du inte redigerar samma post i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="27c86-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="27c86-117">När du slår på integrationen igen synkroniseras posten som du senast redigerade.</span><span class="sxs-lookup"><span data-stu-id="27c86-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="27c86-118">Om du inte gör samma ändringar i den här posten i båda miljöerna kan det därför hända att data går förlorade.</span><span class="sxs-lookup"><span data-stu-id="27c86-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="27c86-119">Öppna sidan Dataverse-integration</span><span class="sxs-lookup"><span data-stu-id="27c86-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="27c86-120">I personalinstansen där du vill visa eller konfigurera inställningar för integrering med Dataverse väljer du panelen **systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="27c86-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="27c86-121">[![Panelen Systemadministration](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="27c86-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="27c86-122">Välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="27c86-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="27c86-123">[![Fliken Länkar](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="27c86-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="27c86-124">Under **Integrationer**, välj **Dataverse konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="27c86-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="27c86-125">[![Dataverse konfigurationslänk](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="27c86-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="27c86-126">Aktivera och inaktivera dataintegrering mellan personal och Dataverse</span><span class="sxs-lookup"><span data-stu-id="27c86-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="27c86-127">Ställ in alternativet **Aktivera Dataverse-integrering** som **Ja** på sidan **Microsoft Dataverse-integrering** för att aktivera integrering.</span><span class="sxs-lookup"><span data-stu-id="27c86-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27c86-128">När du aktiverar integrationen kommer data att synkroniseras nästa gång som batchjobbet **Dataverse-integrering missade begärd synkronisering** körs.</span><span class="sxs-lookup"><span data-stu-id="27c86-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="27c86-129">Alla data måste vara tillgängliga när batch-jobbet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="27c86-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="27c86-130">Om du vill stänga av integrationen ställer du in alternativet på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="27c86-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="27c86-131">[![Aktivera eller inaktivera Dataverse-integreringen](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="27c86-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="27c86-132">Vi rekommenderar att du inaktiverar Dataverse integration när du utför dataflyttningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="27c86-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="27c86-133">Stora dataöverföringar kan påverka prestanda betydligt.</span><span class="sxs-lookup"><span data-stu-id="27c86-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="27c86-134">Exempelvis kan överföringar av 2 000 arbetare ta flera timmar när integreringen är aktiverad och mindre än en timme när den är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="27c86-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="27c86-135">Siffrorna i det här exemplet är endast avsedda som demonstrationer.</span><span class="sxs-lookup"><span data-stu-id="27c86-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="27c86-136">Hur lång tid det tar att importera poster kan variera kraftigt baserat på många faktorer.</span><span class="sxs-lookup"><span data-stu-id="27c86-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="27c86-137">Visa information om dataintegrering</span><span class="sxs-lookup"><span data-stu-id="27c86-137">View data integration details</span></span>

<span data-ttu-id="27c86-138">På snabbfliken **Administration** på sidan **Microsoft Dataverse-integrering** kan du se hur raderna är kopplade till varandra mellan Personal och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="27c86-139">Om du vill visa raderna för ett register markerar du registret i fältet **Dataverse-register**.</span><span class="sxs-lookup"><span data-stu-id="27c86-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="27c86-140">I rutnätet visas alla rader som är länkade till det valda registret.</span><span class="sxs-lookup"><span data-stu-id="27c86-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="27c86-141">Alla Dataverse-register visas inte för närvarande i listan.</span><span class="sxs-lookup"><span data-stu-id="27c86-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="27c86-142">Endast register som stöder användning av anpassade fält visas i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="27c86-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="27c86-143">Nya register blir tillgängliga genom kontinuerliga uppdateringar av Personal.</span><span class="sxs-lookup"><span data-stu-id="27c86-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="27c86-144">Rutnätet innehåller följande fält:</span><span class="sxs-lookup"><span data-stu-id="27c86-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="27c86-145">**Dataverse-register** – Namnet på registret i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="27c86-146">**Registerreferens för Dataverse** – Den identifierare som Dataverse använder för att identifiera en post.</span><span class="sxs-lookup"><span data-stu-id="27c86-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="27c86-147">Detta värde är detsamma som ett värde för personalvärdet **RecId**.</span><span class="sxs-lookup"><span data-stu-id="27c86-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="27c86-148">Du kan hitta identifieraren när du öppnar Dataverse-registret i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="27c86-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="27c86-149">**Namn på Personal-entitet** – den Personal-enhet som senast synkroniserade data till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="27c86-150">Entiteten kan antingen ha Dataverse prefixet eller ett annat prefix.</span><span class="sxs-lookup"><span data-stu-id="27c86-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="27c86-151">**Personalreferens** – **RecId**-värdet som är kopplat till posten i personal.</span><span class="sxs-lookup"><span data-stu-id="27c86-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="27c86-152">**Borttaget från Dataverse** – Ett värde som anger huruvida raden tagits bort från Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="27c86-153">Poster i Personal motsvarar rader i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="27c86-154">Ta bort kopplingen för en Personal-post från en Dataverse-rad</span><span class="sxs-lookup"><span data-stu-id="27c86-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="27c86-155">Om du får problem under synkroniseringen mellan personal och Dataverse kan du kanske lösa dem genom att avmarkera spårningen och låta spårningstabellen synkroniseras igen.</span><span class="sxs-lookup"><span data-stu-id="27c86-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="27c86-156">Om du tar bort kopplingen och sedan ändrar eller tar bort en rad i Dataverse synkroniseras inte ändringarna med Personal.</span><span class="sxs-lookup"><span data-stu-id="27c86-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="27c86-157">Om du utför ändringar i Personal skapas en ny spårningspost och raden uppdateras i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27c86-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="27c86-158">Om du vill ta bort kopplingen mellan en Personal-post och en Dataverse-rad väljer du registret i fältet **Dataverse-register** och sedan **Rensa spårningsinformation**.</span><span class="sxs-lookup"><span data-stu-id="27c86-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="27c86-159">[![Rensa uppföljningsinformation](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="27c86-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="27c86-160">Se nästa procedur för att köra en fullständig synkronisering på registret efter det att du har rensat spårningen.</span><span class="sxs-lookup"><span data-stu-id="27c86-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="27c86-161">Synkronisera ett register mellan Personal och Dataverse</span><span class="sxs-lookup"><span data-stu-id="27c86-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="27c86-162">Gör på följande sätt när:</span><span class="sxs-lookup"><span data-stu-id="27c86-162">Use this procedure when:</span></span>

- <span data-ttu-id="27c86-163">Ändringar från Dataverse tar för lång tid att visas i personal.</span><span class="sxs-lookup"><span data-stu-id="27c86-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="27c86-164">Du måste uppdatera spårningstabellen när du har avmarkerat spårningen.</span><span class="sxs-lookup"><span data-stu-id="27c86-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="27c86-165">Så här kör du en fullständig synkronisering på ett register mellan Personal och Dataverse:</span><span class="sxs-lookup"><span data-stu-id="27c86-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="27c86-166">Välj registret i fältet **Dataverse-register**.</span><span class="sxs-lookup"><span data-stu-id="27c86-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="27c86-167">Välj **Synkronisera nu**.</span><span class="sxs-lookup"><span data-stu-id="27c86-167">Select **Sync now**.</span></span>

<span data-ttu-id="27c86-168">[![Köra en fullständig synkronisering](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="27c86-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="27c86-169">Se även</span><span class="sxs-lookup"><span data-stu-id="27c86-169">See also</span></span>

[<span data-ttu-id="27c86-170">Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="27c86-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="27c86-171">Konfigurera virtuella Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="27c86-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="27c86-172">Vanliga frågor och svar om virtuella register i Personal</span><span class="sxs-lookup"><span data-stu-id="27c86-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="27c86-173">Vad är Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="27c86-173">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="27c86-174">Terminologiuppdateringar</span><span class="sxs-lookup"><span data-stu-id="27c86-174">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]