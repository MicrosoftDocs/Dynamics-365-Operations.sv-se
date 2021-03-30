---
title: Exportera data för dotterbolag till filer
description: I detta ämne beskrivs hur du förbereder export av data från Microsoft Dynamics 365 Finance och sedan importerar den till en konsoliderad juridisk person.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 33c17cc2c1dcaa57244bf0bfaa661b11b221e2f6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205509"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="51563-103">Exportera data för dotterbolag till filer</span><span class="sxs-lookup"><span data-stu-id="51563-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51563-104">Använd sidan **Export** (**Systemadministration \> Arbetsytor \> Import/Export**) för att förbereda export av data för dotterbolagen till filer som sedan kan importeras till en konsoliderad juridisk person.</span><span class="sxs-lookup"><span data-stu-id="51563-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="51563-105">Mer information om processerna för import och export finns i [Översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="51563-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="51563-106">Skapa en juridisk person för konsolideringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="51563-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="51563-107">Mer information om hur du skapar juridiska personer finns i [Skapa en juridisk person](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span><span class="sxs-lookup"><span data-stu-id="51563-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="51563-108">Mer information finns i [Förbered en juridisk person för användning i konsolideringsprocessen](prepare-company-for-consolidation.md) och [Skapa en juridisk person för dotterbolag för konsolidering](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="51563-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="51563-109">Gå till **Konsolideringar \> Exportera företagssaldon**.</span><span class="sxs-lookup"><span data-stu-id="51563-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="51563-110">På sidan **Exportera företagssaldon**, på fliken **Kriterier**, anger du detaljer kring konsolideringen genom att ställa in följande fält.</span><span class="sxs-lookup"><span data-stu-id="51563-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="51563-111">Fält</span><span class="sxs-lookup"><span data-stu-id="51563-111">Field</span></span>                             | <span data-ttu-id="51563-112">beskrivning</span><span class="sxs-lookup"><span data-stu-id="51563-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="51563-113">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="51563-113">Main account</span></span>                      | <span data-ttu-id="51563-114">Ange kontona som ska konsolideras.</span><span class="sxs-lookup"><span data-stu-id="51563-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="51563-115">Lämna det här fältet tomt om du vill inkludera alla konton.</span><span class="sxs-lookup"><span data-stu-id="51563-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="51563-116">Använd konsolideringskonto</span><span class="sxs-lookup"><span data-stu-id="51563-116">Use consolidation account</span></span>         | <span data-ttu-id="51563-117">Om du har angett konsolideringskonton ställer du in det här alternativet på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="51563-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="51563-118">Välj konsolideringskonto från</span><span class="sxs-lookup"><span data-stu-id="51563-118">Select consolidation account from</span></span> | <span data-ttu-id="51563-119">Välj antingen **Huvudkonto** eller **Konsolideringskontogrupp**.</span><span class="sxs-lookup"><span data-stu-id="51563-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="51563-120">Konsolideringskontogrupp</span><span class="sxs-lookup"><span data-stu-id="51563-120">Consolidation account group</span></span>       | <span data-ttu-id="51563-121">Välj en konsolideringskontogrupp för det konsolideringskonto som du har valt.</span><span class="sxs-lookup"><span data-stu-id="51563-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="51563-122">Konsolideringsperiod</span><span class="sxs-lookup"><span data-stu-id="51563-122">Consolidation period</span></span>              | <span data-ttu-id="51563-123">Ange "från och till"-datum för konsolideringen.</span><span class="sxs-lookup"><span data-stu-id="51563-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="51563-124">Inkludera faktiska belopp</span><span class="sxs-lookup"><span data-stu-id="51563-124">Include actual amounts</span></span>            | <span data-ttu-id="51563-125">Ange alternativet som **Ja** om du vill inkludera faktiska belopp.</span><span class="sxs-lookup"><span data-stu-id="51563-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="51563-126">Inkludera budgetbelopp</span><span class="sxs-lookup"><span data-stu-id="51563-126">Include budget amounts</span></span>            | <span data-ttu-id="51563-127">Ange alternativet som **Ja** om du vill inkludera budgetbelopp i konsolideringar.</span><span class="sxs-lookup"><span data-stu-id="51563-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="51563-128">Budgetmodeller</span><span class="sxs-lookup"><span data-stu-id="51563-128">Budget models</span></span>                     | <span data-ttu-id="51563-129">Ange den budgetmodell som ska inkluderas.</span><span class="sxs-lookup"><span data-stu-id="51563-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="51563-130">På fliken **Ekonomiska dimensioner** anger du detaljer för konsolideringen:</span><span class="sxs-lookup"><span data-stu-id="51563-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="51563-131">Anger du den information för ekonomisk dimension som ska föras över från transaktioner i dotterbolaget till transaktioner i konsoliderad juridisk person.</span><span class="sxs-lookup"><span data-stu-id="51563-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="51563-132">Välj ekonomiska dimensioner i listan .</span><span class="sxs-lookup"><span data-stu-id="51563-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="51563-133">Identifiera de korrekta specifikationerna för varje ekonomisk dimension som konsolideras.</span><span class="sxs-lookup"><span data-stu-id="51563-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="51563-134">De tillgängliga alternativen inkluderar **Dimension**, **Gruppdimension**, **Företagskonton** och **Konto**.</span><span class="sxs-lookup"><span data-stu-id="51563-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="51563-135">Med alternativet **Gruppdimension** kan du definiera dimensionsvärdet som används i den grupp med företag som konsolideras.</span><span class="sxs-lookup"><span data-stu-id="51563-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="51563-136">Ange den segmentordning som du vill konsolidera i.</span><span class="sxs-lookup"><span data-stu-id="51563-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="51563-137">Gå till fliken **Juridiska personer** och följ sedan dessa steg för att ange den juridiska person du exporterar:</span><span class="sxs-lookup"><span data-stu-id="51563-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="51563-138">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="51563-138">Select **New**.</span></span>
    2. <span data-ttu-id="51563-139">I fältet **Källa för juridisk person** anger du den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="51563-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="51563-140">Om samma kriterier gäller för flera dotterbolag som finns i databasen, kan du föra över data från dessa dotterbolag till separata exportfiler i en och samma åtgärd:</span><span class="sxs-lookup"><span data-stu-id="51563-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="51563-141">Skapa en rad för respektive juridisk person vars konton ska exporteras till filer.</span><span class="sxs-lookup"><span data-stu-id="51563-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="51563-142">Dessa filer kommer senare att importeras till konsoliderad juridisk person.</span><span class="sxs-lookup"><span data-stu-id="51563-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="51563-143">För varje dotterbolag anger du dess namn och namnet på den exportfil som kommer att skapas under exportjobbet.</span><span class="sxs-lookup"><span data-stu-id="51563-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="51563-144">I fältet **Kontotyp för konverteringsdifferenser** väljer du **Vinst och förlust** eller **Balansräkning**.</span><span class="sxs-lookup"><span data-stu-id="51563-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="51563-145">Ange ett filnamn för exportfilen som ska skapas.</span><span class="sxs-lookup"><span data-stu-id="51563-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="51563-146">Klicka på **OK** om du vill köra exporten.</span><span class="sxs-lookup"><span data-stu-id="51563-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="51563-147">När exporten är slutförd får du ett meddelande som visar antalet poster som sparats i respektive fil.</span><span class="sxs-lookup"><span data-stu-id="51563-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="51563-148">Du kan sedan importera filerna till den konsoliderade juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="51563-148">You can then import the files into the consolidated legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]