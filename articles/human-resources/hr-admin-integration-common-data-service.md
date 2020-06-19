---
title: Konfigurera Common Data Service-integrering
description: Du kan aktivera eller inaktivera integration mellan Common Data Service och Dynamics 365 Human Resources. Du kan också visa synkroniseringsinformation, ta bort uppföljningsdata och synkronisera om en enhet för att hjälpa till att felsöka data från de två miljöerna.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 7aad8217d48917d6855046a6810fe994f5564d94
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431324"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="01823-104">Konfigurera Common Data Service-integrering</span><span class="sxs-lookup"><span data-stu-id="01823-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="01823-105">Du kan aktivera eller inaktivera integration mellan Common Data Service och Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="01823-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="01823-106">Du kan också visa synkroniseringsinformation, ta bort uppföljningsdata och synkronisera om en enhet för att hjälpa till att felsöka data från de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="01823-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="01823-107">När du stänger av integrationen kan användarna göra ändringar i personal eller Common Data Service, men dessa ändringar synkroniseras inte mellan de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="01823-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="01823-108">Som standard inaktiveras dataintegrering mellan personal och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="01823-109">Du kanske vill inaktivera integration i följande situationer:</span><span class="sxs-lookup"><span data-stu-id="01823-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="01823-110">Du fyller i data via datahanteringsramverket och måste importera data flera gånger för att de ska få rätt status.</span><span class="sxs-lookup"><span data-stu-id="01823-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="01823-111">Det finns problem med data i personal eller Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="01823-112">Om du inaktiverar integration kan du ta bort en post i en miljö utan att ta bort den i den andra.</span><span class="sxs-lookup"><span data-stu-id="01823-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="01823-113">När du aktiverar integreringen igen kommer posten i miljön där den inte togs bort att synkroniseras till den miljö där den togs bort.</span><span class="sxs-lookup"><span data-stu-id="01823-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="01823-114">Synkroniseringen påbörjas nästa gång batchjobbet **Common Data Service-integrering missade begärd synkronisering** körs.</span><span class="sxs-lookup"><span data-stu-id="01823-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="01823-115">När du stänger av dataintegreringen måste du se till att du inte redigerar samma post i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="01823-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="01823-116">När du slår på integrationen igen synkroniseras posten som du senast redigerade.</span><span class="sxs-lookup"><span data-stu-id="01823-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="01823-117">Om du inte gör samma ändringar i den här posten i båda miljöerna kan det därför hända att data går förlorade.</span><span class="sxs-lookup"><span data-stu-id="01823-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="01823-118">Öppna sidan Common Data Service-integration</span><span class="sxs-lookup"><span data-stu-id="01823-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="01823-119">I personalinstansen där du vill visa eller konfigurera inställningar för integrering med Common Data Service väljer du panelen **systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="01823-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="01823-120">[![Panelen Systemadministration](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="01823-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="01823-121">Välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="01823-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="01823-122">[![Fliken Länkar](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="01823-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="01823-123">Under **Integrationer**, välj **Common Data Service konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="01823-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="01823-124">[![Common Data Service konfigurationslänk](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="01823-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="01823-125">Aktivera och inaktivera dataintegrering mellan personal och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="01823-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="01823-126">Aktivera integration genom att ställa in alternativet **Aktivera integration till Common Data Service** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="01823-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01823-127">När du aktiverar integrationen kommer data att synkroniseras nästa gång som batchjobbet **Common Data Service-integrering missade begärd synkronisering** körs.</span><span class="sxs-lookup"><span data-stu-id="01823-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="01823-128">Alla data måste vara tillgängliga när batch-jobbet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="01823-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="01823-129">Om du vill stänga av integrationen ställer du in alternativet på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="01823-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="01823-130">[![Aktivera eller inaktivera Common Data Service-integreringen](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="01823-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="01823-131">Visa information om dataintegrering</span><span class="sxs-lookup"><span data-stu-id="01823-131">View data integration details</span></span>

<span data-ttu-id="01823-132">På snabbfliken **administration** på sidan **Common Data Service-integration** kan du se hur posterna är kopplade till varandra mellan personal och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-132">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="01823-133">Om du vill visa posterna för en entitet markerar du enheten i fältet **CDS-enhetsnamn**.</span><span class="sxs-lookup"><span data-stu-id="01823-133">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="01823-134">I rutnätet visas alla poster som är länkade till den valda enheten.</span><span class="sxs-lookup"><span data-stu-id="01823-134">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="01823-135">[![Visa posterna för en enhet](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="01823-135">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="01823-136">Alla Common Data Service-entiteter visas inte för närvarande i listan.</span><span class="sxs-lookup"><span data-stu-id="01823-136">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="01823-137">Endast enheter som stöder användning av anpassade fält visas i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="01823-137">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="01823-138">Nya enheter blir tillgängliga genom kontinuerliga uppdateringar av personal.</span><span class="sxs-lookup"><span data-stu-id="01823-138">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="01823-139">Rutnätet innehåller följande fält:</span><span class="sxs-lookup"><span data-stu-id="01823-139">The grid includes the following fields:</span></span>

- <span data-ttu-id="01823-140">**CDS-enhetsnamn** – namnet på enheten i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-140">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="01823-141">**CD-enhetsreferens** – identifieraren aom Common Data Service använder för att identifiera en post.</span><span class="sxs-lookup"><span data-stu-id="01823-141">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="01823-142">Detta värde är detsamma som ett värde för personalvärdet **RecId**.</span><span class="sxs-lookup"><span data-stu-id="01823-142">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="01823-143">Du kan hitta identifieraren när du öppnar Common Data Service entiteten i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="01823-143">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="01823-144">**Namn på personalenhet** – den enhet som senast synkroniserade data till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-144">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="01823-145">Entiteten kan antingen ha Common Data Service prefixet eller ett annat prefix.</span><span class="sxs-lookup"><span data-stu-id="01823-145">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="01823-146">**Personalreferens** – **RecId**-värdet som är kopplat till posten i personal.</span><span class="sxs-lookup"><span data-stu-id="01823-146">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="01823-147">**Togs bort från CDS** – ett värde som anger om posten togs bort från Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-147">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="01823-148">Ta bort kopplingen för en post i personal från Common Data Service</span><span class="sxs-lookup"><span data-stu-id="01823-148">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="01823-149">Om du får problem under synkroniseringen mellan personal och Common Data Service kan du kanske lösa dem genom att avmarkera spårningen och låta spårningstabellen synkroniseras igen.</span><span class="sxs-lookup"><span data-stu-id="01823-149">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="01823-150">Om du tar bort kopplingen och sedan ändrar eller tar bort en post i Common Data Service synkroniseras inte ändringarna med personal.</span><span class="sxs-lookup"><span data-stu-id="01823-150">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="01823-151">Om du ändrar i personal skapas en ny spårningspost och posten uppdateras i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="01823-151">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="01823-152">Om du vill ta bort en posts koppling mellan personal och Common Data Service, markera enheten i fältet **CDS-enhetsnamn** och väljer sedan **Rensa uppföljningsinformation**.</span><span class="sxs-lookup"><span data-stu-id="01823-152">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="01823-153">[![Rensa uppföljningsinformation](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="01823-153">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="01823-154">Information om hur du kör en fullständig synkronisering på entiteten efter att du har rensat spårningen finns i nästa procedur.</span><span class="sxs-lookup"><span data-stu-id="01823-154">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="01823-155">Synkronisera en enhet mellan personal och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="01823-155">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="01823-156">Gör på följande sätt när:</span><span class="sxs-lookup"><span data-stu-id="01823-156">Use this procedure when:</span></span>

- <span data-ttu-id="01823-157">Ändringar från Common Data Service tar för lång tid att visas i personal.</span><span class="sxs-lookup"><span data-stu-id="01823-157">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="01823-158">Du måste uppdatera spårningstabellen när du har avmarkerat spårningen.</span><span class="sxs-lookup"><span data-stu-id="01823-158">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="01823-159">Så här kör du en fullständig synkronisering på en enhet mellan personal och Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="01823-159">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="01823-160">Välj entitet i fältet **CDS entitetsnamn**.</span><span class="sxs-lookup"><span data-stu-id="01823-160">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="01823-161">Välj **Synkronisera nu**.</span><span class="sxs-lookup"><span data-stu-id="01823-161">Select **Sync now**.</span></span>

<span data-ttu-id="01823-162">[![Köra en fullständig synkronisering](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="01823-162">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


