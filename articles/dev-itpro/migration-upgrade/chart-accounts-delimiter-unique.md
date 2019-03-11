---
title: Gör kontoplansavgränsare unika
description: I Dynamics 365 for Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden. Efter uppgraderingen måste du ändra avgränsarvärden.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e197a1b44e038a97b8bf6db692dcc2eef2bc5f7b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "335863"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Gör kontoplansavgränsare unika

[!include [banner](../includes/banner.md)]

I Microsoft Dynamics AX 2012 kan använda samma avgränsare i diagrammet över konton och dimensionsvärden i Microsoft Dynamics AX 2012. I Dynamics 365 for Finance and Operations kan du inte ha samma avgränsare för kontoplanen och dimensionsvärden. Om det finns dubbla avgränsare kan du ändra den efter uppgraderingen. 

Den här funktionen är inte tillgänglig i:
- Dynamics 365 for Finance and Operations version 8.0
- Dynamics 365 for Finance and Operations version 7.1, KB 4094701 kan inte ange de ekonomiska dimensionerna när dimensionsvärdena innehåller avgränsare för kontoplan
- Dynamics 365 for Finance and Operations version 7.2, KB 4092967 kan inte välja delprojekt som dimension när delprojektformatet innehåller dimensionsavgränsaren

## <a name="update-delimiter"></a>Uppdatera avgränsare
Om det finns en konflikt med kontoplanen, kan avgränsare för kontoplanen och projekt eller delprojekt-ID-formatet ändras. Inga andra avgränsare för dimensionen kan ändras. 
- Du kan ändra avgränsare för kontoplan efter uppgradering till Finance and Operations i **Allmänna redovisningsparametrar** > **Kontoplan och dimensioner** > **Ändra avgränsare**. 
- Om den enda konflikten är projekt/delprojekt-ID-formatet kan du ändra det värdet i **Projekthantering och redovisningsparametrar** > **Allmänt** > **Ändra delprojektformat**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Ta reda på om din miljö kräver uppdaterade avgränsare 
Om avgränsare i din uppgraderade miljö står i konflikt, kan du uppleva instabilitet när du anger värden i en segmenterad postkontroll eller dimensionspostkontroll. Detta innebär att du måste alltid använda sökningar eller en utfälld meny när du anger konto och dimensionskombinationer.
