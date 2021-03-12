---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar integreringen av leverantörsdata mellan Finance and Operations-appar och Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: d2c22123d5f05945b34eb107c5b912852aec387a
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744475"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="04fa5-103">Växla mellan leverantörsdesigner</span><span class="sxs-lookup"><span data-stu-id="04fa5-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="04fa5-104">Leveranstörsdataflöde</span><span class="sxs-lookup"><span data-stu-id="04fa5-104">Vendor data flow</span></span> 

<span data-ttu-id="04fa5-105">Om du väljer att använda tabellen **Konto** för att lagra leverantörer av typen **Organisation** och tabellen **Kontakt** för att lagra leverantörer av typen **Person** konfigurerar du följande arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="04fa5-105">If you choose to use the **Account** table to store vendors of the **Organization** type and the **Contact** table to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="04fa5-106">I annat fall är den här konfigurationen inte obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="04fa5-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="04fa5-107">Använd den utökade leverantörsutformningen för leverantörer av typen organisation</span><span class="sxs-lookup"><span data-stu-id="04fa5-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="04fa5-108">Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser.</span><span class="sxs-lookup"><span data-stu-id="04fa5-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="04fa5-109">Du ska skapa ett arbetsflöde för varje mall.</span><span class="sxs-lookup"><span data-stu-id="04fa5-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="04fa5-110">Skapa leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="04fa5-110">Create Vendors in Accounts Table</span></span>
+ <span data-ttu-id="04fa5-111">Skapa leverantörer i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="04fa5-111">Create Vendors in Vendors Table</span></span>
+ <span data-ttu-id="04fa5-112">Uppdatera leverantörer i tabellen Konton</span><span class="sxs-lookup"><span data-stu-id="04fa5-112">Update Vendors in Accounts Table</span></span>
+ <span data-ttu-id="04fa5-113">Uppdatera leverantörer i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="04fa5-113">Update Vendors in Vendors Table</span></span>

<span data-ttu-id="04fa5-114">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="04fa5-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="04fa5-115">Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer i tabellen Konton**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-115">Create a workflow process for the **Vendor** table, and select the **Create Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="04fa5-116">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-116">Then select **OK**.</span></span> <span data-ttu-id="04fa5-117">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för tabellen **konto**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-117">This workflow handles the vendor creation scenario for the **Account** table.</span></span>

    ![Arbetsflödesprocess Skapa leverantörer i tabellen Konton](media/create_process.png)

2. <span data-ttu-id="04fa5-119">Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i tabellen Konton**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-119">Create a workflow process for the **Vendor** table, and select the **Update Vendors in Accounts Table** workflow process template.</span></span> <span data-ttu-id="04fa5-120">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-120">Then select **OK**.</span></span> <span data-ttu-id="04fa5-121">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för tabellen **konto**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-121">This workflow handles the vendor update scenario for the **Account** table.</span></span>
3. <span data-ttu-id="04fa5-122">Skapa en ny arbetsflödesprocess för tabellen **Konto** och välj arbetsflödesprocessmallen **Skapa leverantörer i tabellen leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-122">Create a workflow process for the **Account** table, and select the **Create Vendors in Vendors Table** workflow process template.</span></span>
4. <span data-ttu-id="04fa5-123">Skapa en ny arbetsflödesprocess för tabellen **Konto** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i tabellen leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-123">Create a workflow process for the **Account** table, and select the **Update Vendors in Vendors Table** workflow process template.</span></span>
5. <span data-ttu-id="04fa5-124">Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav.</span><span class="sxs-lookup"><span data-stu-id="04fa5-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="04fa5-125">Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Knappen Konvertera till ett arbetsflöde i bakgrunden](media/background_workflow.png)

6. <span data-ttu-id="04fa5-127">Aktivera de arbetsflöden som du skapade för tabellerna **Konto** och **Leverantör** för att börja använda tabellen **Konto** för att lagra leverantörsinformation av typen **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-127">Activate the workflows that you created for the **Account** and **Vendor** tables to start to use the **Account** table to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="04fa5-128">Använd den utökade leverantörsutformningen för leverantörer av typen person</span><span class="sxs-lookup"><span data-stu-id="04fa5-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="04fa5-129">Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser.</span><span class="sxs-lookup"><span data-stu-id="04fa5-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="04fa5-130">Du ska skapa ett arbetsflöde för varje mall.</span><span class="sxs-lookup"><span data-stu-id="04fa5-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="04fa5-131">Skapa leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="04fa5-131">Create Vendors of type Person in Vendors Table</span></span>
+ <span data-ttu-id="04fa5-132">Skapa leverantörer av typen person i tabellen Kontakter</span><span class="sxs-lookup"><span data-stu-id="04fa5-132">Create Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="04fa5-133">Uppdatera leverantörer av typen person i tabellen Kontakter</span><span class="sxs-lookup"><span data-stu-id="04fa5-133">Update Vendors of type Person in Contacts Table</span></span>
+ <span data-ttu-id="04fa5-134">Uppdatera leverantörer av typen person i tabellen Leverantörer</span><span class="sxs-lookup"><span data-stu-id="04fa5-134">Update Vendors of type Person in Vendors Table</span></span>

<span data-ttu-id="04fa5-135">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="04fa5-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="04fa5-136">Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i tabellen Kontakter**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-136">Create a workflow process for the **Vendor** table, and select the **Create Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="04fa5-137">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-137">Then select **OK**.</span></span> <span data-ttu-id="04fa5-138">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för tabellen **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-138">This workflow handles the vendor creation scenario for the **Contact** table.</span></span>
2. <span data-ttu-id="04fa5-139">Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i tabellen Kontakter**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-139">Create a workflow process for the **Vendor** table, and select the **Update Vendors of type Person in Contacts Table** workflow process template.</span></span> <span data-ttu-id="04fa5-140">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-140">Then select **OK**.</span></span> <span data-ttu-id="04fa5-141">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för tabellen **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-141">This workflow handles the vendor update scenario for the **Contact** table.</span></span>
3. <span data-ttu-id="04fa5-142">Skapa en ny arbetsflödesprocess för tabellen **Kontakt** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i tabellen Leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-142">Create a workflow process for the **Contact** table, and select the **Create Vendors of type Person in Vendors Table** template.</span></span>
4. <span data-ttu-id="04fa5-143">Skapa en ny arbetsflödesprocess för tabellen **Kontakt** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i tabellen Leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-143">Create a workflow process for the **Contact** table, and select the **Update Vendors of type Person in Vendors Table** template.</span></span>
5. <span data-ttu-id="04fa5-144">Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav.</span><span class="sxs-lookup"><span data-stu-id="04fa5-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="04fa5-145">Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="04fa5-146">Aktivera de arbetsflöden som du skapade för tabellerna **Kontakt** och **Leverantör** för att börja använda tabellen **Kontakt** för att lagra leverantörsinformation av typen **Person**.</span><span class="sxs-lookup"><span data-stu-id="04fa5-146">Activate the workflows that you created on the **Contact** and **Vendor** tables to start to use the **Contact** table to store information for vendors of the **Person** type.</span></span>
