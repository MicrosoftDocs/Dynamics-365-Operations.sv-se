---
title: Ladda upp andra filer än bilder och filmer
description: I det här avsnittet beskrivs hur du överför andra binära filer än bilder och videor i Microsoft Dynamics 365 Commerce webbplatsskaparen.
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
ms.openlocfilehash: fc0490e3532dcbb9c1e91101009b2d4605315416
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097084"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="59d5a-103">Ladda upp andra filer än bilder och filmer</span><span class="sxs-lookup"><span data-stu-id="59d5a-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="59d5a-104">I det här avsnittet beskrivs hur du överför andra filer än bilder och videor i Microsoft Dynamics 365 Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="59d5a-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="59d5a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="59d5a-105">Overview</span></span>

<span data-ttu-id="59d5a-106">Mediabiblioteket Commerce webbplatsskaparen stöder överföring av binära till gångar utom bilder eller videor.</span><span class="sxs-lookup"><span data-stu-id="59d5a-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="59d5a-107">Du kanske till exempel vill överföra Microsoft Excel, Microsoft Word Microsoft PowerPoint eller PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="59d5a-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="59d5a-108">Följande dokumenttyper stöds:</span><span class="sxs-lookup"><span data-stu-id="59d5a-108">The following document types are supported:</span></span>
- <span data-ttu-id="59d5a-109">7Z</span><span class="sxs-lookup"><span data-stu-id="59d5a-109">7Z</span></span>
- <span data-ttu-id="59d5a-110">AVI</span><span class="sxs-lookup"><span data-stu-id="59d5a-110">AVI</span></span>
- <span data-ttu-id="59d5a-111">CS</span><span class="sxs-lookup"><span data-stu-id="59d5a-111">CS</span></span>
- <span data-ttu-id="59d5a-112">CSS</span><span class="sxs-lookup"><span data-stu-id="59d5a-112">CSS</span></span>
- <span data-ttu-id="59d5a-113">DOC</span><span class="sxs-lookup"><span data-stu-id="59d5a-113">DOC</span></span>
- <span data-ttu-id="59d5a-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="59d5a-114">DOCX</span></span>
- <span data-ttu-id="59d5a-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="59d5a-115">EPUB</span></span>
- <span data-ttu-id="59d5a-116">GIF</span><span class="sxs-lookup"><span data-stu-id="59d5a-116">GIF</span></span>
- <span data-ttu-id="59d5a-117">INDD</span><span class="sxs-lookup"><span data-stu-id="59d5a-117">INDD</span></span>
- <span data-ttu-id="59d5a-118">JAR</span><span class="sxs-lookup"><span data-stu-id="59d5a-118">JAR</span></span>
- <span data-ttu-id="59d5a-119">JPG</span><span class="sxs-lookup"><span data-stu-id="59d5a-119">JPG</span></span>
- <span data-ttu-id="59d5a-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="59d5a-120">JPEG</span></span>
- <span data-ttu-id="59d5a-121">JS</span><span class="sxs-lookup"><span data-stu-id="59d5a-121">JS</span></span>
- <span data-ttu-id="59d5a-122">MP3</span><span class="sxs-lookup"><span data-stu-id="59d5a-122">MP3</span></span>
- <span data-ttu-id="59d5a-123">MP4</span><span class="sxs-lookup"><span data-stu-id="59d5a-123">MP4</span></span>
- <span data-ttu-id="59d5a-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="59d5a-124">MPEG</span></span>
- <span data-ttu-id="59d5a-125">MPG</span><span class="sxs-lookup"><span data-stu-id="59d5a-125">MPG</span></span>
- <span data-ttu-id="59d5a-126">ODP</span><span class="sxs-lookup"><span data-stu-id="59d5a-126">ODP</span></span>
- <span data-ttu-id="59d5a-127">ODS</span><span class="sxs-lookup"><span data-stu-id="59d5a-127">ODS</span></span>
- <span data-ttu-id="59d5a-128">ODT</span><span class="sxs-lookup"><span data-stu-id="59d5a-128">ODT</span></span>
- <span data-ttu-id="59d5a-129">PDF</span><span class="sxs-lookup"><span data-stu-id="59d5a-129">PDF</span></span>
- <span data-ttu-id="59d5a-130">PNG</span><span class="sxs-lookup"><span data-stu-id="59d5a-130">PNG</span></span>
- <span data-ttu-id="59d5a-131">PPT</span><span class="sxs-lookup"><span data-stu-id="59d5a-131">PPT</span></span>
- <span data-ttu-id="59d5a-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="59d5a-132">PPTX</span></span>
- <span data-ttu-id="59d5a-133">PS</span><span class="sxs-lookup"><span data-stu-id="59d5a-133">PS</span></span>
- <span data-ttu-id="59d5a-134">QXP</span><span class="sxs-lookup"><span data-stu-id="59d5a-134">QXP</span></span>
- <span data-ttu-id="59d5a-135">RAR</span><span class="sxs-lookup"><span data-stu-id="59d5a-135">RAR</span></span>
- <span data-ttu-id="59d5a-136">RTF</span><span class="sxs-lookup"><span data-stu-id="59d5a-136">RTF</span></span>
- <span data-ttu-id="59d5a-137">SVG</span><span class="sxs-lookup"><span data-stu-id="59d5a-137">SVG</span></span>
- <span data-ttu-id="59d5a-138">TAR</span><span class="sxs-lookup"><span data-stu-id="59d5a-138">TAR</span></span>
- <span data-ttu-id="59d5a-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="59d5a-139">TGZ</span></span>
- <span data-ttu-id="59d5a-140">TXT</span><span class="sxs-lookup"><span data-stu-id="59d5a-140">TXT</span></span>
- <span data-ttu-id="59d5a-141">WMV</span><span class="sxs-lookup"><span data-stu-id="59d5a-141">WMV</span></span>
- <span data-ttu-id="59d5a-142">XLS</span><span class="sxs-lookup"><span data-stu-id="59d5a-142">XLS</span></span>
- <span data-ttu-id="59d5a-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="59d5a-143">XLSX</span></span>
- <span data-ttu-id="59d5a-144">XML</span><span class="sxs-lookup"><span data-stu-id="59d5a-144">XML</span></span>
- <span data-ttu-id="59d5a-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="59d5a-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="59d5a-146">Överför en fil</span><span class="sxs-lookup"><span data-stu-id="59d5a-146">Upload a file</span></span>

<span data-ttu-id="59d5a-147">Så här överför du en fil till din Commerce-webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="59d5a-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="59d5a-148">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="59d5a-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="59d5a-149">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="59d5a-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="59d5a-150">Markera en eller flera filer i Utforskaren och välj sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="59d5a-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="59d5a-151">I dialogrutan **Överför medieartiklar** för nyckelord i dialogrutan överför medieobjekt efter behov.</span><span class="sxs-lookup"><span data-stu-id="59d5a-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="59d5a-152">Om du vill publicera filerna omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="59d5a-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="59d5a-153">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="59d5a-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59d5a-154">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="59d5a-154">Additional resources</span></span>

[<span data-ttu-id="59d5a-155">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="59d5a-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="59d5a-156">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="59d5a-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="59d5a-157">Överför video</span><span class="sxs-lookup"><span data-stu-id="59d5a-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="59d5a-158">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="59d5a-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="59d5a-159">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="59d5a-159">Customize image focal points</span></span>](dam-custom-focal-point.md)
