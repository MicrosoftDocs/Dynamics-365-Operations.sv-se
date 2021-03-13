---
title: Överför en konfiguration till Lifecycle Services
description: Detta avsnitt förklarar hur du skapar en ny elektronisk rapportkonfiguration (ER) och laddar upp den till Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92fc6d7a8b2508c9a1f7b56ca8115adbd6ae00ea
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092551"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="6df88-103">Överför en konfiguration till Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="6df88-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6df88-104">Detta ämne förklarar hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny [konfiguration för elektronisk rapportering (ER)](../general-electronic-reporting.md#Configuration) och ladda upp den i [Tillgångsbibliotek på projektnivå](../../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6df88-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="6df88-105">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. och överföra den till LCS. Dessa steg kan slutföras i alla företag eftersom ER-konfigureringar delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="6df88-105">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="6df88-106">För att slutföra dessa steg måste du först slutföra stegen i [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="6df88-106">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="6df88-107">Du måste också ha tillgång till LCS.</span><span class="sxs-lookup"><span data-stu-id="6df88-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="6df88-108">Logga in på programmet med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="6df88-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="6df88-109">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="6df88-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="6df88-110">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="6df88-110">System administrator</span></span>

2. <span data-ttu-id="6df88-111">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="6df88-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="6df88-112">Välj **Litware, Inc.** och markera den som **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="6df88-112">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="6df88-113">Välj **konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="6df88-113">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="6df88-114">Kontrollera att den aktuella Dynamics 365 Finance användaren är medlem i det LCS-projekt som innehåller [Tillgångsbibliotek](../../lifecycle-services/asset-library.md#asset-library-support) till för att importera ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="6df88-114">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="6df88-115">Du har inte åtkomst till ett LCS-projekt från en ER-databas som representerar en annan domän än den domän som används i Finance.</span><span class="sxs-lookup"><span data-stu-id="6df88-115">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="6df88-116">Om du försöker kommer en tom lista med LCS-projekt att visas, och du kan inte importera ER-konfigurationer från tillgångsbiblioteket på projektnivå i LCS.</span><span class="sxs-lookup"><span data-stu-id="6df88-116">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="6df88-117">Om du vill komma åt tillgångsbibliotek på projektnivå från en ER-databas som används för att importera ER-konfigurationer loggar du in på Finance genom att använda referenserna för en användare som tillhör den innehavare (domän) som den aktuella Finance-instansen har etablerats för.</span><span class="sxs-lookup"><span data-stu-id="6df88-117">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="6df88-118">Skapa en ny datamodellskonfiguration</span><span class="sxs-lookup"><span data-stu-id="6df88-118">Create a new data model configuration</span></span>

1. <span data-ttu-id="6df88-119">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="6df88-119">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="6df88-120">På sidan **konfiguration** välj **Skapa konfiguration** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6df88-120">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="6df88-121">I detta exempel skapar du en konfiguration som innehåller en exempeldatamodell för elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="6df88-121">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="6df88-122">Denna konfiguration av datamodellen ska överföras till LCS senare.</span><span class="sxs-lookup"><span data-stu-id="6df88-122">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="6df88-123">I fältet **Namn** ange **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="6df88-123">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="6df88-124">I fältet **Beskrivning** ange **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="6df88-124">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="6df88-125">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6df88-125">Select **Create configuration**.</span></span>
6. <span data-ttu-id="6df88-126">Välj **modelldesign** .</span><span class="sxs-lookup"><span data-stu-id="6df88-126">Select **Model designer**.</span></span>
7. <span data-ttu-id="6df88-127">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6df88-127">Select **New**.</span></span>
8. <span data-ttu-id="6df88-128">I fältet **Namn** anger du **Startpunkt**.</span><span class="sxs-lookup"><span data-stu-id="6df88-128">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="6df88-129">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="6df88-129">Select **Add**.</span></span>
10. <span data-ttu-id="6df88-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6df88-130">Select **Save**.</span></span>
11. <span data-ttu-id="6df88-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6df88-131">Close the page.</span></span>
12. <span data-ttu-id="6df88-132">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="6df88-132">Select **Change status**.</span></span>
13. <span data-ttu-id="6df88-133">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="6df88-133">Select **Complete**.</span></span>
14. <span data-ttu-id="6df88-134">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6df88-134">Select **OK**.</span></span>
15. <span data-ttu-id="6df88-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6df88-135">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="6df88-136">Registrera ett nytt databas</span><span class="sxs-lookup"><span data-stu-id="6df88-136">Register a new repository</span></span>

1. <span data-ttu-id="6df88-137">Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="6df88-137">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="6df88-138">I avsnittet **Konfigurationsleverantörer** väljer du panelen **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="6df88-138">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="6df88-139">I panelen **Litware, Inc.** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="6df88-139">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="6df88-140">Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="6df88-140">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="6df88-141">Välj **Lägg till** för att öppna listrutan.</span><span class="sxs-lookup"><span data-stu-id="6df88-141">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="6df88-142">Nu kan du lägga till en ny lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="6df88-142">You can now add a new repository.</span></span>

5. <span data-ttu-id="6df88-143">I **konfigurationsdatabas** välj **LCS**.</span><span class="sxs-lookup"><span data-stu-id="6df88-143">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="6df88-144">Välj **Skapa databas**.</span><span class="sxs-lookup"><span data-stu-id="6df88-144">Select **Create repository**.</span></span>
7. <span data-ttu-id="6df88-145">Ange eller välj ett värde i fältet **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="6df88-145">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="6df88-146">I det här exemplet väljer du önskat LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="6df88-146">For this example, select the desired LCS project.</span></span> <span data-ttu-id="6df88-147">Du måste ha [åtkomst](#accessconditions) till projektet.</span><span class="sxs-lookup"><span data-stu-id="6df88-147">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="6df88-148">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6df88-148">Select **OK**.</span></span>

    <span data-ttu-id="6df88-149">Avsluta en ny databaspost.</span><span class="sxs-lookup"><span data-stu-id="6df88-149">Complete a new repository entry.</span></span>

9. <span data-ttu-id="6df88-150">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="6df88-150">In the list, mark the selected row.</span></span>

    <span data-ttu-id="6df88-151">I det här exemplet väljer du databasposten **LCS**.</span><span class="sxs-lookup"><span data-stu-id="6df88-151">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="6df88-152">Observera att en registrerad databas har markerats av den aktuella providern.</span><span class="sxs-lookup"><span data-stu-id="6df88-152">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="6df88-153">Med andra ord kan endast konfigurationer som ägs av den providern placeras i den här databasen och därför överföras till det valda LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="6df88-153">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="6df88-154">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="6df88-154">Select **Open**.</span></span>

    <span data-ttu-id="6df88-155">Du öppnar databasen om du vill visa listan över ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="6df88-155">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="6df88-156">Om det valda projektet ännu inte har använts för delning av ER-konfigurationer kommer listan att vara tom.</span><span class="sxs-lookup"><span data-stu-id="6df88-156">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="6df88-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6df88-157">Close the page.</span></span>
12. <span data-ttu-id="6df88-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6df88-158">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="6df88-159">Överför konfigurationer till LCS</span><span class="sxs-lookup"><span data-stu-id="6df88-159">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="6df88-160">Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="6df88-160">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="6df88-161">På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Konfiguration av exempelmodell**.</span><span class="sxs-lookup"><span data-stu-id="6df88-161">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="6df88-162">Du måste välja en skapad konfiguration som redan har slutförts.</span><span class="sxs-lookup"><span data-stu-id="6df88-162">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="6df88-163">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="6df88-163">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="6df88-164">I det här exemplet väljer du den version av den valda konfigurationen som har status **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="6df88-164">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="6df88-165">Välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="6df88-165">Select **Change status**.</span></span>
5. <span data-ttu-id="6df88-166">Välj **dela**.</span><span class="sxs-lookup"><span data-stu-id="6df88-166">Select **Share**.</span></span>

    <span data-ttu-id="6df88-167">Konfigurationens status ändras från **slutförd** till **delad** när konfigurationen publiceras i LCS.</span><span class="sxs-lookup"><span data-stu-id="6df88-167">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="6df88-168">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6df88-168">Select **OK**.</span></span>
7. <span data-ttu-id="6df88-169">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="6df88-169">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="6df88-170">I det här exemplet väljer du den version av konfigurationen som har status **Delad**.</span><span class="sxs-lookup"><span data-stu-id="6df88-170">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="6df88-171">Observera att statusen för den valda versionen har ändrats från **Slutförd** till **Delad**.</span><span class="sxs-lookup"><span data-stu-id="6df88-171">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="6df88-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6df88-172">Close the page.</span></span>
9. <span data-ttu-id="6df88-173">Välj **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="6df88-173">Select **Repositories**.</span></span>

    <span data-ttu-id="6df88-174">Du kan nu öppna listan över databaser för konfigurationsleverantören Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="6df88-174">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="6df88-175">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="6df88-175">Select **Open**.</span></span>

    <span data-ttu-id="6df88-176">I det här exemplet väljer du databasen **LCS** och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="6df88-176">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="6df88-177">Observera att den valda konfigurationen visas som en tillgång för det valda LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="6df88-177">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="6df88-178">Öppna LCS genom att gå till <https://lcs.dynamics.com> .</span><span class="sxs-lookup"><span data-stu-id="6df88-178">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="6df88-179">Öppna ett projekt som tidigare användes för registrering av databasen.</span><span class="sxs-lookup"><span data-stu-id="6df88-179">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="6df88-180">Öppna resursbiblioteket för projektet.</span><span class="sxs-lookup"><span data-stu-id="6df88-180">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="6df88-181">Välj tillgångstypen **GER-konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6df88-181">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="6df88-182">Den ER-konfiguration som du överförde ska visas i listan.</span><span class="sxs-lookup"><span data-stu-id="6df88-182">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="6df88-183">Observera att den överförda LCS-konfigurationen kan importeras till en annan instans om leverantörerna har tillgång till det här LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="6df88-183">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>
