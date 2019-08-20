---
title: Arbetsflöde för leverantör
description: Ändra leverantörsinformationen och använd arbetsflöde för att godkänna den.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 112f9d6adeee583a63da8ab700d7adc179de2c1d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835320"
---
# <a name="vendor-workflow"></a><span data-ttu-id="4c54c-103">Arbetsflöde för leverantör</span><span class="sxs-lookup"><span data-stu-id="4c54c-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c54c-104">När leverantörens arbetsflöde används skickas ändringar som görs i specifika fält till arbetsflödet för godkännande innan de kan läggas till leverantören.</span><span class="sxs-lookup"><span data-stu-id="4c54c-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="4c54c-105">Ställ in arbetsflöde för leverantör</span><span class="sxs-lookup"><span data-stu-id="4c54c-105">Set up the vendor workflow</span></span>

<span data-ttu-id="4c54c-106">Innan du kan använda funktionen för arbetsflöde måste du aktivera den.</span><span class="sxs-lookup"><span data-stu-id="4c54c-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="4c54c-107">Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="4c54c-108">På fliken **Allmän** på snabbfliken **Allmänt**, ange alternativet **"Leverantörsgodkännande** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="4c54c-109">I fältet **Beteende för datatabell** väljer du vad som ska användas när du importerar data:</span><span class="sxs-lookup"><span data-stu-id="4c54c-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="4c54c-110">**Tillåta ändringar utan godkännande** – datatabellen kan uppdatera leverantörsposten utan att bearbeta den genom arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="4c54c-111">**Ignorera ändringar** – Ändringar kan inte göras till leverantörsposten.</span><span class="sxs-lookup"><span data-stu-id="4c54c-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="4c54c-112">Importen misslyckas för fält som är aktiverade för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="4c54c-113">**Skapa förslag för ändring** – Alla fält ändras förutom fält som är aktiverade för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="4c54c-114">De nya värdena för dessa fält läggs till leverantören som föreslagna ändringar och arbetsflödet startas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4c54c-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="4c54c-115">I listan över leverantörsfält, markera kryssrutan **Aktivera** för alla fält som måste godkännas innan de kan ändras.</span><span class="sxs-lookup"><span data-stu-id="4c54c-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="4c54c-116">Gå till **Leverantörsreskontra \> Inställningar \> Arbetsflöden för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="4c54c-117">Markera **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-117">Select **New**.</span></span>
7. <span data-ttu-id="4c54c-118">Välj **Arbetsflöde för föreslagna leverantörsändringar**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="4c54c-119">Konfigurera arbetsflödet så att det matchar din godkännandeprocess.</span><span class="sxs-lookup"><span data-stu-id="4c54c-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="4c54c-120">Arbetsflödeselementet **Arbetsflödesgodkännande för föreslagen ändring av leverantör** kommer att tillämpa ändringarna på leverantören.</span><span class="sxs-lookup"><span data-stu-id="4c54c-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="4c54c-121">Ändra leverantörsinformation och skicka ändringarna till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="4c54c-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="4c54c-122">När du ändrar ett fält som är aktiverat för arbetsflödet visas sidan **föreslagna ändringar**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="4c54c-123">På den här sidan visas det ursprungliga värdet i fältet och det nya värdet som du angav.</span><span class="sxs-lookup"><span data-stu-id="4c54c-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="4c54c-124">Fältet som du har ändrat återställs till originalvärdet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="4c54c-125">Ett statusmeddelande informerar också vilka ändringarna som inte har skickats.</span><span class="sxs-lookup"><span data-stu-id="4c54c-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="4c54c-126">Varje gång du ändrar ett fält som är aktiverat för arbetsflödet läggs det fältet till i listan på sidan **föreslagna ändringar**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="4c54c-127">Om du vill ångra det föreslagna värdet för ett fält använder du knappen **Ignorera** bredvid fältet i listan.</span><span class="sxs-lookup"><span data-stu-id="4c54c-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="4c54c-128">Om du vill ignorera alla ändringar, använd knappen **Ignorera alla ändringar** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="4c54c-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="4c54c-129">Välj **OK** om du vill stänga sidan.</span><span class="sxs-lookup"><span data-stu-id="4c54c-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="4c54c-130">När du har minst en föreslagen ändring visas två ytterligare flikar i åtgärdsfönstret: **föreslagna ändringar** och **arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="4c54c-131">Välj **föreslagna ändringar** för att öppna sidan **föreslagna ändringar** och granska ändringarna.</span><span class="sxs-lookup"><span data-stu-id="4c54c-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="4c54c-132">Välj **Arbetsflöde \> Skicka för att skicka ändringarna till arbetsflödet**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="4c54c-133">Sidans status ändras till **Ändringar som väntar på godkännande**.</span><span class="sxs-lookup"><span data-stu-id="4c54c-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="4c54c-134">Arbetsflödet följer standard i arbetsflödesprocessen i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4c54c-134">The workflow follows the standard workflow process in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="4c54c-135">Godkännaren dirigeras till sidan **leverantör** där han eller hon kan gå igenom ändringarna på sidan **föreslagna ändringar** sidan och välj sedan **Arbetsflöde \>Godkänn** för att godkänna arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="4c54c-135">The approver is directed to the **Vendor** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="4c54c-136">När alla godkännanden har slutförts uppdateras fälten med de värden du har föreslagit.</span><span class="sxs-lookup"><span data-stu-id="4c54c-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
