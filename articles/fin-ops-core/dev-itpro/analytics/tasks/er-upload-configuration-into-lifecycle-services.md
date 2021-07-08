---
title: Överför en konfiguration till Lifecycle Services
description: Detta avsnitt förklarar hur du skapar en ny elektronisk rapportkonfiguration (ER) och laddar upp den till Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a8fcf2592bde4901aba703e0cd124b1155dac6
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270569"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="dc2de-103">Överför en konfiguration till Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="dc2de-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dc2de-104">Detta ämne förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny [konfiguration för elektronisk rapportering (ER)](../general-electronic-reporting.md#Configuration) och ladda upp den i [Tillgångsbibliotek på projektnivå](../../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="dc2de-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc2de-105">Användningen av LCS som en lagringsdatabas för ER-konfigurationer är [inaktuell](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="dc2de-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="dc2de-106">Mer information finns i [Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)</span><span class="sxs-lookup"><span data-stu-id="dc2de-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="dc2de-107">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. och överföra den till LCS. Dessa steg kan slutföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="dc2de-107">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="dc2de-108">För att slutföra dessa steg måste du först slutföra stegen i [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="dc2de-108">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="dc2de-109">Du måste också ha tillgång till LCS.</span><span class="sxs-lookup"><span data-stu-id="dc2de-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="dc2de-110">Logga in på programmet med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="dc2de-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="dc2de-111">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="dc2de-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="dc2de-112">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="dc2de-112">System administrator</span></span>

2. <span data-ttu-id="dc2de-113">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="dc2de-114">Välj **Litware, Inc.** och markera den som **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-114">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="dc2de-115">Välj **konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-115">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="dc2de-116">Kontrollera att den aktuella Dynamics 365 Finance användaren är medlem i det LCS-projekt som innehåller [Tillgångsbibliotek](../../lifecycle-services/asset-library.md#asset-library-support) till för att importera ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="dc2de-116">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="dc2de-117">Du har inte åtkomst till ett LCS-projekt från en ER-databas som representerar en annan domän än den domän som används i Finance.</span><span class="sxs-lookup"><span data-stu-id="dc2de-117">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="dc2de-118">Om du försöker kommer en tom lista med LCS-projekt att visas, och du kan inte importera ER-konfigurationer från tillgångsbiblioteket på projektnivå i LCS.</span><span class="sxs-lookup"><span data-stu-id="dc2de-118">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="dc2de-119">Om du vill komma åt tillgångsbibliotek på projektnivå från en ER-databas som används för att importera ER-konfigurationer loggar du in på Finance genom att använda referenserna för en användare som tillhör den innehavare (domän) som den aktuella Finance-instansen har etablerats för.</span><span class="sxs-lookup"><span data-stu-id="dc2de-119">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="dc2de-120">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="dc2de-120">Create a new data model configuration</span></span>

1. <span data-ttu-id="dc2de-121">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-121">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="dc2de-122">På sidan **konfiguration** välj **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-122">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="dc2de-123">I detta exempel skapar du en konfiguration som innehåller en exempeldatamodell för elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="dc2de-123">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="dc2de-124">Denna konfiguration av datamodellen ska överföras till LCS senare.</span><span class="sxs-lookup"><span data-stu-id="dc2de-124">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="dc2de-125">I fältet **Namn** ange **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-125">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="dc2de-126">I fältet **Beskrivning** ange **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-126">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="dc2de-127">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-127">Select **Create configuration**.</span></span>
6. <span data-ttu-id="dc2de-128">Välj **modelldesign** .</span><span class="sxs-lookup"><span data-stu-id="dc2de-128">Select **Model designer**.</span></span>
7. <span data-ttu-id="dc2de-129">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-129">Select **New**.</span></span>
8. <span data-ttu-id="dc2de-130">I fältet **Namn** anger du **Startpunkt**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-130">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="dc2de-131">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-131">Select **Add**.</span></span>
10. <span data-ttu-id="dc2de-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-132">Select **Save**.</span></span>
11. <span data-ttu-id="dc2de-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-133">Close the page.</span></span>
12. <span data-ttu-id="dc2de-134">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-134">Select **Change status**.</span></span>
13. <span data-ttu-id="dc2de-135">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-135">Select **Complete**.</span></span>
14. <span data-ttu-id="dc2de-136">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-136">Select **OK**.</span></span>
15. <span data-ttu-id="dc2de-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-137">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="dc2de-138">Registrera ett nytt databas</span><span class="sxs-lookup"><span data-stu-id="dc2de-138">Register a new repository</span></span>

1. <span data-ttu-id="dc2de-139">Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-139">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="dc2de-140">I avsnittet **Konfigurationsleverantörer** väljer du panelen **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-140">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="dc2de-141">I panelen **Litware, Inc.** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-141">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="dc2de-142">Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="dc2de-142">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="dc2de-143">Välj **Lägg till** för att öppna listrutan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-143">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="dc2de-144">Nu kan du lägga till en ny lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="dc2de-144">You can now add a new repository.</span></span>

5. <span data-ttu-id="dc2de-145">I **konfigurationsdatabas** välj **LCS**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-145">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="dc2de-146">Välj **Skapa databas**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-146">Select **Create repository**.</span></span>
7. <span data-ttu-id="dc2de-147">Ange eller välj ett värde i fältet **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-147">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="dc2de-148">I det här exemplet väljer du önskat LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="dc2de-148">For this example, select the desired LCS project.</span></span> <span data-ttu-id="dc2de-149">Du måste ha [åtkomst](#accessconditions) till projektet.</span><span class="sxs-lookup"><span data-stu-id="dc2de-149">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="dc2de-150">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-150">Select **OK**.</span></span>

    <span data-ttu-id="dc2de-151">Avsluta en ny databaspost.</span><span class="sxs-lookup"><span data-stu-id="dc2de-151">Complete a new repository entry.</span></span>

9. <span data-ttu-id="dc2de-152">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-152">In the list, mark the selected row.</span></span>

    <span data-ttu-id="dc2de-153">I det här exemplet väljer du databasposten **LCS**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-153">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="dc2de-154">Observera att en registrerad databas har markerats av den aktuella providern.</span><span class="sxs-lookup"><span data-stu-id="dc2de-154">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="dc2de-155">Med andra ord kan endast konfigurationer som ägs av den providern placeras i den här databasen och därför överföras till det valda LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="dc2de-155">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="dc2de-156">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-156">Select **Open**.</span></span>

    <span data-ttu-id="dc2de-157">Du öppnar databasen om du vill visa listan över ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="dc2de-157">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="dc2de-158">Om det valda projektet ännu inte har använts för delning av ER-konfigurationer kommer listan att vara tom.</span><span class="sxs-lookup"><span data-stu-id="dc2de-158">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="dc2de-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-159">Close the page.</span></span>
12. <span data-ttu-id="dc2de-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-160">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="dc2de-161">Överför konfigurationer till LCS</span><span class="sxs-lookup"><span data-stu-id="dc2de-161">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="dc2de-162">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-162">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="dc2de-163">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-163">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="dc2de-164">Du måste välja en skapad konfiguration som redan har slutförts.</span><span class="sxs-lookup"><span data-stu-id="dc2de-164">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="dc2de-165">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-165">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="dc2de-166">I det här exemplet väljer du den version av den valda konfigurationen som har status **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-166">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="dc2de-167">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-167">Select **Change status**.</span></span>
5. <span data-ttu-id="dc2de-168">Välj **dela**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-168">Select **Share**.</span></span>

    <span data-ttu-id="dc2de-169">Konfigurationens status ändras från **slutförd** till **delad** när konfigurationen publiceras i LCS.</span><span class="sxs-lookup"><span data-stu-id="dc2de-169">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="dc2de-170">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-170">Select **OK**.</span></span>
7. <span data-ttu-id="dc2de-171">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-171">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="dc2de-172">I det här exemplet väljer du den version av konfigurationen som har status **Delad**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-172">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="dc2de-173">Observera att statusen för den valda versionen har ändrats från **Slutförd** till **Delad**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-173">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="dc2de-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-174">Close the page.</span></span>
9. <span data-ttu-id="dc2de-175">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-175">Select **Repositories**.</span></span>

    <span data-ttu-id="dc2de-176">Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="dc2de-176">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="dc2de-177">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-177">Select **Open**.</span></span>

    <span data-ttu-id="dc2de-178">I det här exemplet väljer du databasen **LCS** och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="dc2de-178">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="dc2de-179">Observera att den valda konfigurationen visas som en tillgång för det valda LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="dc2de-179">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="dc2de-180">Öppna LCS genom att gå till <https://lcs.dynamics.com> .</span><span class="sxs-lookup"><span data-stu-id="dc2de-180">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="dc2de-181">Öppna ett projekt som tidigare användes för registrering av databasen.</span><span class="sxs-lookup"><span data-stu-id="dc2de-181">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="dc2de-182">Öppna resursbiblioteket för projektet.</span><span class="sxs-lookup"><span data-stu-id="dc2de-182">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="dc2de-183">Välj tillgångstypen **GER-konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="dc2de-183">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="dc2de-184">Den ER-konfiguration som du överförde ska visas i listan.</span><span class="sxs-lookup"><span data-stu-id="dc2de-184">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="dc2de-185">Observera att den överförda LCS-konfigurationen kan importeras till en annan instans om leverantörerna har tillgång till det här LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="dc2de-185">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
