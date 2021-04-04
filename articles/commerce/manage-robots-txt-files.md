---
title: Hantera robots.txt-filer
description: I det här avsnittet beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: afd7982179dc9845c9adc24e8c7c9951a04460a3
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477718"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="fe7da-103">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="fe7da-103">Manage robots.txt files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe7da-104">I det här avsnittet beskrivs hur du hanterar robots.txt-filer i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe7da-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="fe7da-105">Robots-exkluderingsstandarden, eller robots.txt, är en standard som webbplatser använder för att kommunicera med webbrobotar.</span><span class="sxs-lookup"><span data-stu-id="fe7da-105">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="fe7da-106">Den instruerar webbrobotar om alla områden på en webbplats som inte bör besökas.</span><span class="sxs-lookup"><span data-stu-id="fe7da-106">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="fe7da-107">Robotar används ofta av sökmotorer för att indexera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="fe7da-107">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="fe7da-108">Om du vill utesluta robotar från en server skapar du en fil på servern.</span><span class="sxs-lookup"><span data-stu-id="fe7da-108">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="fe7da-109">I den här filen anger du en åtkomstprincip för robotar.</span><span class="sxs-lookup"><span data-stu-id="fe7da-109">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="fe7da-110">Filen måste vara tillgänglig via HTTP på den lokala URL: **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="fe7da-110">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="fe7da-111">Filen robots.txt hjälper sökmotorer att indexera innehållet på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="fe7da-111">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="fe7da-112">Dynamics 365 Commerce låter dig ladda upp en robots.txt-fil för din domän.</span><span class="sxs-lookup"><span data-stu-id="fe7da-112">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="fe7da-113">För varje domän i din Commerce-miljö kan du ladda upp en robots.txt-fil och associera den med den domänen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-113">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="fe7da-114">För mer information om robots.txt-filen, besök [sidor för webbrobotar](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="fe7da-114">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="fe7da-115">Ladda upp en robots.txt-fil</span><span class="sxs-lookup"><span data-stu-id="fe7da-115">Upload a robots.txt file</span></span>

<span data-ttu-id="fe7da-116">När du har skapat och redigerat filen robots.txt enligt [robots-exkluderingsstandarden](https://www.robotstxt.org/orig.html) kontrollerar du att filen är tillgänglig på den dator där du ska använda Commerce-redigeringsverktygen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-116">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="fe7da-117">Filen måste ha namnet **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="fe7da-117">The file must be named **robots.txt**.</span></span> <span data-ttu-id="fe7da-118">För bästa resultat måste det vara i det format som anges i standarden.</span><span class="sxs-lookup"><span data-stu-id="fe7da-118">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="fe7da-119">Varje Commerce-kund ansvarar för att validera och underhålla innehållet i sin robots.txt-fil.</span><span class="sxs-lookup"><span data-stu-id="fe7da-119">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="fe7da-120">För att överföra en robots.txt-file måste du logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="fe7da-120">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="fe7da-121">Så här överför du en robots.txt-fil i Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe7da-121">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="fe7da-122">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="fe7da-122">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="fe7da-123">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="fe7da-123">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="fe7da-124">Under **innehavarinställningar** väljer du **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="fe7da-124">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="fe7da-125">En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe7da-125">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="fe7da-126">Välj **hantera** om du vill överföra en robots.txt-fil för en domän i din miljö.</span><span class="sxs-lookup"><span data-stu-id="fe7da-126">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="fe7da-127">På menyn till höger väljer du knappen **Överför** (pilen uppåt) bredvid den domän som är associerad med robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-127">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="fe7da-128">En dialogruta för filbläddraren visas.</span><span class="sxs-lookup"><span data-stu-id="fe7da-128">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="fe7da-129">Bläddra till och markera den robots.txt-fil som du vill överföra för den associerade domänen i dialogrutan och välj sedan **öppna** för att slutföra överföringen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-129">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="fe7da-130">Under överföringen verifierar Commerce att filen är en textfil, men den validerar inte filens innehåll.</span><span class="sxs-lookup"><span data-stu-id="fe7da-130">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="fe7da-131">Ladda ned en robots.txt-fil</span><span class="sxs-lookup"><span data-stu-id="fe7da-131">Download a robots.txt file</span></span>

<span data-ttu-id="fe7da-132">Så här laddar du ned en robots.txt-fil i Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe7da-132">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="fe7da-133">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="fe7da-133">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="fe7da-134">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="fe7da-134">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="fe7da-135">Under **innehavarinställningar** väljer du **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="fe7da-135">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="fe7da-136">En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe7da-136">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="fe7da-137">Välj **hantera** om du vill ladda ned en robots.txt-fil för en domän i din miljö.</span><span class="sxs-lookup"><span data-stu-id="fe7da-137">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="fe7da-138">På menyn till höger väljer du knappen **Ladda ned** (pilen nedåt) bredvid den domän som är associerad med robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-138">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="fe7da-139">En dialogruta för filbläddraren visas.</span><span class="sxs-lookup"><span data-stu-id="fe7da-139">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="fe7da-140">Gå till önskad plats på den lokala enheten i dialogrutan, bekräfta eller ange ett filnamn och välj sedan **spara** för att slutföra hämtningen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-140">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="fe7da-141">Den här proceduren kan endast användas för att hämta robots.txt-filer som tidigare har överförts via Commerce redigeringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="fe7da-141">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="fe7da-142">Ta bort en robots.txt-fil</span><span class="sxs-lookup"><span data-stu-id="fe7da-142">Delete a robots.txt file</span></span>

<span data-ttu-id="fe7da-143">Så här tar du bort en robots.txt-fil i Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe7da-143">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="fe7da-144">Logga in på Commerce som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="fe7da-144">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="fe7da-145">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** (bredvid kugghjulssymbolen) för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="fe7da-145">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="fe7da-146">Under **innehavarinställningar** väljer du **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="fe7da-146">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="fe7da-147">En lista över alla domäner som är associerade med din miljö visas i huvuddelen av fönstret.</span><span class="sxs-lookup"><span data-stu-id="fe7da-147">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="fe7da-148">Välj **hantera** om du vill ta bort en robots.txt-fil för en domän i din miljö.</span><span class="sxs-lookup"><span data-stu-id="fe7da-148">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="fe7da-149">På menyn till höger väljer du knappen **Ta bort** (papperskorgsymbolen) bredvid den domän som är associerad med robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-149">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="fe7da-150">Ett filwebbläsarfönster visas.</span><span class="sxs-lookup"><span data-stu-id="fe7da-150">A file browser window appears.</span></span>
6. <span data-ttu-id="fe7da-151">Bläddra till filwebbläsarfönster och markera den robots.txt-fil som du vill ta bort för domänen i dialogrutan och välj sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="fe7da-151">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="fe7da-152">En varningsmeddelanderuta visas.</span><span class="sxs-lookup"><span data-stu-id="fe7da-152">A warning message box appears.</span></span>
7. <span data-ttu-id="fe7da-153">I meddelanderutan väljer du **ta bort** för att bekräfta borttagningen av robots.txt-filen.</span><span class="sxs-lookup"><span data-stu-id="fe7da-153">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="fe7da-154">Den här proceduren kan endast användas för att ta bort robots.txt-filer som tidigare har överförts via Commerce redigeringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="fe7da-154">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe7da-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fe7da-155">Additional resources</span></span>

[<span data-ttu-id="fe7da-156">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="fe7da-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="fe7da-157">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="fe7da-157">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="fe7da-158">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="fe7da-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="fe7da-159">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="fe7da-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="fe7da-160">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="fe7da-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="fe7da-161">Ställa in en B2C-klientorganisation i Commerce</span><span class="sxs-lookup"><span data-stu-id="fe7da-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="fe7da-162">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="fe7da-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="fe7da-163">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="fe7da-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="fe7da-164">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="fe7da-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="fe7da-165">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="fe7da-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
