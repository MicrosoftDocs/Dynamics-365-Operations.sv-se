---
title: Importera uppdaterade versioner av ER-konfigurationer
description: I det här avsnittet beskrivs hur du importerar uppdaterade versioner av konfigurationer av elektronisk rapportering (ER) från den globala lagringsplatsen för konfigurationstjänsten.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 1e021105c19273db5ded7cb0902eca1d502ced8e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753370"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="50a66-103">Importera uppdaterade versioner av ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="50a66-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50a66-104">Elektronisk rapportering (ER) [databaser](general-electronic-reporting.md#Repository) används för att dela [ER-konfigurationer](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="50a66-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="50a66-105">Du kan [Importera](download-electronic-reporting-configuration-lcs.md) ER-konfigurationer från olika databaser till din instans av Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="50a66-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="50a66-106">När du importerar ER-konfigurationer kan [konfigurationsprovidern](general-electronic-reporting.md#Provider) publicera nya databaser för [versioner](general-electronic-reporting.md#component-versioning) så att de kan delas.</span><span class="sxs-lookup"><span data-stu-id="50a66-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="50a66-107">I det här avsnittet beskrivs hur du importerar uppdaterade versioner av ER-konfigurationer från den globala lagringsplatsen för konfigurationstjänsten.</span><span class="sxs-lookup"><span data-stu-id="50a66-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="50a66-108">Mer information finns i [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, konfigurationstjänst](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="50a66-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="50a66-109">Granska tillgängliga uppdaterade versioner</span><span class="sxs-lookup"><span data-stu-id="50a66-109">Review the available updated versions</span></span>

1. <span data-ttu-id="50a66-110">Logga in på Finance med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="50a66-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="50a66-111">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="50a66-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="50a66-112">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="50a66-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="50a66-113">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="50a66-113">System administrator</span></span>

2. <span data-ttu-id="50a66-114">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="50a66-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="50a66-115">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Importera uppdateringar av konfigurationsversioner**.</span><span class="sxs-lookup"><span data-stu-id="50a66-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Sidan lokaliseringskonfigurationer](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="50a66-117">I dialogrutan **Importera uppdateringar av konfigurationsversioner för elektronisk rapportering** i fältet **Körläge** välj **Visa endast tillgängliga uppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="50a66-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="50a66-118">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="50a66-118">Then select **OK**.</span></span> 

    ![Fältet körläge är inställt på att endast visa tillgängliga uppdateringar](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="50a66-120">Granska de meddelanden som du får.</span><span class="sxs-lookup"><span data-stu-id="50a66-120">Review the messages that you receive.</span></span> <span data-ttu-id="50a66-121">Dessa meddelanden innehåller följande information om ER-konfigurationer i den aktuella Finance-instansen och hur de jämförs med innehållet i den globala databasen:</span><span class="sxs-lookup"><span data-stu-id="50a66-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="50a66-122">Totalt antal ER-konfigurationer</span><span class="sxs-lookup"><span data-stu-id="50a66-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="50a66-123">ER-konfigurationer som inte finns i den globala databasen</span><span class="sxs-lookup"><span data-stu-id="50a66-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="50a66-124">ER-konfigurationer för vilka den senaste versionen redan finns tillgänglig i den aktuella Finance-instansen (om du vill visa den fullständiga listan med dessa ER-konfigurationer väljer du länken **Meddelandeinformation** .)</span><span class="sxs-lookup"><span data-stu-id="50a66-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Meddelandet "De senaste versionerna av följande konfigurationer har redan importerats" och meddelandeinformation](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="50a66-126">ER-konfigurationer för vilka den senaste versionen finns tillgänglig i den globala databasen kan importeras till den aktuella Finance-instansen (om du vill visa den fullständiga listan med dessa ER-konfigurationer väljer du länken **Meddelandeinformation** .)</span><span class="sxs-lookup"><span data-stu-id="50a66-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Meddelandet "Tillgängliga uppdateringar" och meddelandeinformation](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="50a66-128">Importera tillgängliga uppdaterade versioner</span><span class="sxs-lookup"><span data-stu-id="50a66-128">Import available updated versions</span></span>

1. <span data-ttu-id="50a66-129">Logga in på Finance med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="50a66-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="50a66-130">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="50a66-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="50a66-131">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="50a66-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="50a66-132">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="50a66-132">System administrator</span></span>

2. <span data-ttu-id="50a66-133">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="50a66-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="50a66-134">På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Importera uppdateringar av konfigurationsversioner**.</span><span class="sxs-lookup"><span data-stu-id="50a66-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="50a66-135">I dialogrutan **Importera uppdateringar av konfigurationsversioner för elektronisk rapportering** i fältet **Körläge** väljer du **Importera senaste uppdateringar** för att importera de senaste versionerna av ER-konfigurationer från den globala databasen till den aktuella Finance-instansen.</span><span class="sxs-lookup"><span data-stu-id="50a66-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="50a66-136">Om du vill tidsplanera ett batchjobb för importen, på snabbfliken **Kör i bakgrunden** anger du alternativet **Batchbearbetning** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="50a66-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="50a66-137">Om du vill upprepa importen regelbundet måste du konfigurera den nödvändiga återupprepningen.</span><span class="sxs-lookup"><span data-stu-id="50a66-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Fältet körläge har angetts för import av de senaste uppdateringarna](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="50a66-139">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="50a66-139">Select **OK**.</span></span>
7. <span data-ttu-id="50a66-140">Gör något av följande om du vill veta vilka konfigurationsversioner som har importerats:</span><span class="sxs-lookup"><span data-stu-id="50a66-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="50a66-141">Om du kör importen interaktivt i stället för att använda ett batchjobb kan du granska de meddelanden som du får.</span><span class="sxs-lookup"><span data-stu-id="50a66-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Mottagna meddelanden under en interaktiv importkörning](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="50a66-143">Gör så här om du kör kommandot Importera i batchläge:</span><span class="sxs-lookup"><span data-stu-id="50a66-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="50a66-144">Gå till **Vanlig** \> **Förfrågningar** \> **Batchjobb** \> **Mina batchjobb**.</span><span class="sxs-lookup"><span data-stu-id="50a66-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="50a66-145">Sök och markera jobbet **Importera uppdateringar av konfigurationsversioner för elektronisk rapportering** och sedan i åtgärdsfönstret väljer du fliken **Batchjobb**, välj **Historik över batchjobb** för att visa jobbhistoriken.</span><span class="sxs-lookup"><span data-stu-id="50a66-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="50a66-146">På sidan **Historik över batchjobb**, välj **Logg**.</span><span class="sxs-lookup"><span data-stu-id="50a66-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="50a66-147">I meddelandet som du tar emot väljer du länken **Meddelandeinformation** för att visa jobbloggen.</span><span class="sxs-lookup"><span data-stu-id="50a66-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Jobblogg](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="50a66-149">Vi rekommenderar inte att du schemalägger ett återkommande batchjobb för att importera uppdaterade versioner av ER-konfigurationer direkt från den globala databasen till en produktionsmiljö, eftersom de importerade versionerna omedelbart kommer att vara tillgängliga för användning.</span><span class="sxs-lookup"><span data-stu-id="50a66-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="50a66-150">Använd i stället den här metoden för att distribuera versioner av ER-konfigurationer till en begränsad miljö.</span><span class="sxs-lookup"><span data-stu-id="50a66-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="50a66-151">De kan sedan utvärderas i begränsat läge innan de distribueras till en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="50a66-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50a66-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="50a66-152">Additional resources</span></span>

- [<span data-ttu-id="50a66-153">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="50a66-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="50a66-154">Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster</span><span class="sxs-lookup"><span data-stu-id="50a66-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]