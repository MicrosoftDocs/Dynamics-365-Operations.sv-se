---
title: Skanna streckkoder med hjälp av en kamera i lagerhållningsappen
description: Det här avsnittet beskriver hur du ställer in i lagerhållningsappen för att skanna streckkoder med en kamera på en mobil enhet.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: fd4818ab936e1c93000793da756c97df6d05b2a9
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530016"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a><span data-ttu-id="c363a-103">Skanna streckkoder med hjälp av en kamera i lagerhållningsappen</span><span class="sxs-lookup"><span data-stu-id="c363a-103">Scan bar codes using a camera in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c363a-104">Det här avsnittet beskriver hur du ställer in i lagerhållningsappen för att skanna streckkoder med en kamera på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="c363a-104">This topic explains how to set up the warehouse app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c363a-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c363a-105">Prerequisites</span></span>
<span data-ttu-id="c363a-106">Om du vill använda den här funktionen måste du ha version 1.2.0.0 av lagerhållningsappen installerat och enheten måste ha en kamera.</span><span class="sxs-lookup"><span data-stu-id="c363a-106">To use this feature, you need to have version 1.2.0.0 of the warehouse app installed, and your device must have a camera.</span></span> <span data-ttu-id="c363a-107">När du öppnar programmet, efter att ha uppdaterat, uppmanas du att tillåta appen att använda kameran.</span><span class="sxs-lookup"><span data-stu-id="c363a-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="c363a-108">Om enheten inte har någon kamera visas inte frågan och du kan inte använda en kamera som skanner.</span><span class="sxs-lookup"><span data-stu-id="c363a-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="c363a-109">Konfigurera</span><span class="sxs-lookup"><span data-stu-id="c363a-109">Setup</span></span>
<span data-ttu-id="c363a-110">Du kan välja om kameran ska användas för skanning av streckkoder i visningsinställningar i lagerhållningsappen.</span><span class="sxs-lookup"><span data-stu-id="c363a-110">In the Display settings of the warehouse application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="c363a-111">Om du aktiverar **använda kameran som skanner** kan du använda kameran på alla inmatningsfält med inmatningsläget **skanning**.</span><span class="sxs-lookup"><span data-stu-id="c363a-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="c363a-112">För att bestämma att ett indatafält ska vara skanningsbart, på sidan **Namnordning för lagerställeapp** anger du **önskat inmatningsläge** till **Skanning**.</span><span class="sxs-lookup"><span data-stu-id="c363a-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="c363a-113">När det här alternativet väljs kan en kamera användas för skanning i lagerhållningsappen.</span><span class="sxs-lookup"><span data-stu-id="c363a-113">When this option is selected, a camera can be used for scanning in the warehouse app.</span></span> <span data-ttu-id="c363a-114">Information om hur du konfigurerar app fältnamn i Warehousing finns i [konfigurera app fältnamn i lagerhållningsappen](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="c363a-114">For information about how to configure app field names in Warehousing, see [Configure app field names in warehouse app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="c363a-115">Streckkodsformat som stöds</span><span class="sxs-lookup"><span data-stu-id="c363a-115">Supported bar code formats</span></span>
<span data-ttu-id="c363a-116">De vanligaste formaten för streckkod stöds, inklusive kod 128, kod 39, kod 93, EAN-8, EAN-13, UPC-E, UPC-A och QR-koder.</span><span class="sxs-lookup"><span data-stu-id="c363a-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="c363a-117">Navigering</span><span class="sxs-lookup"><span data-stu-id="c363a-117">Navigation</span></span>
<span data-ttu-id="c363a-118">Sidan för kamera initieras på varje sida där inmatningsfält har indataläge skanning. När du är på kamerasidan använd följande alternativ när du navigerar:</span><span class="sxs-lookup"><span data-stu-id="c363a-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="c363a-119">Klicka på bakåt om du vill gå tillbaka till sidan Task and details.</span><span class="sxs-lookup"><span data-stu-id="c363a-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="c363a-120">Klicka på pennan på sidan Task and details för att gå till den sida där du kan skriva in data manuellt.</span><span class="sxs-lookup"><span data-stu-id="c363a-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="c363a-121">Klicka på kameran på sidan Task and details för att gå tillbaka till kamerasidan.</span><span class="sxs-lookup"><span data-stu-id="c363a-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="c363a-122">Sidan Task and details</span><span class="sxs-lookup"><span data-stu-id="c363a-122">Task and details page</span></span> | <span data-ttu-id="c363a-123">Kamerasida</span><span class="sxs-lookup"><span data-stu-id="c363a-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Sidan Kameraskanning exempelinformationssida](./media/camera-scanning-example-task-detail-page50.png)          | ![Kameraskanning exempel, kamerasida mindre](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="c363a-126">När du klickar på knappen kamera på kamerasidan visas den nedtonad under identifiering av en streckkod.</span><span class="sxs-lookup"><span data-stu-id="c363a-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="c363a-127">Om en streckkod inte identifieras inom 5 sekunder inaktiveras processen och kameraknappen blir tillgänglig igen.</span><span class="sxs-lookup"><span data-stu-id="c363a-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="c363a-128">Du kommer sedan att kunna försöka skanna streckkoden igen.</span><span class="sxs-lookup"><span data-stu-id="c363a-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="c363a-129">För bästa resultat håller du kameran i linje när du riktar den över streckkoden.</span><span class="sxs-lookup"><span data-stu-id="c363a-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="c363a-130">När en streckkod har skannats bearbetas informationen och du kommer till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="c363a-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="c363a-131">Om nästa steg innehåller ytterligare ett inmatningsfält med inmatningsläge skanning, startar kamerasidan igen.</span><span class="sxs-lookup"><span data-stu-id="c363a-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="c363a-132">Om nästa steg inte är skanning, kommer kamerasidan inte att startas.</span><span class="sxs-lookup"><span data-stu-id="c363a-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>

