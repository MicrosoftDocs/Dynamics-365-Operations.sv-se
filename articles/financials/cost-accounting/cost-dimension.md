---
title: Skapa dimensioner och importera dimensionsmedlemmar
description: Kostnadsredovisningen är en oberoende modul som kräver huvuddata från andra moduler.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d48ba0a0b80d251e107baa0ceeb66d8e328f13dc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "342326"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Skapa dimensioner och importera dimensionsmedlemmar

[!include [banner](../includes/banner.md)]

Kostnadsredovisningen är en oberoende modul som kräver data från andra moduler. Denna data kategoriseras till följande:

-  Kostnadselement
-  Kostnadsobjekt
-  Statistikdimensioner

Ett **Kostnadselement** motsvarar en kostnadsrelevant artikel i kontolistan. Ett **kostnadsobjekt** motsvarar valfri ekonomisk dimensionstyp, till exempel produkter, kostnadsställen samt projekt som du vill beräkna, allokera kostnader till eller mäta direkt. En **statistisk dimension** och dess medlemmar används för att registrera icke-monetära poster. Statistiska dimensionsmedlemmar kan användas som allokeringsbas inom kostnadsdistribution och -allokering 

Följande diagram illustrerar de dimensioner som används inom kostnadsredovisningen.

[![Dimensioner i kostnadsredovisning](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

När datan väl har importerats till kostnadsredovisningen kan du använda den för att skapa olika perspektiv som ger insikter till chefer på alla organisationsnivåer. Mer information om hur du skapar dimensioner och importerar dimensionsmedlemmar finns i följande avsnitt: 

-  [Dimensioner för kostnadselement](cost-elements.md)
-  [Skapa kostnadselement (uppgiftsguide)](./tasks/create-cost-elements.md)
-  [Kostnadsobjektdimensioner](cost-objects.md)
-  [Skapa kostnadselement (uppgiftsguide)](./tasks/create-cost-objects.md)
-  [Mappa dimensionsmedlemmar för kostnadselement till en gemensam uppsättning dimensionsmedlemmar](map-cost-elements-dimension-members.md)
-  [Mappa dimension för kostnadselement (uppgiftsguide)](./tasks/map-cost-element-dimension.md)
-  [Providermallar för statistiska dimensionsmedlemmar och statistiska mätningar](statistical-measure-provider-template.md)






