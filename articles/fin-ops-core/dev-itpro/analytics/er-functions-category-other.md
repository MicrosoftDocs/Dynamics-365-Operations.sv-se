---
title: Lista över ER-funktioner i företagsdomänspecifika kategorin
description: Det här ämnet ger information om företagsdomänspecifika funktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 8f7612e83d9f30281e2b1a783275365459e67a40
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686133"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Lista över ER-funktioner i företagsdomänspecifika kategorin

[!include [banner](../includes/banner.md)]

De domänspecifika funktionerna för elektronisk rapportering (ER) kan användas för att utföra beräkningar och dataåtkomst begäranden som är specifika för implementeringen av Microsoft Dynamics 365 Finance. Det här avsnittet innehåller en sammanfattning av dessa funktioner.

## <a name="list-of-supported-functions"></a>Lista över funktioner som stöds

| Funktion| Beskrivning |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Den här funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens som ett MOD10-uttryck, baserat på siffrorna i det angivna fakturanumret. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Den här funktionen returnerar ett *sträng*-värde som representerar ett enda ekonomisk dimensions-ID som hämtas från den angivna strängen. Den angivna strängen visar alla dimensioner som en kommaseparerad lista med ID:n. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Den här funktionen returnerar ett *Real*-värde som representerar resultatet av att konvertera det angivna monetära beloppet från den angivna källvalutan till den angivna målvalutan genom att använda inställningarna för det angivna företaget på det angivna datumet. |
| [CurCredRef](er-functions-other-curcredref.md) | Den här funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens baserat på siffrorna i det angivna fakturanumret. |
| [FA_Balance](er-functions-other-fabalance.md) | Den här funktionen returnerar ett värde för *behållare* (post) som består av data för anläggningstillgångssaldo för den angivna anläggningstillgångsartikeln, värdemodellkoden, rapporteringsår och rapporterigsdatum. |
| [FA_Sum](er-functions-other-fasum.md) | Den här funktionen returnerar ett värde för *behållare (post)* som består av data för anläggningstillgångsbeloppen för den angivna anläggningstillgångsartikeln, värdemodellkoden och datumperioden. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Funktionen returnerar ett *Sträng*-värde som representerar koden för den juridiska person (företag) som användaren är inloggad i för närvarande. |
| [ISOCredRef](er-functions-other-isocredref.md) | Funktionen returnerar ett *Sträng*-värde som representerar en International Organization for Standardization (ISO)-betalningsmottagarreferens baserad på siffror och bokstäver i det angivna fakturanumret. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Den här funktionen returnerar ett *booleskt* värde för **SANT** när en specificerad sträng representerar ett giltigt internationellt bankkontonummer (IBAN). Annars returnerar uttrycket värdet *boolesk* av **FALSK**. |
| [Mod_97](er-functions-other-mod97.md) | Den här funktionen returnerar ett *sträng*-värde som representerar en betalningsmottagarreferens som ett MOD97-uttryck, baserat på siffrorna i det angivna fakturanumret. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Den här funktionen returnerar ett *Sträng*-värde som representerar det nya genererade värdet för en nummerserie, baserat på den angivna nummersekvensen, omfattningen och omfattnings-ID. Omfattnings-ID är lika med företagskoden som tillhandahålls av kontexten som ER-formatet körs under. |
| [RoundAmount](er-functions-other-roundamount.md) | Den här funktionen returnerar ett *Real*-värde som representerar resultatet av avrundning av det angivna numret till det angivna numret av antal decimaler enligt den angivna avrundningsregeln. |
| [TableName2ID](er-functions-other-tablename2id.md) | Den här funktionen returnerar en numerisk representation av tabell-ID för det angivna tabellnamnet som värdet *heltal*. |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Formelspråk i elektronisk rapportering](er-formula-language.md)
