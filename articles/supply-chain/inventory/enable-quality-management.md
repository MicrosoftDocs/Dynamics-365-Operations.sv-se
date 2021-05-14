---
title: Aktivera kvalitets- och avvikelsehantering
description: Detta ämne innehåller en översikt över processen för att ställa in och konfigurera kvalitet och avvikelsehanteringsfunktioner i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956264"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="6230c-103">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="6230c-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6230c-104">Detta ämne innehåller en översikt över processen för att ställa in och konfigurera kvalitet och avvikelsehanteringsfunktioner i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6230c-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="6230c-105">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="6230c-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="6230c-106">Följ stegen nedan om du vill aktivera kvalitetshantering i systemet.</span><span class="sxs-lookup"><span data-stu-id="6230c-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="6230c-107">Gå till **Lagerhantering \> Inställningar \> Parametrar för hantering av lager och lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="6230c-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="6230c-108">På fliken **Kvalitetshantering** anger du alternativet **Använd kvalitetshantering** som *Ja*.</span><span class="sxs-lookup"><span data-stu-id="6230c-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="6230c-109">Ange timlön i den lokala valutan i fältet **Timtariff**.</span><span class="sxs-lookup"><span data-stu-id="6230c-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="6230c-110">Timpriset används för beräkning av kostnader för operationer som hör till en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="6230c-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="6230c-111">Timtariffen och de beräknade kostnaderna utgör referensinformation för en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="6230c-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="6230c-112">De påverkar inte andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="6230c-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="6230c-113">Välj **Rapportinställningar**.</span><span class="sxs-lookup"><span data-stu-id="6230c-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="6230c-114">Lägg till nya rader för de olika rapporttyperna och välj sedan den typ av dokument som ska användas för respektive rapport.</span><span class="sxs-lookup"><span data-stu-id="6230c-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="6230c-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6230c-115">Close the page.</span></span>
1. <span data-ttu-id="6230c-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6230c-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="6230c-117">Konfigurationsprocess för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="6230c-117">Quality management configuration process</span></span>

<span data-ttu-id="6230c-118">Innan du kan börja använda funktionerna för kvalitetshantering och generera kvalitetsorder, måste du konfigurera systemet och förutsättningarna.</span><span class="sxs-lookup"><span data-stu-id="6230c-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="6230c-119">Här finns en lista med de steg som måste utföras för att konfigurera kvalitetshanteringen.</span><span class="sxs-lookup"><span data-stu-id="6230c-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="6230c-120">[Aktivera kvalitets- och avvikelsehantering](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="6230c-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="6230c-121">Valfritt: [Konfigurera testinstrument](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="6230c-122">[Konfigurera tester](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="6230c-123">[Konfigurera testvariabler och resultat](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="6230c-124">[Konfigurera testgrupper](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="6230c-125">Valfritt: [Konfigurera kvalitetsgrupper och länka till produkter](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="6230c-126">Valfritt: [Konfigurera kvalitetsassociationer](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="6230c-127">När konfigurationen är klar kan du börja skapa och bearbeta kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="6230c-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="6230c-128">Mer information om hur du skapar och arbetar med kvalitetsorder finns i [Kvalitetsorder](quality-orders.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="6230c-129">Konfigurationsprocess för avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="6230c-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="6230c-130">Innan du kan börja använda hanteringsfunktionerna för avvikelse och generera avvikelser måste du konfigurera systemet och förutsättningarna.</span><span class="sxs-lookup"><span data-stu-id="6230c-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="6230c-131">Här finns en lista med de steg som måste utföras för att konfigurera avvikelsehanteringen.</span><span class="sxs-lookup"><span data-stu-id="6230c-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="6230c-132">[Aktivera kvalitets- och avvikelsehantering](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="6230c-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="6230c-133">[Konfigurera medarbetare som ansvarar för godkännande av avvikelser](quality-responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="6230c-134">[Konfigurera problemtyper](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="6230c-135">[Konfigurera karantänzoner](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="6230c-136">[Konfigurera diagnostyper](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="6230c-137">[Konfigurera funktioner](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="6230c-138">Valfritt: [Konfigurera kvalitetsavgifter](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="6230c-139">När konfigurationen är klar kan du börja skapa och bearbeta avvikelser.</span><span class="sxs-lookup"><span data-stu-id="6230c-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="6230c-140">Mer information om hur du skapar och arbetar med avvikelser finns i [Skapa och bearbeta avvikelser](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="6230c-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6230c-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6230c-141">Additional resources</span></span>

- [<span data-ttu-id="6230c-142">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="6230c-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="6230c-143">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="6230c-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="6230c-144">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="6230c-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
