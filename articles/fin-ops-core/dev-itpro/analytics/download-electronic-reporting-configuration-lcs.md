---
title: Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services
description: Detta avsnitt innehåller information om hur du hämtar elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 14f0f2b1a4d63101d432b1361379c61a70ac9345
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271193"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="b6c46-103">Hämta konfigurationer för elektronisk rapportering från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="b6c46-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6c46-104">I det här avsnittet beskrivs hur du hämtar den senaste versionen av dina [Elektronisk rapportering (ER) konfigurationer](general-electronic-reporting.md#Configuration) från [biblioteket med gemensamma tillgångar](../lifecycle-services/asset-library.md) i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b6c46-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6c46-105">Användningen av LCS som en lagringsdatabas för ER-konfigurationer är [inaktuell](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="b6c46-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="b6c46-106">Mer information finns i [Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md)</span><span class="sxs-lookup"><span data-stu-id="b6c46-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

1. <span data-ttu-id="b6c46-107">Logga in på programmet med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="b6c46-107">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="b6c46-108">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="b6c46-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="b6c46-109">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="b6c46-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="b6c46-110">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="b6c46-110">System administrator</span></span>

2. <span data-ttu-id="b6c46-111">Gå till **Organisationsadministration** &gt; **Arbetsytor** &gt; **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="b6c46-111">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="b6c46-112">I avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b6c46-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="b6c46-113">I panelen **Microsoft** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="b6c46-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="b6c46-114">[![Microsoft-panel på sidan lokaliseringskonfiguration](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="b6c46-114">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="b6c46-115">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **LCS**-typen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="b6c46-116">Om denna databas inte visas i rutnätet, följ då nedanstående steg:</span><span class="sxs-lookup"><span data-stu-id="b6c46-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="b6c46-117">Välj **Lägg till** för att lägga till en databas.</span><span class="sxs-lookup"><span data-stu-id="b6c46-117">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="b6c46-118">Välj **LCS** som databastyp.</span><span class="sxs-lookup"><span data-stu-id="b6c46-118">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="b6c46-119">Välj **Skapa databas**.</span><span class="sxs-lookup"><span data-stu-id="b6c46-119">Select **Create repository**.</span></span>
    4. <span data-ttu-id="b6c46-120">Om du tillfrågas om auktorisering följer du instruktionerna på skärmen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-120">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="b6c46-121">Skriv ett namn och en beskrivning för databasen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-121">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="b6c46-122">Klicka på **OK** för att bekräfta den nya databasposten.</span><span class="sxs-lookup"><span data-stu-id="b6c46-122">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="b6c46-123">I rutnätet väljer du den nya databasen för **LCS**-typen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-123">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="b6c46-124">Välj **Öppna** om du vill visa listan över ER-konfigurationer för den valda databasen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-124">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="b6c46-125">[![Sidan Konfigurationsdatabas](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="b6c46-125">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="b6c46-126">Om du har problem med att komma åt LCS-databasen för hämtning av konfigurationer från biblioteket med gemensamma tillgångar i LCS kan du i stället hämta konfigurationer från den [globala databasen](er-download-configurations-global-repo.md) .</span><span class="sxs-lookup"><span data-stu-id="b6c46-126">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="b6c46-127">I konfigurationsträdet i det vänstra fönstret väljer du erforderlig ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b6c46-127">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="b6c46-128">I snabbfliken **Versioner** väljer du erforderlig version för vald ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b6c46-128">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="b6c46-129">Klicka på **Importera** för att hämta den valda versionen från LCS till den aktuella instansen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-129">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b6c46-130">Knappen **Importera** är inte tillgänglig för ER-konfigurationsversioner som redan finns i den aktuella instansen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-130">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="b6c46-131">[![Sidan Konfigurationsdatabas](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="b6c46-131">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b6c46-132">Beroende på ER-inställningarna valideras konfigurationerna när de har importerats.</span><span class="sxs-lookup"><span data-stu-id="b6c46-132">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="b6c46-133">Du kan komma att meddelas om eventuella inkonsekvensproblem som upptäcks.</span><span class="sxs-lookup"><span data-stu-id="b6c46-133">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="b6c46-134">Du måste lösa dessa problem innan du kan använda den importerade konfigurationsversionen.</span><span class="sxs-lookup"><span data-stu-id="b6c46-134">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="b6c46-135">Mer information finns i listan över relaterade artiklar för detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b6c46-135">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6c46-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b6c46-136">Additional resources</span></span>

[<span data-ttu-id="b6c46-137">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="b6c46-137">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="b6c46-138">Hämta ER-konfigurationer från den globala databasen med konfigurationstjänster</span><span class="sxs-lookup"><span data-stu-id="b6c46-138">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
