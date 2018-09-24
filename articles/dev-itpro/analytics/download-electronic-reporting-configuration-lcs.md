---
title: "Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services"
description: "Detta avsnitt innehåller information om hur du hämtar elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 8686d2639a3ab7f2e79944cc5eed51571d463261
ms.contentlocale: sv-se
ms.lasthandoff: 08/13/2018

---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="adc70-103">Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="adc70-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="adc70-104">Detta avsnitt innehåller information om hur du hämtar elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="adc70-104">This topic explains how to download Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="adc70-105">Denna guide vägleder dig genom processen att hämta den senaste versionen av elektroniska rapportkonfigurationer (ER) från Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="adc70-105">This tutorial guides you through the process of downloading the newest version of Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="adc70-106">Logga in på Finance and Operations med någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="adc70-106">Sign in to Finance and Operations by using one of the following roles:</span></span>

    - <span data-ttu-id="adc70-107">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="adc70-107">Electronic reporting developer</span></span>
    - <span data-ttu-id="adc70-108">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="adc70-108">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="adc70-109">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="adc70-109">System administrator</span></span>

2. <span data-ttu-id="adc70-110">Navigera tilll **Organisationsadministrering** &gt; **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="adc70-110">Go to **Organization administration** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="adc70-111">I avsnittet **Konfigurationsleverantörer** väljer du panelen **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="adc70-111">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="adc70-112">I panelen **Microsoft** väljer du **Databaser**.</span><span class="sxs-lookup"><span data-stu-id="adc70-112">On the **Microsoft** tile, click **Repositories**.</span></span>

    <span data-ttu-id="adc70-113">[![uppdatera-er-från-lcs-för-ms-öppna-lista-över-ms-databaser](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="adc70-113">[![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="adc70-114">På sidan **Konfigurationsdatabaser** väljer du i rutnätet den befintliga databasen för **LCS**-typen.</span><span class="sxs-lookup"><span data-stu-id="adc70-114">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="adc70-115">Om denna databas inte visas i rutnätet, följ då nedanstående steg:</span><span class="sxs-lookup"><span data-stu-id="adc70-115">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="adc70-116">Klicka på Click **Lägg till** för att lägga till en ny databas.</span><span class="sxs-lookup"><span data-stu-id="adc70-116">Click **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="adc70-117">Välj **LCS** som databastyp.</span><span class="sxs-lookup"><span data-stu-id="adc70-117">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="adc70-118">Klicka på **Skapa databas**.</span><span class="sxs-lookup"><span data-stu-id="adc70-118">Click **Create repository**.</span></span>
    4. <span data-ttu-id="adc70-119">Följ autoriseringsinstruktionerna om du uppmanas.</span><span class="sxs-lookup"><span data-stu-id="adc70-119">If prompted, follow the authorization instructions.</span></span>
    5. <span data-ttu-id="adc70-120">Skriv ett namn och en beskrivning för databasen.</span><span class="sxs-lookup"><span data-stu-id="adc70-120">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="adc70-121">Klicka på **OK** för att bekräfta den nya databasposten.</span><span class="sxs-lookup"><span data-stu-id="adc70-121">Click **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="adc70-122">I rutnätet väljer du den nya databasen för **LCS**-typen.</span><span class="sxs-lookup"><span data-stu-id="adc70-122">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="adc70-123">Klicka på **Öppna** om du vill visa listan över ER-konfigurationer för den valda databasen.</span><span class="sxs-lookup"><span data-stu-id="adc70-123">Click **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="adc70-124">[![uppdatera-er-från-lcs-för-ms-skapa-lcs-databas](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="adc70-124">[![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

7. <span data-ttu-id="adc70-125">I konfigurationsträdet i det vänstra fönstret väljer du erforderlig ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="adc70-125">In the configurations tree in the left pane, select the ER configuration that you require.</span></span>
8. <span data-ttu-id="adc70-126">I snabbfliken **Versioner** väljer du erforderlig version för vald ER-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="adc70-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="adc70-127">Klicka på **Importera** för att hämta den valda versionen från LCS till den aktuella Finance and Operations-instansen.</span><span class="sxs-lookup"><span data-stu-id="adc70-127">Click **Import** to download the selected version from LCS to the current Finance and Operations instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="adc70-128">Knappen **Importera** är inte tillgänglig för ER-konfigurationsversioner som redan finns i den aktuella Finance and Operations-instansen.</span><span class="sxs-lookup"><span data-stu-id="adc70-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance and Operations instance.</span></span>

    <span data-ttu-id="adc70-129">[![uppdatera-er-från-lcs-för-ms-hämta-konfiguration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="adc70-129">[![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="adc70-130">Beroende på ER-inställningarna valideras konfigurationerna när de har importerats.</span><span class="sxs-lookup"><span data-stu-id="adc70-130">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="adc70-131">Du kan komma att meddelas om eventuella inkonsekvensproblem som upptäcks.</span><span class="sxs-lookup"><span data-stu-id="adc70-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="adc70-132">Du måste lösa dessa problem innan du kan använda den importerade konfigurationsversionen.</span><span class="sxs-lookup"><span data-stu-id="adc70-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="adc70-133">Mer information finns i listan över relaterade artiklar för detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="adc70-133">For more information, see the list of related articles for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="adc70-134">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="adc70-134">Additional resources</span></span>

[<span data-ttu-id="adc70-135">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="adc70-135">Electronic reporting overview</span></span>](general-electronic-reporting.md)

