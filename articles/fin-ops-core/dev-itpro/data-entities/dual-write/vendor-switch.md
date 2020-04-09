---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: ffd7a4c01810578b4abb6942aeff76e5147fafa9
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173049"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="0e727-103">Växla mellan leverantörsdesigner</span><span class="sxs-lookup"><span data-stu-id="0e727-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="0e727-104">Leveranstörsdataflöde</span><span class="sxs-lookup"><span data-stu-id="0e727-104">Vendor data flow</span></span> 

<span data-ttu-id="0e727-105">Om du väljer att använda entiteten **Konto** för att lagra leverantörer av typen **Organisation** och entiteten **Kontakt** för att lagra leverantörer av typen **Person** konfigurerar du följande arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="0e727-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="0e727-106">I annat fall är den här konfigurationen inte obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="0e727-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="0e727-107">Använd den utökade leverantörsutformningen för leverantörer av typen organisation</span><span class="sxs-lookup"><span data-stu-id="0e727-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="0e727-108">Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser.</span><span class="sxs-lookup"><span data-stu-id="0e727-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="0e727-109">Du ska skapa ett arbetsflöde för varje mall.</span><span class="sxs-lookup"><span data-stu-id="0e727-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="0e727-110">Skapa leverantörer i entiteten konton</span><span class="sxs-lookup"><span data-stu-id="0e727-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="0e727-111">Skapa leverantörer i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="0e727-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="0e727-112">Uppdatera leverantörer i entiteten konton</span><span class="sxs-lookup"><span data-stu-id="0e727-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="0e727-113">Uppdatera leverantörer i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="0e727-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="0e727-114">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="0e727-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="0e727-115">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer i entiteten konton**.</span><span class="sxs-lookup"><span data-stu-id="0e727-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="0e727-116">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e727-116">Then select **OK**.</span></span> <span data-ttu-id="0e727-117">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="0e727-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Arbetsflödesprocess Skapa leverantörer i entiteten konton](media/create_process.png)

2. <span data-ttu-id="0e727-119">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i entiteten konton**.</span><span class="sxs-lookup"><span data-stu-id="0e727-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="0e727-120">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e727-120">Then select **OK**.</span></span> <span data-ttu-id="0e727-121">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="0e727-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="0e727-122">Skapa en ny arbetsflödesprocess för entiteten **Konto** och välj arbetsflödesprocessmallen **Skapa leverantörer i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="0e727-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="0e727-123">Skapa en ny arbetsflödesprocess för entiteten **Konto** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="0e727-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="0e727-124">Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav.</span><span class="sxs-lookup"><span data-stu-id="0e727-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="0e727-125">Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="0e727-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Knappen Konvertera till ett arbetsflöde i bakgrunden](media/background_workflow.png)

6. <span data-ttu-id="0e727-127">Aktivera de arbetsflöden som du skapade för entiteterna **konto** och **leverantör** för att börja använda entiteten **Konto** för att lagra leverantörsinformation av typen **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="0e727-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="0e727-128">Använd den utökade leverantörsutformningen för leverantörer av typen person</span><span class="sxs-lookup"><span data-stu-id="0e727-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="0e727-129">Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser.</span><span class="sxs-lookup"><span data-stu-id="0e727-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="0e727-130">Du ska skapa ett arbetsflöde för varje mall.</span><span class="sxs-lookup"><span data-stu-id="0e727-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="0e727-131">Skapa leverantörer av typen person i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="0e727-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="0e727-132">Skapa leverantörer av typen person i entiteten kontakt</span><span class="sxs-lookup"><span data-stu-id="0e727-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="0e727-133">Uppdatera leverantörer av typen person i entiteten kontakt</span><span class="sxs-lookup"><span data-stu-id="0e727-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="0e727-134">Uppdatera leverantörer av typen person i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="0e727-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="0e727-135">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="0e727-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="0e727-136">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i entiteten kontakt**.</span><span class="sxs-lookup"><span data-stu-id="0e727-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="0e727-137">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e727-137">Then select **OK**.</span></span> <span data-ttu-id="0e727-138">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="0e727-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="0e727-139">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i entiteten kontakt**.</span><span class="sxs-lookup"><span data-stu-id="0e727-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="0e727-140">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e727-140">Then select **OK**.</span></span> <span data-ttu-id="0e727-141">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="0e727-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="0e727-142">Skapa en ny arbetsflödesprocess för entiteten **Kontakt** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="0e727-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="0e727-143">Skapa en ny arbetsflödesprocess för entiteten **Kontakt** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="0e727-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="0e727-144">Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav.</span><span class="sxs-lookup"><span data-stu-id="0e727-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="0e727-145">Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="0e727-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="0e727-146">Aktivera de arbetsflöden som du skapade för entiteterna **Kontakt** och **leverantör** för att börja använda entiteten **Kontakt** för att lagra leverantörsinformation av typen **Person**.</span><span class="sxs-lookup"><span data-stu-id="0e727-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
