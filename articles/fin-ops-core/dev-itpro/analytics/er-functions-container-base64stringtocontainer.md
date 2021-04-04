---
title: Base64StringToContainer ER-funktion
description: Det här avsnittet innehåller information om hur funktionen Base64StringToContainer elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 612590dacc1887b87677c12eddaef42660a7a154
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561552"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="3a837-103">Base64StringToContainer ER-funktion</span><span class="sxs-lookup"><span data-stu-id="3a837-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a837-104">`BASE64STRINGTOCONTAINER` [funktion](er-formula-language.md#functions) konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *[Behållare](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="3a837-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a837-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a837-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="3a837-106">Argument</span><span class="sxs-lookup"><span data-stu-id="3a837-106">Arguments</span></span>

<span data-ttu-id="3a837-107">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="3a837-107">`input`: *String*</span></span>

<span data-ttu-id="3a837-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="3a837-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3a837-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="3a837-109">Return values</span></span>

<span data-ttu-id="3a837-110">*Container*</span><span class="sxs-lookup"><span data-stu-id="3a837-110">*Container*</span></span>

<span data-ttu-id="3a837-111">Det resulterande binära värdet i binärt stort objekt (BLOB) format.</span><span class="sxs-lookup"><span data-stu-id="3a837-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3a837-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="3a837-112">Usage notes</span></span>

<span data-ttu-id="3a837-113">Undantaget "Parameter är inte giltig" är aktuell om indatasträngen inte ger en korrekt Base64-grupp av binär-till-text-kodningsscheman.</span><span class="sxs-lookup"><span data-stu-id="3a837-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="3a837-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="3a837-114">Example</span></span>

<span data-ttu-id="3a837-115">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="3a837-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="3a837-116">Roten **DocuTypeGroupEnum**-datakällan för typen *Dynamics 365 for Operations / uppräkning* som refererar till **DocuTypeGroup** programuppräkning</span><span class="sxs-lookup"><span data-stu-id="3a837-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="3a837-117">Roten **Kund** datakälla av typen *Dynamics 365 for Operations / Tabellregister* som refererar till programtabellen **CustTable**</span><span class="sxs-lookup"><span data-stu-id="3a837-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="3a837-118">Datakällan **\#Media** av typen *Calculated field* som konfigureras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3a837-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="3a837-119">Den läggs till som underordnad datakälla till datakällan **kund**.</span><span class="sxs-lookup"><span data-stu-id="3a837-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="3a837-120">Den innehåller uttrycket `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="3a837-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="3a837-121">Datakällan **\#MediaAsBase64String** av typen *Calculated field* som konfigureras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3a837-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="3a837-122">Den läggs till som underordnad datakälla till datakällan **Kund.'\#Media'**.</span><span class="sxs-lookup"><span data-stu-id="3a837-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="3a837-123">Den innehåller uttrycket `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="3a837-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="3a837-124">Datakällan **\#BlobFomBase64** av typen *Calculated field* som konfigureras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3a837-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="3a837-125">Den läggs till som underordnad datakälla till datakällan **Kund.'\#Media'**.</span><span class="sxs-lookup"><span data-stu-id="3a837-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="3a837-126">Den innehåller uttrycket `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="3a837-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="3a837-127">I det här exemplet kodar datakällan **\#MediaAsBase64String** det binära innehållet i den aktuella mediebilagan som text som representerar en Base64-grupp med binär-till-text-kodningsscheman.</span><span class="sxs-lookup"><span data-stu-id="3a837-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="3a837-128">Datakällan **\#BlobFomBase64** avkodar Base64-strängen och returnerar ett binärt värde i BLOB-format.</span><span class="sxs-lookup"><span data-stu-id="3a837-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Exempeldatakälla på sidan för ER-modellmappningsdesigner](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="3a837-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3a837-130">Additional resources</span></span>

[<span data-ttu-id="3a837-131">Behållarfunktioner</span><span class="sxs-lookup"><span data-stu-id="3a837-131">Container functions</span></span>](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]