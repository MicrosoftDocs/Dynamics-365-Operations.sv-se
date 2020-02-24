---
title: Konfigurera Common Data Service-integrering
description: Du kan aktivera eller inaktivera integration mellan Common Data Service och en instans av Microsoft Dynamics 365 Human Resources. Du kan också visa synkroniseringsinformation, ta bort uppföljningsdata och synkronisera om en enhet för att hjälpa till att felsöka data från de två miljöerna.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010572"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="34847-104">Konfigurera Common Data Service-integrering</span><span class="sxs-lookup"><span data-stu-id="34847-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="34847-105">Du kan aktivera eller inaktivera integration mellan Common Data Service och en instans av Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="34847-105">You can turn integration between Common Data Service and an instance of Microsoft Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="34847-106">Du kan också visa synkroniseringsinformation, ta bort uppföljningsdata och synkronisera om en enhet för att hjälpa till att felsöka data från de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="34847-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="34847-107">När du stänger av integrationen kan användarna göra ändringar i personal eller Common Data Service, men dessa ändringar synkroniseras inte mellan de två miljöerna.</span><span class="sxs-lookup"><span data-stu-id="34847-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="34847-108">Som standard är integration mellan personal och Common Data Service antingen av eller på, beroende på förekomst av demonstrationsdata i miljön:</span><span class="sxs-lookup"><span data-stu-id="34847-108">By default, integration between Human Resources and Common Data Service is turned either off or on, depending on the presence of demo data in the environments:</span></span>

- <span data-ttu-id="34847-109">**Av** för nya miljöer som inte innehåller demodata</span><span class="sxs-lookup"><span data-stu-id="34847-109">**Off** for new environments that don't include demo data</span></span>
- <span data-ttu-id="34847-110">**På** för nya miljöer som innehåller demodata</span><span class="sxs-lookup"><span data-stu-id="34847-110">**On** for new environments that include demo data</span></span>

<span data-ttu-id="34847-111">Nya miljöer med demodata börjar synkronisera data när de etableras.</span><span class="sxs-lookup"><span data-stu-id="34847-111">New environments that include demo data will start to sync data when they are provisioned.</span></span>

<span data-ttu-id="34847-112">Du kanske vill inaktivera integration i följande situationer:</span><span class="sxs-lookup"><span data-stu-id="34847-112">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="34847-113">Du fyller i data via datahanteringsramverket och måste importera data flera gånger för att de ska få rätt status.</span><span class="sxs-lookup"><span data-stu-id="34847-113">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="34847-114">Det finns problem med data i personal eller Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34847-114">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="34847-115">Om du inaktiverar integration kan du ta bort en post i en miljö utan att ta bort den i den andra.</span><span class="sxs-lookup"><span data-stu-id="34847-115">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="34847-116">När du aktiverar integreringen igen kommer posten i miljön där den inte togs bort att synkroniseras på nytt till den miljö där den togs bort.</span><span class="sxs-lookup"><span data-stu-id="34847-116">When you turn integration back on, the record in the environment where it wasn't deleted will be synced back to the environment where it was deleted.</span></span> <span data-ttu-id="34847-117">Synkroniseringen påbörjas nästa gång batchjobbet **Common Data Service-integrering missade begärd synkronisering** körs.</span><span class="sxs-lookup"><span data-stu-id="34847-117">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="34847-118">När du stänger av dataintegreringen måste du se till att du inte redigerar samma post i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="34847-118">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="34847-119">När du slår på integrationen igen synkroniseras posten som du senast redigerade.</span><span class="sxs-lookup"><span data-stu-id="34847-119">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="34847-120">Om du inte gör samma ändringar i den här posten i båda miljöerna kan det därför hända att data går förlorade.</span><span class="sxs-lookup"><span data-stu-id="34847-120">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="34847-121">Öppna sidan Common Data Service-integration</span><span class="sxs-lookup"><span data-stu-id="34847-121">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="34847-122">I personalinstansen där du vill visa eller konfigurera inställningar för integrering med Common Data Service väljer du panelen **systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="34847-122">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="34847-123">[![Panelen Systemadministration](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="34847-123">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="34847-124">Välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="34847-124">Select the **Links** tab.</span></span>

    <span data-ttu-id="34847-125">[![Fliken Länkar](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="34847-125">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="34847-126">Under **Integrationer**, välj **Common Data Service konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="34847-126">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="34847-127">[![Common Data Service konfigurationslänk](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="34847-127">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="34847-128">Aktivera och inaktivera dataintegrering mellan personal och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="34847-128">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="34847-129">Aktivera integration genom att ställa in alternativet **Aktivera integration till Common Data Service** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="34847-129">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="34847-130">När du aktiverar integrationen kommer data att synkroniseras nästa gång som batchjobbet **Common Data Service-integrering missade begärd synkronisering** körs.</span><span class="sxs-lookup"><span data-stu-id="34847-130">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="34847-131">Alla data måste vara tillgängliga när batch-jobbet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="34847-131">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="34847-132">Om du vill stänga av integrationen ställer du in alternativet på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="34847-132">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="34847-133">[![Aktivera eller inaktivera Common Data Service-integreringen](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="34847-133">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="34847-134">Visa information om dataintegrering</span><span class="sxs-lookup"><span data-stu-id="34847-134">View data integration details</span></span>

<span data-ttu-id="34847-135">På snabbfliken **administration** på sidan **Common Data Service-integration** kan du se hur posterna är kopplade till varandra mellan personal och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34847-135">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="34847-136">Om du vill visa posterna för en entitet markerar du enheten i fältet **CDS-enhetsnamn**.</span><span class="sxs-lookup"><span data-stu-id="34847-136">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="34847-137">I rutnätet visas alla poster som är länkade till den valda enheten.</span><span class="sxs-lookup"><span data-stu-id="34847-137">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="34847-138">[![Visa posterna för en enhet](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="34847-138">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="34847-139">Alla Common Data Service-entiteter visas inte för närvarande i listan.</span><span class="sxs-lookup"><span data-stu-id="34847-139">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="34847-140">Endast enheter som stöder användning av anpassade fält visas i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="34847-140">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="34847-141">Nya enheter blir tillgängliga genom kontinuerliga uppdateringar av personal.</span><span class="sxs-lookup"><span data-stu-id="34847-141">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="34847-142">Rutnätet innehåller följande fält:</span><span class="sxs-lookup"><span data-stu-id="34847-142">The grid includes the following fields:</span></span>

- <span data-ttu-id="34847-143">**CDS-enhetsnamn** – namnet på enheten i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34847-143">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="34847-144">**CD-enhetsreferens** – identifieraren aom Common Data Service använder för att identifiera en post.</span><span class="sxs-lookup"><span data-stu-id="34847-144">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="34847-145">Detta värde är detsamma som ett värde för personalvärdet **RecId**.</span><span class="sxs-lookup"><span data-stu-id="34847-145">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="34847-146">Du kan hitta identifieraren när du öppnar Common Data Service entiteten i Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="34847-146">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="34847-147">**Namn på personalenhet** – den enhet som senast synkroniserade data till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34847-147">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="34847-148">Entiteten kan antingen ha Common Data Service prefixet eller ett annat prefix.</span><span class="sxs-lookup"><span data-stu-id="34847-148">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="34847-149">**Personalreferens** – **RecId**-värdet som är kopplat till posten i personal.</span><span class="sxs-lookup"><span data-stu-id="34847-149">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="34847-150">**Togs bort från CDS** – ett värde som anger om posten togs bort från Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34847-150">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="34847-151">Ta bort kopplingen för en post i personal från Common Data Service</span><span class="sxs-lookup"><span data-stu-id="34847-151">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="34847-152">Om du får problem under synkroniseringen mellan personal och Common Data Service kan du kanske lösa dem genom att avmarkera spårningen och låta spårningstabellen synkroniseras igen.</span><span class="sxs-lookup"><span data-stu-id="34847-152">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="34847-153">Om du tar bort kopplingen och sedan ändrar eller tar bort en post i Common Data Service synkroniseras inte ändringarna med personal.</span><span class="sxs-lookup"><span data-stu-id="34847-153">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="34847-154">Om du ändrar i personal skapas en ny spårningspost och posten uppdateras i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="34847-154">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="34847-155">Om du vill ta bort en posts koppling mellan personal och Common Data Service, markera enheten i fältet **CDS-enhetsnamn** och väljer sedan **Rensa uppföljningsinformation**.</span><span class="sxs-lookup"><span data-stu-id="34847-155">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="34847-156">[![Rensa uppföljningsinformation](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="34847-156">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="34847-157">Information om hur du kör en fullständig synkronisering på entiteten efter att du har rensat spårningen finns i nästa procedur.</span><span class="sxs-lookup"><span data-stu-id="34847-157">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="34847-158">Synkronisera en enhet mellan personal och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="34847-158">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="34847-159">Använd den här proceduren om ändringar från Common Data Service tar för lång tid att visa ändringar i personal, eller om du måste uppdatera spårningstabellen när du har avmarkerat spårningen.</span><span class="sxs-lookup"><span data-stu-id="34847-159">Use this procedure if changes from Common Data Service are taking too long to appear in Human Resources, or if you must refresh the tracking table after you clear the tracking.</span></span>

- <span data-ttu-id="34847-160">Om du vill köra en fullständig synkronisering på en enhet mellan personal och Common Data Service väljer du enheten i **CDS-enhetsnamn-** och väljer sedan **synkronisera nu**.</span><span class="sxs-lookup"><span data-stu-id="34847-160">To run a full synchronization on an entity between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Sync now**.</span></span>

<span data-ttu-id="34847-161">[![Köra en fullständig synkronisering](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="34847-161">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


