---
title: Överför bilder
description: I det här avsnittet beskrivs hur du laddar upp bilder i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799239"
---
# <a name="upload-images"></a><span data-ttu-id="3f758-103">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="3f758-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3f758-104">I det här avsnittet beskrivs hur du laddar upp bilder i Microsoft Dynamics 365 Commerce webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="3f758-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="3f758-105">Med mediabiblioteket för Commerce webbplatsskapare kan du överföra bilder, antingen enstaka eller i bulk, med hjälp av mappar.</span><span class="sxs-lookup"><span data-stu-id="3f758-105">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="3f758-106">Du bör alltid överföra bildens version med högsta upplösning och kvalitet eftersom bilden storleksändringskomponent automatiskt optimerar bilden för olika visningspunkter och deras brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="3f758-106">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="3f758-107">Avbildningsinformation som anges under överföringen</span><span class="sxs-lookup"><span data-stu-id="3f758-107">Image information specified during upload</span></span>

<span data-ttu-id="3f758-108">När du överför en bild kan du ange följande information.</span><span class="sxs-lookup"><span data-stu-id="3f758-108">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="3f758-109">**Rubrik, Alt text, beskrivning, nyckelord**: metadata för bilden eller bilderna.</span><span class="sxs-lookup"><span data-stu-id="3f758-109">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="3f758-110">Rubrik och Alt text är obligatoriska värden.</span><span class="sxs-lookup"><span data-stu-id="3f758-110">Title and alt text are required values.</span></span>
- <span data-ttu-id="3f758-111">**Välj kategori**:</span><span class="sxs-lookup"><span data-stu-id="3f758-111">**Select category**:</span></span>
    - <span data-ttu-id="3f758-112">**Ingen**: används för en näthandels berättandebild eller bilder.</span><span class="sxs-lookup"><span data-stu-id="3f758-112">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="3f758-113">**Produkt, kategori, kund, medarbetare, katalog**: används för Dynamics 365 Commerce bild eller bilder i flera kanaler.</span><span class="sxs-lookup"><span data-stu-id="3f758-113">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="3f758-114">**Publicera resurser efter uppladdning**: när den här kryssrutan är markerad publiceras bilden eller bilderna omedelbart efter överföringen.</span><span class="sxs-lookup"><span data-stu-id="3f758-114">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="3f758-115">Bildtillgångar med en tilldelad kategori kodas också automatiskt med kategorin som nyckelord för att underlätta sökningen efter tillgångar i en viss kategori.</span><span class="sxs-lookup"><span data-stu-id="3f758-115">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="3f758-116">Namnge regler för flerkanalsbilder</span><span class="sxs-lookup"><span data-stu-id="3f758-116">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="3f758-117">Om du har konfigurerat mediebiblioteket som flerkanalsbild kan du använda bildkategorier för att ange vilken kategori den uppladdade bilden tillhör.</span><span class="sxs-lookup"><span data-stu-id="3f758-117">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="3f758-118">Det finns också en namnkonvention som ska följas för att se till att bilderna hämtas korrekt av andra kanaler, t.ex. POS.</span><span class="sxs-lookup"><span data-stu-id="3f758-118">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="3f758-119">Standard namngivningskonventionen varierar beroende på vilken kategori:</span><span class="sxs-lookup"><span data-stu-id="3f758-119">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="3f758-120">Katalogbilder ska heta "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="3f758-120">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="3f758-121">Kategoribilder ska heta "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="3f758-121">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="3f758-122">Kundbilder ska heta "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="3f758-122">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="3f758-123">De anställdas bilder ska heta "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="3f758-123">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="3f758-124">Produktbilder ska heta "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="3f758-124">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="3f758-125">001 är sekvensen av bilden och den kan vara 001, 002, 003, 004 eller 005</span><span class="sxs-lookup"><span data-stu-id="3f758-125">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="3f758-126">Produktvariantbilder ska heta "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="3f758-126">Product variant images should be named "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span></span>
    - <span data-ttu-id="3f758-127">Till exempel: 93039 \^\^ 2 \^ Svart \^_000_001.png</span><span class="sxs-lookup"><span data-stu-id="3f758-127">For example: 93039 \^ \^ 2 \^ Black \^_000_001.png</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="3f758-128">Ladda upp en bild</span><span class="sxs-lookup"><span data-stu-id="3f758-128">Upload an image</span></span>

<span data-ttu-id="3f758-129">Så här överför du en bild i webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="3f758-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3f758-130">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="3f758-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="3f758-131">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="3f758-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="3f758-132">I fönstret Utforskaren navigerar du till och markerar en eller flera bildfiler som ska överföras och väljer sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="3f758-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="3f758-133">I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.</span><span class="sxs-lookup"><span data-stu-id="3f758-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="3f758-134">Ange valfri beskrivning och nyckelord och välj en kategori om du vill.</span><span class="sxs-lookup"><span data-stu-id="3f758-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="3f758-135">Om du vill publicera bilden omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="3f758-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="3f758-136">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f758-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="3f758-137">Överföra en mapp med bilder</span><span class="sxs-lookup"><span data-stu-id="3f758-137">Upload a folder of images</span></span>

<span data-ttu-id="3f758-138">Så här massöverför du en mapp av bilder i webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="3f758-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3f758-139">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="3f758-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="3f758-140">I kommandofältet, välj **Överför \> Överför mapp**.</span><span class="sxs-lookup"><span data-stu-id="3f758-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="3f758-141">I fönstret Utforskaren navigerar du till och markerar en mapp att överföra och väljer sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="3f758-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="3f758-142">I dialogrutan **Överför medieartiklar** ange valfria nyckelord och välj en kategori om så önskas.</span><span class="sxs-lookup"><span data-stu-id="3f758-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="3f758-143">Om du vill publicera bilden i mappen omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="3f758-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="3f758-144">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f758-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f758-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3f758-145">Additional resources</span></span>

[<span data-ttu-id="3f758-146">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="3f758-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="3f758-147">Överför video</span><span class="sxs-lookup"><span data-stu-id="3f758-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="3f758-148">Överför filer</span><span class="sxs-lookup"><span data-stu-id="3f758-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="3f758-149">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="3f758-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="3f758-150">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="3f758-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="3f758-151">Ladda upp och betjäna statiska filer</span><span class="sxs-lookup"><span data-stu-id="3f758-151">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
