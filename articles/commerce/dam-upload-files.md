---
title: Ladda upp andra filer än bilder och filmer
description: I det här avsnittet beskrivs hur du överför andra binära filer än bilder och videor i Microsoft Dynamics 365 Commerce webbplatsskaparen.
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
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799263"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="1b4d4-103">Överföra andra filer än bilder och videor</span><span class="sxs-lookup"><span data-stu-id="1b4d4-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1b4d4-104">I det här avsnittet beskrivs hur du överför andra filer än bilder och videor i Microsoft Dynamics 365 Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="1b4d4-105">Mediabiblioteket Commerce webbplatsskaparen stöder överföring av binära till gångar utom bilder eller videor.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="1b4d4-106">Du kanske till exempel vill överföra Microsoft Excel, Microsoft Word Microsoft PowerPoint eller PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="1b4d4-107">Följande dokumenttyper stöds:</span><span class="sxs-lookup"><span data-stu-id="1b4d4-107">The following document types are supported:</span></span>
- <span data-ttu-id="1b4d4-108">7Z</span><span class="sxs-lookup"><span data-stu-id="1b4d4-108">7Z</span></span>
- <span data-ttu-id="1b4d4-109">AVI</span><span class="sxs-lookup"><span data-stu-id="1b4d4-109">AVI</span></span>
- <span data-ttu-id="1b4d4-110">CS</span><span class="sxs-lookup"><span data-stu-id="1b4d4-110">CS</span></span>
- <span data-ttu-id="1b4d4-111">CSS</span><span class="sxs-lookup"><span data-stu-id="1b4d4-111">CSS</span></span>
- <span data-ttu-id="1b4d4-112">DOC</span><span class="sxs-lookup"><span data-stu-id="1b4d4-112">DOC</span></span>
- <span data-ttu-id="1b4d4-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="1b4d4-113">DOCX</span></span>
- <span data-ttu-id="1b4d4-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="1b4d4-114">EPUB</span></span>
- <span data-ttu-id="1b4d4-115">GIF</span><span class="sxs-lookup"><span data-stu-id="1b4d4-115">GIF</span></span>
- <span data-ttu-id="1b4d4-116">INDD</span><span class="sxs-lookup"><span data-stu-id="1b4d4-116">INDD</span></span>
- <span data-ttu-id="1b4d4-117">JAR</span><span class="sxs-lookup"><span data-stu-id="1b4d4-117">JAR</span></span>
- <span data-ttu-id="1b4d4-118">JPG</span><span class="sxs-lookup"><span data-stu-id="1b4d4-118">JPG</span></span>
- <span data-ttu-id="1b4d4-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="1b4d4-119">JPEG</span></span>
- <span data-ttu-id="1b4d4-120">JS</span><span class="sxs-lookup"><span data-stu-id="1b4d4-120">JS</span></span>
- <span data-ttu-id="1b4d4-121">MP3</span><span class="sxs-lookup"><span data-stu-id="1b4d4-121">MP3</span></span>
- <span data-ttu-id="1b4d4-122">MP4</span><span class="sxs-lookup"><span data-stu-id="1b4d4-122">MP4</span></span>
- <span data-ttu-id="1b4d4-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="1b4d4-123">MPEG</span></span>
- <span data-ttu-id="1b4d4-124">MPG</span><span class="sxs-lookup"><span data-stu-id="1b4d4-124">MPG</span></span>
- <span data-ttu-id="1b4d4-125">ODP</span><span class="sxs-lookup"><span data-stu-id="1b4d4-125">ODP</span></span>
- <span data-ttu-id="1b4d4-126">ODS</span><span class="sxs-lookup"><span data-stu-id="1b4d4-126">ODS</span></span>
- <span data-ttu-id="1b4d4-127">ODT</span><span class="sxs-lookup"><span data-stu-id="1b4d4-127">ODT</span></span>
- <span data-ttu-id="1b4d4-128">PDF</span><span class="sxs-lookup"><span data-stu-id="1b4d4-128">PDF</span></span>
- <span data-ttu-id="1b4d4-129">PNG</span><span class="sxs-lookup"><span data-stu-id="1b4d4-129">PNG</span></span>
- <span data-ttu-id="1b4d4-130">PPT</span><span class="sxs-lookup"><span data-stu-id="1b4d4-130">PPT</span></span>
- <span data-ttu-id="1b4d4-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="1b4d4-131">PPTX</span></span>
- <span data-ttu-id="1b4d4-132">PS</span><span class="sxs-lookup"><span data-stu-id="1b4d4-132">PS</span></span>
- <span data-ttu-id="1b4d4-133">QXP</span><span class="sxs-lookup"><span data-stu-id="1b4d4-133">QXP</span></span>
- <span data-ttu-id="1b4d4-134">RAR</span><span class="sxs-lookup"><span data-stu-id="1b4d4-134">RAR</span></span>
- <span data-ttu-id="1b4d4-135">RTF</span><span class="sxs-lookup"><span data-stu-id="1b4d4-135">RTF</span></span>
- <span data-ttu-id="1b4d4-136">SVG</span><span class="sxs-lookup"><span data-stu-id="1b4d4-136">SVG</span></span>
- <span data-ttu-id="1b4d4-137">TAR</span><span class="sxs-lookup"><span data-stu-id="1b4d4-137">TAR</span></span>
- <span data-ttu-id="1b4d4-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="1b4d4-138">TGZ</span></span>
- <span data-ttu-id="1b4d4-139">TXT</span><span class="sxs-lookup"><span data-stu-id="1b4d4-139">TXT</span></span>
- <span data-ttu-id="1b4d4-140">WMV</span><span class="sxs-lookup"><span data-stu-id="1b4d4-140">WMV</span></span>
- <span data-ttu-id="1b4d4-141">XLS</span><span class="sxs-lookup"><span data-stu-id="1b4d4-141">XLS</span></span>
- <span data-ttu-id="1b4d4-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="1b4d4-142">XLSX</span></span>
- <span data-ttu-id="1b4d4-143">XML</span><span class="sxs-lookup"><span data-stu-id="1b4d4-143">XML</span></span>
- <span data-ttu-id="1b4d4-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="1b4d4-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="1b4d4-145">Överför en fil</span><span class="sxs-lookup"><span data-stu-id="1b4d4-145">Upload a file</span></span>

<span data-ttu-id="1b4d4-146">Så här överför du en fil till din Commerce-webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1b4d4-147">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="1b4d4-148">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="1b4d4-149">Markera en eller flera filer i Utforskaren och välj sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="1b4d4-150">I dialogrutan **Överför medieartiklar** för nyckelord i dialogrutan överför medieobjekt efter behov.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="1b4d4-151">Om du vill publicera filerna omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="1b4d4-152">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b4d4-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b4d4-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1b4d4-153">Additional resources</span></span>

[<span data-ttu-id="1b4d4-154">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="1b4d4-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="1b4d4-155">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="1b4d4-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="1b4d4-156">Överför video</span><span class="sxs-lookup"><span data-stu-id="1b4d4-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="1b4d4-157">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="1b4d4-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="1b4d4-158">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="1b4d4-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="1b4d4-159">Ladda upp och betjäna statiska filer</span><span class="sxs-lookup"><span data-stu-id="1b4d4-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
