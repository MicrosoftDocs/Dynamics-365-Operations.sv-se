---
title: QRCODE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen QRCODE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bac0910d213ee05a2a7a7b218a6714d4f935be16
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916762"
---
# <span data-ttu-id="11a9a-103"><a name="QRCODE">QRCODE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="11a9a-103"><a name="QRCODE">QRCODE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11a9a-104">`QRCODE`-funktionen returnerar ett värde för *behållare* som visar en bild för snabb svarskod (QR-kod) för den angivna strängen i binärt format.</span><span class="sxs-lookup"><span data-stu-id="11a9a-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="11a9a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="11a9a-105">Syntax</span></span>

```
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="11a9a-106">Argument</span><span class="sxs-lookup"><span data-stu-id="11a9a-106">Arguments</span></span>

<span data-ttu-id="11a9a-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="11a9a-107">`text`: *String*</span></span>

<span data-ttu-id="11a9a-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="11a9a-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="11a9a-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="11a9a-109">Return values</span></span>

<span data-ttu-id="11a9a-110">*Behållare*</span><span class="sxs-lookup"><span data-stu-id="11a9a-110">*Container*</span></span>

<span data-ttu-id="11a9a-111">Den resulterande binära strömmen.</span><span class="sxs-lookup"><span data-stu-id="11a9a-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="11a9a-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="11a9a-112">Example</span></span>

<span data-ttu-id="11a9a-113">Du kan konfigurera ett format för elektronisk rapportering (ER) för att generera ett utgående dokument i Microsoft Office-format (Excel-arbetsböcker eller Word-dokument) med hjälp av en fördefinierad mall.</span><span class="sxs-lookup"><span data-stu-id="11a9a-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="11a9a-114">Den här mallen kan innehålla ett **bildobjekt** (Excel-arbetsbok) eller en **bildinnehållskontroll** (Word-dokument) som en platshållare för en QR-kodavbildning.</span><span class="sxs-lookup"><span data-stu-id="11a9a-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="11a9a-115">Du måste lägga till ett konfigurerade ER-format ett **Cell**-element som ska användas för att fylla platshållaren i.</span><span class="sxs-lookup"><span data-stu-id="11a9a-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="11a9a-116">Om du vill ange vilken information som ska lagras i en QR-kod måste du definiera en bindning för det här **Cell**-elementet.</span><span class="sxs-lookup"><span data-stu-id="11a9a-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="11a9a-117">Du kan till exempel konfigurera en sådan bindning som innehåller följande uttryck:</span><span class="sxs-lookup"><span data-stu-id="11a9a-117">For example, you can configure such binding as containing the following expression:</span></span>

```
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="11a9a-118">När du kör det konfigurerade ER-formatet visas textvärdet för **LabelText** för datakällan **model.ListOfShelfLabels** kommer att användas för att generera en QR-kodavbildning.</span><span class="sxs-lookup"><span data-stu-id="11a9a-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="11a9a-119">Den här bilden ersätter en platshållare för QR-kodbilder i dokumentmallen med hjälp av för att generera ett utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="11a9a-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="11a9a-120">När den här bilden av det genererade dokumentet skannas returneras den text som hämtats från fältet **LabelText** i datakällan **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="11a9a-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="11a9a-121">För mer information om [Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)</span><span class="sxs-lookup"><span data-stu-id="11a9a-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11a9a-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="11a9a-122">Additional resources</span></span>

[<span data-ttu-id="11a9a-123">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="11a9a-123">Text functions</span></span>](er-functions-category-text.md)
