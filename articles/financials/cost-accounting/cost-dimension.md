---
title: Skapa dimensioner och importera dimensionsmedlemmar
description: "Kostnadsredovisningen är en oberoende modul som kräver huvuddata från andra moduler."
author: YuyuScheller
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0012761b3aa8ce391b956329a9e249e5c9339db7
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="create-dimensions-and-import-dimension-members"></a>Skapa dimensioner och importera dimensionsmedlemmar

[!include[banner](../includes/banner.md)]

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







