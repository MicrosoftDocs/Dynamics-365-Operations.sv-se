---
title: Kundarbetsflöde
description: Det här avsnittet innehåller information om kundarbetsflödet. Du ändrar specifika fält för en kund och skickar sedan ändringarna för godkännande via arbetsflödet innan de läggs till för kunden.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 10149351d548ab63b9d765ce34afd5908e43e12f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835080"
---
# <a name="customer-workflow"></a><span data-ttu-id="aec47-104">Kundarbetsflöde</span><span class="sxs-lookup"><span data-stu-id="aec47-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aec47-105">Kundarbetsflödet är en nyhet i Microsoft Dynamics 365 for Finance and Operations version 8.0.4.</span><span class="sxs-lookup"><span data-stu-id="aec47-105">The customer workflow has been added to Microsoft Dynamics 365 for Finance and Operations version 8.0.4.</span></span> <span data-ttu-id="aec47-106">Du kan ändra specifika fält för en kund och sedan skicka ändringarna för godkännande via arbetsflödet innan de läggs till för kunden.</span><span class="sxs-lookup"><span data-stu-id="aec47-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="aec47-107">Ställ in kundarbetsflödet</span><span class="sxs-lookup"><span data-stu-id="aec47-107">Set up the customer workflow</span></span>

<span data-ttu-id="aec47-108">Innan du kan använda funktionen för kundarbetsflöde måste du aktivera den.</span><span class="sxs-lookup"><span data-stu-id="aec47-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="aec47-109">Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="aec47-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="aec47-110">Aktivera funktionen genom att gå till fliken **Allmänt** och snabbfliken **Kundgodkännande** där du anger **Aktivera kundgodkännanden** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="aec47-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="aec47-111">I fältet **Beteende för datatabell** väljer du ett beteende som datatabellen ska använda när data importeras:</span><span class="sxs-lookup"><span data-stu-id="aec47-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="aec47-112">**Tillåt ändringar utan godkännande** – En enhet kan uppdatera kundposten utan att den bearbetas genom arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="aec47-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="aec47-113">**Avvisa ändringar** – Det går inte att ändra kundposten.</span><span class="sxs-lookup"><span data-stu-id="aec47-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="aec47-114">Importen går inte att genomföra för fält som är aktiverade för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="aec47-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="aec47-115">**Skapa ändringsförslag** – Alla fält ändras utom de fält som har aktiverats för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="aec47-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="aec47-116">De nya värdena för dessa fält läggs till för kunden som föreslagna ändringar och arbetsflödet startar automatiskt.</span><span class="sxs-lookup"><span data-stu-id="aec47-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="aec47-117">Gå sedan till listan med kundfält och markera kryssrutan **Aktivera** för alla fält som måste godkännas innan de kan ändras.</span><span class="sxs-lookup"><span data-stu-id="aec47-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="aec47-118">Gå till **Kundreskontra \> Inställningar \> Arbetsflöden för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="aec47-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="aec47-119">Välj **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="aec47-119">Select **New**.</span></span>
7. <span data-ttu-id="aec47-120">Välj **Arbetsflöde för föreslagen kundändring**.</span><span class="sxs-lookup"><span data-stu-id="aec47-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="aec47-121">Konfigurera arbetsflödet så att det matchar godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="aec47-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="aec47-122">Godkännandeelementet **Arbetsflödesgodkännande för föreslagen kundändring** i arbetsflödet tillämpar ändringarna på kunden.</span><span class="sxs-lookup"><span data-stu-id="aec47-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="aec47-123">Ändra kundinformation och skicka ändringarna till arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="aec47-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="aec47-124">När du ändrar ett fält som har aktiverats för arbetsflödet visas sidan **Föreslagna ändringar**.</span><span class="sxs-lookup"><span data-stu-id="aec47-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="aec47-125">På den här sidan visas det ursprungliga värdet i fältet och det nya värdet som du angav.</span><span class="sxs-lookup"><span data-stu-id="aec47-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="aec47-126">Fältet som du har ändrat återställs till originalvärdet.</span><span class="sxs-lookup"><span data-stu-id="aec47-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="aec47-127">Ett statusmeddelande på sidan anger att ändringarna inte har skickats.</span><span class="sxs-lookup"><span data-stu-id="aec47-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="aec47-128">Varje gång du ändrar ett fält som är aktiverat för arbetsflödet läggs fältet till i listan över föreslagna ändringar.</span><span class="sxs-lookup"><span data-stu-id="aec47-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="aec47-129">Om du vill ångra det föreslagna värdet för ett fält använder du knappen **Ta bort** bredvid fältet i listan.</span><span class="sxs-lookup"><span data-stu-id="aec47-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="aec47-130">Om du vill ignorera alla ändringar använder du knappen **Ignorera alla ändringar** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="aec47-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="aec47-131">Stäng sidan genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="aec47-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="aec47-132">När du har minst en föreslagen ändring visas två extra menyer i åtgärdsfönstret: **Föreslagna ändringar** och **Arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="aec47-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="aec47-133">Välj **Föreslagna ändringar** om du vill öppna sidan **Föreslagna ändringar** och granska ändringarna.</span><span class="sxs-lookup"><span data-stu-id="aec47-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="aec47-134">Välj **Arbetsflöde \> Skicka** för att skicka ändringarna till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="aec47-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="aec47-135">Sidans status ändras till **Ändringar som väntar på godkännande**.</span><span class="sxs-lookup"><span data-stu-id="aec47-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="aec47-136">Arbetsflödet följer den vanliga arbetsflödesprocessen i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aec47-136">The workflow follows the standard workflow process in Finance and Operations.</span></span> <span data-ttu-id="aec47-137">Godkännaren dirigeras till sidan **Kund** där han eller hon kan granska ändringarna på sidan **Föreslagna ändringar** och sedan välja **Arbetsflöde \> Godkänn** för att godkänna arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="aec47-137">The approver is directed to the **Customer** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="aec47-138">När alla godkännanden har slutförts uppdateras fälten med de värden du har föreslagit.</span><span class="sxs-lookup"><span data-stu-id="aec47-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
