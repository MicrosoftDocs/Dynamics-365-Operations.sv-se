---
title: Gör kontoplansavgränsare unika
description: Det här ämnet förklarar hur du inte kan ha samma avgränsare för kontoplanen och dimensionsvärden. Efter uppgraderingen måste du ändra avgränsarvärden.
author: panolte
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 72965e9c6182bdac123feb1bc5cc4b82d91cd588
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020114"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Gör kontoplansavgränsare unika

[!include [banner](../includes/banner.md)]

I Microsoft Dynamics AX 2012 kan använda samma avgränsare i diagrammet över konton och dimensionsvärden. I aktuella versioner av Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden. Om det finns dubbla avgränsare kan du ändra den efter uppgraderingen. 

Den här funktionen finns inte i följande versioner:
- Finance and Operations version 8.0
- Finance and Operations version 7.1, KB 4094701 kan inte ange de ekonomiska dimensionerna när dimensionsvärdena innehåller avgränsare för kontoplan
- Finance and Operations version 7.2, KB 4092967 kan inte välja delprojekt som dimension när delprojektformatet innehåller dimensionsavgränsaren

## <a name="update-delimiter"></a>Uppdatera avgränsare
Om det finns en konflikt med kontoplanen, kan avgränsare för kontoplanen och projekt eller delprojekt-ID-formatet ändras. Inga andra avgränsare för dimensionen kan ändras. 
- Du kan ändra avgränsare för kontoplan efter uppgradering i **Allmänna redovisningsparametrar** > **Kontoplan och dimensioner** > **Ändra avgränsare**. 
- Om den enda konflikten är projekt/delprojekt-ID-formatet kan du ändra det värdet i **Projekthantering och redovisningsparametrar** > **Allmänt** > **Ändra delprojektformat**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Ta reda på om din miljö kräver uppdaterade avgränsare 
Om avgränsare i din uppgraderade miljö står i konflikt, kan du uppleva instabilitet när du anger värden i en segmenterad postkontroll eller dimensionspostkontroll. Detta innebär att du måste alltid använda sökningar eller en utfälld meny när du anger konto och dimensionskombinationer.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]