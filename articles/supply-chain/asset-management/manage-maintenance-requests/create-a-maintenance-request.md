---
title: Skapa underhållsbegäranden
description: I det här avsnittet beskrivs hur du skapar en underhållsbegäran i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7fc9ec2f6a9a8a11d824e4b5c13d5aa173541454
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571931"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="73a4e-103">Skapa underhållsbegäranden</span><span class="sxs-lookup"><span data-stu-id="73a4e-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="73a4e-104">Underhållsbegäran kan användas om underhållsarbetare eller produktionsarbetare upptäcker att utrustning behöver repareras, men reparationsjobbet inte kan utföras direkt.</span><span class="sxs-lookup"><span data-stu-id="73a4e-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="73a4e-105">**Exempel:** när en underhållsarbetare gör en reparation, upptäcker hon att en annan tillgång på samma plats måste servas.</span><span class="sxs-lookup"><span data-stu-id="73a4e-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="73a4e-106">Underhållsarbetaren har dock inte tid eller nödvändiga reservdelar för att utföra reparationsjobbet.</span><span class="sxs-lookup"><span data-stu-id="73a4e-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="73a4e-107">Därför skapar hon en underhållsbegäran på tillgången och anger en kort beskrivning av problemet.</span><span class="sxs-lookup"><span data-stu-id="73a4e-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="73a4e-108">Avsnittet **aktiva underhållsbegäran** i rutan **relaterad information** till höger på sidan **alla tillgångar** eller **aktiva tillgångar** (**tillgångshantering** \> **allmänt** \> **tillgångar** \> **alla tillgångar** eller **aktiva tillgångar**) visar aktiva underhållsbegäran som är kopplade till den valda tillgången.</span><span class="sxs-lookup"><span data-stu-id="73a4e-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="73a4e-109">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **alla underhållbegäran** eller **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="73a4e-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-110">Select **New**.</span></span>
3. <span data-ttu-id="73a4e-111">I dialogrutan **Skapa begäran** i fältet **underhållsbegärantyp** väljer du typ av underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="73a4e-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="73a4e-112">En standardtyp föreslås.</span><span class="sxs-lookup"><span data-stu-id="73a4e-112">A default type is suggested.</span></span>
4. <span data-ttu-id="73a4e-113">I fältet **beskrivning** anger du ett namn eller en rubrik som kortfattat beskriver underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="73a4e-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="73a4e-114">I fälten **funktionsplats** och **tillgång** väljer du en funktionsplats eller en tillgång, eller en kombination av en funktionsplats och en tillgång, som du behöver.</span><span class="sxs-lookup"><span data-stu-id="73a4e-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="73a4e-115">Du kan skapa en underhållsbegäran utan att välja en tillgång och tillgången kan läggas till underhållbegäran senare.</span><span class="sxs-lookup"><span data-stu-id="73a4e-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="73a4e-116">Om underhållsarbetaren som är inloggad på är relaterad till en resurs som är relaterad till en tillgång, ställs fältet **tillgång** in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="73a4e-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="73a4e-117">Om en underhållsbegäran redan är kopplad till den valda tillgången, visas ett meddelandefält överst i dialogrutan **skapa begäran** för att meddela dig om ID för den befintliga underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="73a4e-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="73a4e-118">Ett meddelandefält meddelar dig också om tillgången täcks av ett garantiavtal.</span><span class="sxs-lookup"><span data-stu-id="73a4e-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="73a4e-119">I fältet **Servicenivå** väljer du en servicenivå som anger begärans brådskande.</span><span class="sxs-lookup"><span data-stu-id="73a4e-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="73a4e-120">Om du har valt en tillgång i steg 5 kan du använda fälten **felsymptom**, **felområde** och **feltyp** för att skapa en felregistrering.</span><span class="sxs-lookup"><span data-stu-id="73a4e-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="73a4e-121">Om underhållsbegäran har orsakat underhållsstopp, ange startdatum och tid för driftstopp.</span><span class="sxs-lookup"><span data-stu-id="73a4e-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="73a4e-122">Fältet **Startad av** anges automatiskt till ditt namn.</span><span class="sxs-lookup"><span data-stu-id="73a4e-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="73a4e-123">Fältet **Faktisk start** är automatiskt inställt på aktuellt datum och aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="73a4e-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="73a4e-124">Du kan dock ändra värdet som du vill.</span><span class="sxs-lookup"><span data-stu-id="73a4e-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="73a4e-125">I fältet **noteringar** anger du eventuella ytterligare noteringar som krävs.</span><span class="sxs-lookup"><span data-stu-id="73a4e-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="73a4e-126">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-126">Select **OK**.</span></span>

![Skapa underhållsbegäran](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="73a4e-128">Efterföljande behandling av underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="73a4e-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="73a4e-129">När en underhållsbegäran har skapats, men innan den konverteras till en arbetsorder, bör olika information uppdateras på den.</span><span class="sxs-lookup"><span data-stu-id="73a4e-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="73a4e-130">Vanligtvis slutför en planerare eller en annan administrativ medarbetare den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="73a4e-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="73a4e-131">På sidan **alla underhållsbegäran** eller **aktiva underhållsbegäran** väljer du den begäran att arbeta med och väljer sedan **redigera**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="73a4e-132">I informationsvyn kan du uppdatera olika information.</span><span class="sxs-lookup"><span data-stu-id="73a4e-132">In the details view, you can update various information.</span></span> <span data-ttu-id="73a4e-133">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="73a4e-133">Here are some examples:</span></span>

- <span data-ttu-id="73a4e-134">Välj och verifiera tillgången.</span><span class="sxs-lookup"><span data-stu-id="73a4e-134">Select and verify the asset.</span></span> <span data-ttu-id="73a4e-135">Om du måste välja en annan tillgång senare, kan du ange alternativet **tillgång verifierad** till **nej**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="73a4e-136">Välj en ansvarig underhållsarbetsgrupp och/eller en ansvarig underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="73a4e-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="73a4e-137">Mer information om de nödvändiga inställningarna finns i [ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="73a4e-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="73a4e-138">Välj en typ av underhållsjobb och, om denna information är relevant, en relaterad underhållsjobbvariant och en jobbhandel.</span><span class="sxs-lookup"><span data-stu-id="73a4e-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="73a4e-139">Ange geografiska koordinater i fälten **latitud** och **longitud**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="73a4e-140">Alla koordinater som läggs till i en underhållsbegäran överförs automatiskt till en relaterad arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="73a4e-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Uppdatera underhållsbegäran](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="73a4e-142">Om du väljer en tillgång när du skapar en underhållsbegäran kan du lägga till ett fel till tillgången.</span><span class="sxs-lookup"><span data-stu-id="73a4e-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="73a4e-143">När underhållsbegäran har skapats kan du lägga till fler fel, som du behöver.</span><span class="sxs-lookup"><span data-stu-id="73a4e-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="73a4e-144">Om du vill lägga till fel väljer du **tillgångsfel** på sidan **alla underhållsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="73a4e-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
