---
title: Importera en konfiguration från Lifecycle Services
description: I det här avsnittet beskrivs hur du importerar en ny version av konfiguration av elektronisk rapportering (ER) från Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b58ecb8a7d6f52631dbca7642a4acbcf6ff895a3
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270847"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="f1d15-103">Importera en konfiguration från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="f1d15-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f1d15-104">Detta ämne förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en [konfiguration för elektronisk rapportering (ER)](../general-electronic-reporting.md#Configuration) från [Tillgångsbibliotek på projektnivå](../../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f1d15-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1d15-105">Användningen av LCS som en lagringsdatabas för ER-konfigurationer är [inaktuell](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="f1d15-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="f1d15-106">Mer information finns i [Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)</span><span class="sxs-lookup"><span data-stu-id="f1d15-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="f1d15-107">I det här exemplet ska du välja önskad version av ER-konfigurationen och importera den för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="f1d15-107">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="f1d15-108">För att slutföra dessa steg måste du först slutföra stegen i proceduren [Överföra en konfiguration till Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1d15-108">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="f1d15-109">Du måste också ha tillgång till LCS.</span><span class="sxs-lookup"><span data-stu-id="f1d15-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="f1d15-110">Logga in på programmet med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="f1d15-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="f1d15-111">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="f1d15-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="f1d15-112">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="f1d15-112">System administrator</span></span>

2. <span data-ttu-id="f1d15-113">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="f1d15-114">Välj **konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-114">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="f1d15-115">Kontrollera att den aktuella Dynamics 365 Finance användaren är medlem i det LCS-projekt som innehåller det resursbibliotek som användaren vill kunna få [åtkomst](../../lifecycle-services/asset-library.md#asset-library-support) till för att importera ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f1d15-115">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="f1d15-116">Du har inte åtkomst till ett LCS-projekt från en ER-databas som representerar en annan domän än den domän som används i Finance.</span><span class="sxs-lookup"><span data-stu-id="f1d15-116">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="f1d15-117">Om du försöker kommer en tom lista med LCS-projekt att visas, och du kan inte importera ER-konfigurationer från tillgångsbiblioteket på projektnivå i LCS.</span><span class="sxs-lookup"><span data-stu-id="f1d15-117">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="f1d15-118">Om du vill komma åt tillgångsbibliotek på projektnivå från en ER-databas som används för att importera ER-konfigurationer loggar du in på Finance genom att använda referenserna för en användare som tillhör den innehavare (domän) som den aktuella Finance-instansen har etablerats för.</span><span class="sxs-lookup"><span data-stu-id="f1d15-118">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="f1d15-119">Ta bort en delad version av konfiguration av datamodell</span><span class="sxs-lookup"><span data-stu-id="f1d15-119">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="f1d15-120">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-120">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="f1d15-121">Du skapade den första versionen av en konfigurationsmodell för en datamodell och publicerade den till LCS när du slutförde stegen i [Överför en konfiguration till Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1d15-121">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="f1d15-122">I den här proceduren kommer du ta bort den här versionen av ER-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f1d15-122">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="f1d15-123">Därefter ska du importera den versionen från LCS senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="f1d15-123">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="f1d15-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-124">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="f1d15-125">I det här exemplet väljer du den version av konfigurationen som har status **Delad**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-125">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="f1d15-126">Statusen visar att konfigurationen har publicerats till LCS.</span><span class="sxs-lookup"><span data-stu-id="f1d15-126">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="f1d15-127">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-127">Select **Change status**.</span></span>
4. <span data-ttu-id="f1d15-128">Välj **Upphör**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-128">Select **Discontinue**.</span></span>

    <span data-ttu-id="f1d15-129">Genom att ändra status för den valda versionen från **Delad** till **Upphörd** måste du göra versionen tillgänglig för radering.</span><span class="sxs-lookup"><span data-stu-id="f1d15-129">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="f1d15-130">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-130">Select **OK**.</span></span>
6. <span data-ttu-id="f1d15-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-131">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="f1d15-132">I det här exemplet väljer du den version av konfigurationen som har status **Upphörd**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-132">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="f1d15-133">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-133">Select **Delete**.</span></span>
8. <span data-ttu-id="f1d15-134">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-134">Select **Yes**.</span></span>

    <span data-ttu-id="f1d15-135">Observera att den enda utkastversionen 2 i den valda konfigurationen av datamodell nu är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f1d15-135">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="f1d15-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-136">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="f1d15-137">Importera en delad version av konfiguration av datamodell från LCS</span><span class="sxs-lookup"><span data-stu-id="f1d15-137">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="f1d15-138">Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-138">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="f1d15-139">I avsnittet **Konfigurationsleverantörer** väljer du panelen **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-139">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="f1d15-140">I panelen **Litware, Inc.** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-140">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="f1d15-141">Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="f1d15-141">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="f1d15-142">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-142">Select **Open**.</span></span>

    <span data-ttu-id="f1d15-143">I det här exemplet väljer du databasen **LCS** och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="f1d15-143">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="f1d15-144">Du måste ha [åtkomst](#accessconditions) till LCS-projektet och till tillgångsbiblioteket som du öppnar med den valda ER-databasen.</span><span class="sxs-lookup"><span data-stu-id="f1d15-144">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="f1d15-145">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-145">In the list, mark the selected row.</span></span>

    <span data-ttu-id="f1d15-146">Välj till exempel den första versionen av **Konfiguration av exempelmodell** i versionslistan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-146">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="f1d15-147">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-147">Select **Import**.</span></span>
7. <span data-ttu-id="f1d15-148">Välj **Ja** för att bekräfta importen av den valda versionen från LCS.</span><span class="sxs-lookup"><span data-stu-id="f1d15-148">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="f1d15-149">Ett informationsmeddelande bekräftar att den valda versionen har importerats utan fel.</span><span class="sxs-lookup"><span data-stu-id="f1d15-149">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="f1d15-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-150">Close the page.</span></span>
9. <span data-ttu-id="f1d15-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-151">Close the page.</span></span>
10. <span data-ttu-id="f1d15-152">Välj **konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-152">Select **Configurations**.</span></span>
11. <span data-ttu-id="f1d15-153">Välj **Konfiguration av exempelmodell** i trädet.</span><span class="sxs-lookup"><span data-stu-id="f1d15-153">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="f1d15-154">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d15-154">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="f1d15-155">I det här exemplet väljer du den version av konfigurationen som har status **Delad**.</span><span class="sxs-lookup"><span data-stu-id="f1d15-155">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="f1d15-156">Observera att den enda delade versionen 1 i den valda konfigurationen av datamodell nu också är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f1d15-156">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
