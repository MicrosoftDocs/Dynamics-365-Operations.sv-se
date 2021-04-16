---
title: Lista över ER-funktioner i datainsamlingskategorin
description: Det här ämnet ger information om datainsamlingsfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
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
ms.openlocfilehash: 31b5e7b08a3de77d461fff5e42164975e53dfe1e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748073"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Lista över ER-funktioner i datainsamlingskategorin

[!include [banner](../includes/banner.md)]

Datainsamlingsfunktioner för elektronisk rapportering (ER) används för att göra inventering och summering i ett ER-format som körs, baserat på data från utdata som redan har genererats i **text** eller **Xml**-format. Den här metoden används för att förbättra prestanda för ett ER-format som körs, för att ange värden för löpande summor i genererade dokument och för andra syften. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion | Beskrivning |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Den här funktionen ett *postlist*-värde som innehåller listan över värden som returnerades av egenskapen **Collected data key value** för formatelement och samlades in när format elementen användes för att generera utgående dokument under formatkörningen och som uppfyller de angivna villkoren. Varje villkor består av ett nyckelintervall och ett nyckelvärde. |
| [CountIF](er-functions-datacollection-countif.md) | Den här funktionen returnerar ett *heltalsvärde* som representerar antalet formatelement som samlades in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret. Villkoret består av ett nyckelintervall och ett nyckelvärde. |
| [CountIFs](er-functions-datacollection-countifs.md) | Den här funktionen returnerar ett *heltalsvärde* som representerar antalet formatelement som samlades in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret. Varje villkor består av ett nyckelintervall och ett nyckelvärde. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Den här funktionen returnerar ett *sträng*-värde som representerar namnet på det aktuella elementet för ER-format. |
| [SumIF](er-functions-datacollection-sumif.md) | Den här funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret. Villkoret består av ett nyckelintervall och ett nyckelvärde. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Den här funktionen returnerar ett värde för *Realtal* som representerar summan av värden som returneras av bindningar av formatelement och samlas in när format elementen användes för att generera ett utgående dokument under formatkörningen, och som uppfyller det angivna villkoret. Varje villkor består av ett nyckelintervall och ett nyckelvärde. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]