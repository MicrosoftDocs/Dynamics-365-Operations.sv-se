---
title: Hantera leasing med ramverket för import av leasing
description: I det här ämnet beskrivs hur du använder importramverket för leasing för att justera flera leasingar samtidigt.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7df2f55f596cab54315c2da2ec0492422514f49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971313"
---
# <a name="manage-leases-through-the-lease-import-framework"></a><span data-ttu-id="a6caf-103">Hantera leasing med ramverket för import av leasing</span><span class="sxs-lookup"><span data-stu-id="a6caf-103">Manage leases through the Lease import framework</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6caf-104">I det här ämnet beskrivs hur du använder importramverket för leasing för att justera flera leasingar i ett steg.</span><span class="sxs-lookup"><span data-stu-id="a6caf-104">This topic explains how to use the Lease import framework to adjust multiple leases in one step.</span></span> <span data-ttu-id="a6caf-105">Genom att använda den här funktionen kan du spara tid och du kan också se till att ändringarna blir mer exakta genom att minska risken för mänsklig fel.</span><span class="sxs-lookup"><span data-stu-id="a6caf-105">By using this capability, you can save time, and you can also ensure more accurate adjustments by reducing the chance of human error.</span></span> <span data-ttu-id="a6caf-106">Dessutom kan den här funktionen ansluta Microsoft Dynamics 365 Finance med externa dataentiteter för att effektivt ladda upp data.</span><span class="sxs-lookup"><span data-stu-id="a6caf-106">Additionally, this capability can connect Microsoft Dynamics 365 Finance with external data entities to efficiently upload data.</span></span>

<span data-ttu-id="a6caf-107">Följande dataentiteter kan användas för att integrera Leasing av tillgångar med externa system:</span><span class="sxs-lookup"><span data-stu-id="a6caf-107">The following data entities can be used to integrate Asset leasing with external systems:</span></span>

- <span data-ttu-id="a6caf-108">Mellanlagring av leasingavtal</span><span class="sxs-lookup"><span data-stu-id="a6caf-108">Lease staging</span></span>
- <span data-ttu-id="a6caf-109">Mellanlagring av betalningskontrakt</span><span class="sxs-lookup"><span data-stu-id="a6caf-109">Payment contract staging</span></span>
- <span data-ttu-id="a6caf-110">Mellanlagring av verkställande kontrakt</span><span class="sxs-lookup"><span data-stu-id="a6caf-110">Executory contract staging</span></span>

<span data-ttu-id="a6caf-111">Du kan använda importprocessen för att justera en leasing, uppdatera icke-ekonomisk information och lägga till nya leasingar.</span><span class="sxs-lookup"><span data-stu-id="a6caf-111">You can use the import process to adjust a lease, update non-financial information, or add new leases.</span></span> <span data-ttu-id="a6caf-112">Du kan visa och redigera leasinginformationen innan du importerar den.</span><span class="sxs-lookup"><span data-stu-id="a6caf-112">You can view and edit the leasing data before you import it.</span></span>

<span data-ttu-id="a6caf-113">Systemet kan köra följande tre processer via importsviten för leasingen.</span><span class="sxs-lookup"><span data-stu-id="a6caf-113">The system can run the following three processes through the lease import suite.</span></span>

| <span data-ttu-id="a6caf-114">Processtyp</span><span class="sxs-lookup"><span data-stu-id="a6caf-114">Process type</span></span>  | <span data-ttu-id="a6caf-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a6caf-115">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="a6caf-116">Lägg till post</span><span class="sxs-lookup"><span data-stu-id="a6caf-116">Add record</span></span>    | <span data-ttu-id="a6caf-117">Migrerade leasingar som har den här processtypen skapar en leasing i systemet.</span><span class="sxs-lookup"><span data-stu-id="a6caf-117">Migrated leases that have this process type create a lease in the system.</span></span> <span data-ttu-id="a6caf-118">Betalningsplanen måste bekräftas manuellt och journalposten för det första bokföringstillfället måste bokföras manuellt efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="a6caf-118">The payment schedule must be manually confirmed, and the initial recognition journal entry must be manually posted after the migration.</span></span> |
| <span data-ttu-id="a6caf-119">Uppdatera post</span><span class="sxs-lookup"><span data-stu-id="a6caf-119">Update record</span></span> | <span data-ttu-id="a6caf-120">Migrerade leasingar som har den här processtypen uppdaterar fältvärden för en leasing som redan finns i systemet.</span><span class="sxs-lookup"><span data-stu-id="a6caf-120">Migrated leases that have this process type update field values for a lease that is already in the system.</span></span> <span data-ttu-id="a6caf-121">Endast de fält som har markerats på sidan **Uppdatera valda fält** uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a6caf-121">Only the fields that have been selected on the **Update fields selection** page are updated.</span></span> <span data-ttu-id="a6caf-122">Vi rekommenderar att du väljer icke-finansiella fält på sidan **Uppdatera valda fält** eftersom den här processtypen inte justerar leasingen.</span><span class="sxs-lookup"><span data-stu-id="a6caf-122">We recommended that you select non-financial fields on the **Update fields selection** page, because this process type doesn't adjust the lease.</span></span> |
| <span data-ttu-id="a6caf-123">Justera post</span><span class="sxs-lookup"><span data-stu-id="a6caf-123">Adjust record</span></span> | <span data-ttu-id="a6caf-124">Migrerade leasingar som har den här processtypen justerar leasingen.</span><span class="sxs-lookup"><span data-stu-id="a6caf-124">Migrated leases that have this process type adjust the lease.</span></span> <span data-ttu-id="a6caf-125">Denna justering medför en finansiell leasingändring av leasingen.</span><span class="sxs-lookup"><span data-stu-id="a6caf-125">This adjustment causes a financial lease modification of the lease.</span></span> <span data-ttu-id="a6caf-126">När leasingen bearbetas skapar systemet en ny betalningsplan genom att använda nya data från importsviten för leasingen.</span><span class="sxs-lookup"><span data-stu-id="a6caf-126">After the lease is processed, the system creates a new payment schedule by using the new data from the lease import suite.</span></span> <span data-ttu-id="a6caf-127">Systemet bekräftar inte betalningsplanen och bokför inte justeringsjournalposten.</span><span class="sxs-lookup"><span data-stu-id="a6caf-127">The system doesn't confirm the payment schedule or post the adjustment journal entry.</span></span> |

<span data-ttu-id="a6caf-128">När information har laddats upp via arbetsytan **Datahantering** öppnar du sidan **Importhuvud** (**Leasing av tillgångar \> Ramverk för import av leasing \> Importhuvud**).</span><span class="sxs-lookup"><span data-stu-id="a6caf-128">After information is uploaded through the **Data management** workspace, open the **Import header** page (**Asset leasing \> Lease import framework \> Import header**).</span></span> <span data-ttu-id="a6caf-129">På den här sidan visas alla importer av de tre dataentiteter som listades tidigare.</span><span class="sxs-lookup"><span data-stu-id="a6caf-129">This page lists all imports of the three data entities that were listed earlier.</span></span>

<span data-ttu-id="a6caf-130">Om du vill visa mellanlagringsdata för leasing innan bearbetningen körs väljer du **Mellanlagringsdata**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-130">To view the lease staging data before processing is run, select **Staging data**.</span></span>

<span data-ttu-id="a6caf-131">Med jämförelsefunktionen kan du jämföra en post som du importerar med motsvarande post som redan finns i systemet.</span><span class="sxs-lookup"><span data-stu-id="a6caf-131">The compare function lets you compare a record that you're importing with the corresponding record that's already in your system.</span></span> <span data-ttu-id="a6caf-132">Om du vill jämföra en enskild leasingpost väljer du en leasing lån och väljer sedan **Jämför**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-132">To compare an individual lease record, select a lease, and then select **Compare**.</span></span> <span data-ttu-id="a6caf-133">Du bör slutföra det här steget för att generera en **Skillnader**-rapport innan du migrerar leasingposterna.</span><span class="sxs-lookup"><span data-stu-id="a6caf-133">You should complete this step to generate a **Differences** report before you migrate the lease records.</span></span> <span data-ttu-id="a6caf-134">Jämförelsefunktionen jämför värdena i dina mellanlagringsdata med värden för de leasingar som för närvarande finns i systemet.</span><span class="sxs-lookup"><span data-stu-id="a6caf-134">The Compare functionality compares the values in the staging data to the values for leases that are currently in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="a6caf-135">Jämförelsefunktionen fungerar inte för leasingar som har processtypen **Lägg till post** eftersom det inte finns något att jämföra med denna leasing.</span><span class="sxs-lookup"><span data-stu-id="a6caf-135">The Compare functionality doesn't work for leases that have the **Add record** process type, because there is nothing to compare against that lease.</span></span>
>
> <span data-ttu-id="a6caf-136">Om du vill jämföra flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Periodisk \> Jämför** och välja **Jämför**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-136">To compare multiple leases at the same time, go to **Asset leasing \> Lease import framework \> Periodic \> Compare**, and select **Compare**.</span></span>

<span data-ttu-id="a6caf-137">För varje entitet kan du visa skillnaderna mellan vad som finns i systemet och vad som finns i mellanlagringstabellerna.</span><span class="sxs-lookup"><span data-stu-id="a6caf-137">For each entity, you can view the differences between what is currently in the system and what is in the staging tables.</span></span> <span data-ttu-id="a6caf-138">Välj **Visa skillnader** för varje entitet i mellanlagringstabellerna.</span><span class="sxs-lookup"><span data-stu-id="a6caf-138">For each entity in the staging tables, select **See differences**.</span></span> <span data-ttu-id="a6caf-139">Dialogrutan som visas visar det aktuella värdet och det föreslagna mellanlagringsvärdet.</span><span class="sxs-lookup"><span data-stu-id="a6caf-139">The dialog box that appears shows the current value and the proposed staging value.</span></span>

<span data-ttu-id="a6caf-140">Du kan också uppdatera ditt mellanlagringsvärde genom att ändra det i kolumnen **Nytt värde** och sedan välja **Uppdatera mellanlagring**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-140">You can also update the staging value by changing it in the **New Value** column and then selecting **Update staging**.</span></span>

<span data-ttu-id="a6caf-141">Du kan validera leasingar för att säkerställa att posterna kan föras in i systemet utan att några fel uppstår.</span><span class="sxs-lookup"><span data-stu-id="a6caf-141">You can validate leases to ensure that the records can be brought into the system without introducing errors.</span></span> <span data-ttu-id="a6caf-142">Innan en leasingpost migreras kör systemet flera valideringar för att kontrollera att posten kommer att importeras utan problem.</span><span class="sxs-lookup"><span data-stu-id="a6caf-142">Before a lease record is migrated, the system runs several validations to ensure that the record will be successfully imported.</span></span> <span data-ttu-id="a6caf-143">Om du vill validera en enskild leasing väljer du **Validera**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-143">To validate an individual lease, select **Validate**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6caf-144">Om du vill validera flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Periodisk \> Validera** och välja **Jämför**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-144">To validate multiple leases at the same time, go to **Asset leasing \> Lease import framework \> Periodic \> Validate**, and select **Compare**.</span></span>

<span data-ttu-id="a6caf-145">Om du vill bearbeta en enskild leasing väljer du **Migrera leasingposter** på sidan **Importhuvud**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-145">To process an individual lease, select **Migrate lease records** on the **Import header** page.</span></span> <span data-ttu-id="a6caf-146">När en leasing migreras utför systemet den åtgärd som anges i fältet **Processtyp**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-146">When a lease is migrated, the system performs the action that is specified in the **Process type** field.</span></span>

> [!NOTE]
> <span data-ttu-id="a6caf-147">Om du vill validera flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Periodisk \> Validera** och välja **Jämför**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-147">To validate multiple leases at the same time, go to **Asset leasing \> Lease import framework \> Periodic \> Validate**, and select **Compare**.</span></span>

<span data-ttu-id="a6caf-148">När leasingarna jämförs kan du köra en rapport för att visa skillnaderna för varje leasing som ingår i import-ID:t.</span><span class="sxs-lookup"><span data-stu-id="a6caf-148">After the leases are compared, you can run a report to view the differences for each lease that is included in the import ID.</span></span> <span data-ttu-id="a6caf-149">Om du vill köra rapporten för en leasing lån väljer du denna leasing i mellanlagringsdata och väljer sedan **Jämför och visa rapport \> Rapporten Skillnader**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-149">To run the report for one lease, select that lease in the staging data, and then select **Compare and view report \> Differences report**.</span></span>

> [!NOTE]
> <span data-ttu-id="a6caf-150">Om du vill validera flera leasingar samtidigt kan du gå till **Leasing av tillgångar \> Förfrågningar och rapporter \> Rapporten Skillnader** och välja **Jämför**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-150">To validate multiple leases at the same time, go to **Asset leasing \> Inquiries and reports \> Differences report**, and select **Compare**.</span></span>

## <a name="set-up-update-fields"></a><span data-ttu-id="a6caf-151">Konfigurera uppdateringsfält</span><span class="sxs-lookup"><span data-stu-id="a6caf-151">Set up update fields</span></span>

<span data-ttu-id="a6caf-152">Om du använder ramverket för import av leasing för att uppdatera leasingar och process typen är **Uppdatera post** kan du välja vilka fält som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a6caf-152">If you're using the Lease import framework to update leases, and the process type is **Update record**, you can select specific fields to update.</span></span>

1. <span data-ttu-id="a6caf-153">Gå till **Leasing av tillgångar \> Ramverk för import av leasing \> Konfigurera \> Välj fält att uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-153">Go to **Asset leasing \> Lease import framework \> Setup \> Update field selection**.</span></span>
2. <span data-ttu-id="a6caf-154">Välj de fält som ska uppdateras på sidan som visas och välj sedan den gröna pilen för att flytta dem till listan **Valda fält**.</span><span class="sxs-lookup"><span data-stu-id="a6caf-154">On the page that appears, select the fields to update, and then select the green arrow to move them to the **Selected fields** list.</span></span> <span data-ttu-id="a6caf-155">Endast fält i listan **Valda fält** kan uppdateras med hjälp av importsviten för leasing.</span><span class="sxs-lookup"><span data-stu-id="a6caf-155">Only fields in the **Selected fields** list can be updated by using the lease import suite.</span></span>
