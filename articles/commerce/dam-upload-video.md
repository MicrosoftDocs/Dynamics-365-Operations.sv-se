---
title: Överför videor
description: I det här avsnittet beskrivs hur du överför videor i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: a8cabcd3528308919697a9f2ecb2a81ad5acbe31
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000935"
---
# <a name="upload-videos"></a><span data-ttu-id="2bd56-103">Överför videor</span><span class="sxs-lookup"><span data-stu-id="2bd56-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2bd56-104">I det här avsnittet beskrivs hur du överför videor i Microsoft Dynamics 365 Commerce webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="2bd56-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="2bd56-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="2bd56-105">Overview</span></span>

<span data-ttu-id="2bd56-106">Med mediabiblioteket för Commerce webbplatsskapare kan du överföra videor.</span><span class="sxs-lookup"><span data-stu-id="2bd56-106">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="2bd56-107">Du bör alltid överföra versionen av en video med högsta bithastighet och upplösning, eftersom videon omvandlas automatiskt för att vara lämplig för olika visningsportar och deras brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="2bd56-107">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="2bd56-108">Videoinformation som anges under överföringen</span><span class="sxs-lookup"><span data-stu-id="2bd56-108">Video information specified during upload</span></span>

<span data-ttu-id="2bd56-109">När du överför en video kan du ange följande information.</span><span class="sxs-lookup"><span data-stu-id="2bd56-109">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="2bd56-110">**Rubrik, beskrivning, nyckelord**: metadata för videon.</span><span class="sxs-lookup"><span data-stu-id="2bd56-110">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="2bd56-111">**Generera automatiskt stängda bildtexter**: anger om dolda bildtexter ska genereras automatiskt för videon.</span><span class="sxs-lookup"><span data-stu-id="2bd56-111">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="2bd56-112">**Dold textning**: anger den dolda textning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="2bd56-112">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="2bd56-113">**Vanligt ljud**: anger det vanliga ljudspår som ska användas.</span><span class="sxs-lookup"><span data-stu-id="2bd56-113">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="2bd56-114">**Miniatyr**: anger miniatyrbilden för videon.</span><span class="sxs-lookup"><span data-stu-id="2bd56-114">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="2bd56-115">Om den inte anges kommer den att genereras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2bd56-115">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="2bd56-116">**Beskrivande ljud**: anger det beskrivande ljudspår som ska användas.</span><span class="sxs-lookup"><span data-stu-id="2bd56-116">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="2bd56-117">Överför en video</span><span class="sxs-lookup"><span data-stu-id="2bd56-117">Upload a video</span></span>

<span data-ttu-id="2bd56-118">Så här överför du en video i webbplatsskapare.</span><span class="sxs-lookup"><span data-stu-id="2bd56-118">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="2bd56-119">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="2bd56-119">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="2bd56-120">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="2bd56-120">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="2bd56-121">I fönstret Utforskaren navigerar du till och markerar en eller flera videofiler som ska överföras och väljer sedan **öppna**.</span><span class="sxs-lookup"><span data-stu-id="2bd56-121">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="2bd56-122">I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.</span><span class="sxs-lookup"><span data-stu-id="2bd56-122">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="2bd56-123">Ange valfri beskrivning och nyckelord och välj en kategori om du vill.</span><span class="sxs-lookup"><span data-stu-id="2bd56-123">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="2bd56-124">Om du vill publicera bilden omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**</span><span class="sxs-lookup"><span data-stu-id="2bd56-124">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="2bd56-125">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bd56-125">Select **OK**.</span></span>

<span data-ttu-id="2bd56-126">Om du överför flera typer av tillgångar samtidigt (t.ex. bilder och videor) i dialogrutan **överför medieobjekt** kan du bara ange nyckelord, om filerna ska publiceras direkt efter överföringen och om det ska genereras dolda bildtexter automatiskt för videofilerna.</span><span class="sxs-lookup"><span data-stu-id="2bd56-126">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="2bd56-127">Alla tillgångar kommer att dela samma nyckelord.</span><span class="sxs-lookup"><span data-stu-id="2bd56-127">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2bd56-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2bd56-128">Additional resources</span></span>

[<span data-ttu-id="2bd56-129">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="2bd56-129">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="2bd56-130">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="2bd56-130">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="2bd56-131">Överför filer</span><span class="sxs-lookup"><span data-stu-id="2bd56-131">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="2bd56-132">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="2bd56-132">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="2bd56-133">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="2bd56-133">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="2bd56-134">Ladda upp och betjäna statiska filer</span><span class="sxs-lookup"><span data-stu-id="2bd56-134">Upload and serve static files</span></span>](upload-serve-static-files.md)
