---
title: Det går inte att lägga till fältet Prisenhet på sidan Inköpsavtal
description: När du öppnar sidan för Inköpsavtal i ett radvisningsläge kan du inte anpassa sidan genom att lägga till fältet Prisenhet i översikten för raden
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 56d2ce94fb4b74d982cb6a052cca71c18190cd04
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477604"
---
# <a name="you-cant-add-the-price-unit-field-to-the-purchase-agreement-page"></a>Det går inte att lägga till fältet Prisenhet på sidan Inköpsavtal

## <a name="symptoms"></a>Symtom

När du öppnar sidan **Inköpsavtal** i ett radvisningsläge kan du inte anpassa sidan genom att lägga till fältet **Prisenhet** i översikten för raden.

## <a name="resolution"></a>Lösning

Vissa delade fält i avtalsramverket kan inte inkluderas i anpassningar. Den här begränsningen beror på den datamodell som implementeras. Därför kan du inte personanpassa fältet **Prisenhet**.
