---
title: Hantera robots.txt-filer
description: I det här avsnittet beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: e472f3612bd6860e7262bb128035f2aed3b39372
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946082"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="b3de8-103">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="b3de8-103">Manage robots.txt files</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b3de8-104">I det här avsnittet beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3de8-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b3de8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="b3de8-105">Overview</span></span>

<span data-ttu-id="b3de8-106">Robots-exkluderingsstandarden, eller robots.txt, är en standard som webbplatser använder för att kommunicera med webbrobotar.</span><span class="sxs-lookup"><span data-stu-id="b3de8-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="b3de8-107">Den instruerar webbrobotar om alla områden på en webbplats som inte bör besökas.</span><span class="sxs-lookup"><span data-stu-id="b3de8-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="b3de8-108">Robotar används ofta av sökmotorer för att indexera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="b3de8-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="b3de8-109">Om du vill utesluta robotar från en server skapar du en fil på servern.</span><span class="sxs-lookup"><span data-stu-id="b3de8-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="b3de8-110">I den här filen anger du en åtkomstprincip för robotar.</span><span class="sxs-lookup"><span data-stu-id="b3de8-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="b3de8-111">Filen måste vara tillgänglig via HTTP på den lokala URL: **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="b3de8-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="b3de8-112">Filen robots.txt hjälper sökmotorer att indexera innehållet på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="b3de8-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="b3de8-113">Dynamics 365 Commerce låter dig ladda upp en robots.txt-fil för din domän.</span><span class="sxs-lookup"><span data-stu-id="b3de8-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="b3de8-114">För varje domän i din Commerce-miljö kan du ladda upp en robots.txt-fil och associera den med den domänen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="b3de8-115">För mer information om robots.txt-filen, besök [sidor för webbrobotar](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="b3de8-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="b3de8-116">Ladda upp en robots.txt-fil</span><span class="sxs-lookup"><span data-stu-id="b3de8-116">Upload a robots.txt file</span></span>

<span data-ttu-id="b3de8-117">När du har skapat och redigerat filen robots.txt enligt [robots-exkluderingsstandarden](https://www.robotstxt.org/orig.html) kontrollerar du att filen är tillgänglig på den dator där du ska använda Commerce-redigeringsverktygen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="b3de8-118">Filen måste ha namnet **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="b3de8-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="b3de8-119">För bästa resultat måste det vara i det format som anges i standarden.</span><span class="sxs-lookup"><span data-stu-id="b3de8-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="b3de8-120">Varje Commerce-kund ansvarar för att validera och underhålla innehållet i sin robots.txt-fil.</span><span class="sxs-lookup"><span data-stu-id="b3de8-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="b3de8-121">För att överföra en robots.txt-file måste du logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="b3de8-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="b3de8-122">Så här överför du en robots.txt-fil i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3de8-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b3de8-123">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="b3de8-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="b3de8-124">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="b3de8-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="b3de8-125">Under **innehavarinställningar** väljer du **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="b3de8-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="b3de8-126">En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="b3de8-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="b3de8-127">Välj **hantera** om du vill överföra en robots.txt-fil för en domän i din miljö.</span><span class="sxs-lookup"><span data-stu-id="b3de8-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="b3de8-128">På menyn till höger väljer du knappen **Överför** (pilen uppåt) bredvid den domän som är associerad med robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="b3de8-129">En dialogruta för filbläddraren visas.</span><span class="sxs-lookup"><span data-stu-id="b3de8-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="b3de8-130">Bläddra till och markera den robots.txt-fil som du vill överföra för den associerade domänen i dialogrutan och välj sedan **öppna** för att slutföra överföringen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="b3de8-131">Under överföringen verifierar Commerce att filen är en textfil, men den validerar inte filens innehåll.</span><span class="sxs-lookup"><span data-stu-id="b3de8-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="b3de8-132">Ladda ned en robots.txt-fil</span><span class="sxs-lookup"><span data-stu-id="b3de8-132">Download a robots.txt file</span></span>

<span data-ttu-id="b3de8-133">Så här laddar du ned en robots.txt-fil i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3de8-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b3de8-134">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="b3de8-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="b3de8-135">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="b3de8-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="b3de8-136">Under **innehavarinställningar** väljer du **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="b3de8-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="b3de8-137">En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="b3de8-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="b3de8-138">Välj **hantera** om du vill ladda ned en robots.txt-fil för en domän i din miljö.</span><span class="sxs-lookup"><span data-stu-id="b3de8-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="b3de8-139">På menyn till höger väljer du knappen **Ladda ned** (pilen nedåt) bredvid den domän som är associerad med robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="b3de8-140">En dialogruta för filbläddraren visas.</span><span class="sxs-lookup"><span data-stu-id="b3de8-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="b3de8-141">Gå till önskad plats på den lokala enheten i dialogrutan, bekräfta eller ange ett filnamn och välj sedan **spara** för att slutföra hämtningen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="b3de8-142">Den här proceduren kan endast användas för att hämta robots.txt-filer som tidigare har överförts via Commerce redigeringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="b3de8-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="b3de8-143">Ta bort en robots.txt-fil</span><span class="sxs-lookup"><span data-stu-id="b3de8-143">Delete a robots.txt file</span></span>

<span data-ttu-id="b3de8-144">Så här tar du bort en robots.txt-fil i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3de8-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b3de8-145">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="b3de8-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="b3de8-146">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="b3de8-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="b3de8-147">Under **innehavarinställningar** väljer du **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="b3de8-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="b3de8-148">En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="b3de8-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="b3de8-149">Välj **hantera** om du vill ta bort en robots.txt-fil för en domän i din miljö.</span><span class="sxs-lookup"><span data-stu-id="b3de8-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="b3de8-150">På menyn till höger väljer du knappen **Ta bort** (papperskorgsymbolen) bredvid den domän som är associerad med robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="b3de8-151">Ett filwebbläsarfönster visas.</span><span class="sxs-lookup"><span data-stu-id="b3de8-151">A file browser window appears.</span></span>
6. <span data-ttu-id="b3de8-152">Bläddra till filwebbläsarfönster och markera den robots.txt-fil som du vill ta bort för domänen i dialogrutan och välj sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="b3de8-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="b3de8-153">En varningsmeddelanderuta visas.</span><span class="sxs-lookup"><span data-stu-id="b3de8-153">A warning message box appears.</span></span>
7. <span data-ttu-id="b3de8-154">I meddelanderutan väljer du **ta bort** för att bekräfta borttagningen av robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="b3de8-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="b3de8-155">Den här proceduren kan endast användas för att ta bort robots.txt-filer som tidigare har överförts via Commerce redigeringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="b3de8-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3de8-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b3de8-156">Additional resources</span></span>

[<span data-ttu-id="b3de8-157">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="b3de8-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="b3de8-158">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="b3de8-158">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="b3de8-159">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="b3de8-159">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="b3de8-160">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="b3de8-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="b3de8-161">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="b3de8-161">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="b3de8-162">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="b3de8-162">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="b3de8-163">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="b3de8-163">Enable location-based store detection</span></span>](enable-store-detection.md)
