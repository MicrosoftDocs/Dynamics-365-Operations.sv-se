---
title: Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster
description: I det här avsnittet beskrivs hur du hämtar konfigurationer av elektronisk rapportering (ER) från den globala lagringsplatsen för konfigurationstjänsten.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a96e78a64fe0559ae5f3bfddabf3fe1cad8a3dcb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679568"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="05b48-103">Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster</span><span class="sxs-lookup"><span data-stu-id="05b48-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05b48-104">I det här avsnittet beskrivs hur du hämtar [konfigurationer av elektronisk rapportering](general-electronic-reporting.md#Configuration) från den globala lagringsplatsen för konfigurationstjänsten.</span><span class="sxs-lookup"><span data-stu-id="05b48-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="05b48-105">Mer information finns i [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, konfigurationstjänst](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="05b48-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="05b48-106">Öppna konfigurationsdatabas</span><span class="sxs-lookup"><span data-stu-id="05b48-106">Open configurations repository</span></span>

1. <span data-ttu-id="05b48-107">Logga in på programmet Dynamics 365 Finance med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="05b48-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="05b48-108">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="05b48-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="05b48-109">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="05b48-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="05b48-110">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="05b48-110">System administrator</span></span>

2. <span data-ttu-id="05b48-111">Gå till **Organisationsadministration > Arbetsytor > Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="05b48-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="05b48-112">I avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="05b48-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="05b48-113">I panelen **Microsoft** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="05b48-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Arbetsytan för elektronisk rapportering](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="05b48-115">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **Global**-typen.</span><span class="sxs-lookup"><span data-stu-id="05b48-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="05b48-116">Om denna databas inte visas i rutnätet, följ då nedanstående steg:</span><span class="sxs-lookup"><span data-stu-id="05b48-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="05b48-117">Välj **Lägg till** för att lägga till en ny databas.</span><span class="sxs-lookup"><span data-stu-id="05b48-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="05b48-118">Välj **Global** som databastyp och välj sedan **skapa databas**.</span><span class="sxs-lookup"><span data-stu-id="05b48-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="05b48-119">Följ autoriseringsinstruktionerna om du uppmanas.</span><span class="sxs-lookup"><span data-stu-id="05b48-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="05b48-120">Ange ett namn och en beskrivning för databasen och välj sedan **OK** för att bekräfta den nya databasposten.</span><span class="sxs-lookup"><span data-stu-id="05b48-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="05b48-121">I rutnätet väljer du den nya databasen för **Global**-typen.</span><span class="sxs-lookup"><span data-stu-id="05b48-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="05b48-122">Välj **Öppna** om du vill visa listan över ER-konfigurationer för den valda databasen.</span><span class="sxs-lookup"><span data-stu-id="05b48-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Sidan Konfigurationsdatabas](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="05b48-124">Importera en enda konfiguration</span><span class="sxs-lookup"><span data-stu-id="05b48-124">Import a single configuration</span></span>

1. <span data-ttu-id="05b48-125">På sidan **Konfigurationsdatabas** i konfigurationsträdet, välj den ER-konfiguration du vill ha.</span><span class="sxs-lookup"><span data-stu-id="05b48-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="05b48-126">I snabbfliken **Versioner** väljer du erforderlig version för vald ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="05b48-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="05b48-127">Välj **Importera** för att hämta den valda versionen från den globala databasen till den aktuella Finance-instansen.</span><span class="sxs-lookup"><span data-stu-id="05b48-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05b48-128">Knappen **Importera** är inte tillgänglig för ER-konfigurationsversioner som redan finns i den aktuella Finance-instansen.</span><span class="sxs-lookup"><span data-stu-id="05b48-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Sidan Konfigurationsdatabas](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="05b48-130">Importera filtrerade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="05b48-130">Import filtered configurations</span></span>

1. <span data-ttu-id="05b48-131">På sidan **konfigurationsdatabaser** i konfigurationsträdet expanderar du snabbfliken **Filter**.</span><span class="sxs-lookup"><span data-stu-id="05b48-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="05b48-132">I rutnätet **Taggar** som behövs i taggarna.</span><span class="sxs-lookup"><span data-stu-id="05b48-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="05b48-133">I fältet **Tillämplighet för land/region**, välj lämpliga land/regionskoder och sedan **Använd filter**.</span><span class="sxs-lookup"><span data-stu-id="05b48-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05b48-134">På snabbfliken **konfigurationer** visas alla konfigurationer som uppfyller de angivna villkoren för urval.</span><span class="sxs-lookup"><span data-stu-id="05b48-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="05b48-135">På snabbfliken **konfigurationer** välj **Importera** om du vill hämta de filtrerade konfigurationerna från den globala databasen till den aktuella instansen.</span><span class="sxs-lookup"><span data-stu-id="05b48-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="05b48-136">På snabbfliken **konfigurationer** välj **Återställ filter** för att rensa de angivna villkoren för urval.</span><span class="sxs-lookup"><span data-stu-id="05b48-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Sidan Konfigurationsdatabas](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="05b48-138">Beroende på ER-inställningarna valideras konfigurationerna när de har importerats.</span><span class="sxs-lookup"><span data-stu-id="05b48-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="05b48-139">Du kan komma att meddelas om eventuella inkonsekvensproblem som upptäcks.</span><span class="sxs-lookup"><span data-stu-id="05b48-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="05b48-140">Innan du kan använda den importerade konfigurationsversionen måste du lösa problemen.</span><span class="sxs-lookup"><span data-stu-id="05b48-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="05b48-141">Mer information finns i listan över relaterade resurser för detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="05b48-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="05b48-142">ER-konfigurationer kan konfigureras som beroende på andra konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="05b48-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="05b48-143">Tillsammans med en vald konfiguration kan även andra konfigurationer importeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="05b48-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="05b48-144">Mer information om konfigurationsberoenden finns i [definiera beroendet för ER-konfigurationer i andra komponenter](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="05b48-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05b48-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="05b48-145">Additional resources</span></span>

[<span data-ttu-id="05b48-146">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="05b48-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
