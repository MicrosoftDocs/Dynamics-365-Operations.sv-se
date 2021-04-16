---
title: Skanna streckkoder med kamera i mobilappen för distributionslagerhantering
description: Det här avsnittet beskriver hur du ställer in i mobilappen för distributionslagerhantering för att skanna streckkoder med en kamera på en mobil enhet.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831228"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="efe60-103">Skanna streckkoder med kamera i mobilappen för distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="efe60-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efe60-104">Det här avsnittet beskriver hur du ställer in i mobilappen för distributionslagerhantering för att skanna streckkoder med en kamera på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="efe60-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="efe60-105">Ställ in</span><span class="sxs-lookup"><span data-stu-id="efe60-105">Setup</span></span>

<span data-ttu-id="efe60-106">Du kan välja om kameran ska användas för skanning av streckkoder i visningsinställningar i mobilappen för distributionslagerhantering.</span><span class="sxs-lookup"><span data-stu-id="efe60-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="efe60-107">Om du aktiverar **använda kameran som skanner** kan du använda kameran på alla inmatningsfält med inmatningsläget **skanning**.</span><span class="sxs-lookup"><span data-stu-id="efe60-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="efe60-108">För att bestämma att ett indatafält ska vara skanningsbart, på sidan **Namnordning för lagerställeapp** anger du **önskat inmatningsläge** till **Skanning**.</span><span class="sxs-lookup"><span data-stu-id="efe60-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="efe60-109">När det här alternativet väljs kan en kamera användas för skanning i mobilappen för distributionslagerhantering.</span><span class="sxs-lookup"><span data-stu-id="efe60-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="efe60-110">- Mer information finns i [Konfigurera fält för mobilappen för distributionslagerhantering](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="efe60-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="efe60-111">Streckkodsformat som stöds</span><span class="sxs-lookup"><span data-stu-id="efe60-111">Supported bar code formats</span></span>

<span data-ttu-id="efe60-112">De vanligaste formaten för streckkod stöds, inklusive kod 128, kod 39, kod 93, EAN-8, EAN-13, UPC-E, UPC-A och QR-koder.</span><span class="sxs-lookup"><span data-stu-id="efe60-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="efe60-113">Navigering</span><span class="sxs-lookup"><span data-stu-id="efe60-113">Navigation</span></span>

<span data-ttu-id="efe60-114">Sidan för kamera initieras på varje sida där inmatningsfält har **föredraget indataläge** inställt på *skanning*. När du är på kamerasidan använd följande alternativ när du navigerar:</span><span class="sxs-lookup"><span data-stu-id="efe60-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="efe60-115">Klicka på bakåt om du vill gå tillbaka till sidan **Uppgift och detaljer**.</span><span class="sxs-lookup"><span data-stu-id="efe60-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="efe60-116">Klicka på pennan på sidan **Uppgift och detaljer** för att gå till den sida där du kan skriva in data manuellt.</span><span class="sxs-lookup"><span data-stu-id="efe60-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="efe60-117">Klicka på kameran på sidan **Uppgift och detaljer** för att gå tillbaka till kamerasidan.</span><span class="sxs-lookup"><span data-stu-id="efe60-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="efe60-118">När du klickar på knappen kamera på kamerasidan visas den nedtonad under identifiering av en streckkod.</span><span class="sxs-lookup"><span data-stu-id="efe60-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="efe60-119">Om en streckkod inte identifieras inom 5 sekunder inaktiveras processen och kameraknappen blir tillgänglig igen.</span><span class="sxs-lookup"><span data-stu-id="efe60-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="efe60-120">Du kommer sedan att kunna försöka skanna streckkoden igen.</span><span class="sxs-lookup"><span data-stu-id="efe60-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="efe60-121">För bästa resultat håller du kameran i linje när du riktar den över streckkoden.</span><span class="sxs-lookup"><span data-stu-id="efe60-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="efe60-122">När en streckkod har skannats bearbetas informationen och du kommer till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="efe60-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="efe60-123">Om nästa steg innehåller ytterligare ett inmatningsfält med inmatningsläge skanning, startar kamerasidan igen.</span><span class="sxs-lookup"><span data-stu-id="efe60-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="efe60-124">Om nästa steg inte är skanning, kommer kamerasidan inte att startas.</span><span class="sxs-lookup"><span data-stu-id="efe60-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]