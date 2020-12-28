---
title: Överför bilder
description: I det här avsnittet beskrivs hur du överför bilder i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f562d3376fde6a24e6a1e1a3f7f4192cf290ae90
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594294"
---
# <a name="upload-images"></a><span data-ttu-id="f3915-103">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="f3915-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f3915-104">I det här avsnittet beskrivs hur du överför bilder i Microsoft Dynamics 365 Commerce webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="f3915-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="f3915-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="f3915-105">Overview</span></span>

<span data-ttu-id="f3915-106">Med mediabiblioteket för Commerce webbplatsskapare kan du överföra bilder, antingen enstaka eller i bulk, med hjälp av mappar.</span><span class="sxs-lookup"><span data-stu-id="f3915-106">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="f3915-107">Du bör alltid överföra bildens version med högsta upplösning och kvalitet eftersom bilden storleksändringskomponent automatiskt optimerar bilden för olika visningspunkter och deras brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="f3915-107">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="f3915-108">Avbildningsinformation som anges under överföringen</span><span class="sxs-lookup"><span data-stu-id="f3915-108">Image information specified during upload</span></span>

<span data-ttu-id="f3915-109">När du överför en bild kan du ange följande information.</span><span class="sxs-lookup"><span data-stu-id="f3915-109">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="f3915-110">**Rubrik, Alt text, beskrivning, nyckelord**: metadata för bilden eller bilderna.</span><span class="sxs-lookup"><span data-stu-id="f3915-110">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="f3915-111">Rubrik och Alt text är obligatoriska värden.</span><span class="sxs-lookup"><span data-stu-id="f3915-111">Title and alt text are required values.</span></span>
- <span data-ttu-id="f3915-112">**Välj kategori**:</span><span class="sxs-lookup"><span data-stu-id="f3915-112">**Select category**:</span></span>
    - <span data-ttu-id="f3915-113">**Ingen**: används för en näthandels berättandebild eller bilder.</span><span class="sxs-lookup"><span data-stu-id="f3915-113">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="f3915-114">**Produkt, kategori, kund, medarbetare, katalog**: används för Dynamics 365 Commerce bild eller bilder i flera kanaler.</span><span class="sxs-lookup"><span data-stu-id="f3915-114">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="f3915-115">**Publicera resurser efter uppladdning**: när den här kryssrutan är markerad publiceras bilden eller bilderna omedelbart efter överföringen.</span><span class="sxs-lookup"><span data-stu-id="f3915-115">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="f3915-116">Bildtillgångar med en tilldelad kategori kodas också automatiskt med kategorin som nyckelord för att underlätta sökningen efter tillgångar i en viss kategori.</span><span class="sxs-lookup"><span data-stu-id="f3915-116">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="f3915-117">Namnge regler för flerkanalsbilder</span><span class="sxs-lookup"><span data-stu-id="f3915-117">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="f3915-118">Om du har konfigurerat mediebiblioteket som flerkanalsbild kan du använda bildkategorier för att ange vilken kategori den uppladdade bilden tillhör.</span><span class="sxs-lookup"><span data-stu-id="f3915-118">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="f3915-119">Det finns också en namnkonvention som ska följas för att se till att bilderna hämtas korrekt av andra kanaler, t.ex. kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="f3915-119">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="f3915-120">Standard namngivningskonventionen varierar beroende på vilken kategori:</span><span class="sxs-lookup"><span data-stu-id="f3915-120">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="f3915-121">Katalogbilder ska heta "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="f3915-121">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="f3915-122">Kategoribilder ska heta "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="f3915-122">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="f3915-123">Kundbilder ska heta "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="f3915-123">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="f3915-124">De anställdas bilder ska heta "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="f3915-124">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="f3915-125">Produktbilder ska heta "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="f3915-125">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="f3915-126">001 är sekvensen av bilden och den kan vara 001, 002, 003, 004 eller 005</span><span class="sxs-lookup"><span data-stu-id="f3915-126">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="f3915-127">Produktvariantbilder ska heta "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="f3915-127">Product variant images should be named "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="f3915-128">Ladda upp en bild</span><span class="sxs-lookup"><span data-stu-id="f3915-128">Upload an image</span></span>

<span data-ttu-id="f3915-129">Så här överför du en bild i webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="f3915-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f3915-130">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="f3915-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="f3915-131">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="f3915-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="f3915-132">I fönstret Utforskaren navigerar du till och markerar en eller flera bildfiler som ska överföras och väljer sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="f3915-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="f3915-133">I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.</span><span class="sxs-lookup"><span data-stu-id="f3915-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="f3915-134">Ange valfri beskrivning och nyckelord och välj en kategori om du vill.</span><span class="sxs-lookup"><span data-stu-id="f3915-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="f3915-135">Om du vill publicera bilden omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="f3915-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="f3915-136">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3915-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="f3915-137">Överföra en mapp med bilder</span><span class="sxs-lookup"><span data-stu-id="f3915-137">Upload a folder of images</span></span>

<span data-ttu-id="f3915-138">Så här massöverför du en mapp av bilder i webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="f3915-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f3915-139">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="f3915-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="f3915-140">I kommandofältet, välj **Överför \> Överför mapp**.</span><span class="sxs-lookup"><span data-stu-id="f3915-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="f3915-141">I fönstret Utforskaren navigerar du till och markerar en mapp att överföra och väljer sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="f3915-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="f3915-142">I dialogrutan **Överför medieartiklar** ange valfria nyckelord och välj en kategori om så önskas.</span><span class="sxs-lookup"><span data-stu-id="f3915-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="f3915-143">Om du vill publicera bilden i mappen omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="f3915-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="f3915-144">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3915-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3915-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f3915-145">Additional resources</span></span>

[<span data-ttu-id="f3915-146">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="f3915-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="f3915-147">Överför video</span><span class="sxs-lookup"><span data-stu-id="f3915-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="f3915-148">Överför filer</span><span class="sxs-lookup"><span data-stu-id="f3915-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="f3915-149">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="f3915-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="f3915-150">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="f3915-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="f3915-151">Ladda upp och betjäna statiska filer</span><span class="sxs-lookup"><span data-stu-id="f3915-151">Upload and serve static files</span></span>](upload-serve-static-files.md)
