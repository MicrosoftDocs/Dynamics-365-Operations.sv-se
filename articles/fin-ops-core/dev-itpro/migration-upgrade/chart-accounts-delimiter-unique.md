---
title: Gör kontoplansavgränsare unika
description: Det här ämnet förklarar hur du inte kan ha samma avgränsare för kontoplanen och dimensionsvärden. Efter uppgraderingen måste du ändra avgränsarvärden.
author: panolte
ms.date: 03/23/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 433e9f8a7b0a9f476c74096a4bd7fef03c87dee1
ms.sourcegitcommit: 0d5ee97670bdeb1986aaea880f32962b5e374751
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468061"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Gör kontoplansavgränsare unika

[!include [banner](../includes/banner.md)]

I Microsoft Dynamics AX 2012 kan använda samma avgränsare i diagrammet över konton och dimensionsvärden. I aktuella versioner av Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden. Om det finns dubbla avgränsare kan du ändra den efter uppgraderingen. 

## <a name="update-delimiter"></a>Uppdatera avgränsare
Om det finns en konflikt med kontoplanen, kan avgränsare för kontoplanen och projekt eller delprojekt-ID-formatet ändras. Inga andra avgränsare för dimensionen kan ändras. 
- Du kan ändra avgränsare för kontoplan efter uppgradering i **Allmänna redovisningsparametrar** > **Kontoplan och dimensioner** > **Ändra avgränsare**. 
- Om den enda konflikten är projekt/delprojekt-ID-formatet kan du ändra det värdet i **Projekthantering och redovisningsparametrar** > **Allmänt** > **Ändra delprojektformat**. 

### <a name="other-considerations"></a>Övriga beaktanden
Liknar projekt-/delprojekt-ID bör andra huvuddataposter som används som ekonomiska dimensioner, till exempel leverantörer eller kunder, inte ha konto-ID-värden som använder samma tecken som kontoplansavgränsaren. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Ta reda på om din miljö kräver uppdaterade avgränsare 
Om avgränsare i din uppgraderade miljö står i konflikt, kan du uppleva instabilitet när du anger värden i en segmenterad postkontroll eller dimensionspostkontroll. Detta innebär att du måste alltid använda sökningar eller en utfälld meny när du anger konto och dimensionskombinationer.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
