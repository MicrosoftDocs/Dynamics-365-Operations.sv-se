---
title: Dela ER-konfigurationer i RCS/den globala databasen med externa organisationer
description: Det här avsnittet innehåller information om hur du delar elektroniska rapporteringskonfigurationer (ER) i Microsoft Regulatory Configuration Services (RCS)/den globala databasen direkt med externa organisationer.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0973d36a8fddd16d02776ac6567d424ac6ebc3ae
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994324"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="ffd39-103">Dela elektroniska rapporteringskonfigurationer (ER) i Microsoft Regulatory Configuration Services (RCS)/den globala databasen med externa organisationer</span><span class="sxs-lookup"><span data-stu-id="ffd39-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffd39-104">Du kan använda Microsoft RCS (Regulatoryr Configuration Services) för att dela konfigurationer för elektronisk rapportering (ER) och sedan publicera dem i externa organisationer.</span><span class="sxs-lookup"><span data-stu-id="ffd39-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="ffd39-105">Följande procedurer förklarar hur en RCS-användare kan dela en version av en ER-konfiguration som har konfigurerats i en RCS-instans med en extern organisation.</span><span class="sxs-lookup"><span data-stu-id="ffd39-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="ffd39-106">Innan du kan slutföra dessa procedurer måste du först uppfylla följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="ffd39-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="ffd39-107">Öppna en RCS-instans.</span><span class="sxs-lookup"><span data-stu-id="ffd39-107">Access an RCS instance.</span></span>
- <span data-ttu-id="ffd39-108">Skapa en aktiv konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="ffd39-108">Create an active configuration provider.</span></span> <span data-ttu-id="ffd39-109">Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="ffd39-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="ffd39-110">Skapa och överför en ny version av en ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ffd39-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="ffd39-111">Mer information finns i [Skapa och överföra en ny version av en konfiguration för elektronisk rapportering (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="ffd39-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="ffd39-112">Du måste också säkerställa att en RCS-miljö har etablerats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="ffd39-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="ffd39-113">I en Finance and Operations-app går du till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ffd39-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="ffd39-114">Om ingen RCS-miljö har etablerats för ditt företag väljer du **Regulatory services – extern konfiguration** och följer sedan instruktionerna för att etablera en.</span><span class="sxs-lookup"><span data-stu-id="ffd39-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="ffd39-115">Om en RCS-miljö redan har etablerats för ditt företag kan du använda sidans URL för att komma åt den genom att välja alternativet för inloggning.</span><span class="sxs-lookup"><span data-stu-id="ffd39-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="ffd39-116">Kontrollera konfigurationen du vill dela</span><span class="sxs-lookup"><span data-stu-id="ffd39-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="ffd39-117">Följ dessa steg för att kontrollera att konfigurationen som du vill dela redan har överförts till den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="ffd39-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="ffd39-118">I arbetsytan **Elektronisk rapportering** väljer du **Databaser** för din konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="ffd39-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Konfigurationsleverantörer](media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="ffd39-120">Välj **Global databas** \> **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="ffd39-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="ffd39-121">Sök efter den konfiguration du vill dela.</span><span class="sxs-lookup"><span data-stu-id="ffd39-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="ffd39-122">Du kan använda filterfältet för att begränsa sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="ffd39-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="ffd39-123">Om du inte kan hitta konfigurationen i den globala databasen följer du stegen i [Skapa och ladda upp en ny version av en konfiguration för elektronisk rapportering (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="ffd39-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="ffd39-124">Dela ER-konfigurationer med externa organisationer</span><span class="sxs-lookup"><span data-stu-id="ffd39-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="ffd39-125">När en konfiguration har skapats i din konfigurationsleverantör kan du dela den direkt med externa organisationer genom att använda snabbfliken **Delas med** på sidan **Global konfigurationsdatabas**.</span><span class="sxs-lookup"><span data-stu-id="ffd39-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="ffd39-126">I arbetsytan **Elektronisk rapportering** väljer du **Databaser** för din konfigurationsleverantör.</span><span class="sxs-lookup"><span data-stu-id="ffd39-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="ffd39-127">Välj **Global databas** \> **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="ffd39-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="ffd39-128">Välj den konfiguration du vill dela.</span><span class="sxs-lookup"><span data-stu-id="ffd39-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="ffd39-129">I snabbfliken **Delas med** väljer du **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="ffd39-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Delas med snabbfliken](media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="ffd39-131">I dialogrutan anger du domännamnet för den externa organisationen och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffd39-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Dela konfigurationsversion med dialogrutan för extern organisation](media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="ffd39-133">Konfigurationen delas med den externa organisationen och är tillgänglig för den organisationen i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="ffd39-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="ffd39-134">Därifrån kan den importeras till organisationens instans av RCS eller till dess instanser av Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="ffd39-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

6. <span data-ttu-id="ffd39-135">Om du vill ta bort delning av en konfiguration som tidigare har delats med en extern organisation, markerar du konfigurationen och klickar på **Ta bort delning** innan du väljer **OK**</span><span class="sxs-lookup"><span data-stu-id="ffd39-135">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>
