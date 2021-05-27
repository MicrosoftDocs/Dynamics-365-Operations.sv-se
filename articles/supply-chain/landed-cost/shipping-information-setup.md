---
title: Inställningar för leveransinformation
description: I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5093e42b0b5247c24c271ad50c80889516586d58
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020897"
---
# <a name="shipping-information-setup"></a>Inställningar för leveransinformation

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen **hemtagningskostnad**.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Beskrivning av varor

Beskrivningar av varor gör det möjligt att identifiera en leveransbehållare eller ett folio för gods som finns i den. Du kan välja en beskrivning av gods i leveransbehållarens rubrik eller i folio sidhuvud.

Om du vill arbeta med beskrivningar av varor går du till **Hemtagningskostnad \> Inställning av leveransinformation \> Beskrivning av varor**. Där kan du visa, öppna, skapa och ta bort poster för varubeskrivningar. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Beskrivning av varor | Ange ett unikt ID-namn/nummer för den typ av varor som kommer att använda den här beskrivningen. |
| beskrivning | Ange en beskrivning av typen av varor i denna kategori. |

## <a name="vessels"></a><a name="vessels"></a>Fartyg

Ett fartyg är det unika namn som ett skepp eller fartyg som ett transportföretag eller en förmedling använder. När du skapar en färd måste du alltid välja eller ange att du inte ska använda ett fartyg för den. Om du ofta använder samma fartyg kan du göra det snabbare och enklare att skapa en ny färd genom att skapa en fartygspost och på så sätt göra det möjligt för användarna att välja ur en lista istället för att ange namnet eller numret manuellt varje gång.

Om du vill arbeta med fartyg, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Fartyg**. Där kan du visa, öppna, skapa och ta bort poster för fartyg. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Fartyg | Ange ett unikt ID-namn/nummer för det skepp som ska användas vid transport av gods i en färd. |
| beskrivning | Ange en beskrivning av fartyget. Vanligtvis identifierar denna beskrivning namnet på transportföretaget/agenten. |
| Leveranssätt | Välj det leveranssätt som fartyget använder (t.ex. _Flyg_, _Fartyg_ eller _Tåg_). |

## <a name="exporters"></a>Exportörer

Varje exportörpost identifierar en leverantör eller exportör som kan definieras som leverantör för en kund. Exportören kan kopplas till en exportör och användas för rapportering.

Om du vill arbeta med exportörer, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> exportörer**. Där kan du visa, öppna, skapa och ta bort poster för exportörer. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Exportör | Ange ett unikt ID-namn/nummer för den exportör av varor som transporteras på en färd. |
| beskrivning | Ange en beskrivning av exportören. Vanligtvis identifierar denna beskrivning det fullständiga namnet på transportföretaget/agenten. |

## <a name="commodity-codes"></a>Artikelkoder

Du använder artikelkoder som hjälp när du vill tullidentifiera och beräkna tullsatser för varor på en gång. Du kan välja artikelkoder på sidan **Frisläppta produkter**.

Om du vill arbeta med artikelkoder, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Artikelkoder**. Där kan du visa, öppna, skapa och ta bort poster för artikelkoder. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Artikelkod | Ange en unik kod för den här typen av vara. |
| beskrivning | Ange en beskrivning av artikelkoder. |

## <a name="customs-description"></a>Tullbeskrivning

Med hjälp av tullbeskrivningar kan varor identifieras för tulländamål. Du kan välja en tullbeskrivning på sidan **Frisläppta produkter** eller på inköpsorderrader.

Om du vill arbeta med tullbeskrivningar av varor går du till **Hemtagningskostnad \> Inställning av leveransinformation \> Tullbeskrivning**. Där kan du visa, öppna, skapa och ta bort poster för tullbeskrivningar. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Tullbeskrivning | Ange en unik kod för den här typen av tullklassificering. Ofta blir den här koden den officiella beskrivningen som ges av en tullmyndighet för beskrivningen av och det kvalitativa värdet av varorna. |
| beskrivning | Ange en beskrivning av tullklassificeringen. |
