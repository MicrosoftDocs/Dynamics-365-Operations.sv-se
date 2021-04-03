---
title: Lista över ER-funktioner i datainsamlingskategorin
description: Det här ämnet ger information om datainsamlingsfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba3a1f031a4a98592081b04a4128450aeb8218ef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561744"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="acefd-103">Lista över ER-funktioner i datainsamlingskategorin</span><span class="sxs-lookup"><span data-stu-id="acefd-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="acefd-104">Datainsamlingsfunktioner för elektronisk rapportering (ER) används för att göra inventering och summering i ett ER-format som körs, baserat på data från utdata som redan har genererats i **text** eller **Xml**-format.</span><span class="sxs-lookup"><span data-stu-id="acefd-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="acefd-105">Den här metoden används för att förbättra prestanda för ett ER-format som körs, för att ange värden för löpande summor i genererade dokument och för andra syften.</span><span class="sxs-lookup"><span data-stu-id="acefd-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="acefd-106">Det här avsnittet innehåller en sammanfattning av dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="acefd-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="acefd-107">Lista över funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="acefd-107">List of supported functions</span></span>

| <span data-ttu-id="acefd-108">Funktion</span><span class="sxs-lookup"><span data-stu-id="acefd-108">Function</span></span> | <span data-ttu-id="acefd-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="acefd-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="acefd-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="acefd-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="acefd-111">Den här funktionen ett *postlist*-värde som innehåller listan över värden som returnerades av egenskapen **Collected data key value** för formatelement och samlades in när format elementen användes för att generera utgående dokument under formatkörningen och som uppfyller de angivna villkoren.</span><span class="sxs-lookup"><span data-stu-id="acefd-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="acefd-112">Varje villkor består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="acefd-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="acefd-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="acefd-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="acefd-114">Den här funktionen returnerar ett *heltalsvärde* som representerar antalet formatelement som samlades in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="acefd-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="acefd-115">Villkoret består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="acefd-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="acefd-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="acefd-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="acefd-117">Den här funktionen returnerar ett *heltalsvärde* som representerar antalet formatelement som samlades in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="acefd-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="acefd-118">Varje villkor består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="acefd-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="acefd-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="acefd-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="acefd-120">Den här funktionen returnerar ett *sträng*-värde som representerar namnet på det aktuella elementet för ER-format.</span><span class="sxs-lookup"><span data-stu-id="acefd-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="acefd-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="acefd-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="acefd-122">Den här funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="acefd-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="acefd-123">Villkoret består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="acefd-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="acefd-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="acefd-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="acefd-125">Den här funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret.</span><span class="sxs-lookup"><span data-stu-id="acefd-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="acefd-126">Varje villkor består av ett nyckelintervall och ett nyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="acefd-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="acefd-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="acefd-127">Additional resources</span></span>

[<span data-ttu-id="acefd-128">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="acefd-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="acefd-129">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="acefd-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="acefd-130">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="acefd-130">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]