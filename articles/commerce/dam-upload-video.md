---
title: Överför videor
description: I det här avsnittet beskrivs hur du laddar upp videor i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
ms.date: 06/09/2021
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
ms.openlocfilehash: e3579b54c58898b79c84406480a3b58f541c4621
ms.sourcegitcommit: 257437a57e146496a49782bc8aad179c92fbf6e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "6224548"
---
# <a name="upload-videos"></a><span data-ttu-id="5a990-103">Överför videor</span><span class="sxs-lookup"><span data-stu-id="5a990-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5a990-104">I det här avsnittet beskrivs hur du laddar upp videor i Microsoft Dynamics 365 Commerce webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="5a990-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="5a990-105">Med mediabiblioteket för Commerce webbplatsskapare kan du överföra videor.</span><span class="sxs-lookup"><span data-stu-id="5a990-105">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="5a990-106">Du bör alltid överföra versionen av en video med högsta bithastighet och upplösning, eftersom videon omvandlas automatiskt för att vara lämplig för olika visningsportar och deras brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="5a990-106">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="5a990-107">Videoinformation som anges under överföringen</span><span class="sxs-lookup"><span data-stu-id="5a990-107">Video information specified during upload</span></span>

<span data-ttu-id="5a990-108">När du överför en video kan du ange följande information.</span><span class="sxs-lookup"><span data-stu-id="5a990-108">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="5a990-109">**Rubrik, beskrivning, nyckelord**: metadata för videon.</span><span class="sxs-lookup"><span data-stu-id="5a990-109">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="5a990-110">**Generera underterxter automatiskt**: Anger om undertexter ska genereras automatiskt för videon (stöd finns endast för engelska).</span><span class="sxs-lookup"><span data-stu-id="5a990-110">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video (only English language is supported).</span></span> 
- <span data-ttu-id="5a990-111">**Dold textning**: anger den dolda textning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="5a990-111">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="5a990-112">**Vanligt ljud**: anger det vanliga ljudspår som ska användas.</span><span class="sxs-lookup"><span data-stu-id="5a990-112">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="5a990-113">**Miniatyr**: anger miniatyrbilden för videon.</span><span class="sxs-lookup"><span data-stu-id="5a990-113">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="5a990-114">Om den inte anges kommer den att genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5a990-114">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="5a990-115">**Beskrivande ljud**: anger det beskrivande ljudspår som ska användas.</span><span class="sxs-lookup"><span data-stu-id="5a990-115">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="5a990-116">Överför en video</span><span class="sxs-lookup"><span data-stu-id="5a990-116">Upload a video</span></span>

<span data-ttu-id="5a990-117">Så här överför du en video i webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="5a990-117">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="5a990-118">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="5a990-118">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="5a990-119">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="5a990-119">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="5a990-120">I fönstret Utforskaren navigerar du till och markerar en eller flera videofiler som ska överföras och väljer sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="5a990-120">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="5a990-121">I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.</span><span class="sxs-lookup"><span data-stu-id="5a990-121">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="5a990-122">Ange valfri beskrivning och nyckelord och välj en kategori om du vill.</span><span class="sxs-lookup"><span data-stu-id="5a990-122">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="5a990-123">Om du vill publicera bilden omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**</span><span class="sxs-lookup"><span data-stu-id="5a990-123">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="5a990-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a990-124">Select **OK**.</span></span>

<span data-ttu-id="5a990-125">Om du överför flera typer av tillgångar samtidigt (t.ex. bilder och videor) i dialogrutan **överför medieobjekt** kan du bara ange nyckelord, om filerna ska publiceras direkt efter överföringen och om det ska genereras dolda bildtexter automatiskt för videofilerna.</span><span class="sxs-lookup"><span data-stu-id="5a990-125">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="5a990-126">Alla tillgångar kommer att dela samma nyckelord.</span><span class="sxs-lookup"><span data-stu-id="5a990-126">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a990-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5a990-127">Additional resources</span></span>

[<span data-ttu-id="5a990-128">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="5a990-128">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="5a990-129">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="5a990-129">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="5a990-130">Överför filer</span><span class="sxs-lookup"><span data-stu-id="5a990-130">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="5a990-131">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="5a990-131">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="5a990-132">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="5a990-132">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="5a990-133">Ladda upp och betjäna statiska filer</span><span class="sxs-lookup"><span data-stu-id="5a990-133">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
